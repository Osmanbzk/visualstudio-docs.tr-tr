---
title: 'Nasıl Yapılır: Komut satırını kullanarak eşzamanlılık verileri toplamak için bağımsız bir yerel uygulama Profiler ile başlatma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: e5aed651-afed-4b70-9a7e-1a6032cc614f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: a144462902ec13d116a083c3475b6ec3f8f01a8a
ms.sourcegitcommit: 34840a954ed3446c789e80ee87da6cbf1203cbb5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53592592"
---
# <a name="how-to-launch-a-stand-alone-native-application-with-the-profiler-to-collect-concurrency-data-by-using-the-command-line"></a>Nasıl Yapılır: Komut satırını kullanarak eşzamanlılık verileri toplamak için bağımsız bir yerel uygulamayı başlatma
Bu konu nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yerel tek başına (istemci) uygulamasına başlatmak ve işlem ve iş parçacığı eşzamanlılık verileri toplamak için profil oluşturma araçları komut satırı araçları.  
  
 Profil oluşturma oturumunu aşağıdaki bölümden oluşur:  
  
-   Uygulamayı Profil Oluşturucu ile başlatma  
  
-   Veri toplama denetimi  
  
-   Profil Araçları oturumunu sonlandırma  
  
> [!NOTE]
>  Profil oluşturma araçları için olan yolu almak için bkz: [komut satırı araçları yolunu belirtin](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). 64-bit bilgisayarlarda araçların 64-bit hem 32-bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresinin PATH ortam değişkenine ekleyin veya komutun kendisine eklemeniz gerekir.

## <a name="start-the-application-with-the-profiler"></a>Uygulamayı Profil Oluşturucu ile başlatma  
 Hedef bir uygulamaya Profil Oluşturucu ile başlatmak için kullandığınız [VSPerfCmd.exe](../profiling/vsperfcmd.md)**/start** ve **/başlatma** Profiler'ı başlatın ve uygulamayı başlatmak için Seçenekler. Belirtebileceğiniz **/start** ve **/başlatma** ve onların kendi seçenekleri. Ayrıca ekleyebilirsiniz **/globaloff** hedef uygulamanın başlatıldığı sırada veri toplamayı duraklatma seçeneğinin. Daha sonra **/globalon** veri toplamaya başlamak için.  
  
#### <a name="to-start-an-application-with-the-profiler"></a>Profil Oluşturucu ile bir uygulamayı başlatmak için  
  
1.  Bir komut isteminde aşağıdaki komutu yazın:  
  
     [VSPerfCmd](../profiling/vsperfcmd.md) **/start:concurrency/Output:** `OutputFile` [`Options`]  
  
     [/Output](../profiling/output.md)**:** `OutputFile` ile seçeneği gereklidir **/start**. `OutputFile` Profil oluşturma veri (.vsp) dosyasının konumunu ve adını belirtir.  
  
     Aşağıdaki tabloda seçeneklerden herhangi birini kullanabilirsiniz **/start:concurrency** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Profil oluşturma sırasında Tahsil edilecek Windows performans sayacı belirtir.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|İle kullanma **/wincounter** yalnızca. Windows performans sayacı toplama olayları arasındaki milisaniye sayısını belirtir. Varsayılan değer 500'dür.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Profil oluşturma sırasında Tahsil edilecek bir olay izleme için Windows (ETW) olayı belirtir. ETW olayları ayrı (.etl) dosyasında toplanır.|  
  
2.  Hedef uygulama yazarak başlatın:  
  
     **VSPerfCmd**[/başlatma](../profiling/launch.md) **:** `AppName` [`Options`]    
  
     Aşağıdaki tabloda seçeneklerden herhangi birini kullanabilirsiniz **/başlatma** seçeneği.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[args](../profiling/args.md) **:** `Arguments`|Hedef uygulama için geçirilecek komut satırı bağımsız değişkenleri içeren bir dize belirtir.|  
    |[/ Console](../profiling/console.md)|Hedef komut satırı uygulaması ayrı bir pencerede başlatır.|  
    |[/ targetclr](../profiling/targetclr.md) **:** `CLRVersion`|Ortak dil çalışma zamanı (CLR birden fazla sürümünü uygulama yüklenirse, profil CLR) sürümünü belirtir.|  
  
## <a name="control-data-collection"></a>Veri toplamayı denetleme  
 Hedef uygulama çalışırken, dosyasına verilerin yazılmasını durdurmayla ve veri toplamayı kontrol edebilirsiniz *VSPerfCmd.exe* seçenekleri. Denetleme veri toplama işlemi tarafından program yürütmenin, uygulamanın başlatılması ya da kapatılması gibi özel bir bölümü için veri toplayabilir.  
  
#### <a name="to-start-and-stop-data-collection"></a>Veri toplamayı durdurmak ve başlatmak  
  
-   Aşağıdaki tabloda seçenekleri çiftlerini başlatın ve veri toplama işlemini durdurun. Her seçeneği ayrı bir komut satırında belirtin. Veri Toplama'ı, birden çok kez açıp kapatabilirsiniz.  
  
    |Seçenek|Açıklama|  
    |------------|-----------------|  
    |[/ globalon /globaloff](../profiling/globalon-and-globaloff.md)|Başlar (**/globalon**) veya durdurur (**/globaloff**) tüm işlemler için veri toplama.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Başlar (**/processon**) veya durdurur (**/processoff**) veri toplama işlemi için işlem kimliği (`PID`) belirtir.|  
    |[/ ekleme](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ ekleme** işlem için veri toplamaya başlar, işlem kimliği (`PID`) veya işlem adı (*ProcName*) belirtir. **/ detach** belirlenmiş bir işlem için belirtilen işlem veya tüm işlemler için veri toplamayı durdurur.|  
  
-   Ayrıca **VSPerfCmd.exe**[/mark](../profiling/mark.md) veri dosyasına bir profil oluşturma işareti eklemek için seçeneği. **/Mark** komut tanımlayıcı, bir zaman damgası ve isteğe bağlı kullanıcı tanımlı bir metin dizesi ekler. İşaretler profil oluşturucu raporlar ve veri görünümlerindeki verilere filtre için kullanılabilir.  
  
## <a name="end-the-profiling-session"></a>Profil oluşturma oturumunu sona erdirme  
 Profil oluşturma oturumunu sona erdirmek için Profil Oluşturucu veri toplamıyor olmalıdır. Profili oluşturulan uygulamayı kapatarak veya çağırarak eşzamanlılık verileri toplama işlemini durdurabilirsiniz **VSPerfCmd / detach** seçeneği. Ardından çağırmak **VSPerfCmd/shutdown** profil oluşturucuyu devre dışı bırakırsınız ve profil oluşturma veri dosyasını kapatırsınız.  
  
#### <a name="to-end-a-profiling-session"></a>Profil oluşturma oturumunu sona erdirmek için  
  
1.  Hedef uygulamadaki profil oluşturucuyu kapatarak veya bir komut isteminde aşağıdaki komutu yazarak bağlantısını kesin:  
  
     **VSPerfCmd / detach**  
  
2.  Bir komut isteminde aşağıdaki komutu yazarak profil oluşturucuyu kapatın:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)