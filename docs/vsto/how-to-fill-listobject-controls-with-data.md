---
title: 'Nasıl Yapılır: ListObject denetimlerini veri ile doldurabilirsiniz.'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- disconnecting from data sources
- ListObject control, disconnecting from a data source
- ListObject control, filling with data
- data [Office development in Visual Studio], adding to worksheets
- data binding, ListObject controls
- worksheets, populating with data
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: cafaaebeea2a6fd5d4c750e89e90747da28b254d
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53646695"
---
# <a name="how-to-fill-listobject-controls-with-data"></a>Nasıl Yapılır: ListObject denetimlerini veri ile doldurabilirsiniz.
  Veri bağlama, hızlı bir şekilde belgenize veri eklemek için bir yol olarak kullanabilirsiniz. Verileri Liste nesnesine bağladıktan sonra verileri görüntüler ancak artık veri kaynağına bağlı olduğu için liste nesnesi kesebilirsiniz.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz. [nasıl yaparım? Bir SharePoint listesine bağlı Excel'de bir liste oluşturur? ](http://go.microsoft.com/fwlink/?LinkID=130263).  
  
### <a name="to-bind-data-to-a-listobject-control"></a>ListObject denetimine veri bağlama için  
  
1.  Oluşturma bir <xref:System.Data.DataTable> sınıf düzeyinde.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#20](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet4.cs#20)]
     [!code-vb[Trin_VstcoreHostControlsExcel#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet4.vb#20)]  
  
2.  Örnek sütunlar ekleyip verileri `Startup` olay işleyicisine `Sheet1` sınıfı (belge düzeyi projede) veya `ThisAddIn` sınıfı (uygulama düzeyi projede).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#21](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet4.cs#21)]
     [!code-vb[Trin_VstcoreHostControlsExcel#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet4.vb#21)]  
  
3.  Çağrı <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> yöntemi ve sütun adları göründükleri sırayla geçirin. Liste nesnesinde sütunların sırasını içinde görünen sırası farklı olabilir <xref:System.Data.DataTable>.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#22](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet4.cs#22)]
     [!code-vb[Trin_VstcoreHostControlsExcel#22](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet4.vb#22)]  
  
### <a name="to-disconnect-the-listobject-control-from-the-data-source"></a>ListObject denetimi veri kaynağından bağlantısını kesmek için  
  
1.  Çağrı <xref:Microsoft.Office.Tools.Excel.ListObject.Disconnect%2A> yöntemi `List1`.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#23](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet4.cs#23)]
     [!code-vb[Trin_VstcoreHostControlsExcel#23](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet4.vb#23)]  
  
## <a name="compile-the-code"></a>Kod derleme  
 Bu kod örneği, mevcut bir varsayar <xref:Microsoft.Office.Tools.Excel.ListObject> adlı `list1` bu kodu göründüğü çalışma.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında genişletme](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [Office belgelerine çalışma zamanında denetimler ekleme](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Nasıl yapılır: ListObject sütunlarıyla verileri eşleme](../vsto/how-to-map-listobject-columns-to-data.md)   
 [Genişletilmiş nesneleri kullanarak Excel'i otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md)   
 [ListObject denetimi](../vsto/listobject-control.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Nasıl yapılır: Çalışma sayfalarını veritabanı verileriyle doldurma](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Nasıl yapılır: Belgeleri hizmet verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-services.md)  
  
  