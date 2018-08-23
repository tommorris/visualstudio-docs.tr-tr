---
title: Kaynak denetimini destekleme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], supporting
ms.assetid: 567acde3-354e-4f39-8d99-0ef86c103396
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 01941fdd4899142ae8abb96f57f93e3ebd0b6256
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693697"
---
# <a name="supporting-source-control"></a>Kaynak Denetimini Destekleme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kaynak denetimini destekleme](https://docs.microsoft.com/visualstudio/extensibility/internals/supporting-source-control).  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Dosya kullanıma alma, iade etme işlemleri ve diğer kaynak denetim işlemlerini Proje veya Düzenleyicisi için destekler. Kaynak denetimi istemci olarak [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] gibi kaynak denetim paketi ile etkileşim kuracak şekilde tasarlanmıştır [!INCLUDE[vsvss](../../includes/vsvss-md.md)], arşivleme, sürüm oluşturma ve denetim özellikleri için dinamik olarak tanımlanan bir dosya kümesini sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Kaynak Denetimi Paketleri için Model](../../extensibility/internals/model-for-source-control-packages.md)  
 Bir proje türü uygulanmalı arabirimleri açıklar kaynak denetimi desteklemek için.  
  
 [Tasarım kararları](../../extensibility/internals/source-control-design-decisions.md)  
 Soruların yanıtlarını proje türüne nasıl uygulayacağınıza değiştirme sağlar.  
  
 [Yapılandırma ayrıntıları](../../extensibility/internals/source-control-configuration-details.md)  
 Kaynak denetimini destekleyen bir proje türü uygulamasını nasıl değiştiğini açıklar.  
  
 [Projeler ve düzenleyiciler için ek yönergeler](../../extensibility/internals/additional-source-control-guidelines-for-projects-and-editors.md)  
 Proje türleri ve düzenleyiciler için en iyi uygulamaları açıklar.  
  
 [Çalışma zamanı ayrıntıları](../../extensibility/internals/source-control-runtime-details.md)  
 Bir kullanıcı, bir kaynak denetim sistemine eklediğinde, bir proje kaydetme işlemini açıklamaktadır.  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>  
 Ortam ya da bir dosya hakkında bellekte değiştirilemez veya kaydedilmiş olan kaynak denetim paketi belirtir.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>  
 Projeler ve hiyerarşileri kendilerini kaynak denetimiyle kaydetmesini ve kaynak denetimi durumu hakkında bilgi sağlar.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>  
 Kaynak denetimi proje dosyaları ve proje öğeleri için sağlamak üzere proje sistemindeki uygulanır.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>  
 Ortam eklemek, kaldırmak veya bir dosya veya bir çözüm dizini yeniden adlandırma izni için Sorgulanacak projeleri tarafından kullanılır.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>  
 Proje dosyaları veya dizinleri için yapılan değişiklikler istemcileri bildirir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Proje Türleri](../../extensibility/internals/project-types.md)  
 Temel yapı taşları projelerine genel bir bakış sağlar [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] tümleşik geliştirme ortamı (IDE). Projeler oluşturmak ve kodu derleme nasıl kontrol açıklayan ek konulara bağlantılar sağlanmaktadır.

