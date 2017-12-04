---
title: "Nasıl yapılır: program aracılığıyla çalışma kitaplarını kapatma | Microsoft Docs"
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
- workbooks, closing
- Excel [Office development in Visual Studio], closing workbooks
ms.assetid: 50709caf-2ad8-4843-987c-9a34c8c1e4fe
caps.latest.revision: "52"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2a8d8a11f8fb27c1e5e9d02e939d89f0b7da96fa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-close-workbooks"></a>Nasıl yapılır: Çalışma Kitaplarını Program Aracılığıyla Kapatma
  Etkin çalışma kitabının kapatabilir veya kapatmak için çalışma kitabını belirtebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="closing-the-active-workbook"></a>Etkin çalışma kitabının kapatma  
 Etkin çalışma kitabının kapatmak için iki yordam vardır: biri belge düzeyi özelleştirmeleri ve biri VSTO eklentileri için.  
  
#### <a name="to-close-the-active-workbook-in-a-document-level-customization"></a>Belge düzeyi özelleştirmelerinde etkin çalışma kitabını kapatmak için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.Workbook.Close%2A> yöntemi özelleştirme ile ilişkili çalışma kitabını kapatın. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `Sheet1` Excel için belge düzeyi projede sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#3)]  
  
#### <a name="to-close-the-active-workbook-in-a-vsto-add-in"></a>Etkin çalışma kitabındaki VSTO eklenti kapatmak için  
  
1.  Çağrı <xref:Microsoft.Office.Interop.Excel._Workbook.Close%2A> yöntemi etkin çalışma kitabının kapatın. Aşağıdaki kod örneğini kullanmak için bunu çalıştırabilir `ThisAddIn` Excel için VSTO eklenti projesindeki sınıfı.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="closing-a-workbook-that-you-specify-by-name"></a>Belirttiğiniz bir çalışma kitabını ada göre kapatma  
 Adına göre belirttiğiniz bir çalışma kitabını kapatmanın yol VSTO eklentileri ve belge düzeyi özelleştirmeleri ile aynıdır.  
  
#### <a name="to-close-a-workbook-that-you-specify-by-name"></a>Ada göre belirttiğiniz bir çalışma kitabını kapatmak için  
  
1.  Bağımsız değişken olarak çalışma kitabının adını belirtin <xref:Microsoft.Office.Interop.Excel.Workbooks> koleksiyonu. Aşağıdaki kod örneği, bir çalışma kitabı adlı varsayar **NewWorkbook** Excel'de açıktır.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma kitaplarıyla çalışma](../vsto/working-with-workbooks.md)   
 [Nasıl yapılır: çalışma kitaplarını program aracılığıyla kaydetme](../vsto/how-to-programmatically-save-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla çalışma kitaplarını açma](../vsto/how-to-programmatically-open-workbooks.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)   
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)  
  
  