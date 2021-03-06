---
title: DEBUG_REASON | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_REASON
helpviewer_keywords:
- DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3f3fccdd43b7d26a5bb2dcc5799d77afff6614d1
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49868371"
---
# <a name="debugreason"></a>DEBUG_REASON
Hata ayıklama için işlem neden başlatıldı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
typedef DWORD DEBUG_REASON;  
```  
  
```csharp  
public enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 DEBUG_REASON_ERROR  
 Belirli olmayan bir hata oluştu (yok, diğer uygun neden olduğunda bu bir varsayılan koşul olarak kullanılır).  
  
 DEBUG_REASON_USER_LAUNCHED  
 İşlem, kullanıcının isteğiyle başlatıldı.  
  
 DEBUG_REASON_USER_ATTACHED  
 Zaten çalışan işlemi kullanıcı tarafından eklendi.  
  
 DEBUG_REASON_AUTO_ATTACHED  
 Başlatıldığında işlemi otomatik olarak depolamaya bağlanmıştır.  
  
 DEBUG_REASON_CAUSALITY  
 İşlem şu nedenle başlatıldı bir *Just-ın-Time* (JIT) hata ayıklama olay.  
  
## <a name="remarks"></a>Açıklamalar  
 Öğesinden döndürülen [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)