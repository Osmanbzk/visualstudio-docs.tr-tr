---
title: Derleme eylemleri
description: Bu makalede, C# projeleri için kullanılabilecek çeşitli yapı eylemleri açıklanır.
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: a5b1175caf0ac7f6654fbe20b5300327679eccbc
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51294298"
---
# <a name="build-actions"></a>Derleme eylemleri

Visual Studio'da tüm dosyaları Mac projesi için derleme eylemine sahip. Bu dosya için bir yapı sırasında ne denetler. Bu davranış, herhangi bir dosyaya sağ tıklayıp göz ayarlanabilir **derleme eylemi**, aşağıda gösterildiği gibi:

![Çözüm Gezgini'nden derleme yapı eylemi seçme](media/projects-and-solutions-image1.png)

C# projeleri için bazı ortak eylemler oluşturun:

* **Hiçbiri** -dosyası herhangi bir şekilde oluşturma işleminin bir parçası değil - proje IDE'den kolay erişim için dahildir.
* **Derleme** -dosya, kaynak dosyası olarak C# Derleyici geçirilecek.
* **EmbeddedResource** -C# derleyicisi dosyanın derleme içine gömülü olması için bir kaynak olarak geçirilir. [Assembly.GetManifestResourceStream](https://docs.microsoft.com/dotnet/api/system.reflection.assembly.getmanifestresourcestream), gelen `System.Reflection` ad alanı, ardından derlemeden dosyayı okumak için kullanılabilir.
* **İçerik** -için ASP.NET projeleri, bu dosyaları olacaktır sitenin bir parçası olarak dahil dağıtıldığında. Xamarin.iOS ve Xamarin.Mac projelerinde, bunlar uygulama paketine dahil.

Birden fazla dosya seçin Çözüm Gezgini'nde, tek seferde çok sayıda dosyaya derleme eylemi ayarlamanızı izin verme mümkündür.

Ayrıca, belirli projeleri için derleme eylemler vardır. Xamarin.iOS projeleri **BundleResource** uygulama paket grubunu bir parçası olarak dosya ekleyecektir eylem oluşturun. Xamarin.Android belirli yapı eylemler hakkında bilgi bulunabilir [derleme işlemi](/xamarin/android/deploy-test/building-apps/build-process#Build_Actions) Kılavuzu.