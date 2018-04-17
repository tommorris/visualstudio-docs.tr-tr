---
title: Ne&#39;yeni kaynak denetiminde s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- what's new [Visual Studio SDK], source control
- source control [Visual Studio SDK], what's new
ms.assetid: bcf85418-18fb-4824-9dae-d14bf3d56a77
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b46730ab1acac6605af2e1ff1c418dbe8c886406
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="what39s-new-in-source-control"></a>Ne&#39;yeni kaynak denetiminde s
İçinde [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] kaynak denetimi VSPackage uygulayarak derine tümleşik kaynak denetimi çözümü sağlayabilirsiniz. Bu bölümde, kaynak denetimi VSPackages özelliklerini açıklar ve uygulama adımlarını genel bir bakış sağlar.  
  
## <a name="the-source-control-vspackage"></a>Kaynak denetimi VSPackage  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] iki tür kaynak denetimi çözümlerini destekler. Tüm sürümlerinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], kaynak denetim eklentisi API tabanlı hala tümleştirebilirsiniz eklentisi. VSPackage bir derin tümleştirme, sağlayan kaynak denetimi için de oluşturabilirsiniz [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] yüksek düzeyde açıdan çok yönlülük ve otonomisi gerektiren kaynak denetimi çözümleri için uygun yolu.  
  
 Bir VSPackage işlevsellik neredeyse her türlü ekleyebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Kaynak denetimi VSPackage sağlayan bir tam kaynak denetimi özelliği için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], kaynak denetim sistemi ile arka uç iletişim kullanıcıya sunulan UI gelen.  
  
 Kaynak denetimi VSPackage uygulama "tümü veya hiçbiri" stratejisi gerektirir. Kaynak denetimi VSPackage oluşturan bir dizi kaynak denetim arabirimleri ve yeni kullanıcı Arabirimi öğeleri (iletişim kutuları, menüleri ve araç çubuklarını) tüm kaynak denetim işlevselliği karşılamak üzere uygulamaya çaba önemli miktarda arabirimlerin yanı sıra yatırım gerekir başarıyla ile tümleştirmek için herhangi bir paket gerekli [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Aşağıdaki adımlar bir kaynak denetimi paketi uygulamak için gereken genel bir bakış sağlar. Ayrıntılar için bkz [kaynak denetimi VSPackage oluşturma](../../extensibility/internals/creating-a-source-control-vspackage.md).  
  
1.  Özel kaynak denetimi hizmeti proffers VSPackage oluşturun.  
  
2.  Arabirimler tarafından proffered kaynak denetimi ile ilgili hizmetlerin uygulama [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (örneğin, <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider> arabirimi).  
  
3.  Kaynak Denetim VSPackage kaydedin.  
  
4.  Tüm kaynak denetimi menü öğeleri, iletişim kutuları, araç çubukları ve bağlam menülerini de dahil olmak üzere kullanıcı arabirimini uygular.  
  
5.  Etkin olduğunda ve, VSPackage tarafından işlenen tüm kaynak denetimi ile ilgili olaylar, kaynak denetimi VSackage geçirilir.  
  
6.  Kaynak Denetim VSPackage gerekir dinleme olanlar gibi olayları uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3> arabirim izleme proje belge (TPD) olayları yanı sıra (tarafından uygulanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> arabirimi) ve gerekli adımları uygulayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [Genel bakış](../../extensibility/internals/source-control-integration-overview.md)   
 [Kaynak Denetimi VSPackage’ı Oluşturma](../../extensibility/internals/creating-a-source-control-vspackage.md)