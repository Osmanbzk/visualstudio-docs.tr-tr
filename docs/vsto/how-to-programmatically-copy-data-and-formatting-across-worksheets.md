---
title: "Nasıl yapılır: program aracılığıyla veri ve biçimlendirme çalışma sayfaları arasında kopyalama | Microsoft Docs"
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
- worksheets, copying data
- formatting [Office development in Visual Studio]
- data [Office development in Visual Studio], copying across worksheets
- copying data, Office development in Visual Studio
ms.assetid: eed7dbaf-bdb5-4330-ba2e-5f3d50817eca
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 065e9b7dd30e2d91f09a4e23aec1880a50521304
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-copy-data-and-formatting-across-worksheets"></a>Nasıl yapılır: Çalışma Sayfaları Arasında Program Aracılığıyla Veri ve Biçimlendirme Kopyalama
  Verileri bir sayfada bir aralıktan çalışma kitabındaki tüm diğer sayfalarını kullanarak kopyalayabilirsiniz <xref:Microsoft.Office.Interop.Excel.Worksheets.FillAcrossSheets%2A> yöntemi. Bir aralık belirleyin ve verileri, biçimlendirme veya her ikisi de kopyalamak isteyip istemediğinizi.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>Örnek  
 [!code-csharp[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#44)]
 [!code-vb[Trin_VstcoreExcelAutomation#44](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#44)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnek, adlandırılmış bir aralık gerektirir `rangeData` çalışma sayfasında.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma sayfaları ile çalışma](../vsto/working-with-worksheets.md)   
 [Nasıl yapılır: program aracılığıyla yeni çalışma sayfaları çalışma kitaplarına ekleme](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Nasıl yapılır: program aracılığıyla seçili hücreler içeren çalışma sayfalarındaki satırlarda biçimlendirmeyi değiştirme](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md)   
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)  
  
  