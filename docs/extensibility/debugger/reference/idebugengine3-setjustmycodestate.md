---
title: IDebugEngine3::SetJustMyCodeState | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine3::SetJustMyCodeState
helpviewer_keywords: IDebugEngine3::SetJustMyCodeState
ms.assetid: 8ec17fbf-df93-424a-b2ed-fd1e5ee51256
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3a411287a369ca5b2beab70a9be7e4dcc2e4947d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugengine3setjustmycodestate"></a>IDebugEngine3::SetJustMyCodeState
Bu yöntem hata ayıklama altyapısı JustMyCode durumu bilgilerini söyler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT SetJustMyCodeState(  
   BOOL           fUpdate,  
   DWORD          dwModules,  
   JMC_CODE_SPEC* rgJMCSpec  
);  
```  
  
```csharp  
int SetJustMyCodeState(  
   int             fUpdate,   
   uint            dwModules,   
   JMC_CODE_SPEC[] rgJMCSpec  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fUpdate`  
 [in] Sıfır olmayan (`TRUE`) geçerli bilgilerini güncelleştirmek için sıfır (`FALSE`) (daha önce ayarlamış yoksayar) tüm bilgileri sıfırlanır.  
  
 `dwModules`  
 [in] Bilgi yapıları sayısı`rgJMCSpec.`  
  
 `rgJMCSpec`  
 [in] Dizi [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md) yapıları kullanın.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde, hata kodunu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 JustMyCode olan yalnızca bir kullanıcıya ait kodda hata ayıklama ve sistem kodu gibi tüm ara kodu yoksayılıyor kavramı — kaynak kodu, sistem kodunu kullanılabilir olsa bile.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)   
 [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md)