---
title: "Nasıl yapılır: çalışma sayfalarını program aracılığıyla yazdırma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- printing [Office development in Visual Studio], worksheets
- worksheets, printing
- print preview, worksheets
ms.assetid: 312bfcd7-0a74-421c-b42e-df71a06b7bdf
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 030580d2db7490a7ce806cca86477659a0b00267
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-print-worksheets"></a>Nasıl yapılır: Çalışma Sayfalarını Program Aracılığıyla Yazdırma
  Çalışma kitabındaki tüm çalışma sayfası yazdırabilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="printing-a-worksheet-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde çalışma yazdırma  
  
#### <a name="to-print-a-worksheet"></a>Çalışma yazdırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintOut%2A> yöntemi `Sheet1`, iki kopya isteyin ve belgeyi yazdırma önce önizleyin.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#22)]
     [!code-vb[Trin_VstcoreExcelAutomation#22](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#22)]  
  
 <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> Yöntemi, belirtilen nesneyi görüntülemek tanır **Baskı Önizleme** penceresi. Aşağıdaki kod, varsayar bir <xref:Microsoft.Office.Tools.Excel.Worksheet> konak öğesi adlı `Sheet1`.  
  
#### <a name="to-preview-a-page-before-printing"></a>Bir sayfa yazdırma önce önizlemek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Worksheet.PrintPreview%2A> çalışma sayfasının yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#23)]
     [!code-vb[Trin_VstcoreExcelAutomation#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#23)]  
  
## <a name="printing-a-worksheet-in-a-vsto-add-in"></a>Bir VSTO eklentisinin çalışma yazdırma  
  
#### <a name="to-print-a-worksheet"></a>Çalışma yazdırmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintOut%2A> yöntemi etkin çalışma sayfasının iki kopya isteyin ve belgeyi yazdırma önce önizleyin.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#14)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#14](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#14)]  
  
 <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> Yöntemi, belirtilen nesneyi görüntülemek tanır **Baskı Önizleme** penceresi.  
  
#### <a name="to-preview-a-page-before-printing"></a>Bir sayfa yazdırma önce önizlemek için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Worksheet.PrintPreview%2A> etkin çalışma sayfasının yöntemi.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#15)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#15](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#15)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla çalışma sayfalarında yazım denetimi](../vsto/how-to-programmatically-check-spelling-in-worksheets.md)   
 [Çalışma sayfası konak öğesi](../vsto/worksheet-host-item.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  