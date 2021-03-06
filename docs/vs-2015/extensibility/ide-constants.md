---
title: IDE sabitleri | Microsoft Docs
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
- IDE, errors
- logical views
- errors [Visual Studio], IDE
- UI context constants
- constants, Visual Studio IDE
- IDE, constants
- physical views
ms.assetid: 5030e70a-241d-474a-ba8c-e3b1cf947ff0
caps.latest.revision: 24
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aa8fb2e4af74facc0ca00343e6abad36b7fcec50
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/16/2018
ms.locfileid: "51743311"
---
# <a name="ide-constants"></a>IDE Sabitleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:Microsoft.VisualStudio.VSConstants> Sınıfı olan tümleşik geliştirme ortamı (IDE) belirli ve, önceden tanımlanmış yalnızca üstbilgi dosyalarında sabitler sunar.  
  
## <a name="logical-and-physical-views"></a>Mantıksal ve fiziksel görünümleri  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|[LOGVIEWID_Code_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.code_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` işleyiciler bu değere geçirmesi gerekir <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** olası kod görünümleri, bu durumda, iletişim kutusu.|  
|[LOGVIEWID_Debugging_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.debugging_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` işleyicileri geçirmek için bu değer <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** iletişim kutusunda, bu durumda olası ile doldurulmuş <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Debugging_guid> aynı görünüm olarak eşleyen görünümleri hata ayıklama <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID.Code_guid>.|  
|[LOGVIEWID_Designer_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.designer_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` işleyicileri geçirmek için bu değer <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** iletişim kutusunda, bu duruma **formu görüntüle** Tasarımcı görünümleri.|  
|[LOGVIEWID_Primary_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.primary_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` işleyicileri geçirmek için bu değer <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** iletişim kutusunda, bu durumda varsayılan/ana görünümünde Düzenleyici üreteci.|  
|[LOGVIEWID_TextView_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.textview_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` işleyicileri geçirmek için bu değer <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** belge veya verileri bir metin düzenleyicisi görünümü için bu iletişim kutusu.|  
|[LOGVIEWID_UserChooseView_guid](/dotnet/api/microsoft.visualstudio.vsconstants.logviewid.userchooseview_guid?view=visualstudiosdk-2015)|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97> `cmdidOpenWith` işleyicileri geçirmek için bu değeri <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> yöntemini kullanmak için hangi kullanıcı tanımlı görünüm ister.|  
  
## <a name="editor-factory-flags"></a>Düzenleyici fabrikası bayrakları  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|[CEF.CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015)|Geçersiz bir bayrak bit düzeyinde ilk parametre olarak birleştirilmiş <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> yöntemi.|  
|[CEF.CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015)|Bit düzeyinde ilk parametre olarak birleştirilmiş <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>, yöntemi, bu gösterir Düzenleyici fabrikası gerekli düzeltmeleri gerçekleştirmeniz.|  
|[CEF.CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015)|Bit düzeyinde ilk parametre olarak birleştirilmiş <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> yöntemi, bu bayrağı olduğu birbirini exclusive [CEF. CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015).|  
|[CEF.CloneFile](/dotnet/api/microsoft.visualstudio.vsconstants.cef?view=visualstudiosdk-2015)|Bit düzeyinde ilk parametre olarak birleştirilmiş <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> yöntemi, bu gösterir Düzenleyici fabrikası oluşturmalıdır Düzenleyicisi kullanıcı arabirimi (UI) görüntülemeden.|  
  
## <a name="visual-studio-errors"></a>Visual Studio hataları  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_BUSY>|Zaman uyumsuz davranışı için arabirimleri tarafından döndürülen bir sabit olduğunda, söz konusu nesne zaten meşgul|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>|"Uyumsuz belge verileri için" Visual Studio'ya özel HRESULT hatası.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PACKAGENOTLOADED>|Visual Studio ve bu özel HRESULT hatası "paketi yüklü değil." gösterir|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTALREADYEXISTS>|Visual Studio ve bu özel HRESULT hatası belirten "Projesi zaten var."|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTMIGRATIONFAILED>|Visual Studio ve bu özel HRESULT hatası "proje yapılandırması başarısız oldu." gösterir.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTNOTLOADED>|Visual Studio ve bu özel HRESULT hatası "projesi yüklü değil." gösterir|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONALREADYOPEN>|Visual Studio ve bu özel HRESULT hatası "Çözüm zaten açık." gösterir.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONNOTOPEN>|Visual Studio için özeldir ve "Çözüm açık değil." belirten HRESULT hatası|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SPECIFYING_OUTPUT_UNSUPPORTED>|Bir diziden belirtmek için parametreleri olan yapı arabirimleri tarafından döndürülen <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput> arabirimi, ancak uygulama yalnızca uygulayabileceğiniz yöntemi tüm çıktıları.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>|<xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> Yöntemi, belgede düzenleyicide açılan bir biçim varsa bu değeri döndürür.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_WIZARDBACKBUTTONPRESS>|Kullanıcı bir Visual Studio sihirbazında geri düğmesine basın gösteren HRESULT değerini.|  
  
## <a name="visual-studio-constants"></a>Visual Studio sabitleri  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_PROJECTFORWARDED>|Visual Studio ve bu özel HRESULT hatası "proje iletilen." gösterir|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_TBXMARKER>|Bir "araç kutusu işaretçisi." Visual Studio için belirli bir sabiti|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_ENTERMODAL>|Bir bildirim iletisi aracılığıyla yayımlamak için Visual Studio için belirli bir sabit <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> şekil başlangıcını gösteren yöntemi.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_EXITMODAL>|Bir bildirim iletisi aracılığıyla yayımlamak için Visual Studio için belirli bir sabit <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> şekil sonuna belirten yöntemi.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_TOOLBARMETRICSCHANGE>|Bir bildirim iletisi aracılığıyla yayımlamak için Visual Studio için belirli bir sabit <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> komut çubuğu ölçümleri değiştiğini gösteren yöntemi.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSCOOKIE_NIL>|Visual Studio için bir tanımlama bilgisi ayarlanmamışsa gösteren belirli bir sabit değer.|  
|[VSITEMID. Nil](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Nil>)|Bir proje öğesi olmaması temsil eden bir Visual Studio öğe tanımlayıcısı. Bu değer, geçerli seçim yok olduğunda kullanılır.|
|[VSITEMID. Kök](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Root>)|Bir proje hiyerarşisinin kökü temsil eder ve tek bir öğe yerine tüm bir hiyerarşiye tanımlamak için kullanılan bir Visual Studio öğe tanımlayıcısı.|
|[VSITEMID. Seçimi](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID#Microsoft_VisualStudio_VSConstants_VSITEMID_Selection>)|Seçili öğenin veya hiyerarşisinin kökü içerebilen öğeleri temsil eden bir Visual Studio öğe tanımlayıcısı.| 
  
## <a name="ivsselectionevents"></a>IVsSelectionEvents  
 IDE'nin hangi bileşen yalnızca, içinde seçildi açıklar bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A> , örneğin çağırın.  
  
|Sabit|Değer|
|--------------|-----------|
|[SelectionElement.DocumentFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_DocumentFrame>)|0x2|
|[SelectionElement.PropertyBrowserSID](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_PropertyBrowserSID>)|0x4|
|[SelectionElement.StartupProject](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_StartupProject>)|0x3|
|[SelectionElement.UndoManager](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UndoManager>)|0x0|
|[SelectionElement.UserContext](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_UserContext>)|0x5|
|[SelectionElement.WindowFrame](<xref:Microsoft.VisualStudio.VSConstants.SelectionElement#Microsoft_VisualStudio_VSConstants_SelectionElement_WindowFrame>)|0x1| 
  
## <a name="vsselelemid"></a>VSSELELEMID  
 Yeni bir seçim durumu belirtmek için kullanılan sabit değişkenler.  
  
|Sabit|Değer|  
|--------------|-----------|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|2|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|7|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|4|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|6|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|3|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|0|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|5|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|1.|  
  
## <a name="component-selector-dialog-constants"></a>Bileşen Seçici iletişim sabitleri  
  
|Sabit|Değer|  
|--------------|-----------|  
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELCHANGED>|WM_USER + 1280|  
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELDBLCLICK>|WM_USER + 1281|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_CLEARSELECTION>|WM_USER + 1290|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_GETSELECTION>|WM_USER + 1287|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZELIST>|WM_USER + 1285|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZETAB>|WM_USER + 1288|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_QUERYCANSELECT>|WM_USER + 1286|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_SETMULTISELECT>|WM_USER + 1289'U|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje Sistemlerini Genişletmeye Yönelik IDE Tanımlı Komutlar](../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)

