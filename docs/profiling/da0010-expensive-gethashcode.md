---
title: "DA0010: Pahalı GetHashCode | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.rules.DAExpensiveGetHashCode
- vs.performance.DA0010
- vs.performance.rules.DA0010
- vs.performance.10
ms.assetid: 3987e21a-5b4f-45e4-8a33-6b3f0a472c08
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9209d5f02d543cba3dd0dcec8f5492e2f64b9cef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="da0010-expensive-gethashcode"></a>DA0010: Pahalı GetHashCode
|||  
|-|-|  
|Kural Kimliği|DA0010|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemleri|Örnekleme<br /><br /> .NET bellek|  
|İleti|GetHashCode işlevleri, ucuz ve tüm belleği ayırmaya değil. Karma kod işlevi karmaşıklığını mümkünse azaltın.|  
|İleti türü|Uyarı|  
  
## <a name="cause"></a>Sebep  
 Profil oluşturma verileri önemli bir kısmının türü GetHashCode yöntemi çağrıları aynıdır veya yöntemi bellek ayırır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Karma, hızlı bir şekilde büyük bir koleksiyondaki belirli bir öğe bulmak için bir tekniktir. Karma tabloları çok büyük ve çok yüksek hızda erişim desteklemek zorunda olduğundan, karma tabloları son derece verimli olması gerekir. Bu gereksinim, bir uygulanır, .NET Framework'teki GetHashCode yöntemleri bellek ayırmanız değil ' dir. Bellek ayırma atık toplayıcı üzerindeki yükü artırır ve atık toplama ayırma isteğinin sonucu olarak çalıştırmak için gerekli hale gelirse olası gecikmelere yöntemi gösterir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Yöntem karmaşıklığını azaltın.