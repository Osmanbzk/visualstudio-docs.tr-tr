---
title: Proje özelliği kullanıcı arabirimi | Microsoft Docs
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
- project properties [Visual Studio], user interface
- projects [Visual Studio SDK], properties UI
- project properties UI
ms.assetid: b6aec634-8533-476c-9ebd-36536a2288e2
caps.latest.revision: 17
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e295bff2f8398765f90c3fd537ca4f546208ce4b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51768282"
---
# <a name="project-property-user-interface"></a>Proje Özelliği Kullanıcı Arabirimi
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Proje alt öğeleri projede kullanabileceğiniz **özellik sayfaları** iletişim kutusu temel proje tarafından verdiği Gizle veya salt okunur denetimleri ve tüm sayfaları sağlanan olarak olun veya proje alt özel sayfalar eklemek için **Özellik sayfaları** iletişim kutusu.  
  
## <a name="extending-the-project-property-dialog-box"></a>Proje özelliği iletişim kutusu genişletme  
 Proje alt Otomasyon Genişleticileri ve proje yapılandırma Gözat nesneleri uygular. Bu genişleticilerini uygulama <xref:EnvDTE.IFilterProperties> belirli özellikleri, gizli ya da salt okunur hale getirmek için arabirim. **Özellik sayfaları** temel projenin temel proje tarafından uygulanan iletişim kutusu, Otomasyon Genişleticileri tarafından gerçekleştirilen filtreleme geliştirir.  
  
 Genişletme işleminin bir **proje özelliği** iletişim kutusunda aşağıdaki ana hatları verilmiştir:  
  
- Temel projenin Genişleticileri uygulayarak proje alt türden alır <xref:EnvDTE80.IInternalExtenderProvider> arabirimi. Göz atma, proje otomasyon ve tüm temel projenin proje yapılandırma Gözat nesneleri bu arabirimi uygulayın.  
  
- Uygulamasını <xref:EnvDTE80.IInternalExtenderProvider> proje Gözat nesnesi ve proje Otomasyon nesnesi için temsilci seçmek için <xref:EnvDTE80.IInternalExtenderProvider> uygulaması proje alt Toplayıcısı'nı (diğer bir deyişle, bunlar `QueryInterface` için <xref:EnvDTE80.IInternalExtenderProvider> üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> Proje nesne).  
  
- Ayrıca temel proje yapılandırması Gözat nesnesi uygulayan <xref:EnvDTE80.IInternalExtenderProvider> proje alt yapılandırma nesnesinden Otomasyon Extender içinde doğrudan bağlayabilirsiniz. Uygulaması temsilciler için <xref:EnvDTE80.IInternalExtenderProvider> proje alt toplayıcı tarafından uygulanan arabirimi.  
  
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetProjectItem%2A>, proje göz atma, yapılandırma nesnesi tarafından döndürür uygulanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> nesne.  
  
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetCfg%2A>, aynı zamanda proje göz atma, yapılandırma nesnesi tarafından döndürür uygulanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> nesne.  
  
- Aşağıdaki alarak uygun Catıdlerini çeşitli Genişletilebilir nesnelerin temel projenin çalışma zamanında proje alt belirleyebilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> değerleri:  
  
  -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
  -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
  -   <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
  Proje alt Catıdlerini için Proje kapsamını belirlemek için yukarıdaki özelliklerini alır <xref:Microsoft.VisualStudio.VSConstants.VSITEMID> gelen `VSITEMID``typedef`. Proje alt Ayrıca hangi denetlemek isteyebilir **özellik sayfaları** iletişim kutusu sayfaları projesi için görüntülenen yapılandırmaya bağımlı hem bağımsız yapılandırma. Bazı proje alt türleri yerleşik sayfaları kaldırın ve proje alt türü belirli sayfalar eklemek gerekebilir. Bu, yönetilen bir istemci projesi çağrıları etkinleştirmek için <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> yöntemi için şu özellikleri:  
  
- `VSHPROPID_PropertyPagesCLSIDList` — CLSID yapılandırma bağımsız özellik sayfaları'nın noktalı virgülle ayrılmış listesi.  
  
- `VSHPROPID_CfgPropertyPagesCLSIDList —` CLSID yapılandırma bağımlı özellik sayfaları'nın noktalı virgülle ayrılmış listesi.  
  
  Proje alt tür çünkü toplamalar <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> nesnesi, hangi denetlemek için bu özelliklerin tanımı geçersiz **özellik sayfaları** iletişim kutusu görüntülenir. Proje alt türü iç temel projeden bu özelliklerini almak ve daha sonra ekleyebilir veya CLSID gerektiği şekilde kaldırabilirsiniz.  
  
  Proje alt türü tarafından eklenen yeni özellik sayfaları, temel proje uygulamasından bir proje yapılandırması Gözat nesnesi verilir. Bu proje yapılandırması Gözat nesnesi Otomasyon Genişleticileri destekler. AutomationExtenders hakkında daha fazla bilgi için bkz. [uygulanması ve Otomasyon Genişleticileri kullanılarak](http://msdn.microsoft.com/library/0d5c218c-f412-4b28-ab0c-33a611f62356). Proje alt çağrı tarafından uygulanan özellik sayfalarını <xref:EnvDTE.Project.Extender%2A> temel projenin yapılandırma Gözat nesnesini genişletir, kendi proje alt yapılandırma Gözat nesnesi almak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:EnvDTE.IFilterProperties>   
 [Özellik sayfaları iletişim kutusu](http://msdn.microsoft.com/en-us/4a3d34ac-ed03-45e8-ae60-a0e1aad300e4)

