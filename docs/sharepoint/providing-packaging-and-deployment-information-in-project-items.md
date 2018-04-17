---
title: Paketleme ve dağıtım bilgileri proje öğelerinde sağlama | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.SafeControlEntries
- VS.SharePointTools.Project.ProjectOutputReference
- VS.SharePointTools.Project.FeatureProperties
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, safe controls
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, feature properties
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
- feature properties [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, feature receiver
- feature receiver [SharePoint development in Visual Studio]
- safe controls [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 078715380bb5ddc570d745d76fabe4d8a264eef0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="providing-packaging-and-deployment-information-in-project-items"></a>Proje Öğelerinde Paketleme ve Dağıtım Bilgileri Sağlama
  Tüm SharePoint Proje öğeleri [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] için SharePoint projesi dağıtıldığında ek veri sağlamak için kullanabileceğiniz özellikler vardır. Bu özellikler aşağıdaki gibidir:  
  
-   Özellik özellikleri  
  
-   Özellik alıcıları  
  
-   Proje çıktı başvuruları  
  
-   Güvenli denetim girişleri  
  
 Bu özellikleri görünür **özellikleri** penceresi.  
  
## <a name="feature-properties"></a>Özellik özellikleri  
 Kullanım **özellik özellikleri** özelliğini kullanan verileri belirtmek için özellik. Özellik özellikleri veri SharePoint'e dağıtırken, bir özelliğiyle dahil edilen bir (anahtar/değer çiftleri olarak depolanır) değerler kümesidir. Özellik dağıtıldıktan sonra kodunuzda özellik değerlerini erişebilir.  
  
 Bir proje öğesi için bir özellik özellik değeri eklediğinizde, değer öğesi'nin özellik bildirimi bir öğe olarak eklenir. Bir iş verileri bağlantı (BDC) modeli projesi ModelFileName özellik olarak gibi görünür:  
  
```  
<Property Key="ModelFileName" Value="BdcModel1\BdcModel1.bdcm" />   
```  
  
 Bir özellik değeri ayarlandıktan sonra projenin .spdata dosyasında FeatureProperty öğesi olarak eklenir. SharePoint özelliklerinde erişme hakkında daha fazla bilgi için bkz: [SPFeaturePropertyCollection sınıfı](http://go.microsoft.com/fwlink/?LinkId=177391).  
  
 Aynı özellik özellik değerlerini tüm proje öğelerinden birlikte özelliği bildiriminde birleştirilir. Ancak, iki farklı proje öğeleri eşleşmeyen değerlerle aynı özellik özellik anahtarı belirtirseniz, bir doğrulama hatası meydana gelir.  
  
 Özellik özellikleri doğrudan özellik dosyasına eklemek için (* .feature), çağrı [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint nesne modeli yöntemi <xref:Microsoft.VisualStudio.SharePoint.Features.IPropertyCollection.Add%2A>. Bu yöntemi kullanırsanız, aynı özelliğin özellik değerlerini özelliği özelliklerinde ekleme hakkında aynı kuralın de doğrudan özellik dosyasına eklenen özellikler uygulanacağını unutmayın.  
  
## <a name="feature-receiver"></a>Özellik alıcısı  
 Özellik alıcıları, özellik için bir proje öğesi belirli olaylar oluştuğunda yürütülen kodu içeren ' dir. Örneğin, özelliği yüklendiğinde, etkin veya yükseltilmiş yürütme özellik alıcıları tanımlayabilirsiniz. Özellik alıcısı açıklandığı şekilde doğrudan bir özellik eklemek için eklemenin bir yolu [izlenecek yol: özellik Olay alıcıları ekleme](../sharepoint/walkthrough-add-feature-event-receivers.md). Özellik alıcısı sınıfı adı ve derlemede başvurmak için başka bir yoldur **özellik alıcısı** özelliği.  
  
### <a name="direct-method"></a>Dolaysız Yöntem  
 Özellik alıcısı için bir özellik doğrudan eklediğinizde, bir kod dosyası altına yerleştirilmiş **özelliği** Çözüm Gezgini'nde düğümü. SharePoint Çözümünüzü yapılandırdığınızda, kod bir bütünleştirilmiş koda derler ve SharePoint'e dağıtır. Varsayılan olarak, özellik özellikleri **alıcı derlemesi** ve **alıcı sınıfı** derleme ve sınıf adını başvuru.  
  
### <a name="reference-method"></a>Reference yöntemi  
 Özellik alıcısı eklemek için başka bir yolu kullanmaktır **özellik alıcısı** özelliği bir özellik alıcısı derleme başvurusu için bir proje öğesi. İki alt özellik alıcısı özellik değerine sahip: **derleme** ve **sınıf adı**. Derleme kendi tam kullanmalıdır, tam tür adı "güçlü" adı ve sınıf adı olmalıdır. Daha fazla bilgi için bkz: [Strong-Named derlemeler](http://go.microsoft.com/fwlink/?LinkID=169573). Özelliği için SharePoint çözüm dağıttıktan sonra özellik olayları işlemek için başvurulan özellik alıcısı kullanır.  
  
 Çözüm derleme zamanında, özellik ve projeleri özellik alıcısı özellik değerlerinde SharePoint çözüm (.wsp) dosyası özelliği bildiriminde özellik öğesi ReceiverAssembly ve ReceiverClass özniteliklerini ayarlamak için birleştirir. Bir proje öğesi ve bir özellik derleme ve sınıf adı özelliği değerleri her ikisi de belirtilirse, bu nedenle, proje öğesi ve özellik özellik değerlerini eşleşmesi gerekir. Değerler eşleşmiyorsa bir doğrulama hatası alırsınız. Bir proje öğesi istiyorsanız dışında bir özellik alıcısı derleme başvurusu için onun özellik kullanır, başka bir özellik taşıyın.  
  
 Sunucuda olmayan bir özellik alıcısı derleme başvurusu, derleme dosyası pakette de içermelidir; [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] eklemez onu sizin için. Özellik dağıttığınızda, derleme dosyası ya da sistemin için kopyalanır [!INCLUDE[TLA#tla_gac](../sharepoint/includes/tlasharptla-gac-md.md)] veya SharePoint fiziksel dizini Bin klasörü. Daha fazla bilgi için bkz: nasıl yapılır: [nasıl yapılır: ekleme ve kaldırma ek derlemeler](../sharepoint/how-to-add-and-remove-additional-assemblies.md).  
  
 Özellik alıcıları hakkında daha fazla bilgi için bkz: [özellik olay alıcısı](http://go.microsoft.com/fwlink/?LinkID=169574) ve [özelliği olayları](http://go.microsoft.com/fwlink/?LinkID=169575).  
  
## <a name="project-output-references"></a>Proje çıktı başvuruları  
 Proje çıktı başvuruları özellik proje öğesi çalıştırmak için gereken bir derleme gibi bir bağımlılık belirtir. Örneğin, bir BDC proje ve bir sınıf projesi çözümünüzü olduğunu varsayalım. BDC projesi tarafından sınıfı proje çıktı derleme üzerinde bir bağımlılık varsa, BDC projenin proje çıktı başvuruları özellik derlemede başvuruda bulunabilir. BDC proje paketlendiğinde bağımlı derleme pakete dahil edilir.  
  
 Proje çıktı başvuruları genellikle derlemeleri olan ancak bazı durumlarda (örneğin, Silverlight projeleri) diğer dosya türleri olabilir.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: proje çıktı başvurusu ekleme](../sharepoint/how-to-add-a-project-output-reference.md).  
  
## <a name="safe-control-entries"></a>Güvenli denetim girişleri  
 SharePoint güvenilmeyen kullanıcıların belirli denetimlere erişimi sınırlandırmak için güvenli denetim girişleri olarak adlandırılan bir güvenlik mekanizması sağlar. Tasarım gereği, SharePoint güvenilmeyen kullanıcıların karşıya yükleyin ve SharePoint sunucusu üzerine ASPX sayfaları oluşturmanıza olanak sağlar. Bu kullanıcıların ASPX sayfalar için güvenli olmayan kod eklemesini engellemek için SharePoint erişimlerinin sınırlar *güvenli denetimler*. Güvenli denetimler ASPX denetimleri ve güvenli olarak belirlenmiş Web Bölümleri ve sitenizde herhangi bir kullanıcı tarafından kullanılabilir. Daha fazla bilgi için bkz: [4. adım: Web Bölümünün güvenli denetimler listesine eklemek](http://go.microsoft.com/fwlink/?LinkID=171014).  
  
 Her bir SharePoint Proje öğe [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] adlı bir özelliği vardır **güvenli denetim girişleri** iki Boole alt sahip: **güvenli** ve **karşı güvenli betik**. Güvenli özellik güvenilmeyen kullanıcıların bir denetim erişip erişemeyeceğini belirler. Karşı güvenli betik özellik güvenilmeyen kullanıcıların görüntüleyebilir ve bir denetimin özelliklerini değiştirme olup olmadığını belirtir.  
  
 Güvenli denetimi girdileri bir derleme temelinde başvurulur. Proje öğenin girerek bir projenin derlemeye güvenli denetimi girdileri eklemek **güvenli denetim girişleri** özelliği. Ancak, aynı zamanda güvenli denetim girişleri bir projenin derleme ekleyebileceğiniz **Gelişmiş** sekmesinde **paket tasarımcısını** paketi ek bütünleştirilmiş eklediğinizde. Daha fazla bilgi için bkz: [nasıl yapılır: işareti denetimleri güvenli denetim olarak](../sharepoint/how-to-mark-controls-as-safe-controls.md) veya [güvenli bir denetim olarak bir Web Bölümü derlemesi kaydetme](http://go.microsoft.com/fwlink/?LinkID=171013).  
  
### <a name="xml-entries-for-safe-controls"></a>Güvenli denetimler için XML girişleri  
 Bir proje öğesi veya projenin derleme güvenli denetim girdisi eklediğinizde, bir başvuru paket bildirimi aşağıdaki biçimde yazılır:  
  
```xml  
<Assemblies>  
    <Assembly Location="<assembly name>.dll"     
      DeploymentTarget="<'GlobalAssemblyCache' or 'WebApplication'">>  
        <SafeControls>  
            <SafeControl Assembly="<assembly name>.dll" Namespace=  
              "<SharePoint project name>" Safe="<true/false>"     
                TypeName="<control name>"   
                SafeAgainstScript="<true/false>" />  
        </SafeControls>  
    </Assembly>  
</Assemblies>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paketleme ve SharePoint çözümlerini dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [Çözümde dosyaları eklemeyi modüllerini kullanma](../sharepoint/using-modules-to-include-files-in-the-solution.md)   
 [SharePoint Paketleme ve Dağıtımını Genişletme](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  