---
title: SharePoint Proje öğeleri için öğe şablonları ve proje şablonları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, creating custom templates
- .spdata files
- projects [SharePoint development in Visual Studio], creating custom templates
- SharePoint projects, creating custom templates
- SharePoint development in Visual Studio, creating custom project and item templates
- project items [SharePoint development in Visual Studio], creating custom templates
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b789072b7a9cc84965e3d78a412631120783b40b
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765214"
---
# <a name="creating-item-templates-and-project-templates-for-sharepoint-project-items"></a>Öğe şablonları ve SharePoint Proje öğeleri için proje şablonları oluşturma
  Özel bir SharePoint Proje öğe türüne tanımladığınızda, diğer geliştiriciler Visual Studio Proje öğesi kullanabilmesi, onu bir öğe şablonu veya bir proje şablonu ile ilişkilendirebilirsiniz. Şablon için bir sihirbaz de oluşturabilirsiniz.  
  
 Örneğin, Visual Studio Proje şablonu veya bir SharePoint sitesine bir alan eklemek için öğe şablonu içermez. Bir alanı temsil eden bir SharePoint Proje öğe türüne tanımlayabilir ve diğer geliştiriciler alanı öğesi bir SharePoint projesine eklemek için kullanabileceğiniz bir öğesi şablonu oluşturun. Veya, geliştiriciler alan öğesini içeren yeni bir SharePoint Proje oluşturabilmesi için bir proje şablonu oluşturabilirsiniz. Her iki durumda da, geliştiricilerin şablonunuzu kullanırken görüntülenen Sihirbazı'nı da sağlayabilir. Bu sihirbaz yeni öğe veya projesini yapılandırma geliştiricilerden bilgi toplayabilir.  
  
 Öğe şablonları ve proje şablonları *.zip* bir proje öğesi veya proje oluşturmak için Visual Studio tarafından kullanılan dosyaları içeren dosyaları. Öğe şablonları ve proje şablonları temelleri hakkında daha fazla bilgi için bkz: [oluşturma proje ve öğe şablonlarını](/visualstudio/ide/creating-project-and-item-templates).  
  
## <a name="create-item-templates"></a>Öğe şablonları oluşturma
 Bir SharePoint proje öğesi için bir öğe şablonu oluşturduğunuzda, bazı her zaman gerekli dosyaları ve belirli türde bir proje öğeleri tarafından kullanılan isteğe bağlı dosyalar vardır. Bir SharePoint Proje öğe türüne tanımlamak ve bir öğe şablonu oluşturmak nasıl izlenecek yol için bkz: [izlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md).  
  
 Aşağıdaki tabloda, bir SharePoint proje öğesi için bir öğe şablonu oluşturmak için gereken dosyalar listelenmektedir.  
  
|Gerekli dosya|Açıklama|  
|-------------------|-----------------|  
|Bir *.spdata* dosyası|Bu içeriği ve proje öğesi varsayılan davranışını belirten bir XML dosyasıdır. Bu dosya öğesi şablonunun eklenmesi gerekir. İçeriği hakkında daha fazla bilgi için *.spdata* dosyaları görmek [SharePoint proje öğesi şema başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md).|  
|A *.vstemplate* dosya.|Bu dosyayı Visual Studio şablon görüntülemek için gereken bilgileri sağlar **Yeni Öğe Ekle** iletişim kutusu ve bir proje öğesi şablonu oluşturun. Bu dosya öğesi şablonunun eklenmesi gerekir. Daha fazla bilgi için bkz: [Visual Studio şablon meta veri dosyaları](http://msdn.microsoft.com/en-us/129d59b5-7f9c-4daf-9832-eaedb3c4c961).|  
|Arabirimini uygulayan bir Visual Studio uzantı derlemesi <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> arabirimi.|Bu derleme proje öğesi çalışma zamanı davranışını tanımlar. Bu derleme öğesi şablonuyla VSIX paketi eklenmesi gerekir. Daha fazla bilgi için bkz: [özel SharePoint proje öğesi türlerini tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md) ve [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).|  
  
 Aşağıdaki tabloda bazı öğesi şablona dahil en sık kullanılan isteğe bağlı dosyalar listelenmektedir. Proje öğeleri bazı türleri burada listelenmeyen diğer dosyaları gerektirebilir.  
  
|İsteğe bağlı bir dosya|Açıklama|  
|-------------------|-----------------|  
|*Elements.XML*|A *özellik öğesi* dosya. Bu dosya, kullanıcı Arabirimi ve proje öğesi tarafından oluşturulan özelleştirme davranışını tanımlar. Her özelleştirme liste örnekleri, içerik türleri veya özel eylemler gibi bu dosyanın içeriğini tanımlayan farklı bir şema türü. Daha fazla bilgi için bkz: [yapı taşı: Özellikler](http://go.microsoft.com/fwlink/?LinkId=169183) ve [özelliği şemaları](http://go.microsoft.com/fwlink/?LinkId=169192).|  
|*Schema.XML*|Liste tanımları için şema dosyası. Daha fazla bilgi için bkz: [yapı taşı: listelerin ve belge kitaplıklarını](http://go.microsoft.com/fwlink/?LinkId=177792) ve [Schema.xml](http://go.microsoft.com/fwlink/?LinkId=177793).|  
|*.WebPart*|A *Web Bölümü tanımı* dosya. Bu dosya Web Bölümü için özellik ayarlarını içerir. Daha fazla bilgi için bkz: [yapı taşı: Web Bölümleri](http://go.microsoft.com/fwlink/?LinkId=177791).|  
|*.ascx*|Bir ASP.NET UserControl dosyası. Bu dosya, Visual Web bölümünün kullanıcı arabirimini tanımlar.|  
|*.aspx*|Bir ASP.NET sayfası dosyası. Bu dosya uygulama sayfası tanımlayan XML biçimlendirme içeriyor.|  
|*.cs* veya *.vb* dosyaları|Bu kod dosyaları Visual C# veya Visual Basic kodu, uygulama sayfaları, Web Bölümleri ve iş akışları gibi erişilebilen bir programlama modeli sahip SharePoint özelleştirmeleri davranışını tanımlar.|  
## <a name="create-project-templates"></a>Proje şablonları oluşturma
 Bir SharePoint Proje şablonu oluşturduğunuzda, belirli türde bir projeler tarafından kullanılan gerekli ve isteğe bağlı dosyaları her zaman kullanılan bazı dosyaları vardır. Genellikle, en az bir SharePoint proje öğesi SharePoint projeleri içerir. Ancak, bu gerekli değildir. Örneğin, yalnızca başka projelerde oluşturulan SharePoint çözümlerini dağıtmak için kullanılması hedeflenen bir SharePoint Proje şablonu tanımlayabilirsiniz.  
  
 Bir SharePoint Proje öğe türüne tanımlamak ve bir proje şablonu oluşturmak nasıl izlenecek yol için bkz: [izlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).  
  
 Aşağıdaki tabloda, bir SharePoint Proje şablonu eklenmelidir dosyaları listelenmektedir.  
  
|Gerekli dosya|Açıklama|  
|-------------------|-----------------|  
|A *.vstemplate* dosyası|Bu dosyayı Visual Studio şablon görüntülemek için gereken bilgileri sağlar **yeni proje** iletişim kutusu ve bir proje şablonu oluşturun. Daha fazla bilgi için bkz: [Visual Studio şablon meta veri dosyaları](http://msdn.microsoft.com/en-us/129d59b5-7f9c-4daf-9832-eaedb3c4c961).|  
|A *.csproj* veya *.vbproj* dosyası|Proje dosyası budur. İçeriği ve projeyi yapılandırma ayarlarını tanımlar.|  
|*Package.Package*|Bu dosya, dağıtım paketi proje için tanımlar. Projeniz için çözüm paketini özelleştirme için paket tasarımcısını kullandığınızda, Visual Studio çözüm paketi hakkındaki verileri bu dosyada depolar.<br /><br /> Özel bir SharePoint Proje şablonu oluşturduğunuzda, yalnızca en az gerekli içeriği eklemeniz önerilir *Package.package* dosya ve API'leri kullanarak çözüm paketi yapılandırma <xref:Microsoft.VisualStudio.SharePoint.Packages> ad alanında proje şablonu ile ilişkili uzantı. Bunu yaparsanız, proje şablonu yapısına gelecekteki değişiklikler korunan *Package.package* dosya. Nasıl oluşturulduğunu gösteren bir örnek bir *Package.package* yalnızca gerekli minimum içerik dosya getirin, bkz: [izlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).<br /><br /> Değişiklik yapmak istiyorsanız *Package.package* doğrudan dosya, şema kullanarak içeriği doğrulayabilirsiniz *% Program Files (x86)%\Microsoft Visual Studio 11.0\Xml\Schemas\PackageModelSchema.xsd* .|  
|*Package.Template.xml*|Bu dosya için çözüm bildirim dosyası temelini (*manifest.xml*) SharePoint çözüm paketi için (*.wsp*) projeden oluşturulur. Proje türü kullanıcılar tarafından değiştirilmesi amaçlanmamıştır bazı davranışı belirtmek istiyorsanız, bu dosyaya içerik ekleyebilirsiniz. Daha fazla bilgi için bkz: [yapı taşı: çözümleri](http://go.microsoft.com/fwlink/?LinkId=169186) ve [çözüm şema](http://go.microsoft.com/fwlink/?LinkId=177794).<br /><br /> Projeye ait bir çözüm paketi oluşturma sırasında Visual Studio içeriğini birleştirir *Package.package* ve *Package.Template.xml* çözümü dosyalarıyla bildirim dosyası. Çözüm paketleri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint çözüm paketi (wsp) oluşturma](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b).|  
  
 Aşağıdaki tabloda Proje şablona dahil isteğe bağlı dosyalar listelenmektedir.  
  
|İsteğe bağlı bir dosya|Açıklama|  
|-------------------|-----------------|  
|SharePoint proje öğeleri|SharePoint proje öğesi türlerini tanımlama bir veya daha fazla .spdata dosyaları içerebilir. Her *.spdata* eşleşen bir dosya olmalıdır <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> uygulama uzantısı derlemedeki proje şablonu VSIX paketi bulunmaktadır. Daha fazla bilgi için bkz: [öğe şablonları oluşturma](#creatingitemtemplates).<br /><br /> Genellikle, en az bir SharePoint proje öğesi SharePoint projeleri içerir. Ancak, bu gerekli değildir.|  
|*{featureName} .feature*|Bu dosya, dağıtım için birkaç proje öğeleri gruplandırmak için kullanılan bir SharePoint özelliğini tanımlar. Bir özellik projenizde özelleştirmek için Özellik Tasarımcısı'nı kullandığınızda, Visual Studio özelliğiyle ilgili veri bu dosyada depolar. Proje öğeleri farklı gruplamanızı istiyorsanız, birden çok içerebilir *.feature* dosyaları.<br /><br /> Özel bir SharePoint Proje şablonu oluşturduğunuzda, yalnızca en az gerekli içeriği her dahil olduğunu öneririz *.feature* dosya ve API'leri kullanarak özellikleri yapılandırma <xref:Microsoft.VisualStudio.SharePoint.Features> ad alanında bir Proje şablonu ile ilişkili uzantı. Bunu yaparsanız, proje şablonu yapısına gelecekteki değişiklikler korunan *.feature* dosya. Nasıl oluşturulduğunu gösteren bir örnek bir *.feature* yalnızca gerekli minimum içerik dosya getirin, bkz: [izlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md).<br /><br /> Değişiklik yapmak istiyorsanız bir *.feature* doğrudan dosya, şema kullanarak içeriği doğrulayabilirsiniz *% Program Files (x86)%\Microsoft Visual Studio 11.0\Xml\Schemas\FeatureModelSchema.xsd*.|  
|*{featureName). Template.XML*|Bu dosya için özellik bildirim dosyası temelini (*Feature.xml dosyasına*) projeden oluşturulan her bir özellik için. Proje türü kullanıcılar tarafından değiştirilmesi amaçlanmamıştır bazı davranışı belirtmek istiyorsanız, bu dosyaya içerik ekleyebilirsiniz. Daha fazla bilgi için bkz: [yapı taşı: Özellikler](http://go.microsoft.com/fwlink/?LinkId=169183) ve [Feature.xml dosyasına](http://go.microsoft.com/fwlink/?LinkId=177795) dosyaları.<br /><br /> Projeye ait bir çözüm paketi oluşturma sırasında Visual Studio her çifti içeriğini birleştirir *{featureName} .feature* dosya ve *{featureName}. Template.xml* bir özellik dosyalarıyla bildirim dosyası. Çözüm paketleri oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint çözüm paketi (wsp) oluşturma](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b).|  
  
## <a name="create-wizards-for-item-templates-and-project-templates"></a>Sihirbazlar için öğe şablonları ve proje şablonları oluşturma
 Bir SharePoint proje öğesi türü tanımlama ve bir öğe veya proje şablonuyla ilişkilendirin sonra bir Sihirbazı da oluşturabilirsiniz. Sihirbaz, bir geliştirici SharePoint proje öğesi için bir proje eklemek için öğe şablonu kullandığında ya da bir geliştirici SharePoint proje öğesi içeren yeni bir proje oluşturmak için proje şablonu kullandığında görüntüler. Sihirbaz, geliştiricilerin bilgi toplamak ve yeni SharePoint proje öğesi başlatmak için kullanılabilir.  
  
 Öğe şablonları ve proje şablonları için sihirbazları oluşturma gösteren talimatlara için bkz: [izlenecek yol: bir öğe şablonu, bölüm 2 ile özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md) ve [izlenecek yol: bir Site oluşturma Sütunu proje öğesi ile bir proje şablonu, bölüm 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
 [Özel SharePoint proje öğesi türlerini tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [İzlenecek yol: bir öğe şablonu, bölüm 1 ile bir özel eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [İzlenecek yol: bir öğe şablonu, bölüm 2 ile özel bir eylem proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [İzlenecek yol: bir proje şablonu, bölüm 1 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [İzlenecek yol: bir proje şablonu, bölüm 2 ile bir Site sütunu proje öğesi oluşturma](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Proje ve Öğe Şablonları Oluşturma](/visualstudio/ide/creating-project-and-item-templates)  
  
 