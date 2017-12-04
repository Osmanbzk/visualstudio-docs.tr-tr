---
title: PENDING_BP_STATE_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PENDING_BP_STATE_FLAGS
helpviewer_keywords: PENDING_BP_STATE_FLAGS enumeration
ms.assetid: 85522449-3fd8-4da5-b0fe-a43160e0c33b
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c89469cd1b2d41fc0e3258d2875b9e22b7c55747
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="pendingbpstateflags"></a>PENDING_BP_STATE_FLAGS
Bekleyen kesme noktası durumu bayrakları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_PENDING_BP_STATE_FLAGS {   
   PBPSF_NONE        = 0x0000,  
   PBPSF_VIRTUALIZED = 0x0001  
};  
typedef DWORD PENDING_BP_STATE_FLAGS;  
```  
  
```csharp  
public enum enum_PENDING_BP_STATE_FLAGS {   
   PBPSF_NONE        = 0x0000,  
   PBPSF_VIRTUALIZED = 0x0001  
};  
```  
  
## <a name="members"></a>Üyeler  
 PBPSF_NONE  
 Yer tutucu.  
  
 PBPSF_VIRTUALIZED  
 Sanallaştırılmış bir kesme noktası, yeni kod her yüklenişinde bağlı olan bir belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 İçin kullanılan `flags` üyesi [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md) yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md)