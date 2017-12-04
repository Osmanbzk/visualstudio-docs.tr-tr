---
title: "Birlikte çalışma etkinlik Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Interop.UI
ms.assetid: 800a3403-ba86-41c4-8de1-c4fee9703eb1
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3adc99e0a09d2d82049dcbe816f14b24ab48a55d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="interop-activity-designer"></a>Birlikte çalışma etkinlik Tasarımcısı
**Birlikte çalışabilirliği** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.Interop> etkinlik.  
  
## <a name="the-interop-activity"></a>Birlikte çalışma etkinliği  
 <xref:System.Activities.Statements.Interop> Etkinlik öğesinden türetilen türler yürütülmesi yönetir <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName> bir iş akışındaki.  
  
### <a name="using-the-interop-activity-designer"></a>Birlikte çalışma etkinlik Tasarımcısı'nı kullanarak  
 **Birlikte çalışabilirliği** etkinlik Tasarımcısı bulunabilir **geçiş** kategorisini **araç**, hangi tıklayarak erişildiğinde **araç**sekmesini (Alternatif olarak, seçin **araç** gelen **Görünüm** menüsü veya CTRL + ALT + X.)  
  
 [Geçiş](../workflow-designer/migration-activity-designers.md) içeren kategori <xref:System.Activities.Statements.Interop> etkinliği yalnızca gösterir **araç** projenizi tam hedefliyorsa [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)].  
  
 C# projeleri için tam kullanmak için projeyi yeniden hedefleyebilirsiniz [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] projeye sağ tıklanarak **Çözüm Gezgini** ve seçerek **özellikleri**. Üzerinde **uygulama** sekmesine **NET Framework 4** seçeneğini **hedef framework**. Seçin **Evet** düğmesini **hedef çerçevesini değiştirebilir** bu değişikliği onaylamanızı isteyen görüntüler iletişim.  
  
 VB projeleri için tam kullanmak için projeyi yeniden hedefleyebilirsiniz [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] nde projeye sağ tıklanarak **Çözüm Gezgini** ve seçerek **özellikleri**. Üzerinde **derleme** sekmesini tıklatın, **Gelişmiş derleme seçenekleri** düğmesi. Seçin **.Net Framework 4** gelen **hedef framework listesi** ve ardından **Tamam**. Tıklatın **Evet** düğmesini **hedef çerçevesini değiştirebilir** bu değişikliği onaylamanızı isteyen görüntüler iletişim.  
  
 **Birlikte çalışabilirliği** gelen etkinlik Tasarımcısı sürüklenebilir **araç** ve oturum bırakılan [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, gibi olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu oluşturur bir <xref:System.Activities.Statements.Interop> varsayılan etkinlik **DisplayName** , birlikte çalışabilirlik. <xref:System.Activities.Activity.DisplayName%2A> Üstbilgisinde düzenlenebilir **birlikte çalışabilirliği** etkinlik Tasarımcısı veya **DisplayName** ve özellik ızgarasının kutusu.  
  
 Tıklatın **göz atmak için tıklatın...**  metinde **ActivityType** kutusu, üzerinde **birlikte çalışabilirliği** etkinlik Tasarımcısı veya ortaya çıkarmak için özellik kılavuzunda **göz atma ve seçme bir .net türü** iletişim kutusu. İş akışı 3.0 veya 3.5 iş akışı etkinlikleri türleri yalnızca gösterilir (öğesinden türetilmiş yalnızca tür <xref:System.Workflow.ComponentModel.Activity>). [!INCLUDE[crabout](../test/includes/crabout_md.md)]bir tür belirtmek için bu kutuyu kullanarak bkz [göz atın ve bir .NET türünü seç iletişim kutusu](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box.md) konu.  
  
### <a name="the-interop-properties"></a>Birlikte çalışabilirlik özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.Interop> özellikleri ve bunların Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikleri özellik kılavuzu veya üzerinde düzenlenebilir [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] yüzeyini.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.Interop> etkinlik. Birlikte çalışma varsayılandır. Görünen ad kesinlikle gerekli olmamakla birlikte, bir görünen ad kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.Interop.ActivityType%2A>|Doğru|İçinde etkinlik türünü belirtir <xref:System.Activities.Statements.Interop> etkinlik. Belirtilen bu tür öğesinden türetilmelidir <xref:System.Workflow.ComponentModel.Activity>.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Geçiş](../workflow-designer/migration-activity-designers.md)