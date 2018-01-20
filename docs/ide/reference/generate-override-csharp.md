---
title: "Bir geçersiz kılma - kod oluşturma (C#) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 3801d8ce60cf87126f8894bf44c77056f996cde1
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="generate-an-override-in-c"></a>Bir geçersiz kılma C# ' ta oluştur #

**Ne:** hemen bir taban sınıftan hangi kılınabilir herhangi bir yöntemini kodunu oluşturmak olanak tanır.

**Ne zaman:** bir temel sınıf yöntemini geçersiz kılın ve imza otomatik olarak oluşturmak istediğiniz.

**Neden:** ancak, bu özellik imza otomatik olarak oluşturur, yöntem imzası kendiniz yazabilirsiniz.

**Nasıl:**

1. Tür **geçersiz kılma** burada geçersiz kılınan yöntem imzası eklemek ister misiniz ve IntelliSense açılır listesinde görünür ve bir boşluk, anahtar sözcük.

   ![IntelliSense geçersiz kıl](media/override-intellisense-cs.png)

1. Fareyle tıklatarak veya ona klavye ve tuşlarına basarak gezinme temel sınıfından geçersiz kılmak istediğiniz yöntemi seçin **Enter**.

   >[!TIP]
   >* Özellik simgesi kullanın ![Özellik simgesi](media/override-property-cs.png) göstermek veya özellikler listesinde gizlemek için.
   >* Yöntem simgesini kullanın ![Yöntem simgesi](media/override-method-cs.png) göstermek veya listede yöntemleri gizlemek için.

1. Seçilen yöntemi veya özelliği geçersiz kılma uygulanması için hazır sınıfa eklenir.

   ![Sonuç geçersiz kıl](media/override-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)