---
title: "Etki alanına özgü dil araçları genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language
ms.assetid: 50d93ea2-8c88-4522-853b-40ab194953db
caps.latest.revision: "54"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 20d4222f96958a730c563ff9bc84b2b5d0b08538
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="overview-of-domain-specific-language-tools"></a>Etki Alanına Özgü Dil Araçlarına Genel Bakış
İçinde barındırılan etki alanına özgü dil Araçları (DSL araçları) [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], let bir etki alanına özgü dil tasarlama ve kullanıcıların diline dayalı modelleri oluşturmak için gereken her şeyi oluşturur.  
  
 Aşağıdaki araçlar DSL araçlarında bulunmaktadır:  
  
-   Etki alanına özgü dil geliştirme başlamanıza yardımcı olması için farklı çözüm şablonlar kullanır projesi Sihirbazı.  
  
-   Oluşturma ve etki alanına özgü dil tanımınızı düzenleme için grafik Tasarımcı.  
  
-   Etki alanına özgü dil tanımı doğru biçimlendirildiğinden ve sorunları olduğunda hataları ve uyarıları görüntüler emin olur doğrulama motoru.  
  
-   Bir etki alanına özgü dil tanımı giriş olarak alır ve kaynak kodu çıktı olarak üretir Kod Oluşturucu.  
  
## <a name="the-dsl-tools-solution"></a>DSL araçları çözümü  
 Etki alanına özgü Designer Sihirbazı aşağıdaki çözüm şablonları sağlar:  
  
-   Görev akışı  
  
-   Sınıf diyagramları  
  
-   En az bir dil  
  
-   Bileşen modelleri  
  
-   En az WPF  
  
-   En az Windows.Forms  
  
-   DSL kitaplığı  
  
 Daha fazla bilgi için bkz: [bir etki alanına özgü dil çözüm şablonu seçme](../modeling/choosing-a-domain-specific-language-solution-template.md).  
  
 Sihirbazın oluşturduğu bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şu projeler bulunduğu çözümü:  
  
-   DSL  
  
     Etki alanına özgü dil ve işlemek ve düzenleme araçları Dsl proje tanımlar.  
  
-   **DslPackage**  
  
     Dil araçları nasıl entegre DslPackage proje belirler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="the-dsl-tools-graphical-interface"></a>DSL araçları grafik arabirimi  
 DSL araçları grafik arabirim öğeleri ve ilişkileri, etki alanına özgü dil eklemek için kullanabilirsiniz. Öğeleri ekledikten sonra bunları şekillere eşleme renkleri özelleştirme ve dekoratörler ekleyerek görünümlerini tanımlayabilirsiniz. Araç kutusu öğelerini de ekleyebilirsiniz.  
  
## <a name="validation-in-dsl-tools"></a>Doğrulama DSL araçları  
 Bir etki alanı modeli için kod oluşturmanın temel gereksinimleri karşıladığından emin olmak için doğrulama düzeyini DSL sağlar. Genellikle, kendi etki alanına özgü dil oluşturduğunuzda, iş mantığı kurallarınızı ifade etmek için kendi doğrulama ekleyin. Özel doğrulama hakkında daha fazla bilgi için bkz: [bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md).  
  
 Bunu tasarlarken, etki alanına özgü dil genellikle doğrulamak önerilir. Etki alanına özgü dil doğrulama hatası varsa, kaynak kodu oluşturulamıyor. Şablonlardan kaynak kodu oluşturma işleminin tıklayarak gerçekleştirilen **tüm şablonları dönüştürme** Çözüm Gezgini araç. Dil tanımını değiştirmek olduğunda da emin olun **tüm şablonları dönüştürme**. Daha fazla bilgi için bkz: [nasıl yapılır: bir etki alanına özgü dil çözümü oluşturma](../modeling/how-to-create-a-domain-specific-language-solution.md).  
  
## <a name="customization-of-dsl-tools"></a>DSL araçları özelleştirme  
 Model davranışını daraltın ve dilinizi kısıtlamaları tanımlamak için ek kod sağlayabilir. Gerekirse, metin şablonlarını değiştirerek önemli değişiklikler yapabilirsiniz.  
  
## <a name="distributing-your-dsl-solution"></a>DSL çözümünüzü dağıtma  
 DSL araçları içinde barındırılan bir paket oluşturur [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Paket bir araç kutusu, DSL Gezgini ve etki alanına özgü dil kullanarak modelleri oluşturmak, kullanıcıların izin diğer UI öğelerini görüntüler.  
  
 Ne zaman yapı ve DSL araçları çözüm Çalıştır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ikinci bir örneğini [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , etki alanına özgü dil dil kullanıcıya nasıl göründüğünü gösterir. Her şeyin doğru şekilde çalıştığını doğruladıktan sonra dağıtabilirsiniz `.vsix` dosya DslPackage proje oluşturma klasöründe bulabilirsiniz. Bu dosya DSL olarak yüklemek için kullanılan bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] diğer bilgisayarlar üzerinde uzantısı.  Daha fazla bilgi için bkz: [etki alanına özgü dil çözümleri dağıtma](../modeling/deploying-domain-specific-language-solutions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deneysel örneği](../extensibility/the-experimental-instance.md)   
 [Etki alanına özgü dil araçları sözlüğü](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)