---
title: IEnumDebugReferenceInfo2::Skip | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEnumDebugReferenceInfo2::Skip
helpviewer_keywords:
- IEnumDebugReferenceInfo2::Skip
ms.assetid: 12f07ed8-92bd-47b5-9113-f73fec5bdde6
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 30b185b691b290b0b6aa7a639fbc3db3b340e61b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51755061"
---
# <a name="ienumdebugreferenceinfo2skip"></a>IEnumDebugReferenceInfo2::Skip
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Belirtilen sayıda öğeyi üzerinden atlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `celt`  
 [in] Geçilecek öğelerin sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` varsa `celt` kalan öğeleri sayısından büyüktür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `celt` numarasından daha büyük bir değer belirtir, kalan öğeleri numaralandırma sonuna ayarlanır ve `S_FALSE` döndürülür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)

