---
title: Visual Studio birden fazla sürümünü destekleyen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, supporting multiple versions
- VSPackages, side-by-side compatibility
ms.assetid: 0047aa90-1ed4-40d3-8772-622b2719a4b1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 317ec1f214d18989c3b2c5c27fe9df9309239631
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="supporting-multiple-versions-of-visual-studio"></a>Visual Studio'nun birden çok sürümünü destekleme
Terim *yan yana* yüklemek ve bir ürün aynı bilgisayara birden fazla sürümünü yönetmek anlamına gelir. VSPackages için bir kullanıcı aynı bilgisayarda yüklü birden fazla Visual Studio sürümleri sahip anlamına gelir. Ancak, tek bir Visual Studio sürümüne yüklenen, VSPackages yan yana sürümleri sahip olamaz.  
  
 Visual Studio sürümlerini yan yana yüklenmesi mümkün, VSPackage yapmadan önce aşağıdakileri göz önünde bulundurun:  
  
-   İzlemek istediğiniz hangi yan yana uygulama stratejisi belirlemeniz gerekir.  
  
     Daha fazla bilgi için bkz: [seçme arasında paylaşılan ve sürümü tutulan VSPackages](../extensibility/choosing-between-shared-and-versioned-vspackages.md).  
  
-   Çözüm ve proje dosya biçimleri uygulama stratejinizin uymalıdır.  
  
     Daha fazla bilgi için bkz: [özel projeleri yükseltme](../extensibility/internals/upgrading-projects.md#upgrading-custom-projects) ve [yan yana dağıtımlar için dosya adı uzantılarını kaydetme](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md).  
  
-   Böylece sürümlü bileşenleri ve tüm sürümleri arasında paylaşılan bileşenleri doğru yüklü ve kayıtlı olan, yükleyici uygulaması stratejinizi işlemelidir.  
  
     Daha fazla bilgi için bkz: [yükleme VSPackages ile Windows Installer](../extensibility/internals/installing-vspackages-with-windows-installer.md) ve ayrıca [bileşen Yönetimi](../extensibility/internals/component-management.md).  
  
    > [!NOTE]
    >  Visual Studio sürümünü yükleme de karşılık gelen bir sürümünü yükler [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Örneğin, Visual Studio 2010 ve Visual Studio 2012 aynı bilgisayara yüklenmesi de 4.0 ve 4.5 sürümlerini yükler [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]sırasıyla.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Paylaşılan ve Sürümü Tutulan VSPackage’lar Arasında Seçim Yapma](../extensibility/choosing-between-shared-and-versioned-vspackages.md)  
 VSPackage yan yana sorunları çözün açıklanmaktadır.  
  
 [Yan Yana Dağıtım için Dosya Adı Uzantılarını Kaydetme](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)  
 VSPackage bir yan yana senaryosunda dosya ilişkilendirmeleri ne kaydolabilirsiniz açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Windows Installer ile VSPackage Yükleme](../extensibility/internals/installing-vspackages-with-windows-installer.md)  
