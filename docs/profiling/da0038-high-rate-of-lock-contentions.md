---
title: "DA0038: Yüksek oranda kilit çakışmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.38
- vs.performance.rules.DA0038
- vs.performance.DA0038
ms.assetid: ae0c8b2f-17b2-4f3d-a834-aa2f6371753b
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30f9dbb760bd013bae08b5539f32d652ec3313bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="da0038-high-rate-of-lock-contentions"></a>DA0038: Yüksek Oranda Kilit çakışmaları
|||  
|-|-|  
|Kural Kimliği|DA0038|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemi|Örnekleme<br /><br /> İzleme<br /><br /> .NET bellek|  
|İleti|.NET kilit çakışmaları yüksek oranda oluşmalıdır. Lütfen bir eşzamanlılık profili çalıştırarak bu kilit çakışması nedenlerini araştırın.|  
|Kural türü|Bilgiler|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 25 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 Toplanan sistem performans verilerini profil oluşturma verileri, önemli ölçüde yüksek oranda kilit çakışmaları uygulama yürütmesi sırasında oluştuğunu gösterir. Yeniden çekişmeleri nedenini bulmak için eşzamanlılık profili oluşturma yöntemi kullanarak profil oluşturmayı düşünün.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kilit, çok iş parçacıklı uygulamasında bir seferde bir iş parçacığı tarafından seri olarak yürütülmelidir kod kritik bölümler korumak için kullanılır. Microsoft .NET ortak dil çalışma zamanı (CLR), eşitleme ve temelleri kilitleme tam kümesi sağlar. Örneğin, C# dili lock deyimi (Visual Basic'te SyncLock) destekler. Yönetilen bir uygulamaya Monitor.Enter ve Monitor.Exit yöntemleri edinmeli ve doğrudan kilidi için System.Threading ad alanı içinde çağırabilirsiniz. .NET Framework, ek eşitleme ve temelleri zaman uyumu sağlayıcılar, ReaderWriterLocks ve semaforları destekleyen sınıfları dahil olmak üzere, kilitleme destekler. Daha fazla bilgi için bkz: [eşitleme temellerine genel bakış](http://go.microsoft.com/fwlink/?LinkId=177867) MSDN Web sitesinde .NET Framework Geliştirici Kılavuzu. .NET Framework kendilerini Windows işletim sisteminde yerleşik düşük düzeyli Eşitleme Hizmetleri üzerinde katmanlı sınıflarıdır. Bunlar, kritik bölüm nesneleri ve birçok farklı bekleyin ve işlevleri sinyal olayı içerir. Daha fazla bilgi için bkz: [eşitleme](http://go.microsoft.com/fwlink/?LinkId=177869) Win32 ve COM Geliştirme MSDN Kitaplığı'nda bölümü  
  
 .NET Framework sınıfları ve eşitleme için kullanılan yerel Windows nesneleri temel ve kilitleme birbirine kenetlenmiş işlemler kullanılarak değiştirilmelidir paylaşılan bellek konumlar içindedir. Atomik işlemleri kullanarak kendi durumunu değiştirmek için paylaşılan bellek konumları çalışan işlemleri kullanın donanıma özgü yönergeleri interlocked. Atomik işlemleri makinedeki tüm işlemcilere tutarlı olması garanti. Kilitler ve WaitHandle ayarlayın veya sıfırlama kullanan otomatik olarak birbirine kenetlenmiş işlemler .NET nesneleridir. Olabilir diğer paylaşılan bellek veri yapılarını uygulamanızda da bir iş parçacığı açısından güvenli şekilde güncelleştirilmesi için birbirine kenetlenmiş işlemler kullanmanızı gerektirir. Daha fazla bilgi için bkz: [Interlocked Operations](http://go.microsoft.com/fwlink/?LinkId=177870) MSND kitaplığı .NET Framework bölümünde  
  
 Eşitleme ve kilitleme çoklu iş parçacığı uygulamalarını doğru yürütmek sağlamak için kullanılan mekanizmalardır. Çok iş parçacıklı uygulamasının her bir iş parçacığı bağımsız olarak işletim sistemi tarafından zamanlanmış bir bağımsız yürütme birimidir. Başka bir iş parçacığı kilidi tutan çünkü bir kilit edinmeye çalışırken bir iş parçacığı Gecikmeli her bir kilit çakışması gerçekleşir.  
  
 Kilitleri sık yerleştirilir. İç içe geçme, önemli bir bölümü yürütme iş parçacığı başka bir kilit gerektiren bir işlev gerçekleştirir oluşur. Bazı kilit iç içe geçme kaçınılmaz miktarıdır. Kritik bölümünüzü kilit iş parçacığı açısından güvenli olduğundan emin olmak için bağımlı bir .NET Framework yöntemini çağırabilir. Aynı zamanda bir başka kilit işleci kullanılarak kilitler Framework yöntemi uygulamanıza kritik bazı bölümünde çağrısından iç içe kilitleri neden olur. İç içe geçmiş kilitleme koşullar aydınlatmak ve düzeltmek notoriously zor olan performans sorunlarına yol açabilir.  
  
 Profil oluşturma çalışması sırasında alınan ölçümlere kilit çakışması aşırı yüksek miktarda yoktur belirttiğinizde, bu kural tetikler. Kilit çakışmaları kilidi için bekleyen iş parçacığı yürütme gecikmesi. Kilit çakışması birim testleri veya alt son donanım üzerinde çalışan Yük testlerindeki bile oldukça az miktarda incelenmesi gerekiyor.  
  
> [!NOTE]
>  Profil oluşturma verileri içinde bildirilen kilit çakışmaları oranını aşırı yüksek olduğunda [DA0039: çok yüksek oranda kilit çakışmaları](../profiling/da0039-very-high-rate-of-lock-contentions.md) uyarı iletisi yerine bu bilgi iletisi gönderildi.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 İletinin gitmek için çift [işaretleri](../profiling/marks-view.md) profil oluşturma verileri görünümü.  Bul **.NET CLR LocksAndThreads\Contention oranı / sn** sütun. Olup olmadığını program yürütme belirli aşamaları kilit çakışması diğer aşamalar ağır olduğu belirler.  
  
 Yalnızca eşzamanlılık profili oluşturma yöntemi kullanmıyorsanız bu kuralı ateşlenir. Eşzamanlılık profili oluşturma yöntemi, kilit çakışması uygulamanızda ilgili performans sorunlarını tanılamak için kullanmak için en iyi bir araçtır. Eşzamanlılık profili oluşturma, uygulamanızın kilitlenme davranışını anlamak için verileri toplar. İş parçacığı yürütme süresi contended kilitleri ve hangi belirli bir kod implicated için bekleyen ne kadar Gecikmeli, bu hangi kilitleri yoğun contended anlama içerir. Eşzamanlılık profilleri topladığı verileri tüm kilitleme çekişmeleri, yerel Windows özellikleri, .NET Framework sınıf ve başka bir üçüncü taraf kitaplıklar kilitlenme davranışını dahil olmak üzere, uygulamanızın başvuruları. Öğesinden eşzamanlılık profili oluşturma hakkında bilgi için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE bkz [toplama iş parçacığı ve işlem eşzamanlılık verileri](../profiling/collecting-thread-and-process-concurrency-data.md). Komut satırından profil oluşturma bağlantıları eşzamanlılık hakkında bilgi için bkz **kaynak çekişmesini toplamak ve iş parçacığı etkinliği veri eşzamanlılık yöntemiyle** bölümünü [kullanarak profil oluşturma yöntemlerini gelen Komut satırı](../profiling/using-profiling-methods-to-collect-performance-data-from-the-command-line.md).