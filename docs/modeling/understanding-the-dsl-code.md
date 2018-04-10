---
title: DSL kodu anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, generated code
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 41cf1f19e03c1197c6266b5057af993b677c9c53
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="understanding-the-dsl-code"></a>DSL Kodunu Anlama
Bir etki alanına özgü dil (DSL) çözümü okumak ve DSL örneklerini güncellemek için kullanabileceğiniz bir API üretir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bu API DSL tanımından oluşturulan kodda tanımlanır. Bu konuda oluşturulan API açıklanmaktadır.  
  
## <a name="the-example-solution-component-diagrams"></a>Örnek bir çözüm: Bileşen diyagramları  
 Bu konudaki örnekler çoğunu kaynak çözümü oluşturmak için gelen DSL oluşturun **bileşen modelleri** çözüm şablonu. Bu, yeni bir DSL çözüm oluşturduğunuzda görüntülenen standart şablonları biridir.  
  
> [!NOTE]
>  Bileşen diyagramları DSL şablonu Visual Studio'da mimarisi menüsünü kullanarak oluşturabileceğiniz UML Bileşen diyagramları ilgili değildir. İçinde **yeni proje** iletişim kutusunda, genişletin **diğer proje Types\Extensibility** ve ardından **etki alanına özgü dil Tasarımcısı**.  
  
 Bu çözüm şablonla bilmiyorsanız F5, deneme, basın. Bir bileşenin üzerine bir bağlantı noktası aracını sürükleyerek bağlantı oluşturmak ve bağlantı noktaları bağlanabilir özellikle dikkat edin.  
  
 ![Bileşenleri ve birbirine bağlı bağlantı noktaları](../modeling/media/componentsample.png "ComponentSample")  
  
## <a name="the-structure-of-the-dsl-solution"></a>DSL Çözüm yapısı  
 **Dsl** proje için DSL API tanımlar. **DslPackage** proje tanımlar nasıl ile tümleştirilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Modelden oluşturulan kod de içerebilir kendi projeleri de ekleyebilirsiniz.  
  
### <a name="the-code-directories"></a>Kod dizinleri  
 Bu projelerin her biri kodda çoğunu oluşturulduğu **Dsl\DslDefinition.dsl**. Oluşturulan kod **oluşturulan kod** klasör. Oluşturulmuş bir dosya görmek için tıklatın **[+]** oluşturma yanındaki **.tt** dosya.  
  
 DSL anlamanıza yardımcı olması için oluşturulan kodu incelemenizi öneririz. Oluşturulan dosyalar görmek için Çözüm Gezgini'nde *.tt dosyaları genişletin.  
  
 \*.Tt dosyaları çok az şablonunuzda kod içerir. Bunun yerine, kullandıkları `<#include>` yönergeleri paylaşılan şablon dosyalarını içerir. Paylaşılan dosyaları bulunabilir **\Program Visual Studio 10.0\Common7\IDE\Extensions\Microsoft\DSL SDK\DSL Designer\11.0\TextTemplates**  
  
 Kendi program kodunu DSL çözüme eklediğinizde, oluşturulan kod klasörünün dışında ayrı bir dosya ekleyin. Oluşturmak istediğiniz durumlarda bir **özel kod** klasör. (Yeni bir kod dosyası özel bir klasöre eklediğinizde, ad alanında ilk kod çatıyı düzeltmek unutmayın.)  
  
 Çözümü yeniden oluşturduğunuzda düzenlemeleriniz kaybolacağı için oluşturulan kodun doğrudan düzenlemenizi öneririz. Bunun yerine, DSL özelleştirmek için:  
  
-   DSL tanımında birçok parametreleri ayarlayın.  
  
-   Kısmi sınıflar ayrı kod dosyalarında tanımlanan veya oluşturulan sınıflar tarafından devralınır geçersiz kılma yöntemleri yazma. Bazı durumlarda, ayarlamanız gerekir. **oluşturur çift türetilmiş** oluşturulan yöntemi geçersiz kılmak için DSL tanımındaki bir sınıfın seçeneği.  
  
-   Oluşturulan kodun 'kancaları' sağlamak için kendi kodunuzu neden DSL tanımında seçeneklerini ayarlayın.  
  
     Örneğin, ayarlarsanız **sahip özel Oluşturucu** seçeneği bir etki alanı sınıfının ve çözümü oluşturmak, hata iletisi görürsünüz. Bu hata iletilerinden birini çift tıkladığınızda ne özel kodunuzu sağlamalıdır açıklayan oluşturulan kodu açıklamaları görürsünüz.  
  
-   Uygulamanıza özel kodu oluşturmak için kendi metin şablonları yazma. Kullanım çok sayıda proje için ortak olan şablonları bölümlerini paylaşmak için dosyalar içerebilir ve oluşturabileceğiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje şablonlarını kendi dosya yapısı ile başlatılmış projeleri ayarlayın.  
  
## <a name="generated-files-in-dsl"></a>Dsl oluşturulan dosyaları  
 Aşağıdaki oluşturulan dosyaları görünür **Dsl** projesi.  
  
 *YourDsl* `Schema.xsd`  
  
 DSL örneklerini içeren dosyalar için şema. Bu dosya için derleme kopyalanır (**bin**) dizini. DSL yüklediğinizde, bu dosyaya kopyalayabilirsiniz **\Program Visual Studio 11.0\Xml\Schemas** böylece model dosyalarında doğrulanabilir. Daha fazla bilgi için bkz: [etki alanına özgü dil çözümleri dağıtma](../modeling/deploying-domain-specific-language-solutions.md).  
  
 Seri hale getirme DSL Explorer'da seçeneklerini ayarlayarak özelleştirirseniz şema uygun şekilde değiştirir. Ancak, kendi seri hale getirme kodu yazarsanız, bu dosya artık gerçek şema gösterebilir. Daha fazla bilgi için bkz: [özelleştirme dosya depolama ve XML serileştirme](../modeling/customizing-file-storage-and-xml-serialization.md).  
  
 `ConnectionBuilders.cs`  
  
 Bir bağlantı Oluşturucu ilişkileri oluşturan bir sınıftır. Bağlantı aracını arkasında kodudur. Bu dosya her bağlantı aracı için sınıflar çifti içerir. Adları etki alanı ilişki ve bağlantı aracını adlarından türetilen: *ilişki*oluşturucusu ve *ConnectorTool*ConnectAction.  
  
 (Bileşen çözüm örnekte, bağlantı oluşturucular birini ConnectionBuilder çağrılır, etki alanı ilişkisinin Bağlantısı adlı bir rastlantı olmasıdır.)  
  
 İlişki oluşturulan *ilişki* `Builder.Connect()` yöntemi. Varsayılan sürüm, kaynak ve hedef model öğelerini kabul edilir ve ilişki başlatır doğrular. Örneğin:  
  
 `CommentReferencesSubject(sourceAccepted, targetAccepted);`  
  
 Her Oluşturucusu sınıfının bir düğümden oluşturulan **bağlantı oluşturucular** DSL Explorer bölümünde. Bir `Connect` yöntemi, bir veya daha fazla etki alanı sınıflarını çiftleri arasındaki ilişkileri oluşturabilir. Her bir çifti bir bağlantı bağlanma Oluşturucu düğümünde DSL Explorer'da bulabileceğiniz yönergesi göre tanımlanır.  
  
 Örneğin, örnek DSL ilişkisinde üç türlerinin her biri için bir bağlantı Oluşturucu bağlantı bağlanma yönergeleri ekleyebilirsiniz. Bu kullanıcı bir tek bağlantı aracı sağlar. Kullanıcı tarafından seçilen kaynak ve hedef öğe türleri üzerinde örneği ilişki türüne bağlıdır.  Bağlantı bağlanma yönergeleri eklemek için bir oluşturucu DSL Explorer'da sağ tıklatın.  
  
 Belirli bir etki alanı ilişki türü oluşturulduğunda, çalışan özel kod yazmak için uygun bağlantıyı bağlanmak yönergesi Oluşturucusu düğümünde seçin. Özellikler penceresinde ayarlayın **kullanan özel bağlanma**. Çözümü yeniden derleyin ve sonra sonuçta ortaya çıkan hataları düzeltmek için kodu girin.  
  
 Kullanıcı Bu bağlantı aracı kullandığında çalıştırılan özel kod yazmanıza izin ayarlamak **olan özel** Bağlantı oluşturucu özelliği. Source öğesi, belirli bir kaynak bileşimini olup olmadığını izin verilir ve hedef izin verilir ve bir bağlantı yapıldığında hangi güncelleştirmelerin modele yapılmalıdır olup olmadığını karar kod sağlayabilir. Örneğin, yalnızca, bir döngü diyagramda oluşturacak değil, bir bağlantı izin verebilir. Çoklu ilişki bağlantısı yerine, kaynak ve hedef arasında çeşitli arası ilgili öğelerinin daha karmaşık bir desen örneği oluşturulamadı.  
  
 `Connectors.cs`  
  
 Genellikle başvuru ilişkileri gösteren diyagram öğeler bağlayıcıları için sınıflar içerir. Her sınıf DSL tanımındaki bir bağlayıcı oluşturulur. Öğesinden türetilen her bağlayıcı sınıfı <xref:Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape>  
  
 Rengi ve başka bazı stil özellikleri değişken çalışma zamanında kullanabilmek için DSL tanımı diyagramında sınıfı sağ tıklatın ve işaret **eklemek açığa**.  
  
 Çalışma zamanında ek stil özellikleri değişken yapmak için örneğin bkz <xref:Microsoft.VisualStudio.Modeling.Diagrams.TextField> ve <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement>.  
  
 `Diagram.cs`  
  
 Diyagram tanımlar sınıfı içerir. Öğesinden türetilen <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram>.  
  
 Rengi ve başka bazı stil özellikleri değişken çalışma zamanında kullanabilmek için DSL tanımı diyagramında sınıfı sağ tıklatın ve işaret **eklemek açığa**.  
  
 Ayrıca, bu dosyayı içeren `FixupDiagram` modele yeni bir öğe eklendiğinde, yanıt kuralı. Kural bir şekil ekler ve Şekil model öğesine bağlar.  
  
 `DirectiveProcessor.cs`  
  
 Bu yönerge işlemcisi, DSL örneğini okuma metin şablonları yazma kullanıcılarınıza yardımcı olur. Yönerge işlemcisi, DSL derlemelerde (dll) yükler ve etkili bir şekilde ekler `using` deyimleri ad alanınız için. Bu kod, DSL içinde tanımlanan ilişkileri ve sınıfların kullanmak için metin şablonları sağlar.  
  
 Daha fazla bilgi için bkz: [bir etki alanına özgü dil oluşturma koddan](../modeling/generating-code-from-a-domain-specific-language.md) ve [özel T4 metin şablonu yönerge işlemciler oluşturma](../modeling/creating-custom-t4-text-template-directive-processors.md).  
  
 `DomainClasses.cs`  
  
 Soyut sınıflar ve model kök sınıfı dahil olmak üzere tanımlamış olduğunuz etki alanı sınıflarını uygulamaları. Öğesinden türetilen <xref:Microsoft.VisualStudio.Modeling.ModelElement>.  
  
 Her etki alanı sınıfı içerir:  
  
-   Özellik tanımı ve her bir etki alanı özellik için bir iç içe geçmiş işleyici sınıfı. OnValueChanging() ve OnValueChanged() geçersiz kılabilirsiniz. Daha fazla bilgi için bkz: [etki alanı özellik değeri değişiklik işleyicileri](../modeling/domain-property-value-change-handlers.md).  
  
     DSL, örnekteki `Comment` sınıfı içeren bir özellik `Text` ve bir işleyici sınıfı `TextPropertyHandler`.  
  
-   Bu etki alanı sınıfı içinde yer aldığı ilişkileri erişimci özellikleri. (Rol özellikleri için hiçbir iç içe geçmiş sınıf yoktur.)  
  
     DSL, örnekteki `Comment` sınıfına sahip katıştırma ilişkisi kendi üst modelini erişim erişimciler `ComponentModelHasComments`.  
  
-   Oluşturucular. Bu geçersiz kılmak istiyorsanız, Ayarla **sahip özel Oluşturucu** etki alanı sınıfı.  
  
-   Öğeyi Grup prototip (EGP) işleyici yöntemleri. Bu kullanıcı yapabiliyorsanız, gerekli *birleştirme* (Ekle) bu sınıfın örnekleri, üzerine başka bir öğe. Genellikle kullanıcı bu öğe aracına veya başka bir şekil sürükleyerek veya yapıştırarak yapar.  
  
     Örnekte DSL, bir giriş veya çıkış bağlantı noktasına bir bileşen üzerine birleştirilebilir. Ayrıca, bileşenleri ve açıklamaları model birleştirilebilir. Bu  
  
     Bileşen sınıfı EGP işleyici yöntemleri bağlantı noktaları, ancak değil açıklamaları kabul etmek bir bileşen izin verin. Kök model sınıfı EGP işleyicisinde açıklamaları ve bileşenleri, ancak olmayan bağlantı noktalarını kabul eder.  
  
 `DomainModel.cs`  
  
 Etki alanı modeli temsil eden sınıf. Öğesinden türetilen <xref:Microsoft.VisualStudio.Modeling.DomainModel>.  
  
> [!NOTE]
>  Bu modelin kök sınıf ile aynı değildir.  
  
 Kopyalama ve silme kapanışlar tanımlayın diğer öğeleri olması gereken bir öğe kopyalandığında veya dahil. Ayarlayarak bu davranışı denetleyebilirsiniz **yayar kopyalama** ve **yayar silme** rollerinin her ilişki her tarafında özelliklerini. Dinamik olarak belirlenecek değerleri istiyorsanız, kapatma sınıflarının yöntemleri geçersiz kılmak üzere kod yazabilirsiniz. 
  
 `DomainModelResx.resx`  
  
 Bu, etki alanı sınıfları ve özellikleri, özellik adları, araç kutusu etiketleri, standart hata iletileri ve kullanıcıya görüntülenen diğer dizeleri açıklamalarını gibi dizeleri içerir. Ayrıca, aracı simgeleri ve görüntüleri görüntü şekiller için de içerir.  
  
 Bu dosya, yerleşik derlemeye bağlı ve bu kaynakları, varsayılan değerleri sağlar. Kaynakları yerelleştirilmiş bir sürümünü içeren bir uydu derleme oluşturarak, DSL yerelleştirebilirsiniz. DSL yerelleştirilmiş kaynaklar eşleşen bir kültür yüklendiğinde, bu sürüm kullanılacak. Daha fazla bilgi için bkz: [etki alanına özgü dil çözümleri dağıtma](../modeling/deploying-domain-specific-language-solutions.md).  
  
 `DomainRelationships.cs`  
  
 Bir modeldeki iki öğeler arasındaki her bir bağlantının bir etki alanı ilişki sınıfının bir örneği temsil edilir. Öğesinden türetilmiş tüm ilişkisi sınıflar <xref:Microsoft.VisualStudio.Modeling.ElementLink>, sırayla türetilen <xref:Microsoft.VisualStudio.Modeling.ModelElement>. Bir model öğesi olduğundan, bir ilişki örneği özelliklere sahip olabilir ve kaynak veya hedef ilişkisi olabilir.  
  
 `HelpKeywordHelper.cs`  
  
 Kullanıcı F1 tuşuna bastığında kullanılan işlevleri sağlar.  
  
 `MultiplicityValidation.cs`  
  
 İlişki rolleri 1..1 ya da 1 çokluğu belirlediğiniz.. *, kullanıcı uyarı ilişki en az bir örneğini gereklidir. Bu dosya bu uyarılar uygulayan doğrulama kısıtlamaları sağlar. 1..1 katıştırma üst bağlantı doğrulanamadı.  
  
 Bu kısıtlamaların yürütülmesi, aşağıdakilerden birini ayarlamış olmanız gerekir **kullanan...**  içinde seçenekleri **Editor\Validation** DSL Gezgininde düğümü. Daha fazla bilgi için bkz: [bir etki alanına özgü dil doğrulama](../modeling/validation-in-a-domain-specific-language.md).  
  
 `PropertiesGrid.cs`  
  
 Yalnızca bir etki alanı özelliği için bir özel tür tanımlayıcı eklediyseniz, bu dosyayı kodunu içerir. Daha fazla bilgi için bkz: [Özellikler penceresini özelleştirme](../modeling/customizing-the-properties-window.md).  
  
 `SerializationHelper.cs`  
  
-   İki öğe aynı ad tarafından başvurulduğundan emin olmak için bir doğrulama yöntemi. Daha fazla bilgi için bkz: [özelleştirme dosya depolama ve XML serileştirme](../modeling/customizing-file-storage-and-xml-serialization.md).  
  
-   SerializationHelper sınıf ortak serileştirme sınıfları tarafından kullanılan işlevler sağlar.  
  
 `Serializer.cs`  
  
 Her etki alanı sınıfı, ilişki, şekil, bağlayıcı, Diyagram ve model için seri hale getirici sınıfı.  
  
 Bu sınıfların özelliklerinin çoğu DSL Explorer altında ayarlar tarafından denetlenebilir **Xml serileştirme davranış**.  
  
 `Shapes.cs`  
  
 DSL tanımı'ndaki her şekli sınıf için bir sınıf. Şekilleri türetilir <xref:Microsoft.VisualStudio.Modeling.Diagrams.NodeShape>. Daha fazla bilgi için bkz: [özelleştirme dosya depolama ve XML serileştirme](../modeling/customizing-file-storage-and-xml-serialization.md).  
  
 Bir parçalı sınıf kendi yöntemleri ile oluşturulan yöntemleri geçersiz kılmak için ayarlanmış **oluşturur çift türetilmiş** DSL tanımında bağlayıcı. Bir Oluşturucu ile kendi kodunuzu değiştirmek için **sahip özel Oluşturucu**.  
  
 Rengi ve başka bazı stil özellikleri değişken çalışma zamanında kullanabilmek için DSL tanımı diyagramında sınıfı sağ tıklatın ve işaret **eklemek açığa**.  
  
 Çalışma zamanında ek stil özellikleri değişken olmak için örneğin bakın <xref:Microsoft.VisualStudio.Modeling.Diagrams.TextField> ve <xref:Microsoft.VisualStudio.Modeling.Diagrams.ShapeElement>  
  
 `ToolboxHelper.cs`  
  
 Araç kutusu öğesi araçlarınızla öğesi grubu prototipleri yükleyerek ayarlar. Kullanıcı Aracı'nı çalıştırdığında bu prototipleri kopyalarını hedef öğe ile birleştirilir.  
  
 Geçersiz kılma `CreateElementPrototype()` bazı nesneler bir grup oluşturur bir araç kutusu öğesi tanımlamak için. Örneğin, alt bileşenleriniz nesneleri temsil etmek için bir öğe tanımlayabilirsiniz. Deneysel örneği sıfırlama kodu değiştirdikten sonra [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] araç önbelleğini temizlemek için.  
  
## <a name="generated-files-in-the-dslpackage-project"></a>DslPackage projedeki oluşturulan dosyalar  
 DslPackage couples DSL modeline [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Kabuk, pencere, araç ve menü komutlarını yönetme. Böylece kendi yöntemlerden herhangi birini geçersiz kılabilirsiniz sınıfları türetilmiş, çift çoğu.  
  
 `CommandSet.cs`  
  
 Diyagramda görünür bağlam menüsü komutlarını. Uyarlamayacağınıza ya da bu kümesine ekleyin. Bu dosya komutları kodunu içerir. Menü komutlarını konumunu Commands.vsct dosyası tarafından belirlenir. Daha fazla bilgi için bkz: [yazma kullanıcı komutlarını ve eylemleri](../modeling/writing-user-commands-and-actions.md).  
  
 `Constants.cs`  
  
 GUID.  
  
 `DocData.cs`  
  
 *YourDsl* `DocData` yükleme ve bir modeli dosyasına kaydetme yönetir ve depo örneği oluşturur.  
  
 Örneğin, bir dosya yerine bir veritabanında, DSL kaydetmek istiyorsanız, kılmanız `Load` ve `Save` yöntemleri.  
  
 `DocView.cs`  
  
 *YourDsl* `DocView` diyagram göründüğü penceresi yönetir. Örneğin, bir windows Form içinde diyagramı katıştırmak:  
  
 Bir kullanıcı denetimi dosyasının DslPackage projeye ekleyin. Diyagramda görüntülenebilir bir Panel ekleyin. Düğmelerin ve diğer denetimlerin ekleyin. Formun kod görünümünde, DSL adlarına ayarlama aşağıdaki kodu ekleyin:  
  
```  
using System;  
using System.Collections.Generic;  
using System.ComponentModel;  
using System.Drawing;  
using System.Data;  
using System.Linq;  
using System.Text;  
using System.Windows.Forms;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Shell;  
  
namespace Company.EmbedInForm  
{  
  public partial class UserControl1 : UserControl  
  {  
    public UserControl1()  
    {  
      InitializeComponent();  
    }  
  
    private DiagramDocView docView;  
  
    public UserControl1(DiagramDocView docView, Control content)  
      : this()  
    {  
      this.docView = docView;  
      panel1.Controls.Add(content);  
    }  
  
    private void button1_Click(object sender, EventArgs e)  
    {  
      ExampleModel modelRoot = this.docView.CurrentDiagram.ModelElement as ExampleModel;  
      foreach (ExampleElement element in modelRoot.Elements)  
      {  
       listBox1.Items.Add(element.Name);  
      }  
    }  
  }  
  internal partial class EmbedInFormDocView  
  {  
  
    private ContainerControl container;  
  
    /// <summary>  
    /// Return a User Control instead of the DSL window.   
    /// The user control will contain the DSL window.  
    /// </summary>  
  
    public override System.Windows.Forms.IWin32Window Window  
    {  
      get  
      {  
        if (container == null)  
        {  
          // Put the normal DSL Window inside our control  
          container = new UserControl1(this, (Control)base.Window);  
        }  
        return container;  
      }  
    }  
  }  
  
}  
  
```  
  
 `EditorFactory.cs`  
  
 Başlatır `DocData` ve `DocView`. Standart bir karşıladığı arabirim [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DSL paketinizi başladığında bir Düzenleyicisi'ni açmak için kullanır. İçinde başvurulan `ProvideEditorFactory` Package.cs özniteliği  
  
 `GeneratedVSCT.vsct`  
  
 Menü, diyagram bağlam menüsü gibi standart menü komutlarını bulur **Düzenle** menü ve benzeri. İçinde CommandSet.cs komutları kodudur. Taşıyabilir veya standart komutları değiştirebilir ve kendi komutları ekleyebilirsiniz. Daha fazla bilgi için bkz: [yazma kullanıcı komutlarını ve eylemleri](../modeling/writing-user-commands-and-actions.md).  
  
 `ModelExplorer.cs`  
  
 Model Gezgini, DSL için tanımlar. Diyagram yanı sıra kullanıcı görür modelinin ağaç görünümünü budur.  
  
 Örneğin, kılmanız `InsertTreeView()` öğeleri Model Gezgini'nde görünme sırasını değiştirmek için.  
  
 Diyagram seçimi ile eşitlenmiş tutmak için model Gezgini seçim istiyorsanız, aşağıdaki kodu kullanabilirsiniz:  
  
```  
protected override void OnSelectionChanged(global::System.EventArgs e)  
{  
base.OnSelectionChanged(e);  
// get the selected element  
DslModeling::ModelElement selectedElement =   
this.PrimarySelection as DslModeling::ModelElement;  
// Select in the model explorer  
SelectInModelExplorer<YOURLANGUAGEExplorerToolWindow>(selectedElement);  
}  
private void SelectInModelExplorer<T>(DslModeling::ModelElement modelElement)  
where T : DslShell.ModelExplorerToolWindow  
{  
DslShell::ModelingPackage package =   
this.GetService(typeof(VSShell.Package)) as DslShell::ModelingPackage;  
  
if (package != null)  
{  
// find the model explorer window  
T explorerWindow = package.GetToolWindow(typeof(T), true) as T;  
if (explorerWindow != null)  
{  
// get the tree container  
DslShell.ModelExplorerTreeContainer treeContainer =   
explorerWindow.TreeContainer;  
// find the tree node  
DslShell.ExplorerTreeNode treeNode =   
treeContainer.FindNodeForElement(modelElement);  
// select the node  
explorerWindow.TreeContainer.ObjectModelBrowser.SelectedNode = treeNode;  
}  
}  
}  
  
```  
  
 `ModelExplorerToolWindow.cs`  
  
 Model Gezgini görüntülendiği pencere tanımlar. Explorer'da öğelerin seçimini işler.  
  
 `Package.cs`  
  
 Bu dosya, DSL tümleştirir nasıl tanımlar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Paket sınıfı özniteliklerinde DSL dosya uzantısına sahip, kendi araç tanımlayın ve yeni bir pencerede açmak nasıl tanımlayan dosyaları için varsayılan işleç olarak kaydedin. Initialize() yöntemi zaman ilk DSL yüklendiği içine bir kez çağrılır bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] örneği.  
  
 `Source.extension.vsixmanifest`  
  
 Bu dosyayı özelleştirmek için Düzenle `.tt` dosya.  
  
> [!WARNING]
>  Simgeler veya görüntüleri gibi kaynakları içerecek şekilde .tt dosyayı düzenlerseniz, kaynak dahil olduğundan emin olun VSIX oluşturma. Çözüm Gezgini'nde, dosyayı seçin ve olduğundan emin olun **Include in VSIX** özelliği `True`.  
  
 Bu dosya DSL bir Visual Studio Tümleştirme Uzantısı (VSIX) nasıl paketlenmiş denetler. Daha fazla bilgi için bkz: [etki alanına özgü dil çözümleri dağıtma](../modeling/deploying-domain-specific-language-solutions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir etki alanına özgü dil tanımlama](../modeling/how-to-define-a-domain-specific-language.md)   
 [Anlama modelleri, sınıflar ve ilişkiler](../modeling/understanding-models-classes-and-relationships.md)   
 [Özelleştirme ve bir etki alanına özgü dil genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md)   
 [Etki Alanına Özgü Dili Özelleştirmek için Kod Yazma](../modeling/writing-code-to-customise-a-domain-specific-language.md)
