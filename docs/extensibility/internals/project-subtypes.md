---
title: Proje Subtypes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], subtypes
- project subtypes [Visual Studio SDK]
ms.assetid: d235b47b-cf11-4d47-a63f-e33d9d16105d
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 84d2700e1dfb5d66fb2df6376db9e0ce5352ad4e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="project-subtypes"></a>Proje alt türleri
Proje subtypes özelleştirme veya proje sistemleri davranış flavor izin [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Özelleştirmeleri içeren proje dosyasında ekleme veya öğeleri filtreleme ek verileri kaydetme **Yeni Öğe Ekle** iletişim kutusu, derlemeler nasıl hata ayıklaması ve dağıtılan, denetleme ve projeyi genişletme **özelliği Sayfaları** iletişim kutusu. VSPackages proje alt türleri COM birleştirme kullanarak uygular.  
  
> [!NOTE]
>  Visual C++ proje sistemi proje alt türleri desteklemez. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]kendi SQL Server ve akıllı aygıt projeleri uygulamak için proje subtypes kullanır.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Proje Subtypes tasarım](../../extensibility/internals/project-subtypes-design.md)  
 Proje subtypes kavramını açıklar.  
  
 [Proje Subtypes başlatma sırası](../../extensibility/internals/initialization-sequence-of-project-subtypes.md)  
 Programsal proje alt başlatma sırası tarafından açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ortamı.  
  
 [Özellikleri ve yöntemleri proje alt türleri tarafından Genişletilmiş](../../extensibility/internals/properties-and-methods-extended-by-project-subtypes.md)  
 Ayrıntılı açıklamalar için proje subtypes kullanarak en sık genişletilmiş yöntemleri ve özellikleri sağlar.  
  
 [MSBuild proje dosyası içinde kalıcı veri](../../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)  
 Proje dosyası verilerde sürdürmek nasıl ve nasıl kullanılacağını açıklar <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> proje alt toplama düzeyleri arasında proje dosyasındaki verileri korumak için.  
  
 [Proje özelliği kullanıcı arabirimi](../../extensibility/internals/project-property-user-interface.md)  
 Proje subtypes proje nasıl değiştirebileceğiniz anlatılmaktadır **özellik sayfaları** iletişim kutusu.  
  
 [Temel Project nesne modelini genişletme](../../extensibility/internals/extending-the-object-model-of-the-base-project.md)  
 Proje subtypes Otomasyon nesne modeli genişletmek için Otomasyon Extender'larının nasıl kullanabileceğiniz hakkında bilgi sağlar.  
  
 [Katkıda bulunan yeni öğe Ekle iletişim kutusu](../../extensibility/internals/contributing-to-the-add-new-item-dialog-box.md)  
 Öğeleri eklemeyi açıklar **Yeni Öğe Ekle** iletişim kutusu.  
  
 [Proje dosyalarındaki verileri kaydetme](../../extensibility/saving-data-in-project-files.md)  
 Proje alt nasıl kaydedebilir ve yönetilen paket Framework (MPF) kullanarak proje dosyasında alt özgü verileri almak açıklanmaktadır.  
  
 [Dağıtım işleme özelleştirilmiş](../../extensibility/internals/handling-specialized-deployment.md)  
 Proje subtypes özel dağıtım davranışı uygulayarak nasıl sağlayabilir açıklar <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> arabirimi.  
  
 [Ekleme ve kaldırma özellik sayfaları](../../extensibility/adding-and-removing-property-pages.md)  
 Ekleme ve özellik sayfaları Proje Tasarımcısı'nda kaldırma açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Proje türleri](../../extensibility/internals/project-types.md)  
 Ayrıntılı konulara bağlantılar sağlanır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projeleri.