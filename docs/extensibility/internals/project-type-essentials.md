---
title: "Proje türü Essentials | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: project types [Visual Studio SDK]
ms.assetid: 09991589-2300-430e-b6a4-7f2b95fe676f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 33f31ec1d5adedb2fac6c2a37c050ee65d774894
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="project-type-essentials"></a>Proje türü temelleri
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]diller için birkaç proje türleri gibi içerir [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] veya [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Ayrıca, kendi proje türleri oluşturmanıza olanak tanır.  
  
 Özel komutlar, düzenleyiciler veya aracı windows eklemek istiyorsanız, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], yeni bir proje türü oluşturmadan bunu yapabilirsiniz. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Komutları, menüleri ve araç çubukları](../../extensibility/internals/commands-menus-and-toolbars.md)  
  
-   [Düzenleyici ve dil hizmeti uzantıları](../../extensibility/editor-and-language-service-extensions.md)  
  
-   [Genişletme ve aracı Windows özelleştirme](../../extensibility/extending-and-customizing-tool-windows.md)  
  
 Benzer şekilde, sağlanan davranışını özelleştirmek istiyorsanız [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] yapabileceğiniz proje türleri, proje türlerinde bunu kullanarak. Daha fazla bilgi için bkz: [proje Subtypes](../../extensibility/internals/project-subtypes.md).  
  
 Bir dil dışındaki alan projeler için yeni bir proje türü oluşturmalısınız [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] bir veya daha fazlasını desteklemek istiyorsanız:  
  
-   Derleme  
  
-   Dağıtım  
  
-   Birden fazla yapılandırma  
  
-   Kaynak denetimi  
  
-   Hata Ayıklama  
  
-   Çözüm Gezgini'nde proje öğeleri  
  
-   **Proje Aç** veya **yeni proje** iletişim kutuları  
  
-   Proje iç içe geçme  
  
-   Proje türleri özellikleri hakkında daha fazla bilgi için aşağıdakilere bakın:  
  
-   Proje türleri olan arabirimler kümesi uygulayan bir VSPackage nesneleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bekliyor. C# proje türü geliştirmek için kullanıyorsanız, paketi çerçevesi ile yönetilen proje sınıfları sizin için gerekli arabirimleri uygulamak ve o uygulama devral olanak verir. Daha fazla bilgi için bkz: [proje türü (C#) uygulamak için yönetilen paket Framework kullanılarak](../../extensibility/internals/using-the-managed-package-framework-to-implement-a-project-type-csharp.md).  
  
-   C++ geliştiricileri için HierUtil Kitaplığı'ndaki sınıflar benzer bir şekilde çalışır. Daha fazla bilgi için bkz: [yapı içinde değil: Proje türü (C++) uygulamak için HierUtil7 proje sınıflarını kullanarak](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346).  
  
-   Proje türleri bir .exe veya .dll derlemeye yapı tipik kaynak kodu dosyaları dışında veri destekleyebilir. Örneğin, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] veritabanı projeleri diskte depolanan komut dosyası ve sorgu dosyalarına yapılan başvurular içerir ve komutlarını ekleyin **Çözüm Gezgini** yürütmek için bir veritabanı, ancak projeleri sorguları ve komut dosyalarını desteklemiyor davranış oluşturun. Daha fazla bilgi için bkz: [açma ve kaydetme proje öğeleri](../../extensibility/internals/opening-and-saving-project-items.md).  
  
-   Tüm dosyaları kullanmak bir proje türü yok. Örneğin, bir proje türü tüm verileri bir veritabanında saklayabilirsiniz. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Proje türleri proje ve proje öğeleri için verileri nasıl kalıcı üzerinde tam denetim verir. Daha fazla bilgi için bkz: [proje türü tasarım kararları](../../extensibility/internals/project-type-design-decisions.md).  
  
-   Proje türleri sağlamalıdır bir *proje Fabrika*, projenin bir örneğini oluşturur nesneyi olduğu her tür [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] açmak veya bu proje türüne göre bir proje oluşturmak için bildirilir. Daha fazla bilgi için bkz: [oluşturma proje örnekleri tarafından kullanarak proje Fabrikalarını](../../extensibility/internals/creating-project-instances-by-using-project-factories.md).  
  
-   Proje türleri, projeler ve proje öğeler için şablonlar sağlamanız gerekir. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Kullanıcılar yeni projeler oluşturun ve yeni öğeler eklemek için var olan projelerin şablonları kullanır. Daha fazla bilgi için bkz: [ekleme proje ve proje öğesi şablonları](../../extensibility/internals/adding-project-and-project-item-templates.md).  
  
-   Proje türleri hata ayıklama ve yayın gibi birden çok yapılandırmayı destekler. Kullanıcılar, sağladığınız özellik sayfalarını kullanarak bir proje farklı yapılandırmaları değiştirebilirsiniz. Daha fazla bilgi için bkz: [yönetme yapılandırma seçenekleri](../../extensibility/internals/managing-configuration-options.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje türleri dağıtma](../../extensibility/internals/deploying-project-types.md)