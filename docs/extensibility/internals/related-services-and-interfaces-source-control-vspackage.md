---
title: İlgili hizmet ve arabirimi (kaynak denetimi VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control packages, interfaces
- interfaces, source control packages
ms.assetid: 3e96e838-5675-46bb-99cf-40d420086038
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1f9e8e90fdda61524a9af107df452bc2b13cd90c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="related-services-and-interfaces-source-control-vspackage"></a>İlgili hizmet ve arabirimi (kaynak denetimi VSPackage)
Bu bölümde tüm Kaynak Denetim VSPackage ilgili arabirimlerde listeler [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]. Kaynak denetimi VSPackage bazı bu arabirimlerini uygular ve diğerleri kaynak denetimi görevlerini gerçekleştirmek için kullanır.  
  
## <a name="interfaces-implemented-by-and-for-source-control-vspackages"></a>Kaynak denetimi VSPackages için ve tarafından uygulanan arabirimler  
 Aşağıdaki arabirimleri açıklanan [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], ve bunların bir alt kümesini, istenen özellik kümesi bağlı olarak kaynak denetimi VSPackage uygular. Bazı arabirimler işaretlenmiş gibi gerekli ve her kaynak denetimi VSPackage uygulanmalıdır.  
  
 Bir paket uygulamaz, bu arabirimleri için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] varsayılan uygulamasını sağlar. Varsayılan uygulama hiçbir VSPackage kaydedildiğinde çalışması ve proje için tasarlanmıştır Not denetlenir. Doğru yazılmış kaynak denetimi VSPackage bu arabirimleri varsayılan uygulaması bırakmak yerine tüm gerekli arabirimlerini uygular.  
  
 Kaynak denetimi VSPackage bazılarını veya tümünü aşağıdaki arabirimleri yalıtan bir özel hizmet uygulamanız gerekir.  
  
 Arabirimleri şunlardır:  
  
-   Gerekli: Uygun varlık (kaynak denetimi VSPackage, kaynak denetimi saplama Proje) arabirimini uygulamalıdır.  
  
-   Önerilen: Varlık bu arabirimi uygulamalıdır; Aksi takdirde, kaynak denetimi işlevlerinin sınırlı olabilir.  
  
-   İsteğe bağlı: varlık daha zengin bir özellik kümesi sağlamak için bu arabirimi uygulayabilirsiniz.  
  
|Arabirim|Amaç|Tarafından uygulanan|Uygulansın mı?|  
|---------------|-------------|--------------------|----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|Düzenleyiciler değiştirerek veya bir dosyayı kaydetmeden önce bu arabirim çağırın. Kaynak denetimi VSPackage dosyayı kullanıma alın veya teslim başarısız olursa işlemi engelle.|Kaynak denetimi VSPackage|Önerilen|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|Bu arabirim projelerde kaydetme ve kaynak denetimi projelerle kaydını ve desteği için temel kaynak denetim karakterleri sağlama gibi temel kaynak denetim işlevselliği sağlar.|Kaynak denetimi VSPackage|Gerekli|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|Bu arabirim elde edilen <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> kullanarak <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> işlevi, veya yalnızca uygulama nesnesi atama `IVsHierarchy` için `IVsSccProject2`. Kaynak denetimindeki bir projedeki dosyaları alma veya geçerli kaynak denetim durumu veya konumunun proje bildiren için kullanılır.|Proje|Gerekli|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>|Tümleştirme modülü bu arabirimin geçerli etkin VSPackage ayarlamak için kullanır.|Kaynak denetimi VSPackage|Gerekli|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|Bu arabirim, bir abonelik modeline dayanır. Tüm VSPackage belge olaylarını almak ve Kabuk tarafından çakışmasının üzeresiniz olaylarına tavsiye istediği sinyal. Uygulanan ve tarafından işlenen [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], hangi sırayla geçirir uygulama olayları `IVsTrackProjectDocumentsEvents2` VSPackage için.|Kaynak denetimi saplama|Gerekli|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments3>|Toplu işleme, eşitlenen okuma/yazma işlemleri ve Gelişmiş bu arabirim sağlayan `OnQueryAddFiles` yöntemi.|Kaynak denetimi saplama|Gerekli|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|**Çözüm Gezgini** ve projeleri projelerine yeni dosyalar eklendiğinde veya dosya ve klasörleri yeniden adlandırılmış veya projelerden silinen bu arabirim çağırın. Kaynak denetimi VSPackage proje dosyasını kullanıma veya işlemi iptal edin.|Kaynak denetimi VSPackage|Önerilen|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents3>|**Çözüm Gezgini** ve projeleri bu arabirimi yanıt IVstrackProjectDocuments3 arabirim yöntemleri için yapılan çağrılar olarak çağırın. VSPackage eşitlenen toplu işlemleri izlemek kaynak denetimi okuma/yazma işlemleri ve bir daha gelişmiş iş `OnQueryAddFiles` yöntemi.|Kaynak denetimi VSPackage|Önerilen|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccEnlistmentPathTranslation>|Bu arabirim kaydı yönetimi için Web projeleri desteği sağlar.|Kaynak denetimi VSPackage|Önerilen|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManagerTooltip>|Bu arabirim projelerde kaynak denetimli dosyaları için araç ipuçları almak için kullanılır.|Kaynak denetimi VSPackage|İsteğe Bağlı|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccOpenFromSourceControl>|Bu arabirim ad uzantısı desteği sağlar.|Kaynak denetimi VSPackage|İsteğe Bağlı|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccControlNewSolution>|Bir ad alanı uzantısına tümleştirmek için bu arabirimi VSPackage kullanır **yeni**, **açık**, veya **kaydetmek** iletişim kutuları. Sonuç olarak, projeleri otomatik olarak kaynak denetimi oluşturulurken eklenebilir, veya kaynak denetimine kaydetme zaman eklenen işlemi etkindir.|Kaynak denetimi VSPackage|İsteğe Bağlı|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>|Kaynak denetim karakterleri düğümler için olarak ek karakterleri tanımlamak için bu arabirimi VSPackage kullanır **Çözüm Gezgini**.|Kaynak denetimi VSPackage|İsteğe Bağlı|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccAddWebProjectFromSourceControl>|**Ekle** Web projeleri için iletişim kutusu, bu arabirim kullanır. Kaynak denetimi konumu ve kaynak denetimi deponuza bu konumda daha önce eklenen bir Web projesi açıldığında için gözatma için yöntemleri sağlar.|Kaynak denetimi VSPackage|Önerilen|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc>|Bu arabirim, kaynak denetiminden projeleri zaman uyumsuz (arka plan) yüklenmesi için destek sağlar.|Kaynak denetimi VSPackage|İsteğe Bağlı|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromSccProjectEvents>|Bu arabirim tarafından başlatılan zaman uyumsuz yükleme ilerlemesini izlemek projeleri verir <xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc>.|Proje|İsteğe Bağlı|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccToolsOptions>|Bu arabirim etkin kaynak denetimi VSPackage sorgulamak IDE verir. IDE VSPackage kayıtlı hiçbir etkin kaynak denetimi olduğunda bile anlama sahip kaynak denetim ayarları değerini sorgular. Bu arabirim uygulanan ve tarafından işlenen [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].|Kaynak denetimi saplama|Gerekli|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider>|Bu arabirim, kaynak denetimi VSPackage kaydedilirken kullanılır.|Kaynak denetimi saplama|Gerekli|  
|<xref:EnvDTE.SourceControl>|Bu arabirim, Otomasyon kullanılır. Bu nedenle, yalnızca hiçbir kullanıcı arabirimini görüntülemeden yürütülebilecek işlevleri kullanıma sunar.|Kaynak denetimi VSPackage|İsteğe Bağlı|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>|Bu arabirim, kaynak denetim ayarları çözüm (.sln) dosyasına kaydetmek için kullanılır. Kaynak Denetim durumu bayrakları ve kaynak denetimi konumunu ayarlar içerir.|Kaynak denetimi VSPackage|Önerilen|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>|Bu arabirim, çözüm seçenekleri (.suo) dosyasında kaynak denetim ayarları kaydetmek için kullanılır. Bu, geçerli kullanıcının kaydı konum gibi kullanıcıya özgü kaynak denetim ayarları içerebilir.|Kaynak denetimi VSPackage|Önerilen|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>|Bu arabirim, çözümleri kapatma veya bir projeyi açtığınızda yeni dosyaları kaynak denetiminden alma önce proje dosyalarına denetimi gibi işlemler gerçekleştirmek için olayları izlemek için kullanılır.|Kaynak denetimi VSPackage|Önerilen|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarım öğeleri](../../extensibility/internals/source-control-vspackage-design-elements.md)