---
title: IDebugDisassemblyStream2::Seek | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDisassemblyStream2::Seek
helpviewer_keywords:
- IDebugDisassemblyStream2::Seek
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 375ff5c08c481061d217fbb0b3a4fac38d1e74c5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49896646"
---
# <a name="idebugdisassemblystream2seek"></a>IDebugDisassemblyStream2::Seek
Ayrıştırılmış kod akış yönergeler belirtilen konuma göre verilen sayıda okuma imleci taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT Seek(   
   SEEK_START          dwSeekStart,  
   IDebugCodeContext2* pCodeContext,  
   UINT64              uCodeLocationId,  
   INT64               iInstructions  
);  
```  
  
```csharp  
int Seek(   
   enum_SEEK_START    dwSeekStart,  
   IDebugCodeContext2 pCodeContext,  
   ulong              uCodeLocationId,  
   long               iInstructions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwSeekStart`  
 [in] Bir değer [SEEK_START](../../../extensibility/debugger/reference/seek-start.md) arama işlemi başlatmak için göreceli konumun belirten sabit listesi.  
  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) arama işlemini göreli olduğu kod bağlamı temsil eden nesne. Bu parametre yalnızca, kullanılan `dwSeekStart`  =  `SEEK_START_CODECONTEXT`; Aksi takdirde, bu parametre yoksayılır ve null değeri olabilir.  
  
 `uCodeLocationId`  
 [in] Arama işlemini göreli olduğu kod konum tanımlayıcısı. Bu parametre, kullanılan `dwSeekStart`  =  `SEEK_START_CODELOCID`; Aksi takdirde, bu parametre yoksayılır ve 0 olarak ayarlayın. İçin Açıklamalar bölümüne bakın [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) kod konum tanımlayıcısı bir açıklaması için yöntemi.  
  
 `iInstructions`  
 [in] Belirtilen konumuna göre taşımak için yönergeler sayısını `dwSeekStart`. Bu değer, geriye için negatif olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`. Döndürür `S_FALSE` arama konumu kullanılabilir yönergeleri listenin ötesinde bir nokta ise. Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Listeye başlangıcından önce bir konumu arama ise okuma konumuna listedeki ilk yönerge ayarlanır. Bkz: listenin sonunda bir konuma ise, okuma konumuna son yönerge listesinde ayarlayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [SEEK_START](../../../extensibility/debugger/reference/seek-start.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)