---
title: 'Hata: Hedef işlem çıkıldı işlevi değerlendirilirken &#39;işlevi&#39; | Microsoft Docs'
ms.custom: ''
ms.date: 4/06/2018
ms.topic: reference
f1_keywords:
- vs.debug.error.process_exit_func_eval_abort
ms.technology: vs-ide-debug
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b8dd6f0f47eb7160198d59e788096613da85e22f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-the-target-process-exited-while-evaluating-the-function-39function39"></a>Hata: Hedef işlem çıkıldı işlevi değerlendirilirken &#39;işlevi&#39;

İleti metni tam: hedef işlem çıkıldı 'function' işlevi hesaplanırken. Hedef işlem çıkış kodu için Çıktı Penceresi'ne bakın.

.NET nesneleri durumunu incelemek kolaylaştırmak için hata ayıklayıcı ek kodu çalıştırmak için hata ayıklaması işlemi otomatik olarak zorlar (genellikle özelliği alıcı yöntemlere ve `ToString` işlevleri). Çoğu senaryoda, bu işlevlerin başarıyla tamamlamak veya hata ayıklayıcı tarafından yakalanan özel durumlar oluşturma. Ancak, bunlar çekirdek sınırları, kullanıcı ileti Pompalama gerektirmediği veya kurtarılamaz için özel durum yakalandı olamaz bazı durumlar vardır. Sonuç, özellik alıcısı veya kodu yürütür ToString yöntemi o da açıkça sonlandırır işlemi (örneğin, çağıran `ExitProcess()`) veya yakalanan olamaz işlenmeyen bir özel durum oluşturur (örneğin, `StackOverflowException`) sonlandıracak işlem ve son hata ayıklama oturumu hata ayıklaması. Bu hata iletisiyle karşılaşırsanız, bu durum oluştu.
 
Bir ortak bu sorun kendi kendini çağıran bir özellik hata ayıklayıcı değerlendirirken, bu bir yığın taşması özel sonuçlanabilir nedeni. Yığın taşması özel durumu kurtarılamıyor ve hedef işlemini sonlandırır.
 
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için
 
Bu sorunun iki çözümü vardır.
 
### <a name="solution-1-prevent-the-debugger-from-calling-the-getter-property-or-tostring-method"></a>Çözüm #1: alıcı özellik veya ToString yöntemini çağırma hata ayıklayıcı engelle 

Hata ayıklayıcı ulaşmaya çalıştık işlevin adını hata iletisi size bildirir. İşlev adı ile bu işlevi yeniden hesaplanması deneyebilirsiniz **hemen** değerlendirme hata ayıklamak için penceresi. Hata ayıklama olası gelen değerlendirirken **hemen** penceresi olduğundan, örtük değerlendirmeleri aksine **Yereller/otomobiller/izleme** windows, hata ayıklayıcı keser işlenmeyen özel durumları.

Bu işlev değiştirebilir, özellik Get yordamı çağrılırken hata ayıklayıcı engelleyebilir veya `ToString` yöntemi. Aşağıdakilerden birini deneyin:
 
* Başka türde bir özellik alıcısı yanı sıra kodu yöntemini değiştirin veya ToString yöntemini ve sorun kaybolur.
    -veya-
* (İçin `ToString`) tanımla bir `DebuggerDisplay` özniteliğinin türü hem bir şey dışında değerlendirmek hata ayıklayıcı olabilir `ToString`.
    -veya-
* (Özellik alıcısı için) PUT `[System.Diagnostics.DebuggerBrowsable(DebuggerBrowsableState.Never)]` özelliği özniteliği. Bu özellik API Uyumluluk nedenleriyle kalması için gereken bir yöntem varsa yararlı olabilir, ancak gerçekten bir yöntemi olması gerekir.

Bu yöntem değiştirilemiyor, hedef işlem sırasında alternatif bir yönerge bölün ve değerlendirme yeniden denemek mümkün olabilir.
 
### <a name="solution-2-disable-all-implicit-evaluation"></a>Çözüm #2: tüm örtük değerlendirme devre dışı bırak
 
Önceki çözümler sorunu düzeltin yok, Git **Araçları** > **seçenekleri**ve ayarı işaretini **hata ayıklama**  >   **Genel** > **özellik değerlendirmesi ve diğer dolaylı işlev çağrılarını etkinleştirme**. Bu, çoğu dolaylı İşlev değerlendirmesi devre dışı bırakır ve sorun gidermeniz gerekir.



  