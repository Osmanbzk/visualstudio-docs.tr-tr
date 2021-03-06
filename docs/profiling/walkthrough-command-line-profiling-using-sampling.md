---
title: 'İzlenecek yol: Örnekleme kullanarak komut satırı profili oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance tools, command-line tools
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8dbb5daff9db064cedcfaa6713f5c31a72f961af
ms.sourcegitcommit: 34840a954ed3446c789e80ee87da6cbf1203cbb5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53592436"
---
# <a name="walkthrough-command-line-profiling-using-sampling"></a>İzlenecek yol: Komut satırı kullanarak örnekleme profili oluşturma

Bu yönerge, nasıl bir uygulama komut satırı araçlarını kullanarak ve performans sorunlarını belirlemek için örnekleme profili gösterir.

Bu kılavuzda komut satırı araçlarını kullanarak yönetilen bir uygulama profili oluşturma işlemi adım adım ve uygulamada performans sorunlarını belirlemek ve ayırmak için örnekleme kullanın.

Bu kılavuzda, aşağıdaki adımları izler:

- Bir uygulamayı, komut satırı araçlarını kullanarak ve örnekleme profil.
- Performans sorunlarını bulun ve örneklenen profil oluşturma sonuçları analiz edin.

## <a name="prerequisites"></a>Önkoşullar

- Ara anlayış [!INCLUDE[csharp_current_short](../misc/includes/csharp_current_short_md.md)]
- Komut satırı araçları ile çalışma anlama Ara
- Bir kopyasını [PeopleTrax örneği](../profiling/peopletrax-sample-profiling-tools.md)
- Profil oluşturma tarafından sağlanan bilgiler ile çalışmak için hata ayıklama sembol bilgisi kullanılabilir olması en iyisidir.

## <a name="command-line-profiling-using-the-sampling-method"></a>Örnekleme yöntemini kullanarak komut satırı profili oluşturma

Örnekleme tarafından belirli bir işlem düzenli aralıklarla etkin işlev belirlemek için yoklanabileceği bir profil oluşturma yöntemidir. Sonuçta elde edilen veriler işlem örneklendiğinde ne sıklıkta işlev çağrı yığının en üstünde olan sayısına sağlar.

> [!NOTE]
>  Profil oluşturma araçları için olan yolu almak için bkz: [komut satırı araçları yolunu belirtin](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). 64-bit bilgisayarlarda araçların 64-bit hem 32-bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresinin PATH ortam değişkenine ekleyin veya komutun kendisine eklemeniz gerekir.  

### <a name="to-profile-the-peopletrax-application-by-using-the-sampling-method"></a>Örnekleme yöntemini kullanarak PeopleTrax uygulama profiline

1. PeopleTrax örneği uygulamayı yüklemek ve uygulamanın yayın sürümünü oluşturun.

2. Bir komut istemi penceresi açın ve profil oluşturma araçları dizini için yerel yol ortam değişkenine ekleyin.

3. Çalışma dizini PeopleTrax ikili dosyaları içeren dizine geçin.

4. Uygun ortam değişkenlerini ayarlamak için aşağıdaki komutu yazın:

    ```cmd
    VSPerfCLREnv /sampleon
    ```

5. Çalıştırarak profilini oluşturmaya başla *VSPerfCmd.exe*, profil oluşturucu denetleyen komut satırı aracı. Aşağıdaki komut, uygulama ve profil oluşturucu örnekleme modunda başlatır:

    ```cmd
    VsPerfCmd /start:sample /output:PeopleTraxReport.vsp /launch:PeopleTrax.exe
    ```

     Profil Oluşturucu işlemiyle başlar ve ekler *PeopleTrax.exe* işlem. Rapor dosyasına toplanan profil oluşturma verilerini yazmak profil oluşturucu işlemi başlatır.

6. Tıklayın **kişileri Al**.

7. Tıklayın **ExportData**.

     Notepad açılır ve dışarı aktarılan verileri içeren yeni bir dosya görüntüler **PeopleTrax**.

8. Not Defteri'ni kapatın ve ardından kapatın **PeopleTrax** uygulama.

9. Profil oluşturucuyu kapatın. Şu komutu yazın:

    ```cmd
    VSPerfCmd /shutdown
    ```

10. Ortam değişkenleri sıfırlamak için aşağıdaki komutu kullanın:

    ```cmd
    VSPerfCLREnv /sampleoff
    ```

11. Profil oluşturma verilerini depolanır. *vsp* dosya, aşağıdaki yöntemlerden birini kullanarak sonuçları analiz edin:

    - Açık. *vsp* Visual Studio IDE dosyasında.

         — veya —

    - Virgülle ayrılmış bir değer oluşturur (. *CSV*) komut satırı aracını kullanarak dosya *VSPerfReport.exe*. Dışında kullanım için raporlar üretmek için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE, aşağıdaki komutu kullanın:

        ```cmd
        VSPerfReport <dir> PeopleTraxReport.vsp /output:<dir> /summary:all
        ```

## <a name="see-also"></a>Ayrıca bkz.

[Performans oturumuna genel bakış](../profiling/performance-session-overview.md)  
[Komut satırından profil](../profiling/using-the-profiling-tools-from-the-command-line.md)  
[VSPerfCmd](../profiling/vsperfcmd.md)  
[Örnekleme veri değerlerini anlama](../profiling/understanding-sampling-data-values.md)  
[Performans raporu görünümleri](../profiling/performance-report-views.md)