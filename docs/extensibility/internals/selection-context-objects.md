---
title: Seçim bağlam nesneleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- selection, tracking
- selection, context objects
ms.assetid: 7308ea8f-a42c-47e5-954e-7dee933dce7a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 04ccc4a57ac7af144c134761119433b7533e9bec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131271"
---
# <a name="selection-context-objects"></a>Seçim bağlam nesneleri
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Tümleşik geliştirme ortamı (IDE) genel Seçim bağlam nesnesi IDE içinde görüntüleneceğini belirlemek için kullanır. IDE içinde her penceresi genel seçimi bağlamına gönderilen kendi seçim bağlam nesnesi olabilir. Bu pencere odağa sahip olduğunda IDE genel seçimi bağlam penceresinden değerlerle güncelleştirir. Daha fazla bilgi için bkz: [kullanıcıya geri bildirim](../../extensibility/internals/feedback-to-the-user.md).  
  
 Her bir pencere çerçevesi veya IDE sitede adlı bir hizmet sahip <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>. Pencere çerçevesi tarihli, VSPackage tarafından oluşturulan nesne çağırmalısınız `QueryService` gösteren bir işaretçi almak için yöntemi <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> arabirimi.  
  
 Çerçeve pencereleri başlatıldıklarında genel seçimi bağlamına yayılmasını kendi seçimi bağlam bilgilerinin bölümlerini kullanmaya devam edebilir. Bu özellik boş bir seçim ile başlatmanız gerekebilir aracı windows için kullanışlıdır.  
  
 VSPackages izleyebilirsiniz genel seçimi içerik Tetikleyicileri olayları değiştirme. VSPackages uygulayarak aşağıdaki görevleri gerçekleştirebilirsiniz `IVsTrackSelectionEx` ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection> arabirimleri:  
  
-   Bir hiyerarşide şu anda etkin dosyasını güncelleştirin.  
  
-   İzleyici, belirli türde bir öğeleri değiştirir. Örneğin, bir özel, VSPackage kullanıyorsa, **özellikleri** penceresi, etkin değişiklikleri izleyebilirsiniz **özellikleri** penceresi ve sizin gerektiğinde yeniden başlatın.  
  
 Aşağıdaki izleme seçimi normal seyri gösterilir.  
  
1.  IDE yeni açılan pencereden seçimi bağlamı alır ve genel seçimi bağlamda yerleştirir. Seçim bağlam HIERARCHY_DONTPROPAGATE veya SELCONTAINER_DONTPROPAGATE kullanıyorsa, bu bilgileri genel bağlamda dağıtılmaz. Daha fazla bilgi için bkz: [kullanıcıya geri bildirim](../../extensibility/internals/feedback-to-the-user.md).  
  
2.  Bildirim olayları bunları istenen tüm VSPackage yayınlanır.  
  
3.  Bir aracı ya da diğer benzer görevleri yeniden etkinleştirme bir hiyerarşi güncelleştirme gibi etkinlikleri gerçekleştirerek aldığı olaylarına VSPackage yapar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>   
 [Visual Studio'da hiyerarşileri](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [Seçim ve IDE içinde para birimi](../../extensibility/internals/selection-and-currency-in-the-ide.md)   
 [Proje Türleri](../../extensibility/internals/project-types.md)