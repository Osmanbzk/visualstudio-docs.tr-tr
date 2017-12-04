---
title: "Bir etki alanına özgü dili kod oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3706cc9-2afd-456a-a879-68425a248ebc
caps.latest.revision: "13"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 98811cc3e7830dfcbf548bc34c5b3ee268e6f858
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="generating-code-from-a-domain-specific-language"></a>Etki Alanına Özgü Dilden Kod Oluşturma
Microsoft [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] modellerinde gösterilen veriler kod, belgeler, yapılandırma dosyalarını ve diğer yapıları oluşturmak için güçlü bir yol sağlar. Kullanarak [!INCLUDE[dsl](../modeling/includes/dsl_md.md)], verilerinizi temsil eden sınıfları kümesi oluşturabilirsiniz ve metin şablonları sınıflarda adları yazabilirsiniz ve özellikleri verileri yansıtır.  
  
 Örneğin, Fabrikam müşteri adları ve e-posta adreslerini içeren bir XML dosyası vardır. Kendi geliştiriciler müşteri özellikleri ad ve e-posta ile bir sınıf olduğu bir modeli oluşturun. Bunlar, bir HTML sayfası bir parçası olarak bir tablo tüm müşterilerin üreten bu parçasını da dahil olmak üzere bu verileri işlemek için birkaç metin şablonları yazma:  
  
```  
<table>  
<# foreach (Customer c in ContactList) {  #>  
  <tr><td> <#= c.FullName #> </td>   
      <td> <#= c.EmailAddress #> </td> </tr>  
<# } #>  </table>  
```  
  
 Müşteri veritabanı işlendiğinde XML dosyasını model deposuna okunur. A *yönerge işlemcisi*, kullanılarak oluşturulmuş [!INCLUDE[dsl](../modeling/includes/dsl_md.md)], müşteri sınıf metin şablonu kodu için kullanılabilir hale getirir. Birçok metin şablonları aynı deponun karşı çalıştırabilirsiniz.  
  
 Metin şablonları için temel [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]. Etki alanı modeli VSPackage ve araçları ile tümleştirmek için kullanılan denetimler de öğelerini kaynak kodunu oluşturmak için kullanılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 Bu bölümde bazı oluşturmak, değiştirmek ve metin şablonları kullanılan hata ayıklama yolları açıklanmaktadır [!INCLUDE[dsl](../modeling/includes/dsl_md.md)].  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Metin şablonları erişilirken modellerinden](../modeling/accessing-models-from-text-templates.md)  
  
 Metin şablonları etki alanına özgü dil başvurma hakkında temel bilgiler sağlar.  
  
 [İzlenecek yol: metin şablonu bu erişimleri bir modeli hata ayıklama](../modeling/walkthrough-debugging-a-text-template-that-accesses-a-model.md)  
  
 Sorun giderme ve bir etki alanına özgü dil başvuran bir metin şablonu hata ayıklama yapmak açıklar.  
  
 [İzlenecek yol: bir oluşturulan bir yönerge işlemcisi konağa bağlanma](../modeling/walkthrough-connecting-a-host-to-a-generated-directive-processor.md)  
  
 Oluşturulan bir yönerge işlemcisi özel bir ana bilgisayara bağlanmaya açıklar.  
  
 [DslTextTransform komutu](../modeling/the-dsltexttransform-command.md)  
  
 Etki alanına özgü dil başvurusu metin şablonları için komut satırında TextTransform yürütülebilir yürütür komut dosyası açıklanmaktadır.  
  
## <a name="reference"></a>Başvuru  
 [T4 metin şablonu yazma](../modeling/writing-a-t4-text-template.md)  
  
 Metin şablonu yönergeleri ve denetim blokları sözdizimi sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md)  
  
 Metin şablonu dönüştürme süreci açıklanmaktadır.  
  
 [Derleme sürecinde kod oluşturma](../modeling/code-generation-in-a-build-process.md)  
  
 Derleme sunucusundaki DSL gelen dosyaları oluşturma varsa bu konuyu okuyun.