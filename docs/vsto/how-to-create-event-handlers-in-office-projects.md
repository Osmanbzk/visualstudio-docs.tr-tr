---
title: 'Nasıl Yapılır: Office projelerinde olay işleyicileri oluşturma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Basic [Office development in Visual Studio], event handlers
- event handlers [Office development in Visual Studio]
- Visual C# [Office development in Visual Studio], event handlers
- events [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: be56b279750c71ab71f1337f6bc7b2038e1195fe
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53648606"
---
# <a name="how-to-create-event-handlers-in-office-projects"></a>Nasıl Yapılır: Office projelerinde olay işleyicileri oluşturma
  Visual Basic'te olay işleyicileri oluşturmanın birkaç yolu vardır ve C#. Tasarım görünümünde, varsayılan olay işleyicileri denetimleri için denetimi çift tıklayarak oluşturabilir, veya olayları bölmesini kullanarak **özellikleri** herhangi bir olay işleyicileri denetimi oluşturmak için pencere. Ancak, kod Görünümü'nde, bir olay işleyicisi oluşturmak için Tasarım görünümüne geçiş yapmak istemeyebilirsiniz.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-create-an-event-handler-in-visual-basic"></a>Visual Basic'te bir olay işleyicisi oluşturmak için  
  
1.  Gelen **sınıf adı** Kod Düzenleyicisi'nin üst aşağı açılan listesinde, istediğiniz nesneyi seçin için bir olay işleyicisi oluşturun.  
  
    > [!NOTE]  
    >  Olay işleyicileri oluşturmak istiyorsanız `ThisDocument` veya `ThisWorkbook`, seçmelisiniz **(ThisDocument olayları)** veya **(ThisWorkbook olayları)** içinde **sınıf adı**aşağı açılan listesi  
  
2.  Gelen **yöntem adı** açılır listede Kod Düzenleyicisi'nin en üstünde, olayı seçin.  
  
     Visual Studio, olay işleyicisi oluşturur ve yeni oluşturulan olay işleyicisi ekleme noktasını taşır. Olay işleyicisi zaten varsa, ekleme noktasını varolan olay işleyicisine taşır.  
  
### <a name="to-create-an-event-handler-in-c"></a>Bir olay işleyicisi oluşturmak içinC#  
  
1.  Olay temsilcisini oluşturmak **başlangıç** olay sınıfının ardından bir boşluk tam olay adını yazarak ve ardından yazarak **+=** ardından boşluk. Örneğin:  
  
     `this.<object name>.<event name> +=`  
  
2.  Kod satırının sonunda iki kez SEKME tuşuna basın.  
  
     Visual Studio otomatik olarak kod satırının tamamlanır, olay işleyicisi oluşturur ve yeni oluşturulan olay işleyicisi ekleme noktasını taşır.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [İzlenecek yol: NamedRange denetimi olaylarına karşı programlama](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Office çözümleri oluşturun](../vsto/building-office-solutions.md)  
  
  