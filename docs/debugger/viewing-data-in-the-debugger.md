---
title: Hata ayıklayıcıda verilerin özel görünümlerini oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/20/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], inspecting programs
- debugger, viewing data
ms.assetid: 13e1105f-f987-402e-9108-ec6ac12be042
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c750e9e3152ae5efdf2e2ecf09034b6928fe9fa7
ms.sourcegitcommit: 35bebf794f528d73d82602e096fd97d7b8f82c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53561859"
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcıda verilerin özel görünümlerini oluşturma
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] İncelemek ve programınızın durumunu değiştirmek için hata ayıklayıcı birçok araç sağlar. Bu araçlar işlevi yalnızca kesme modunda çoğunu.

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>Değişken pencereler ve DataTips verilerin özel görünümlerini oluşturma
 Çoğu [windows hata ayıklayıcı](../debugger/debugger-windows.md), gibi **Otolar** ve **izleme** windows, değişkenleri inceleyebilir izin verir. Nasıl yerel türler, yönetilen nesneleri özelleştirebilirsiniz ve hata ayıklayıcı değişken pencerelerinde ve kendi türlerinizi gösterilen [DataTips](../debugger/view-data-values-in-data-tips-in-the-code-editor.md). Daha fazla bilgi için [yerel nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-native-objects.md) ve [yönetilen nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-dot-managed-objects.md).
  
## <a name="create-custom-visualizers"></a>Özel görselleştiriciler oluşturma  
 Görselleştiriciler, bir nesnenin veya değişkenin içeriklerini anlamlı bir şekilde görüntülemek etkinleştirin. Visual Studio hata ayıklayıcısının Görselleştirici Büyüteç'i kullanarak açabilirsiniz farklı windows başvuruyor ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "Görselleştirici simgesi") simgesi. Örneğin, nasıl bir HTML dizesi yorumlanır ve bir tarayıcıda görüntülenen HTML görselleştiriciyi gösterir. Görselleştiriciler ipuçlarından erişebileceğiniz **izleme** penceresinde **Otolar** penceresinde ve **Yereller** penceresi. **QuickWatch** iletişim kutusu Görselleştirici de sağlar. Daha fazla bilgi için [özel görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md).
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Hata ayıklayıcıya ilk bakış](../debugger/debugger-feature-tour.md) [komut penceresi](../ide/reference/command-window.md)   
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)