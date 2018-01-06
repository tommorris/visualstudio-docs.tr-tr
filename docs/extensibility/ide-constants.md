---
title: IDE sabitleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
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
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4a43bc68a87d00dcce90f1a948b64dd786e9b440
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ide-constants"></a>IDE sabitleri
<xref:Microsoft.VisualStudio.VSConstants> Sınıfı özgü tümleşik geliştirme ortamı (IDE), daha önce tanımlanan ve yalnızca üstbilgi dosyalarında sabitleri sağlar.  
  
## <a name="logical-and-physical-views"></a>Mantıksal ve fiziksel görünümleri  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Code>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` işleyicileri bu değer için geçmesi <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** iletişim kutusunda, bu durumda olası kod görünümleri.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Debugging>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` işleyicileri geçirmek için bu değeri <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** iletişim kutusunda, bu durumda ile olası doldurulmuş <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Debugging> aynı görünüm olarak Eşle görünümler hata ayıklama <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Code>.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Designer>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` işleyicileri geçirmek için bu değeri <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** iletişim kutusunda, bu durumda **formu görüntüle** Tasarımcı görünümleri.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Primary>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` işleyicileri geçirmek için bu değeri <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** iletişim kutusunda, bu durumda Düzenleyici üreteci varsayılan/birincil görünümü.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_TextView>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` işleyicileri geçirmek için bu değeri <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> almak için yöntemi **birlikte Aç** iletişim kutusunda, bu belge veya veri bir metin düzenleyicisi görünümü.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_UserChooseView>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` işleyicileri geçirmek için bu değeri <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> kullanmak üzere hangi kullanıcı tarafından tanımlanan görünüm seçmek için kullanıcıdan yöntemi.|  
  
## <a name="editor-factory-flags"></a>Düzenleyici üreteci bayrakları  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.CEF_CLONEFILE>|Geçersiz bayrak birleşik ilk parametresi olarak Bitsel <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> yöntemi.|  
|<xref:Microsoft.VisualStudio.VSConstants.CEF_OPENASNEW>|Öğesinin ilk parametresi olarak Bitsel birleştirilmiş <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>, yöntem, bu gösterir Düzenleyici üreteci gerekli düzeltmeleri gerçekleştirmeniz.|  
|<xref:Microsoft.VisualStudio.VSConstants.CEF_OPENFILE>|Öğesinin ilk parametresi olarak Bitsel birleştirilmiş <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> yöntemi, bu bayrak olduğu birbirini exclusive <xref:Microsoft.VisualStudio.VSConstants.CEF_CLONEFILE>.|  
|<xref:Microsoft.VisualStudio.VSConstants.CEF_SILENT>|Öğesinin ilk parametresi olarak Bitsel birleştirilmiş <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> yöntemi, bu gösterir Düzenleyici üreteci oluşturma Düzenleyicisi kullanıcı arabirimini (UI) görüntülemeden.|  
  
## <a name="visual-studio-errors"></a>Visual Studio hataları  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_BUSY>|Zaman uyumsuz davranışı arabirimleri tarafından döndürülen bir sabit olduğunda, söz konusu nesne zaten meşgul|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>|Özel HRESULT hata [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] "uyumsuz belge verileri" için.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PACKAGENOTLOADED>|Özel HRESULT hata [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve "paketi yüklü değil." gösterir|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTALREADYEXISTS>|Özel HRESULT hata [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve gösterir, "Proje zaten mevcut."|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTMIGRATIONFAILED>|Özel HRESULT hata [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve belirten "proje yapılandırması başarısız oldu."|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTNOTLOADED>|Özel HRESULT hata [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve "proje yüklü değil." gösterir|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONALREADYOPEN>|Özel HRESULT hata [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve "Çözüm zaten açık." gösterir|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONNOTOPEN>|Özel HRESULT hata [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve "Çözüm açık değil." gösterir|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SPECIFYING_OUTPUT_UNSUPPORTED>|Dizisinden belirtmek için parametrelerine sahip yapı arabirimleri tarafından döndürülen <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput> arabirimi, ancak uygulama yalnızca uygulayabileceğiniz yöntemi tüm çıktıları.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>|<xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> Yöntemi düzenleyicide açık bir biçimde belge varsa, bu değeri döndürür.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_WIZARDBACKBUTTONPRESS>|Kullanıcı Geri düğmesini isabet belirten bir HRESULT değeri bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Sihirbazı.|  
  
## <a name="visual-studio-constants"></a>Visual Studio sabitleri  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_PROJECTFORWARDED>|Özel HRESULT hata [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve "projesi iletilen." gösterir|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_TBXMARKER>|Özel bir sabit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] için bir "araç işaretçisi."|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_ENTERMODAL>|Özel bir sabit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] aracılığıyla bir bildirim iletisi yayınlamak üzere <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> şekil başlangıcını gösteren yöntemi.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_EXITMODAL>|Özel bir sabit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] aracılığıyla bir bildirim iletisi yayınlamak üzere <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> şekil sonunu gösterir yöntemi.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_TOOLBARMETRICSCHANGE>|Özel bir sabit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] aracılığıyla bir bildirim iletisi yayınlamak üzere <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> komut çubuğu ölçümleri değiştiğini gösteren yöntemi.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSCOOKIE_NIL>|Özel bir sabit [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] belirten bir tanımlama bilgisi ayarlanmamışsa.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSITEMID_NIL>|A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir proje öğesi yokluğu temsil eden öğe tanımlayıcısı. Bu değer, geçerli seçim olduğunda kullanılır.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT>|A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir proje hiyerarşisi kökünü temsil eder ve tüm hiyerarşi için tek bir öğe aksine tanımlamak için kullanılan öğe tanımlayıcısı.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSITEMID_SELECTION>|A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] şu anda seçili öğe veya hiyerarşisinin kökü içerebilir öğelerini temsil eden öğe tanımlayıcısı.|  
  
## <a name="ivsselectionevents"></a>IVsSelectionEvents  
 IDE hangi bileşen yalnızca, buna seçilmiş açıklar bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A> , örneğin çağırın.  
  
|Sabit|Değer|  
|--------------|-----------|  
|<xref:Microsoft.VisualStudio.VSConstants.DocumentFrame>|0x2|  
|<xref:Microsoft.VisualStudio.VSConstants.PropertyBrowserSID>|0x4|  
|<xref:Microsoft.VisualStudio.VSConstants.StartupProject>|0x3|  
|<xref:Microsoft.VisualStudio.VSConstants.UndoManager>|0x0|  
|<xref:Microsoft.VisualStudio.VSConstants.UserContext>|0x5|  
|<xref:Microsoft.VisualStudio.VSConstants.WindowFrame>|0x1|  
  
## <a name="vsselelemid"></a>VSSELELEMID  
 Sabitler yeni bir seçim durumu göstermek için kullanılır.  
  
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