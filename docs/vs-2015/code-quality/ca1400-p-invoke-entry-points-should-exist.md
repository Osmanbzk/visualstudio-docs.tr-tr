---
title: 'CA1400: P-Invoke giriş noktaları bulunmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1400
- PInvokeEntryPointsShouldExist
helpviewer_keywords:
- PInvokeEntryPointsShouldExist
- CA1400
ms.assetid: 1d64e470-7b2f-4cca-8fb0-ac92829e6332
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f564f130c4f225d62b71778bc141170ea528d4ab
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49810639"
---
# <a name="ca1400-pinvoke-entry-points-should-exist"></a>CA1400: P/Invoke giriş noktaları bulunmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|PInvokeEntryPointsShouldExist|
|CheckId|CA1400|
|Kategori|Microsoft.Interoperability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Ortak veya korumalı yöntem ile işaretlenmiş <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. Yönetilmeyen kitaplık bulunamadı ya da yöntem için bir işlev kitaplığında eşleştirilemedi. Kural gibi tam olarak belirtilen yöntem adı bulamazsanız, ANSI veya geniş karakter sürümleri yöntemi için yöntem adı '' veya 'G' ekleyerek görünüyor. Eşleşme bulunursa, kural __stdcall adı biçimini kullanarak bir işlev bulmaya çalışır (_MyMethod@12, burada bağımsız değişkenlerinin uzunluğu 12 temsil eder). Eşleşme ve yöntem adı '#' ile başlar, kural işlevi için bir ad başvurusu yerine sıralı bir başvuru olarak arar.

## <a name="rule-description"></a>Kural Tanımı
 Hiçbir derleme zamanı denetlemesi emin olmak kullanılabilir ile işaretlenmiş yöntemler <xref:System.Runtime.InteropServices.DllImportAttribute> başvurulan yönetilmeyen DLL içinde yer alır. Belirtilen ada sahip bir işlev kitaplığında yok veya yöntem bağımsız değişkenleri işlev bağımsız değişkenleri eşleşmiyor, ortak dil çalışma zamanı bir özel durum oluşturur.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için yöntemin düzeltmek <xref:System.Runtime.InteropServices.DllImportAttribute> özniteliği. Yönetilmeyen kitaplık varolduğundan ve yöntemi içeren derlemenin ile aynı dizinde olduğundan emin olun. Kitaplık bulunduğundan ve doğru şekilde başvurulan ise, yöntem adı, dönüş türü ve bağımsız değişken imza kitaplığı işlevi eşleştiğini doğrulayın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Yönetilmeyen kitaplık başvurduğu yönetilen bütünleştirilmiş kod ile aynı dizinde olduğunda bu kuraldan bir uyarıyı bastırmayın. Burada yönetilmeyen kitaplık bulunamadı durumda bu kuraldan bir uyarıyı bastırmak güvenli olabilir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir. Adında hiçbir işlev `DoSomethingUnmanaged` kernel32.dll içinde gerçekleşir.

 [!code-csharp[FxCop.Interoperability.DLLExists#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DLLExists/cs/FxCop.Interoperability.DLLExists.cs#1)]

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>



