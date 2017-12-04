---
title: "CA1409: Com görünebilir türler oluşturulabilmelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
helpviewer_keywords:
- ComVisibleTypesShouldBeCreatable
- CA1409
ms.assetid: 9f59569b-de15-4a38-b7cb-cff152972243
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c8d9fe357142cf8b95be0298797c4a18e9ee0df7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1409-com-visible-types-should-be-creatable"></a>CA1409: Com görünebilir türler oluşturulabilmelidir
|||  
|-|-|  
|TypeName|ComVisibleTypesShouldBeCreatable|  
|CheckId|CA1409|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Özellikle Bileşen Nesne Modeli (COM) olarak görünür olarak işaretlenmiş bir başvuru türü bir public parametreli Oluşturucu içeriyor ancak (parametresiz) ortak varsayılan bir oluşturucu içermiyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Genel varsayılan bir oluşturucu olmadan türü COM istemcileri tarafından oluşturulamıyor. Ancak, başka bir yöntem türü oluşturmak ve istemcinin (örneğin, üzerinden bir yöntem çağrısının dönüş değerini) geçirmek kullanılabilir durumdaysa türü hala COM istemcileri tarafından erişilebilir.  
  
 Kural türetilmiş türler yoksayar <xref:System.Delegate?displayProperty=fullName>.  
  
 Varsayılan olarak, COM görünür şunlardır: derlemeleri, genel türleri, genel türlerde ortak örnek üyeleri ve ortak değer türleri tüm üyeleri.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal gidermek için genel varsayılan bir oluşturucu ekleyin veya kaldırın <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> türünden.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan oluşturmak ve COM istemciye nesneyi geçirmek için diğer yolları sağladıysanız gizlemek güvenlidir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1017: derlemeleri ComVisibleAttribute ile işaretleme](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birlikte çalışma için .NET türlerini niteleme](/dotnet/framework/interop/qualifying-net-types-for-interoperation)   
 [Yönetilmeyen kod ile birlikte çalışma](/dotnet/framework/interop/index)