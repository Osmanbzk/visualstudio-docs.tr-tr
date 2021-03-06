---
title: "'This' nesnesine atanamaz | Microsoft Docs"
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5000
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f47778075b0395e4f0791d8f485188d40fab87a4
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/27/2018
ms.locfileid: "53802598"
---
# <a name="cannot-assign-to-this"></a>'this' nesnesine atanamaz
Bir değer atayın çalışıldı **bu**. **Bu** olduğu bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] anahtar sözcüğü ya da ifade eder:

- bir yöntem yürütülmekte nesnesi

- Genel nesne geçerli bir yöntem (veya başka bir nesneye yöntemi ait değil ise).

Bir yöntem bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneyle çağrılan işlev. Bir yöntem içinde **bu** anahtar sözcüğü yöntemi aracılığıyla çağrıldığı nesneye bir başvurudur (ile sınıfın Oluşturucusu çağrılarak oluşturulan nesne olmasını olur **yeni** işleci).

Bir yöntem içinde kullanabilirsiniz **bu** geçerli nesne, ancak sizin için yeni bir değere atanamaz **bu**.

## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Atama çalışmayın **bu**. Bir özellik veya yöntem örneklenmiş bir nesnenin erişmek için nokta işlecini kullanın (örneğin, **circle.radius**).

  > [!NOTE]
  > Örneğin bir kullanıcı tarafından oluşturulan değişken adı **bu**; bu bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ayrılmış sözcük.

## <a name="see-also"></a>Ayrıca Bkz.

- [this Deyimi](../../javascript/reference/this-statement-javascript.md)
- [Komut Dosyalarınızda Sorun Giderme](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)