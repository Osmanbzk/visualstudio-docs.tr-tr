---
title: Bir veritabanından resimlere denetim bağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- images [Visual Basic], displaying on Windows Forms
- data binding [Windows Forms], pictures
- images [Visual Basic], data binding
- pictures, data binding
- pictures, dragging from Data Sources window
- Data Sources Window, setting controls to display images
- PictureBox control [Windows Forms], data binding
- images [Visual Basic], dragging from Data Sources window
ms.assetid: 9748815e-3556-49e8-86b1-c6aa593c6163
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1e50a3126407c9306e2a1f00a411e08f69c69602
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53647071"
---
# <a name="bind-controls-to-pictures-from-a-database"></a>Bir veritabanından resimlere denetim bağlama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Kullanabileceğiniz **veri kaynakları** görüntü uygulamanızda bir denetimin bir veritabanına bağlamak için penceresi. Örneğin, bir görüntüye bağlayabilirsiniz bir <xref:System.Windows.Controls.Image> WPF uygulamasında veya çok denetleyen bir <xref:System.Windows.Forms.PictureBox> denetimini Windows Forms uygulamasında.  
  
 Bir veritabanı resimleri genellikle bayt dizisi depolanır. Öğeler **veri kaynakları** bayt dizileri türü denetimi gibi depolanmış penceresini ayarlamak **hiçbiri** varsayılan olarak, her şey basit bir yürütülebilir dosyanın bir bayt dizisi bayt dizileri içerebileceğinden büyük bir uygulama. Bir bayt dizisi öğesinde veriye bağlı denetim oluşturmak için **veri kaynakları** bir resmi temsil eden pencere oluşturmak için denetimi seçmesi gerekir.  
  
 Aşağıdaki yordam olduğunu varsayar **veri kaynakları** penceresi görüntüye bağlı bir öğe ile önceden doldurulur.
  
## <a name="bind-a-picture-in-a-database-to-a-control"></a>Bir resmi bir veritabanında bir denetime bağlama  
  
1.  Tasarım yüzeyinde denetime eklemek istediğiniz WPF Tasarımcısı veya Windows Forms Tasarımcısı'nda açık olduğundan emin olun.  
  
2.  İçinde **veri kaynakları** penceresinde istediğiniz tabloyu genişletin veya kendi sütunları veya özelliklerini görüntülemek için nesne.  
  
3.  Sütun veya görüntü verilerinizi içeren bir özellik seçin ve kendi denetimi aşağı açılan listeden aşağıdaki denetimlerden birini seçin:  
  
    -   WPF Tasarımcısı açıksa seçin **görüntü**.  
  
    -   Windows Forms Tasarımcısı açıksa seçin **PictureBox**.  
  
    -   Alternatif olarak, veri bağlamayı destekleyen ve resimleri görüntülemek farklı bir denetimi seçebilirsiniz. Kullanmak istediğiniz denetim kullanılabilir denetimleri listesinde değilse, listeye ekleyin ve ardından bu seçeneği belirleyin. Daha fazla bilgi için [veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da verilere WPF denetimleri bağlama](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)
