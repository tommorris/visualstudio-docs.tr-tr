---
title: "Proje türleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project types, new
- projects [Visual Studio SDK], new project types
ms.assetid: bdb2d22e-d622-450c-bb2d-98152a745fcf
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f7c0bba9b80e4e874f222ce00834f44a2d93e3e7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-project-types"></a>Proje türleri oluşturma
Genişletebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yeni bir proje türü oluşturarak. Yeni bir proje türü oluşturmak için birkaç kavramları anlamanız ve birkaç adımı tamamlamanız gerekir. Aşağıdaki konular proje türleri oluşturmak nasıl bir bakış sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Proje türü tasarım kararları](../../extensibility/internals/project-type-design-decisions.md)  
 Öğesi, proje dosyası Kalıcılık ve yeni bir proje türü oluşturmadan önce yapmak zorunda taahhüt teknisyenin tasarım kararları anlatılmaktadır.  
  
 [Denetim listesi: Yeni proje türleri oluşturma](../../extensibility/internals/checklist-creating-new-project-types.md)  
 Kod düzenleme ve derlerken, derleme, hata ayıklama ve projenizdeki uygulamaları dağıtma programlama görevleri destekleyen yeni bir proje türü oluşturmak için izlemeniz gereken adımları genel bir bakış sağlar.  
  
 [Proje Fabrikalarını kullanarak proje örnekleri oluşturma](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)  
 Sağlamak ve yeni bir proje örneklerini oluşturmak için bir proje fabrikası kullanma hakkında bilgi sağlar.  
  
 [Proje türü kaydetme](../../extensibility/internals/registering-a-project-type.md)  
 Kod örnekleri, her deyim için kayıt defteri komut dosyası girişlerinden içeren varsayılan yolları ve veri ve bir tablo sağlayan deyimleri kayıt defterinden sağlar.  
  
 [Proje kalıcılığı](../../extensibility/internals/project-persistence.md)  
 Kullanımı anlatılmaktadır `IPersistFileFormat` hem dosya hem de dosya tabanlı olmayan proje nesneleri kalıcı hale getirmek için.  
  
 [MSBuild kullanma](../../extensibility/internals/using-msbuild.md)  
 Proje türüne nasıl kullanabileceğinizi açıklar [!INCLUDE[vstecmsbuild](../../extensibility/internals/includes/vstecmsbuild_md.md)] gelen derleme kullanıcıların izin verecek şekilde altyapısının yapı [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve komut satırı.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Simgenin tarama araçları destekleme](../../extensibility/internals/supporting-symbol-browsing-tools.md)  
 Kod araçları gibi görüntüleme mimarisini açıklar **Nesne Tarayıcısı** ve **sınıf görünümü** penceresi. Gözatma nesnesi bir VSPackage uygulamak için kullanılan yöntemleri ve arabirimler açıklanmaktadır.  
  
 [Proje ve proje öğesi şablonları ekleme](../../extensibility/internals/adding-project-and-project-item-templates.md)  
 Bir proje öğesi açıldığında hangi Düzenleyicisi kullanılır belirlerken projeleri yürütmek önemi açıklanır ve nasıl proje kaynakları yönetilebilir.  
  
 [Windows Installer ile VSPackages yükleme](../../extensibility/internals/installing-vspackages-with-windows-installer.md)  
 Benzersiz kimliğini, VSPackage vermek ve bir Windows Installer paketinde VSPackage DLL'ler ve diğer bilgileri sarmalama gösterir (. MSI dosyası) dağıtım müşterileriniz için.  
  
 [Visual Studio'da hiyerarşileri](../../extensibility/internals/hierarchies-in-visual-studio.md)  
 Açıklar nasıl [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] görünümleri ve adresleri hiyerarşileri.  
  
 [VSPackages](../../extensibility/internals/vspackages.md)  
 Bir VSPackage genişletir yüklenebilir bir COM nesnesi genel bir bakış sağlar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ortamı ve nasıl kendi VSPackage uygulanacağını anlatır.  
  
 [Proje türleri](../../extensibility/internals/project-types.md)  
 Projeleri kodu değiştirin, derleme ve kod, derleme ve çalıştırma ve kodda hata ayıklama için nasıl kullanılacağı açıklanır ve proje türleri oluşturma hakkında ayrıntılı konulara bağlantılar sağlar.