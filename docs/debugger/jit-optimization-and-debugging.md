---
title: JIT iyileştirmesi ve hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], optimized code
- optimized code, debugging
ms.assetid: 19bfabf3-1a2e-49dc-8819-a813982e86fd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9a8cb56b35092bb958ebf2e6947006acb3d0d240
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53646580"
---
# <a name="jit-optimization-and-debugging"></a>JIT İyileştirmesi ve Hata Ayıklaması
**En iyi duruma getirme,. NET'te nasıl:** Kod hatalarını ayıklamak çalışıyorsanız, bu kod olduğunu daha kolay olduğunda **değil** en iyi duruma getirilmiş. Kodun en iyilenmesi, böylece daha hızlı çalışır ancak özgün kaynak kodu doğrudan bir eşlemeye sahip derleyici ve çalışma zamanı yayılan CPU koda değişiklik olmasıdır. Başka bir deyişle, hata ayıklayıcıları yerel değişkenlerin değerini söyleyin ve kod atlama sık belirleyemiyoruz ve kesme noktaları beklediğiniz gibi çalışmayabilir.

Normalde en iyi duruma getirilmiş kod sürüm yapı yapılandırmasını oluşturur ve hata ayıklama yapısı yapılandırması yok. `Optimize` MSBuild özelliği, derleyici kodu en iyi duruma getirme bildirilir olup olmadığını denetler.

.NET ekosisteminde, iki adımlı bir işlem CPU yönergeleri için kaynak kod etkinleştirilir: ilk C# derleyici, yazdığınız metni MSIL olarak adlandırılan bir ara ikili biçimine dönüştürür ve .dll dosyaları için bu yazıyor. Daha sonra .NET çalışma zamanı bu MSIL yönergeleri CPU dönüştürür. Her iki adım bir dereceye kadar en iyi duruma getirebilirsiniz, ancak daha önemli iyileştirmeler .NET çalışma zamanı tarafından gerçekleştirilen ikinci adım gerçekleştirir.

**'Modül yükleme (sadece yönetilen) JIT iyileştirmesini' seçeneği:** Hata ayıklayıcı hedef işlemin içinde iyileştirmeler derlenmiş DLL yüklendiğinde ne olduğunu denetleyen bir seçenek sunar. Bu seçenek işaretli değilse (varsayılan durumu), .NET çalışma zamanı, MSIL kodu CPU koda derlediğinde, iyileştirmeler bırakır. daha sonra. Bu seçenek işaretlenirse, hata ayıklayıcı iyileştirmeleri devre dışı bırakılmasını ister.

Bulunacak **Modül yükleme (sadece yönetilen) JIT iyileştirmesini** seçeneği için **Araçları** > **seçenekleri**ve ardından  **Genel** altındaki **hata ayıklama** düğümü.

**Olduğunda bu seçeneği işaretleyin:** Bir nuget paketi gibi başka bir kaynaktan DLL'leri indirdiğiniz ve bu DLL kodda hata ayıklama istediğinizde bu seçeneği işaretleyin. Bunun çalışması sırada bu DLL için Sembol (.pdb) dosyası da bulmanız gerekir.

Yalnızca yerel olarak oluşturmakta olduğunuz kod hata ayıklamaya ilgileniyorsanız, bazı durumlarda, bu seçeneğin etkinleştirilmesi önemli ölçüde hata ayıklama aşağı yavaşlatır gibi bu seçeneği işaretlemeyin en iyisidir. Yavaşlama bunun iki nedeni vardır:

* En iyi duruma getirilmiş kod daha hızlı çalışır. Çok sayıda kod iyileştirmeleri kapatarak, performans etkisini ekleyebilirsiniz.
* Yalnızca kendi kodum varsa, hata ayıklayıcı bile deneyin ve iyileştirilmiş DLL'leri için sembolleri. Sembol bulma uzun sürebilir.

**Bu seçenek sınırlamaları:** Burada bu seçeneği olacak iki durum vardır **değil** çalışır:

1. Burada hata ayıklayıcı zaten çalışan bir işleme iliştirmekte olduğunuz durumlarda, hata ayıklayıcı iliştirilmiş olduğu sırada zaten yüklenmiş olan modülleri üzerinde hiçbir etkisi bu seçeneğine sahip olursunuz.
2. Bu seçenek silinmiş DLL'leri üzerinde etkiye sahip değildir (a.k.a Ngen) yerel kod için önceden derlenmiş. Ancak, önceden derlenmiş kod kullanımını '1' değişkeni 'COMPlus_ZapDisable' olarak ayarlanan ortam işlem başlayarak devre dışı bırakabilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [Hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md)   
 [Çalıştırma işlemleri iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Yönetilen Yürütme İşlemi](/dotnet/standard/managed-execution-process)
