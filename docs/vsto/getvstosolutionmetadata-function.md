---
title: GetVstoSolutionMetadata işlevi
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: baa5cf48d317da80f78d19a1b72f81824b1bed62
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53647277"
---
# <a name="getvstosolutionmetadata-function"></a>GetVstoSolutionMetadata işlevi
  Bu API Office altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```csharp
HRESULT WINAPI GetVstoSolutionMetadata(  
    LPCWSTR lpwszSolutionMetadataKey,  
    ISolutionMetadata** ppSolutionInfo  
);  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*lpwszSolutionMetadataKey*|Kullanmayın.|  
|*ppSolutionInfo*|Kullanmayın.|  
  
## <a name="return-value"></a>Dönüş değeri  
 İşlev başarılı olursa, döndürür **S_OK**. İşlev başarısız olursa hata kodu döndürür.  
  
  