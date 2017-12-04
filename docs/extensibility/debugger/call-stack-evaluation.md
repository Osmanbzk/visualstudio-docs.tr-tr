---
title: "Çağrı yığını değerlendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], call stack evaluation
- call stacks, evaluation
ms.assetid: 373d6b49-0459-4cce-816e-05745a44fe49
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 21626804ae60ca14b360f23acf17b3e336fa600b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="call-stack-evaluation"></a>Çağrı yığını değerlendirme
Kesme modunda çağrı yığınının yığın çerçeveleri görüntüleyebilmek için uygulamanız gereken [EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) yöntemi.  
  
## <a name="methods-for-evaluation"></a>Değerlendirme için yöntemleri  
 Basit hata ayıklama motoru (DE), tek bir yığın çerçevesi olabilir. Kesme modunda yığın çerçevesi incelemek için aşağıdaki yöntemleri uygulamak [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md).  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|Yığın çerçevesi için kod bağlamını alır. Kod bağlamı geçerli yönerge işaretçisi yığın çerçevesinde temsil eder.|  
|[GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|Yığın çerçevesi için belge bağlamını alır. Belge bağlam yığın çerçevesi için kaynak kodundaki geçerli konumunu temsil eder. Bir programı durdurulduğunda kaynak kodunu görüntülemek için gereklidir.|  
  
 Bu yöntemler birkaç bağlamı ile ilgili arabirimler ve yöntemler uygulaması gerektirir. Bu nedenle, uygulamanız gereken [GetDocumentContext](../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) yöntemi ve aşağıdaki yöntemlerden birini [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md).  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|Bir belge bağlamı dosya deyimi aralığını alır.|  
  
 Kod bağlamları numaralandırmak için tüm yöntemleri uygulamak [IEnumDebugCodeContexts2](../../extensibility/debugger/reference/ienumdebugcodecontexts2.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme denetimi ve durum değerlendirme](../../extensibility/debugger/execution-control-and-state-evaluation.md)