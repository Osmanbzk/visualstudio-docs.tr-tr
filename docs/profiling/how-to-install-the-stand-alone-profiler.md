---
title: "Nasıl Yapılır: Tek başına Profiler'ı yükleme | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, installing stand-alone profiler
- profiling tools, stand-alone profiler
ms.assetid: cae81c95-83cd-4ab6-8a98-84ef977a2f6d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0f8f4204a48a9846a6193c6b8b60c3ef321816e
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53648674"
---
# <a name="how-to-install-the-stand-alone-profiler"></a>Nasıl Yapılır: Bağımsız profil oluşturucuyu yükleme
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir komut satırı tabanlı yüklemeden çalıştırabilirsiniz bağımsız profil oluşturucuyu sağlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE. Bir bilgisayar yok ya da yüklü bir geliştirme ortamı olamaz bu durum oluşur. Örneğin, bir üretim web sunucusunda bir geliştirme ortamı yüklememelidir.  
  
> [!NOTE]
>  Bir ASP.NET web sitesi için performans verilerini toplamak için bağımsız profil oluşturucuyu kullanırken [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md) Çizgi aracı üzerinden önerilir [VSPerfCmd](../profiling/vsperfcmd.md) aracı.  
  
### <a name="to-install-the-stand-alone-profiler"></a>Bağımsız profil oluşturucuyu yükleme  

1. İndirme [Visual Studio için performans araçları](https://visualstudio.microsoft.com/downloads/?q=performance+tools#performance-tools-for-visual-studio-2017).

1. Bağımsız Profil yükleyicisini bulun (*vs_standaloneprofiler.exe*) performans araçları indirdiğiniz ve çalıştırın.
  
2. Yollarını eklemek *vsintr.exe* ve *msdis150.dll* sistem yolu.  
  
   > [!NOTE]
   >  Profil oluşturma araçları için olan yolu almak için bkz: [komut satırı araçları yolunu belirtin](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md). 64-bit bilgisayarlarda araçların 64-bit hem 32-bit sürümleri kullanılabilir. Profil oluşturucu komut satırı araçlarını kullanmak için Araçlar yolunu komut istemi penceresinin PATH ortam değişkenine ekleyin veya komutun kendisine eklemeniz gerekir. 
  
3. Komut isteminde **Vsınstr**.  
  
   > [!NOTE]
   >  Vsinstr.exe yönelik kullanım bilgilerini gösterilirse, her şeyin doğru şekilde ayarlanır. Vsinstr.exe belirten bir hata göreceğiniz ya da bağımlılıklarından biri bulunamadı, cihazınızdaki yollar 2. adımda açıklandığı gibi doğru şekilde ayarlanmış olduğundan emin olun.  
  
4. Sembol sunucusu ayarlamak, **_NT_SYMBOL_PATH** değişkenini **symsrv\*symsrv.dll\*c:\localcache\*http://msdl.microsoft.com/download/symbols**  
  
5. Sistem ortam değişkenlerini kullanarak sembol sunucunuz ayarladıktan sonra komut satırından profil oluşturucu Araçlar yeni bir komut isteminde çalıştırın. Bu, etkili olması yeni ortam değişkenlerini tanır. Komut İstemi penceresinde aşağıdaki komutu yazın:  
  
    **COMSPEC % Başlat**  
  
   > [!NOTE]
   >  Sembol sunucusu paketi ayarlama konusunda ayrıntılı yönergeler için bkz: [nasıl yapılır: Windows sembol bilgilerini başvuru](../profiling/how-to-reference-windows-symbol-information.md).  
  
6. Kullanım [VSPerfReport](../profiling/vsperfreport.md) aracı profil oluşturma veri (.vsp) dosyasına, semboller serileştirmek için. Kullanım **VSPerfReport userrulesdirectory packsymbols** anahtarlar. Veri dosyasına eklenmiş semboller yoksa _NT_SYMBOL_PATH ortam değişken kümesi olduğunu emin olun.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Komut satırından profil](../profiling/using-the-profiling-tools-from-the-command-line.md)   
 [İzlenecek yol: Komut satırı kullanarak örnekleme profili oluşturma](../profiling/walkthrough-command-line-profiling-using-sampling.md)   
 [İzlenecek yol: Komut satırı araçları kullanarak profil oluşturma](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)   
 [Nasıl yapılır: Başvuru Windows sembol bilgileri](../profiling/how-to-reference-windows-symbol-information.md)   
 [VSPerfReport](../profiling/vsperfreport.md)