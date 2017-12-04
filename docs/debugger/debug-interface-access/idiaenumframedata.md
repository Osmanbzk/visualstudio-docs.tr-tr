---
title: Idiaenumframedata | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumFrameData interface
ms.assetid: 2ca7fd5a-b2fa-4b3a-9492-0263eafc435b
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1850fd8eab4151dfb24bdc30dafe2e110406c37a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumframedata"></a>IDiaEnumFrameData
Veri kaynağında bulunan çeşitli çerçeve veri öğeleri numaralandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaEnumFrameData : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaEnumFrameData`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiaenumframedata::get__newenum](../../debugger/debug-interface-access/idiaenumframedata-get-newenum.md)|Alır `IEnumVARIANT Interface` bu Sıralayıcı sürümü.|  
|[Idiaenumframedata::get_Count](../../debugger/debug-interface-access/idiaenumframedata-get-count.md)|Çerçeve veri öğe sayısını alır.|  
|[Idiaenumframedata::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md)|Bir çerçeve veri öğesi, bir dizin yoluyla alır.|  
|[Idiaenumframedata::Next](../../debugger/debug-interface-access/idiaenumframedata-next.md)|Çerçeve veri öğeleri numaralandırması dizisinde belirtilen sayısını alır.|  
|[Idiaenumframedata::Skip](../../debugger/debug-interface-access/idiaenumframedata-skip.md)|Çerçeve veri öğeleri bir numaralandırma dizisinde belirtilen sayıda atlar.|  
|[Idiaenumframedata::reset](../../debugger/debug-interface-access/idiaenumframedata-reset.md)|Bir numaralandırma sırasını başlangıç durumuna sıfırlar.|  
|[Idiaenumframedata::Clone](../../debugger/debug-interface-access/idiaenumframedata-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
|[Idiaenumframedata::framebyrva](../../debugger/debug-interface-access/idiaenumframedata-framebyrva.md)|Bir çerçeve göreli sanal adresiyle (RAV) döndürür.|  
|[Idiaenumframedata::framebyva](../../debugger/debug-interface-access/idiaenumframedata-framebyva.md)|Bir çerçeve sanal adresiyle (VA) döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirimden elde [Idiasession::getenumtables](../../debugger/debug-interface-access/idiasession-getenumtables.md) yöntemi. Ayrıntılar için bkz.  
  
## <a name="example"></a>Örnek  
 Bu örnek nasıl alınacağını gösterir ( `GetEnumFrameData` işlevi) ve kullanma ( `ShowFrameData` işlevi) `IDiaEnumFrameData` arabirimi. Bkz: [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md) ilişkin bir örnek arabirimi `PrintFrameData` işlevi.  
  
```C++  
  
      IDiaEnumFrameData* GetEnumFrameData(IDiaSession *pSession)  
{  
    IDiaEnumFrameData* pUnknown    = NULL;  
    REFIID             iid         = __uuidof(IDiaEnumFrameData);  
    IDiaEnumTables*    pEnumTables = NULL;  
    IDiaTable*         pTable      = NULL;  
    ULONG              celt        = 0;  
  
    if (pSession->getEnumTables(&pEnumTables) != S_OK)  
    {  
        wprintf(L"ERROR - GetTable() getEnumTables\n");  
        return NULL;  
    }  
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)  
    {  
        // There is only one table that matches the given iid  
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);  
        pTable->Release();  
        if (hr == S_OK)  
        {  
            break;  
        }  
    }  
    pEnumTables->Release();  
    return pUnknown;  
}  
  
void ShowFrameData(IDiaSession *pSession)  
{  
    IDiaEnumFrameData* pEnumFrameData = GetEnumFrameData(pSession);;  
  
    if (pEnumFrameData != NULL)  
    {  
        IDiaFrameData* pFrameData;  
        ULONG celt = 0;  
  
        while(pEnumFrameData->Next(1, &pFrameData, &celt) == S_OK &&  
              celt == 1)  
        {  
            PrintFrameData(pFrameData);  
            pFrameData->Release();  
        }  
        pEnumFrameData->Release();   
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** Dia2.h  
  
 **Kitaplığı:** diaguids.lib  
  
 **DLL:** msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession::getenumtables](../../debugger/debug-interface-access/idiasession-getenumtables.md)   
 [Idiaframedata](../../debugger/debug-interface-access/idiaframedata.md)