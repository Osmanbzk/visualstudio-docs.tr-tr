---
title: Idiasegment | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSegment interface
ms.assetid: 384ae0e1-077e-4d4f-98de-ac43c32c882f
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12bc8e73457c1afc4b1799549ad43974d5771252
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasegment"></a>IDiaSegment
Adres alanı kesimleri bölüm numarası verilerini eşleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaSegment : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaSegment`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiasegment::get_frame](../../debugger/debug-interface-access/idiasegment-get-frame.md)|Segment numarasını alır.|  
|[Idiasegment::get_offset](../../debugger/debug-interface-access/idiasegment-get-offset.md)|Bölüm başladığı Segment uzaklığı alır.|  
|[Idiasegment::get_length](../../debugger/debug-interface-access/idiasegment-get-length.md)|Kesimdeki bayt sayısını alır.|  
|[Idiasegment::get_read](../../debugger/debug-interface-access/idiasegment-get-read.md)|Segment okunur olup olmadığını belirten bir bayrak alır.|  
|[Idiasegment::get_write](../../debugger/debug-interface-access/idiasegment-get-write.md)|Kesim değiştirilebilir olup olmadığını gösteren bir bayrak alır.|  
|[Idiasegment::get_execute](../../debugger/debug-interface-access/idiasegment-get-execute.md)|Kesim yürütülebilir olup olmadığını belirten bir bayrak alır.|  
|[Idiasegment::get_addresssection](../../debugger/debug-interface-access/idiasegment-get-addresssection.md)|Bu kesimin eşlemeleri bölüm numarası alır.|  
|[Idiasegment::get_relativevirtualaddress](../../debugger/debug-interface-access/idiasegment-get-relativevirtualaddress.md)|Bölüm başlangıcının göreli sanal adres (RAV) alır.|  
|[Idiasegment::get_virtualaddress](../../debugger/debug-interface-access/idiasegment-get-virtualaddress.md)|Bölüm başına sanal adres (VA) alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 DIA SDK zaten çevirileri bölüm uzaklığı göreli sanal adreslerine gerçekleştirdiğinden, uygulamaların çoğu değil olun bölüm eşlemesi bilgileri kullanın.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde [Idiaenumsegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md) veya [Idiaenumsegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md) yöntemleri. Ayrıntılar için bkz.  
  
## <a name="example"></a>Örnek  
 Bu işlev, tablo ve en yakın simgesi tüm parçaları adresini görüntüler.  
  
```C++  
void ShowSegments(IDiaTable *pTable, IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSegments> pSegments;  
    if ( SUCCEEDED( pTable->QueryInterface(  
                                _uuidof( IDiaEnumSegments ),  
                               (void**)&pSegments )  
                  )  
       )  
    {  
        CComPtr<IDiaSegment> pSegment;  
        while ( SUCCEEDED( hr = pSegments->Next( 1, &pSegment, &celt ) ) &&  
                celt == 1 )  
        {  
            DWORD rva;  
            DWORD seg;  
  
            pSegment->get_addressSection( &seg );  
            if ( pSegment->get_relativeVirtualAddress( &rva ) == S_OK )  
            {  
                printf( "Segment %i addr: 0x%.8X\n", seg, rva );  
                pSegment = NULL;  
  
                CComPtr<IDiaSymbol> pSym;  
                if ( psession->findSymbolByRVA( rva, SymTagNull, &pSym ) == S_OK )  
                {  
                    CDiaBSTR name;  
                    DWORD    tag;  
  
                    pSym->get_symTag( &tag );  
                    pSym->get_name( &name );  
                    printf( "\tClosest symbol: %ws (%ws)\n",  
                            name != NULL ? name : L"",  
                            szTags[ tag ] );  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumsegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)   
 [Idiaenumsegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md)