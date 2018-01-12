---
title: "Araç uzantıları SharePoint programlama modeline genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visual Studio, extending tools
- SharePoint development in Visual Studio, extensibility object models
- SharePoint development in Visual Studio, extending tools
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8eaa1f5d1cfe8120ec6a01c2fe7f646cf90be44a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="overview-of-the-programming-model-of-sharepoint-tools-extensions"></a>SharePoint Araç Uzantılarının Programlama Modeline Genel Bakış
  Visual Studio'da SharePoint araçları için uzantı oluştururken SharePoint araçları tarafından kullanıma sunulan bir veya daha fazla genişletilebilirlik arabirimleri uygulayarak başlar. Çoğu durumda, uzantı özellikleri uygulamak için SharePoint araçları tarafından sağlanan diğer türleri de kullanır. Bazı senaryolarda, Visual Studio ve SharePoint tarafından sağlanan diğer nesne modelleri türlerinde de kullanabilirsiniz. Bu nesne modellerinin her biri amacını anlama ve bunların birbirleriyle SharePoint araçları için Uzantılar oluşturmak için nasıl kullanılacağını bilmeniz gerekir.  
  
## <a name="extending-the-sharepoint-tools-by-implementing-extensibility-interfaces"></a>Genişletilebilirlik arabirimleri uygulayarak SharePoint araçları genişletme  
 Visual Studio için SharePoint araçları genişletilebilirliği modeli sağlamak için .NET Framework 4'te Yönetilen Genişletilebilirlik Çerçevesi (MEF) kullanır. MEF olduğu (System.ComponentModel.Composition derlemede uygulanan) bir API genişletilebilirlik noktaları kullanıma ve bulmak ve çalışma zamanında uzantıları yüklemek uygulamaları etkinleştirir. MEF hakkında daha fazla bilgi için bkz: [Genişletilebilirlik Çerçevesi ile yönetilen &#40; MEF &#41; ](/dotnet/framework/mef/index).  
  
 SharePoint araçları genişletmek için Visual Studio tarafından sunulan bir veya daha fazla genişletilebilirlik arabirimlerini uygular. Ayrıca uygulamalısınız <xref:System.ComponentModel.Composition.ExportAttribute>, ve ek SharePoint araçları özgü arabirimi uygulamanız gerektiğinde, öznitelikleri. Aşağıdaki tabloda, SharePoint araçları genişletmek için uygulayabileceğiniz arabirimlerini listeler.  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider>|Yeni bir SharePoint proje öğesi türünü tanımlamak için bu arabirimi uygular. Bir örnek için bkz: [nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension>|Visual Studio'da yüklü SharePoint proje öğesi türü genişletmek için bu arabirimi uygular. Bir örnek için bkz: [nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension>|SharePoint projeleri genişletmek için bu arabirimi uygular. Bir örnek için bkz: [nasıl yapılır: bir SharePoint proje uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentStep>|Bir SharePoint proje öğesi dağıtıldığında veya geri çekilebilir, yürütülebilir yeni bir dağıtım adımı tanımlamak için bu arabirimi uygular. Bir örnek için bkz: [izlenecek yol: SharePoint projeleri için bir özel dağıtım adımı oluşturma](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeExtension>|Varolan bir düğümü altında genişletmek için bu arabirimi uygulayan **SharePoint bağlantıları** düğümünde **Sunucu Gezgini** penceresi. Bir örnek için bkz: [nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeProvider>|Düğümü altında yeni bir tür tanımlamak için bu arabirimi uygulayan **SharePoint bağlantıları** düğümünde **Sunucu Gezgini** penceresi. Bir örnek için bkz: [nasıl yapılır: Sunucu Gezgininde SharePoint düğümünü genişletme](../sharepoint/how-to-extend-a-sharepoint-node-in-server-explorer.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule>|Bir özel özellik doğrulama kuralı tanımlamak için bu arabirimi uygular. Bir örnek için bkz: [nasıl yapılır: özel özellik oluşturmak ve paket doğrulama kuralları SharePoint çözümleri için](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).|  
|<xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule>|Özel paket doğrulama kuralı tanımlamak için bu arabirimi uygular. Bir örnek için bkz: [nasıl yapılır: özel özellik oluşturmak ve paket doğrulama kuralları SharePoint çözümleri için](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).|  
  
 SharePoint araçları uzantısı uygulandıktan sonra bulmak ve uzantıyı yüklemek Visual Studio etkinleştirmek için Visual Studio Uzantısı (VSIX) paketi uzantı derlemesi dağıtmanız gerekir. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="understanding-the-object-models-that-you-use-in-sharepoint-tools-extensions"></a>Araç uzantılarının SharePoint'te kullandığınız nesne modellerini anlama  
 SharePoint araçları için uzantılarını oluştururken kullanabileceğiniz birçok nesne modelleri vardır:  
  
-   *SharePoint araçları nesne modeli*. Bu nesne modeli SharePoint araç uzantıları ve diğer ilgili türleri oluşturmak için uygulaması genişletilebilirlik arabirimleri sağlar.  
  
-   *Visual Studio Otomasyonu ve tümleştirme nesne modelleri*. SharePoint araçları nesne modeli kapsamı dışındadır Visual Studio özelliklerine erişmek için bu nesne modelleri kullanın.  
  
    > [!NOTE]  
    >  Bazı nesneler Visual Studio Otomasyon nesneleri için SharePoint araçları nesne modeli ve tümleştirme nesne modelleri ve bunun tersi de, SharePoint Proje hizmetini kullanarak dönüştürebilirsiniz. Daha fazla bilgi için bkz: [dönüştürme arasında SharePoint Proje sistem türleri ve diğer Visual Studio Proje türleri](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).  
  
-   *SharePoint sunucu ve istemci nesne modelleri*. Bu nesne modelleri bir SharePoint sitesi değiştirmek veya bir SharePoint araçları uzantısı bağlamında bir SharePoint sitesinden veri almak için kullanın.  
  
### <a name="sharepoint-tools-object-model"></a>SharePoint araçları nesne modeli  
 Her SharePoint araçları uzantı türleri uzantının işlevselliği ve çekirdek davranışını tanımlamak için SharePoint araçları nesne modelinde kullanır. Aşağıdaki tabloda, bu nesne modelinde dahil edilen ad alanlarını açıklar.  
  
|Derleme|Ad Alanı|Açıklama|  
|--------------|---------------|-----------------|  
|Microsoft.VisualStudio.SharePoint.dll|<xref:Microsoft.VisualStudio.SharePoint>|SharePoint Proje sisteminin otomatikleştirmek ve genişletmek için kullandığınız türler içerir. Örneğin, yerleşik SharePoint projeleri ve proje öğelerini genişletme veya kendi proje öğeleri oluşturabilirsiniz. Daha fazla bilgi için bkz: [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md).|  
||<xref:Microsoft.VisualStudio.SharePoint.Deployment>|SharePoint projeleri, kendi dağıtım adımları ve dağıtım yapılandırmaları oluşturma gibi dağıtım işlemi genişletmek için kullandığınız türler içerir. Daha fazla bilgi için bkz: [genişletme SharePoint paketleme ve dağıtım](../sharepoint/extending-sharepoint-packaging-and-deployment.md).|  
||<xref:Microsoft.VisualStudio.SharePoint.Explorer>|Düğümleri altında genişletmek için kullandığınız türleri içeriyor **SharePoint bağlantıları** düğümünde **Sunucu Gezgini** penceresinde veya yeni düğüm türlerini tanımlamak için. Daha fazla bilgi için bkz: [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).|  
||<xref:Microsoft.VisualStudio.SharePoint.Features>|Bir SharePoint proje özellik tanımlarında erişmek için kullandığınız türler içerir.|  
||<xref:Microsoft.VisualStudio.SharePoint.Packages>|Bir SharePoint çözüm paketi tanımında erişmek için kullandığınız türler içerir.|  
||<xref:Microsoft.VisualStudio.SharePoint.Validation>|SharePoint projeleri için özellik ve paket doğrulama davranışını özelleştirmek için kullandığınız türler içerir. Daha fazla bilgi için bkz: [nasıl yapılır: özel özellik oluşturmak ve paket doğrulama kuralları SharePoint çözümleri için](../sharepoint/how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions.md).|  
|Microsoft.VisualStudio.SharePoint.Commands.dll|<xref:Microsoft.VisualStudio.SharePoint.Commands>|Özel oluşturmak için kullanabileceğiniz türlerini içeren *SharePoint komutları*. Bir SharePoint komutu SharePoint sunucusu nesne modelinde bir SharePoint araçları uzantı çağıran bir yöntemdir. Daha fazla bilgi için bkz: [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md).|  
|Microsoft.VisualStudio.SharePoint.Explorer.Extensions.dll|<xref:Microsoft.VisualStudio.SharePoint.Explorer.Extensions>|Yerleşik hakkında bilgi almak için kullanabileceğiniz türleri içeren **Sunucu Gezgini** bileşenleri tek tek bir listesi, alan veya içerik türünü temsil eden bir düğüm gibi bir SharePoint sitesinde temsil eden düğümleri. Daha fazla bilgi için bkz: [Sunucu Gezgininde SharePoint bağlantıları düğümünü genişletme](../sharepoint/extending-the-sharepoint-connections-node-in-server-explorer.md).|  
  
### <a name="visual-studio-automation-object-model"></a>Visual Studio Otomasyon nesne modeli  
 Visual Studio Otomasyon nesne modeli, Visual Studio projeleri otomatikleştirmek için kullanabileceğiniz API'ları ve IDE sağlar. Visual Studio nesne modelini SharePoint projelerine özgü olmayan proje ile ilgili görevleri gerçekleştirmeniz veya Visual Studio'da diğer genel otomasyon görevleri gerçekleştirmek için kullanın. Geleneksel olarak, bu nesne modeli genellikle Visual Studio eklentiler ve makrolar kullanılır, ancak siz de SharePoint araç uzantıları kullanabilirsiniz.  
  
 Visual Studio Otomasyon nesne modeli ana bölümünü EnvDTE.dll derlemesinde tanımlanmıştır. EnvDTE*sürüm*.dll derlemeler belirli Visual Studio sürümlerinde kullanıma sunulan ek işlevsellik sağlar. Bu derlemeler ile Visual Studio dahil edilir.  
  
 Otomasyon nesne modeli hakkında daha fazla bilgi için bkz: [Visual Studio SDK'sı başvurusu](../extensibility/visual-studio-sdk-reference.md).  
  
### <a name="visual-studio-integration-object-model"></a>Visual Studio tümleştirmesi nesne modeli  
 Tümleştirme nesne modeli oluşturarak Visual Studio'ya özellikleri eklemek için kullanabileceğiniz API'ler sağlar bir *VSPackage*. Bir VSPackage aracı windows, düzenleyiciler, tasarımcıları, hizmetleri ve projeleri gibi özel özellikler sağlayarak Visual Studio IDE genişleten bir modüldür.  
  
 Yerleşik SharePoint araçları ile kullanılacak yeni bir Visual Studio özelliğini eklemek istiyorsanız, tümleştirme nesne modelini kullanabilirsiniz. Örneğin, bir SharePoint sitesi için özel bir eylemi temsil eden özel bir SharePoint proje öğesi oluşturursanız, özel eylemi için bir tasarımcı uygulayan bir VSPackage de oluşturabilirsiniz. Özel eylemi temsil eden proje öğesi bir kısayol menü öğesi ekleyerek özel eylem Tasarımcı ilişkilendirebilirsiniz **Çözüm Gezgini**. (Özel eylem projeye sağ tıklanarak öğesi veya bunu seçerek ve ardından SHIFT + F10 tuşlarına) kısayol menüsünü açarak ve ardından, Tasarımcısı açabilirsiniz **açmak**.  
  
 Bu nesne modeli Visual Studio SDK ile birlikte dahil edilen derlemeler kümesini tanımlanır. Bu nesne modeli içindeki ana derlemelerden bazıları Microsoft.VisualStudio.Shell.11.0.dll, Microsoft.VisualStudio.Shell.Interop.dll ve Microsoft.VisualStudio.OLE.Interop.dll içerir.  
  
 Tümleştirme nesne modeli hakkında daha fazla bilgi için bkz: [Otomasyon modeline genel bakış](/visualstudio/extensibility/internals/automation-model-overview) ve [Visual Studio SDK'sı başvurusu](/visualstudio/extensibility/visual-studio-sdk-reference).  
  
### <a name="sharepoint-object-models"></a>SharePoint nesne modelleri  
 SharePoint araç uzantıları SharePoint API'leri bir SharePoint sitesi değiştirmek veya bir SharePoint sitesinden veri almak için kullanabilirsiniz. [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]ve [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] iki farklı nesne modelleri sağlar: bir sunucu nesne modeli ve bir istemci nesne modeli.  
  
 İki nesne modelinde bir SharePoint araçları uzantısında API'leri kullanabilirsiniz, ancak her nesne modeli SharePoint araç uzantıları bağlamında bazı avantajları ve sakıncaları vardır. Daha fazla bilgi için bkz: [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md).  
  
|Nesne modeli|Açıklama|  
|------------------|-----------------|  
|Sunucu nesne modeli|Tüm özellikler erişim sunucusu nesne modeline sağlayan [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] ve [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] programlı olarak kullanıma sunar. Bu nesne modeli, SharePoint sunucu üzerinde çalışan SharePoint çözümlerini tarafından kullanılmak üzere tasarlanmıştır. Bu nesne modeli çoğunun Microsoft.SharePoint.dll derlemesinde tanımlanmıştır. Sunucu nesne modeli hakkında daha fazla bilgi için bkz: [SharePoint Foundation Sunucu tarafı nesne modelini kullanarak](http://go.microsoft.com/fwlink/?LinkId=177796).|  
|İstemci nesne modeli|İstemci nesne modelini uzak istemci veya sunucu SharePoint verileri birlikte çalışmanız için kullanılan sunucu nesne modeli alt kümesidir. Ortak görevleri gerçekleştirmek için yürütülmelidir gidiş dönüş sayısını en aza indirmek için tasarlanmıştır. İstemci nesne modeli çoğunun Microsoft.SharePoint.Client.dll ve Microsoft.SharePoint.Client.Runtime.dll derlemelerde tanımlanır. İstemci nesne modeli hakkında daha fazla bilgi için bkz: [yönetilen istemci nesne modelini](http://go.microsoft.com/fwlink/?LinkId=177797).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da SharePoint araçları genişletme](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [SharePoint nesne modellerini çağırma](../sharepoint/calling-into-the-sharepoint-object-models.md)   
 [SharePoint Proje Hizmetini Kullanma](../sharepoint/using-the-sharepoint-project-service.md)  
  
  