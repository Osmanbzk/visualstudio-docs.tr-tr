---
title: "Idiastackframe::get_rawlvarınstancevalue | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5559ad617afbb2ae4a65ecbf399f7f79d93ae1c7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
Bu yöntem, ham bayt olarak belirtilen yerel değişkenin değerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pInstance`  
 [in] Bir `IDiaLVarInstance` değerini almak için yerel değişken örneğini temsil eden nesne.  
  
 `cbDataMax`  
 [in] Tarafından arabellekteki bayt sayısını işaret için `pbData`. Bu en fazla 8 bayt olabilir (`sizeof(ULONGLONG)`).  
  
 `pcbData`  
 [out] Arabellekte depolanan bayt sayısını döndürür.  
  
 `pbData`  
 [out] Veri ile doldurulacak arabellek. Bu olamaz `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiastackframe](../../debugger/debug-interface-access/idiastackframe.md)