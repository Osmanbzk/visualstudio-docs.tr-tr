---
title: "Adlandırma uyarıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.namingrules
helpviewer_keywords:
- managed code analysis warnings, naming warnings
- naming warnings
- warnings, naming
ms.assetid: f97223ce-1d39-4134-81c9-fff2c75d979b
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 21c23e1ebdcf4a4c14fe269376b56a62742e44db
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="naming-warnings"></a>Adlandırma Uyarıları
Adlandırma uyarıları adlandırma kurallarına destek bağlılığı [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] tasarım yönergeleri.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1700: numaralandırma değerlerini 'Ayrılmış' adını vermeyin](../code-quality/ca1700-do-not-name-enum-values-reserved.md)|Bu kural, "ayrılmış" içeren bir ada sahip numaralandırma üyesi şu anda kullanılmamaktadır ancak yeniden adlandırılabilir veya gelecekteki bir sürüme kaldırıldığını varsayar. Üye kaldırma veya yeniden adlandırma bölünmesi farklıdır.|  
|[CA1713: Olaylar önce veya sonra önek olmamalıdır](../code-quality/ca1713-events-should-not-have-before-or-after-prefix.md)|Olay adı "Önce" veya "Sonra" ile başlar. Belirli bir sırayla ilgili olayları adlandırmak için şimdiki veya geçmiş zamanı göreceli konumun sıralı eylemlerini belirtmek için kullanın.|  
|[CA1714: Bayrak numaralandırmalarında çoğul adlar olmalıdır](../code-quality/ca1714-flags-enums-should-have-plural-names.md)|Genel sabit listesi System.FlagsAttribute özniteliği var ve adını "s" bitmez. FlagsAttribute ile işaretlenmiş türleri, öznitelik birden fazla değer belirtilebilir gösterir çünkü çoğul adlar sahip.|  
|[CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)|Dışarıdan görünen bir tanımlayıcı ad Microsoft yazım denetimi kitaplığı tarafından tanınmayan bir veya birkaç sözcük içerir.|  
|[CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)|Ortak dil çalışma zamanı hedef dilleri büyük/küçük harf duyarlı olması gerekmediğinden ad alanları, türler, üyeler ve parametreler için tanımlayıcılar yalnızca büyük/küçük harfe göre farklılık göstermeyebilir.|  
|[CA1715: Tanımlayıcılar doğru olmalıdır](../code-quality/ca1715-identifiers-should-have-correct-prefix.md)|Dışarıdan görünür arabirim adı bir büyük harf "ı ile" başlatılmaz.  Harici olarak görünen türü veya yöntemi genel tür parametresinin adı "T" büyük ile başlamaz.|  
|[CA1720: Tanımlayıcılar tür adları içermemelidir](../code-quality/ca1720-identifiers-should-not-contain-type-names.md)|Parametre adı dışarıdan görünen üye, veri türü adını içerir ya da açıkça görünen üyenin adı dil özellikli veri türü adı içerir.|  
|[CA1722: Tanımlayıcılar yanlış önek olmamalıdır](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)|Kural gereği, programlama öğelerinin belirli bir önek ile başlayan adları vardır.|  
|[CA1711: Tanımlayıcılar yanlış sonekine sahip olmamalıdır](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)|Kural gereği, yalnızca, belirli temel türleri genişleten veya bazı arabirimleri ya da bu türlerinden türetilmiş türleri uygulayan tür adları belirli ayrılmış öneklerle bitmelidir. Diğer tür adları aşağıdaki ayrılmış sonekleri kullanmamalı.|  
|[CA1717: Yalnızca FlagsAttribute numaralandırmalarında çoğul adlar olmalıdır](../code-quality/ca1717-only-flagsattribute-enums-should-have-plural-names.md)|Adlandırma kuralları numaralandırma için adlandırma aynı anda birden fazla numaralandırma değeri olduğunu gösterir.|  
|[CA1725: Parametre adları taban ile eşleşmelidir](../code-quality/ca1725-parameter-names-should-match-base-declaration.md)|Parametreyi geçersiz kılma hiyerarşisinde tutarlı adlandırma yöntemini geçersiz kılmaları kullanılabilirliği artırır. Temel bildirim alanındaki addan farklı türetilmiş yöntem parametre adı taban yöntemini geçersiz kılma veya yeni aşırı yöntemin yöntem olup olmadığı hakkında karışıklığa neden olabilir.|  
|[CA1719: Parametre adları üye adlarıyla eşleşmemelidir](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)|Bir parametre adı bir parametre anlamını iletişim kurmanız gerekir ve bir üye adı üyesi anlamını iletişim kurmanız gerekir. Bunların aynı olduğu yerlerde nadir bir tasarım olur. Aynı üye adıyla parametreyi adlandırma sezgisel değildir ve kütüphane kullanımını zorlaştırır.|  
|[CA1701: Kaynak dize bileşik sözcüklerinin doğru ortası](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)|Her sözcüğün kaynak dizesi büyük/küçük harf üzerinde temel belirteçler içine ayrılır. Her bir bitişik ikili-işaret kombinasyonu Microsoft yazım kitaplığı tarafından denetlenir. Tanınırsa, kelime kural ihlali üretir.|  
|[CA1703: Kaynak dizeler doğru yazılmalıdır](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)|Kaynak dizesi, Microsoft Yazım kitaplığı tarafından tanınmayan bir veya birkaç sözcük içerir.|  
|[CA1724: Tür adları ad alanları eşleşmemelidir](../code-quality/ca1724-type-names-should-not-match-namespaces.md)|Tür adları tanımlanan ad alanları adlarını değil eşleşmelidir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sınıf kitaplığı. Bu kural ihlal kitaplığı kullanılabilirliğini azaltabilir.|  
|[CA1707: Tanımlayıcılar alt çizgi içermemelidir](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)|Kural gereği, tanımlayıcı adlar alt çizgi (_) karakterini içermez. Bu kural ad alanlarını, türleri, üyeleri ve parametreleri denetler.|  
|[Ca1721: Tür adları eşleşmemelidir alma yöntemleri](../code-quality/ca1721-property-names-should-not-match-get-methods.md)|Ortak veya korumalı bir üye adı "Get" ile başlar ve aksi durumda ortak veya korumalı özellik adıyla eşleşir. "Get" yöntemlerinin ve özelliklerinin açıkça işlevlerinden ayırt edilebilen adları olması gerekir.|  
|[CA1716: Tanımlayıcılar anahtar sözcükleri eşleşmemelidir](../code-quality/ca1716-identifiers-should-not-match-keywords.md)|Ad alanı adı veya tür adı ayrılmış anahtar sözcük bir programlama dili ile eşleşir. Tanımlayıcı adı ve türleri için ortak dil çalışma zamanı, hedef diller tarafından tanımlanan anahtar sözcüklerle aynı değildir.|  
|[CA1726: tercih edilen kullanım koşulları](../code-quality/ca1726-use-preferred-terms.md)|Dışarıdan görünen bir tanımlayıcının adı, tercih edilen terim varolduğunda alternatif olarak bir terim içerir. Alternatif olarak ad, "Bayrak" veya "Bayraklar" terimini içerir.|  
|[CA1709: Tanımlayıcılar doğru ortası](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)|Kurala göre parametre adları ortası büyük/küçük harf ve ad alanı, tür ve üye adlarının Pascal büyük/küçük harf.|  
|[CA1702: Bileşik sözcüklerin doğru ortası](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)|Tanımlayıcının adı birden çok sözcük içerir ve bu sözcüklerden en az biri büyük harf kullanımı hatasına maruz kalmış birleşik kelime olarak görülür.|  
|[CA1712: numaralandırma değerleri tür adıyla önek kullanmayın](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)|Tür bilgileri geliştirme araçları tarafından sağlanacak beklendiğinden numaralandırma üyeleri adlarını tür adıyla önek değil.|  
|[CA1710: Tanımlayıcılar doğru olmalıdır](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)|Kurala göre belli temel türleri genişletmek veya belirli arabirimlerine veya bu türlerinden türetilmiş türler uygulayan türü adlarının temel türü veya arabirim ile ilişkili bir son eke sahip.|