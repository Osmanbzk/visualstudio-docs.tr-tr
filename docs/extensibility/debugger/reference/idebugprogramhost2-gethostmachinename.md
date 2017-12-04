---
title: IDebugProgramHost2::GetHostMachineName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramHost2::GetHostMachineName
helpviewer_keywords: IDebugProgramHost2::GetHostMachineName
ms.assetid: 4677ffe4-aa9b-4450-a63b-74cd3984d956
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa47d74aef66d26fedaa1de6ac4348941234f642
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramhost2gethostmachinename"></a>IDebugProgramHost2::GetHostMachineName
Bu program barındırma işlemi çalışmıyor makine adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetHostMachineName(   
   BSTR* pbstrHostMachineName  
);  
```  
  
```csharp  
int GetHostMachineName(   
   out string pbstrHostMachineName  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pbstrHostMachineName`  
 [out] Makinenin adını döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)