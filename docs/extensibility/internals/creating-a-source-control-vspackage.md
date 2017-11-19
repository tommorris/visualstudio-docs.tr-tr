---
title: "Kaynak denetimi VSPackage oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], creating source control packages
- source control packages
ms.assetid: cca0a9ed-48ff-409f-8036-ed8db0f7533e
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4c3d414f1fcf6a7f4cd4155eb04e3696fb39740a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-source-control-vspackage"></a>Kaynak denetimi VSPackage oluşturma
Bu belge mimarisine genel bakış ile tümleştirilmiş bir kaynak denetimi paketin bağlantılarını içerir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], uygulanacak arabirimleri ve tüketilmesi hizmetler tarafından tanımlanan API ve basit bir kaynağı gösteren bir örnek paket uygulama denetler.  
  
 Bir kaynak denetimi VSPackage ile derin tümleştirme yolu ile tümleştirmek kaynak denetimi için oluşturabileceğiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Varsayılan kaynak denetimi tarafından barındırılan UI atlamak paket etkinleştirir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], proje sistemden kaynak denetimi isteklerini yanıtlamak ve etkileşim [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bileşenleri gibi **Çözüm Gezgini**. [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] Güçlendirir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ortakları ile tümleşen bir VSPackage oluşturmak için bir mekanizma ile [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bir hizmet modeli kullanarak.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Başlarken](../../extensibility/internals/getting-started-with-source-control-vspackages.md)  
 Kaynak denetimi uygulamak üzere eklenti kaynak denetimi için daha gelişmiş bir alternatif kaynak denetimi paketi anlatılmaktadır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Mimarisi](../../extensibility/internals/source-control-vspackage-architecture.md)  
 Bir diyagramını sunar ve kaynak denetimi paketi bileşenlerinin açıklanmaktadır.  
  
 [Özellikleri](../../extensibility/internals/source-control-vspackage-features.md)  
 Kaynak denetimi paketi çeşitli özelliklerini açıklar.  
  
 [Tasarım öğeleri](../../extensibility/internals/source-control-vspackage-design-elements.md)  
 Kaynak denetimi paketi için derin tümleştirme uygulamalıdır VSPackage yapısını tanımlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kaynak Denetimi Eklentisi oluşturma](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 Kaynak Denetim işlevleri sağlayan bir kaynak denetimi eklenti oluşturmak nasıl ele [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kaynak denetimi kullanıcı arabirimini (UI).  
  
 [Kaynak denetimi](../../extensibility/internals/source-control.md)  
 Kaynak denetimi tümleşik bir özellik olarak uygulamak için seçenekleri açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].