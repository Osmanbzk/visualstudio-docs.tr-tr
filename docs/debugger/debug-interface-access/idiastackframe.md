---
title: Idiastackframe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackFrame interface
ms.assetid: 486d25b8-a590-41c1-bdb5-faff3ae35632
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30b3ca5d68731fccf874b250741a6e67697539fb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackframe"></a>IDiaStackFrame
Yığın çerçevesi özelliklerini gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaStackFrame : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Bu arabirim tarafından desteklenen yöntemleri şunlardır:  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaStackFrame::get_allocatesBasePointer](../../debugger/debug-interface-access/idiastackframe-get-allocatesbasepointer.md)|Bu adres aralığındaki kod için temel işaretçi ayrılır belirten bir bayrak alır. Bu yöntem kullanım dışıdır.|  
|[Idiastackframe::get_base](../../debugger/debug-interface-access/idiastackframe-get-base.md)|Çerçevenin adresini temel alır.|  
|[Idiastackframe::get_cplusplusexceptionhandling](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)|C++ özel durum işleme geçerli olduğunu belirten bir bayrak alır.|  
|[IDiaStackFrame::get_functionStart](../../debugger/debug-interface-access/idiastackframe-get-functionstart.md)|Blok işlevinin giriş noktası içerdiğini belirten bir bayrak alır.|  
|[Idiastackframe::get_lengthlocals](../../debugger/debug-interface-access/idiastackframe-get-lengthlocals.md)|Yerel değişkenler yığına bayt sayısını alır.|  
|[Idiastackframe::get_lengthparams](../../debugger/debug-interface-access/idiastackframe-get-lengthparams.md)|Yığına parametrelerinin bayt sayısını alır.|  
|[Idiastackframe::get_lengthprolog](../../debugger/debug-interface-access/idiastackframe-get-lengthprolog.md)|Başlangıç kod bloğundaki bayt sayısını alır.|  
|[Idiastackframe::get_lengthsavedregisters](../../debugger/debug-interface-access/idiastackframe-get-lengthsavedregisters.md)|Kaydedilmiş Yazmaçlar yığına bayt sayısını alır.|  
|[Idiastackframe::get_localsbase](../../debugger/debug-interface-access/idiastackframe-get-localsbase.md)|Yerel Adres temel alır.|  
|[Idiastackframe::get_maxstack](../../debugger/debug-interface-access/idiastackframe-get-maxstack.md)|Yığın çerçevesi içinde gönderilen bayt sayısını alır.|  
|[Idiastackframe::get_rawlvarınstancevalue](../../debugger/debug-interface-access/idiastackframe-get-rawlvarinstancevalue.md)|Belirtilen yerel değişkenin değerini ham bayt olarak alır.|  
|[Idiastackframe::get_registervalue](../../debugger/debug-interface-access/idiastackframe-get-registervalue.md)|Belirtilen yazmaç değerini alır.|  
|[Idiastackframe::get_returnaddress](../../debugger/debug-interface-access/idiastackframe-get-returnaddress.md)|Çerçevenin dönüş adresi alır.|  
|[Idiastackframe::get_size](../../debugger/debug-interface-access/idiastackframe-get-size.md)|Çerçevenin bayt boyutunu alır.|  
|[IDiaStackFrame::get_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md)|Sistem özel durum işleme geçerli olduğunu belirten bir bayrak alır.|  
|[Idiastackframe::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)|Çerçeve türünü alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yığın çerçevesi bir işlev çağrısı, yürütme sırasında soyutlamadır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde [Idiaenumstackframes::Next](../../debugger/debug-interface-access/idiaenumstackframes-next.md) yöntemi. Bkz: [Idiaenumstackframes](../../debugger/debug-interface-access/idiaenumstackframes.md) edinme konusunda bir örnek arabirimi `IDiaStackFrame` arabirimi.  
  
## <a name="example"></a>Örnek  
 Bu örnek yığın çerçevesi çeşitli özniteliklerini görüntüler.  
  
```C++  
void PrintStackFrame(IDiaStackFrame* pFrame)  
{  
    if (pFrame != NULL)  
    {  
        ULONGLONG bottom = 0;  
        ULONGLONG top    = 0;  
  
        if (pFrame->get_base(&bottom) == S_OK &&  
            pFrame->get_registerValue( CV_REG_ESP, &top ) == S_OK )  
        {  
             printf("range = 0x%08I64x - 0x%08I64x\n", bottom, top);  
        }  
  
        ULONGLONG returnAddress = 0;  
        if (pFrame->get_returnAddress(&returnAddress) == S_OK)  
        {  
             printf("return address = 0x%08I64x\n", returnAddress);  
        }  
  
        DWORD lengthFrame     = 0;  
        DWORD lengthLocals    = 0;  
        DWORD lengthParams    = 0;  
        DWORD lengthProlog    = 0;  
        DWORD lengthSavedRegs = 0;  
        if (pFrame->get_size(&lengthFrame) == S_OK &&  
            pFrame->get_lengthLocals(&lengthLocals) == S_OK &&  
            pFrame->get_lengthParams(&lengthParams) == S_OK &&  
            pFrame->get_lengthProlog(&lengthProlog) == S_OK &&  
            pFrame->get_lengthSavedRegisters(&lengthSavedRegs) == S_OK)  
        {  
            printf("stack frame size          = 0x%08lx bytes\n", lengthFrame);  
            printf("length of locals          = 0x%08lx bytes\n", lengthLocals);  
            printf("length of parameters      = 0x%08lx bytes\n", lengthParams);  
            printf("length of prolog          = 0x%08lx bytes\n", lengthProlog);  
            printf("length of saved registers = 0x%08lx bytes\n", lengthSavedRegs);  
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
 [Idiaenumstackframes](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [Idiaenumstackframes::Next](../../debugger/debug-interface-access/idiaenumstackframes-next.md)   
 [Idiastackwalkframe](../../debugger/debug-interface-access/idiastackwalkframe.md)