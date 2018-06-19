---
title: Özellikler genişletme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, providing support
ms.assetid: 68e2cbd4-861c-453f-8c9f-4ab6afc80e67
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d1a34edfbc6cede24f3238068549412d630827cd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31131668"
---
# <a name="extending-properties"></a>Genişletme özellikleri
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **Özellikleri** penceresi COM ve COM + bileşenleri için evrensel özellik tarayıcısı ve tüm destekler [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ürünler. **Özellikleri** penceresi çalışır `ITypeInfo` bilgi ve herhangi bir tümleşik geliştirme ortamı (IDE) penceresinde seçili nesne için tasarım zamanı özellikleri listelemek için COM + meta verileri yazın.  
  
 **Özellikleri** F4 klavyedeki veya seçerek açılır pencere **Özellikler penceresini** üzerinde **Görünüm** menüsünde görüntülemek ve düzenlemek için kullanılır Yapılandırma bağımsız, tasarım zamanı özellikleri ve olayları seçili nesnelerin. Çözümler ve projeler, ile ilişkili yapılandırma bağımlı özellikler görüntülenir [özellik sayfaları](../../extensibility/internals/property-pages.md). Daha fazla bilgi için [yönetme yapılandırma seçenekleri](../../extensibility/internals/managing-configuration-options.md).  
  
 ![Özellikler penceresi genel bakış](../../extensibility/internals/media/vspropertieswindow.png "vsPropertiesWindow")  
Özellik penceresi  
  
 Bu bölümde, tek tek alanlarına ilgili ayrıntılı bilgiler sağlar **özellikleri** penceresi ve uygulamanız gereken arabirimleri ve pencereyi doldurmak için çağrı.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Özellikler Penceresine Genel Bakış](../../extensibility/internals/properties-window-overview.md)  
 Amacını açıklayan **özellikleri** araç ve belge penceresinde göre penceresi.  
  
 [Şablon İlkesi ve Özellikler Penceresi](../../extensibility/internals/template-policy-and-the-properties-window.md)  
 Bir proje kurumsal şablon projesinde nasıl bulunur ve bu kurumsal Şablonu proje ilke nasıl uygulayabilir açıklanır.  
  
 [Özellikler Penceresi Alanları ve Arabirimleri](../../extensibility/internals/properties-window-fields-and-interfaces.md)  
 Hangi bilgilerin görüntüleneceğini belirler seçimi için temel açıklar **özellikleri** penceresi.  
  
 [Özellikler Penceresi Nesne Listesi](../../extensibility/internals/properties-window-object-list.md)  
 Amacını açıklayan **özellikleri** pencere nesnesi listesi açıklayan bir çağrı bu listeden farklı bir nesne tetikler, nasıl ortamında yeni bir nesne seçili bilgilendirilir.  
  
 [Özellikler Penceresi Düğmeleri](../../extensibility/internals/properties-window-buttons.md)  
 Görüntülenen dört varsayılan düğmeleri amacını açıklayan **özellikleri** penceresi araç.  
  
 [Özellikler Görüntü Kılavuzu](../../extensibility/internals/properties-display-grid.md)  
 Özellik adları ve özellik değerlerini alanları kılavuzda burada bulunan açıklanmaktadır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Proje Türleri](../../extensibility/internals/project-types.md)  
 Projeleri yapı taşları olarak ele alınmıştır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 [Derleme ve Oluşturma](../../ide/compiling-and-building-in-visual-studio.md)  
 Nasıl kullanabileceğinizi açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sürekli test ve bunları oluşturmak gibi uygulamalarında hata ayıklama için Platform.  
  
 [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx)  
 Açıklar `IDispatch` ilk erişmek ve bir nesne özellikleri ve yöntemleri hakkında bilgi almak için geç bağlama mekanizma sağlamadan Otomasyonu desteklemek için tasarlanmış arabirim.  
  
 [Uygulama ayarları (.NET) yönetme](../../ide/managing-application-settings-dotnet.md)  
 Özellik değerleri uygulamanın derlenmiş kod yerine bir dış yapılandırma dosyasında depolanır, böylece uygulamanız yapılandırmanıza imkan sağlayan uygulama ayarlarına genel bakış sağlar.  
  
 [Çözümler ve projeler](../../ide/solutions-and-projects-in-visual-studio.md)  
 Açıklar nasıl [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] başvuruları, veri bağlantıları, klasörler ve geliştirme çabanızı çözümler ve projeler aracılığıyla tarafından gerekli olan dosyalar gibi öğeleri yönetir.  
  
 [Visual Studio’nun Diğer Bölümlerini Genişletme](../../extensibility/extending-other-parts-of-visual-studio.md)  
 Nasıl kullanılacağı açıklanmaktadır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kalan eşleşen kullanıcı Arabirimi öğeleri oluşturmak için Sertifika Hizmetleri'ni [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].