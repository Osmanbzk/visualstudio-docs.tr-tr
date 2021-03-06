---
title: Hangi&#39;s kaynak denetimine'deki yenilikler | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- what's new [Visual Studio SDK], source control
- source control [Visual Studio SDK], what's new
ms.assetid: bcf85418-18fb-4824-9dae-d14bf3d56a77
caps.latest.revision: 28
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9a108acb2ae32b64292cd819c75de4726f067a00
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51752463"
---
# <a name="what39s-new-in-source-control"></a>Hangi&#39;da kaynak denetimi
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

İçinde [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] kaynak denetimi VSPackage'ı uygulayarak, derin tümleşik kaynak denetimi çözümü sağlayabilirsiniz. Bu bölümde, kaynak denetimi VSPackage'ları özelliklerini açıklar ve uygulama adımlarını genel bir bakış sağlar.  
  
## <a name="the-source-control-vspackage"></a>Kaynak denetimi VSPackage'ı  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] iki tür kaynak denetimine çözüm destekler. Tüm sürümlerinde [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], kaynak denetimi eklentisi API tabanlı hâlâ bütünleştirebilirsiniz eklenti. VSPackage sağlayan bir derin tümleştirme, kaynak denetimi için de oluşturabilirsiniz [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] açıdan çok yönlülük ve otonomi yüksek düzeyde gerektiren kaynak denetim çözümleri için uygun yolu.  
  
 VSPackage neredeyse her çeşit bir işlevselliği için ekleyebilirsiniz [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Kaynak denetimi VSPackage'ı için bir tam kaynak denetimi özelliği sağlar [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], kaynak denetim sistemi ile arka uca iletişimi kullanıcıya sunulan kullanıcı arabiriminden.  
  
 Kaynak denetimi VSPackage'ı uygulayan bir "tümü veya hiçbiri" stratejisi gerektirir. Kaynak denetimi VSPackage'ı oluşturan arabirimlerin yanı sıra kaynak denetim arabirimleri ve yeni kullanıcı Arabirimi öğeleri (iletişim kutuları, menüler ve araç çubukları) tüm kaynak denetimi işlevini kapsayan bir dizi uygulamaya çabayı önemli ölçüde yatırım gerekir herhangi bir paket başarılı bir şekilde tümleştirmek için gerekli [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 Aşağıdaki adımları, kaynak denetim paketi uygulamak için gereken genel bir bakış sağlar. Ayrıntılar için bkz [bir kaynak denetimi VSPackage'ı oluşturma](../../extensibility/internals/creating-a-source-control-vspackage.md).  
  
1.  Özel kaynak denetimi hizmetini proffers bir VSPackage'ı oluşturun.  
  
2.  Tarafından proffered kaynak denetimi ile ilgili hizmetler, arabirimler uygulama [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] (örneğin, <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider> arabirimi).  
  
3.  Kaynak denetimi VSPackage'ı kaydedin.  
  
4.  Tüm menü öğelerini, iletişim kutuları, araç çubukları ve bağlam menülerini de dahil olmak üzere kullanıcı Arabirimi, kaynak denetimi uygulayın.  
  
5.  Etkin olan ve sizin VSPackage tarafından işlenmesi gereken tüm kaynak denetimi ile ilgili olaylar, kaynak denetimine VSackage geçirilir.  
  
6.  Kaynak denetimi VSPackage'ı gerekir dinlemek için olanlar gibi olayları uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3> arabirim yanı sıra izleme proje belge (TPD) olayları (tarafından uygulanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> arabirimi) ve gerekli eylemi gerçekleştirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [Genel bakış](../../extensibility/internals/source-control-integration-overview.md)   
 [Kaynak Denetimi VSPackage’ı Oluşturma](../../extensibility/internals/creating-a-source-control-vspackage.md)

