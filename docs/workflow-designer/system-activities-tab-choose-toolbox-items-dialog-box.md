---
title: "System.Activities sekmesini seçin araç kutusu öğelerini iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VS.CHOOSEITEMS.SYSTEM.ACTIVITIES_COMPONENTS
- VS.CHOOSEITEMS.SYSTEM.ACTIVITIES COMPONENTS
ms.assetid: cef390cd-eeda-42e6-9d2e-18c8325a4f06
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc005e282e7581aa2af5cba7da3a23040bf9d8b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="systemactivities-tab-choose-toolbox-items-dialog-box"></a>System.Activities sekmesini seçin araç kutusu öğelerini iletişim kutusu
Bu sekme, **araç kutusu öğelerini Seç** iletişim kutusu görüntüler listesini [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] etkinlikleri, şablonları ve öğeler için kullanılabilir. Bu listeyi görüntülemek için seçin **araç kutusu öğelerini Seç** gelen **Araçları** menü veya sağ tıklanarak **araç** ve seçerek **öğeleri Seç**görüntülemek için **araç kutusu öğelerini Seç** iletişim kutusunu ve ardından kendi **System.Activities** sekmesi. Kutudan çıktığında, liste System.Activities, System.ServiceModel.Activities ve System.Activities.Core.Presentation derlemelerden iş akışı etkinlikleri içerir. Ancak, yalnızca sistem tarafından sağlanan gösterilen etkinlikleri ve görüntülenen diğer derlemeler üzerinden eklenen etkinlikler **araç** varsayılan olarak işaretli. En son eklenen etkinlikler otomatik olarak denetlenir ve görüntülenmesini **araç** tıkladığınızda **Tamam** iletişim kutusunda. Bu öğeler ayrıca görünür **araç** etkinlik/öğesi/şablonu bulunduğu ad alanı için karşılık gelen yeni bir kategori altında.  
  
> [!WARNING]
>  Tüm iş akışı etkinlikleri içermeyen bir derlemeyi eklemeyi denediğinizde derleme hiçbir etkinlik yok açıklayan hata iletişim kutusu görüntülenir.  
  
 Bu iletişim kutusu proje belirsiz olduğu ve bu nedenle **System.Activities** sekmesinde devam tek başına XAML ya da bir iş akışı olmayan proje türü görünmesini sağlar.  
  
 Filtreleme, her bir sekmede yapılır. Bu iş akışı etkinlikleri eklemek mümkün olmadığı gelir **.NET bileşeni** sekmesi. Aracılığıyla eklenecek sahip oldukları **System.Activities** kendisini sekmesinde.  
  
 Tüm öğeleri görmek istemiyorsanız onay kutusunu temizleyin **araç** bu iletişim kutusundan sekmesi, veya alternatif olarak, bunu kullanarak yapabilirsiniz **silmek** bağlam menüsü seçeneğini **araç** ve XML'deki bir derlemeyi başvuran öğesinden kaldırmaz **araç**.  
  
 Etkinlik Tasarımcısı üzerinde bırakarak başlatmasını başvurulan derlemelerin liste öğesine otomatik olarak içeren derlemenin ekler. Etkinlik derleme C başvuruyorsa, ayrıca, C başvurulan derleme listesi eklemez. Derleme C GAC veya b etkinlik olarak aynı dizinde olması gerekir Tek başına durumda derlemesi GAC veya VS araştırma yollarına olması gerekir. Ancak bundan sonra sürükleyip bırakabilirsiniz etkinliği iş akışı Tasarımcısı yüzey üzerinde.  
  
 **Araç kutusu** ayarları varsayılan olarak kullanıcı seçenekleri kaydedileceği böylece zaman, bir sonraki açışınızda, **araç**, iş akışı etkinlikleri özelleştirilmiş listesini görüntüler. Bu bir yan etkisi olduğundan, bu, belirli bir etki alanı öğelerinizi eklediyseniz **araç** aracılığıyla **araç kutusu öğelerini Seç** iletişim kutusu, yine de devam, çalışırken bu öğeleri görmek bir De iş akışı konsol uygulaması. Bunları görmek istemiyorsanız, sonra bağlam menüsünü kullanarak bunları silin veya aralarında işaretini **araç kutusu öğelerini Seç** daha önce belirtildiği gibi iletişim kutusu.  
  
 Sütunları bu iletişim kutusunda aşağıdaki bilgileri içerir:  
  
 Ad  
 Şu anda yerel makinenizde kayıtlı iş akışı etkinlikleri adlarını listeler.  
  
 Ad Alanı  
 Etkinlik yapısını tanımlar .NET Framework sınıf kitaplığı ad hiyerarşi gösterir.  
  
 Derleme adı  
 Etkinliği içeren .NET Framework derlemesinin sürümü ve adını görüntüler.  
  
 Dizin  
 İş akışı etkinlikleri içeren .NET Framework derlemesinin konumunu görüntüler. Genel Derleme Önbelleği tüm derlemeler için varsayılan konumdur.  
  
 Listelenen bileşenler sıralamak için sütun başlığını seçin.