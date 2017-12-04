---
title: "-Yükseltme (devenv.exe) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /upgrade Devenv switch
- Devenv, /upgrade switch
- upgrade Devenv switch
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 464846eaf76761008ffc351db53d92669812f691
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="upgrade-devenvexe"></a>/Upgrade (devenv.exe)
Çözüm dosyasını ve tüm proje dosyalarını veya, geçerli belirtilen proje dosyası güncelleştirmeleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bu dosyalar için biçimleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv SolutionFile | ProjectFile /upgrade  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionFile`  
 Çözümün tamamında ve projeleri yükseltiyorsanız gereklidir. Yol ve çözüm dosya adı. Yalnızca çözüm dosyasını veya adı bir tam yol ve çözüm dosyasının adını girebilirsiniz. Adlı dosyayı veya klasörü henüz mevcut değilse, oluşturulur.  
  
 `ProjectFile`  
 Tek bir proje yükseltiyorsanız gereklidir. Yol ve çözüm içinde proje dosyasının adı. Yeni proje dosyası veya bir tam yol adı ve proje dosyası adını girebilirsiniz. Adlı dosyayı veya klasörü henüz mevcut değilse, oluşturulur.  
  
## <a name="remarks"></a>Açıklamalar  
 Yedeklemeleri otomatik olarak oluşturulur ve geçerli dizinde oluşturulan yedekleme adlı bir dizine kopyalanır.  
  
 Yükseltilebilmesi için önce kaynak denetimli çözümleri veya projeleri kullanıma alınması gerekir.  
  
 Kullanarak `/upgrade` anahtar başlamıyor [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Yükseltme sonuçlarını, proje ve çözüm geliştirme dilini yükseltme raporunda görülebilir. Hiçbir hata ya da kullanım bilgilerini döndürülür. Proje yükseltme hakkında daha fazla bilgi için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], bkz: [bağlantı noktası, geçirme ve yükseltme Visual Studio projeleri](../../porting/port-migrate-and-upgrade-visual-studio-projects.md).  
  
## <a name="example"></a>Örnek  
 Bu örnek için varsayılan klasörünüzde "MyProject.sln" adlı bir çözüm dosyasını yükseltir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] çözümler.  
  
```  
devenv "MyProject.sln" /upgrade  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)