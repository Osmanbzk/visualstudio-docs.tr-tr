---
title: "&lt;postActionData&gt; öğesi (Visual Studio'da Office Geliştirme)"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- <postActionData> element
- application manifests [Office development in Visual Studio], <postActionData> element
- postActionData element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 58b085e35971fa557d946f3967af4db81b577fff
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804831"
---
# <a name="ltpostactiondatagt-element-office-development-in-visual-studio"></a>&lt;postActionData&gt; öğesi (Visual Studio'da Office Geliştirme)
  `postActionData` Öğesinin `vstav3` Office çözümleri yüklendikten sonra çalıştırılan bir dağıtım sonrası eylemi ile ilişkili verileri ad alanını belirtir.

## <a name="syntax"></a>Sözdizimi

```xml
<postActionData>
</postActionData>
```

## <a name="elements-and-attributes"></a>Öğeler ve öznitelikler
 `postActionData` Öğe isteğe bağlıdır ve içinde `vstav3` ad alanı. Bir `postActionData` her dağıtım sonrası eylemi için uygulama bildiriminde tanımlanan öğe.

 `postActions` Öğesi özniteliklere sahip değildir.

 `postActions` alt öğe yok.

## <a name="post-deployment-action-example"></a>Dağıtım sonrası eylemi örneği

### <a name="description"></a>Açıklama
 Aşağıdaki kod örneğinde gösterilmiştir `postAction` öğesi kullanılarak dağıtılan bir Office çözümü için uygulama bildiriminde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği, sağlanan daha büyük bir örneğin parçasıdır [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kod

```xml
<vstav3:postActionData>
  data in any format
</vstav3:postActionData>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)
- [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)
