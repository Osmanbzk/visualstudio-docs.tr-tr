---
title: 'Nasıl Yapılır: Ön ve son izleme komutları belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.instrument
helpviewer_keywords:
- profiling tools, pre-instrument events
- events [Visual Studio], pre-instrument
- pre-instrument events, performance tools
ms.assetid: 6a8d5340-1d1b-4d81-88dd-8e1f435eb828
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 94c27fe4616ffcf541602cc8ab61bbaa26ddbb18
ms.sourcegitcommit: 34840a954ed3446c789e80ee87da6cbf1203cbb5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53593008"
---
# <a name="how-to-specify-pre--and-post-instrument-commands"></a>Nasıl Yapılır: Ön ve son izleme komutları belirtme

Önce veya sonra performans oturumu içindeki ikili dosyaları notınstrumented çalışan komutlar belirtebilirsiniz. Komut satırından verilen herhangi bir komutu bir işaretleme öncesi veya izleme sonrası olayı olarak belirtilebilir. Örneğin, ikili dosyaları algılayıcılarla sonra çalıştırılan bir toplu iş dosyasında bir tanımlayıcı ad anahtarıyla bir derlemenin bildirimin otomatikleştirmek komutları belirtebilirsiniz.

Komutları için profil oluşturma çalıştırmasını tüm izleme eklenmiş ikili dosyaları veya bireysel ikili dosyaları belirtebilirsiniz. Bununla birlikte, önce çalıştırmak için yalnızca bir işaretleme öncesi komutu ve izleme işleminden sonra çalıştırmak için yalnızca bir son izleme komut belirtebilirsiniz. Komutları bireysel ikili dosyaları ve hem tüm ikili dosyaları için belirtilemez. Tüm ikili dosyaları için komutları belirttiğinizde, önce veya sonra her bir ikili izleme oturumunda komutları çalıştırılır.

Komutları yürütülürken çalışma dizini çalıştırdığınız işletim sistemine bağlıdır [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] ve profili oluşturulan uygulamanın hedef platformu.

Profil oluşturma araçları için olan yolu almak için bkz: [komut satırı araçları yolunu belirtin](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).

## <a name="to-specify-pre-instrument-commands"></a>İşaretleme öncesi komut belirtmek için

1. Aşağıdaki adımlardan birini uygulayın:

    - İşaretleme öncesi komutlar tüm ikili dosyaları için bir performans oturumu belirtmek için performans oturumu düğümünde seçin **performans Gezgini**ve ardından sağ tıklayıp **özellikleri**.

    - İşaretleme öncesi komut için belirli bir ikili belirtmek için ikili adına sağ tıklayın **hedefleri** performans oturumu tıklayın ve ardından listesi **özellikleri**.

2. İçinde **özellik sayfaları**, tıklayın **izleme**.

3. Komut türü **komut satırı** metin kutusu altında **işaretleme öncesi olaylar**.

    > [!NOTE]
    > Üç nokta düğmesine tıklayabilirsiniz **(...)**  bitişik olan **komut satırı** kutusunu göz atın ve uygun .exe, .cmd veya .bat dosyasını seçin.

4. **Tamam**'ı tıklatın.

     Komut çalışmasını kaldırmadan devre dışı bırakmak için seçin **İzleme'den Dışla** onay kutusu. Derleyici veya bağlayıcı ayarları değiştirmek için proje özellik sayfalarını kullanın.

## <a name="to-specify-post-instrument-commands"></a>Son izleme komutları belirtmek için

1. Aşağıdaki adımlardan birini uygulayın:

    - Son izleme komutları tüm ikili dosyaları için bir performans oturumu belirtmek için performans oturumu düğümünde seçin **performans Gezgini**ve ardından sağ tıklayıp **özellikleri**.

    - Son izleme komutları için belirli bir ikili belirtmek için ikili adına sağ tıklayın **hedefleri** performans oturumu tıklayın ve ardından listesi **özellikleri**.

2. İçinde **özellik sayfaları**, tıklayın **izleme**.

3. Komut türü **komut satırı** metin kutusu altında **son izleme olayları**.

    > [!NOTE]
    > Üç nokta düğmesine tıklayabilirsiniz **(...)**  bitişik olan **komut satırı** kutusunu göz atın ve uygun .exe, .cmd veya .bat dosyasını seçin.

4. **Tamam**'ı tıklatın.

     Komut çalışmasını kaldırmadan devre dışı bırakmak için seçin **İzleme'den Dışla** onay kutusu. Derleyici veya bağlayıcı ayarları değiştirmek için proje özellik sayfalarını kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)
