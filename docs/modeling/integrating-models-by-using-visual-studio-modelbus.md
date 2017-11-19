---
title: "Visual Studio Modelbus kullanarak modelleri tümleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ff722f3-21d6-44e2-9efd-f6694aee9987
caps.latest.revision: "26"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 63295738603d2a88adb70b43d41e185c7eabbc69
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="integrating-models-by-using-visual-studio-modelbus"></a>Visual Studio Modelbus'ı Kullanarak Modelleri Tümleştirme
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ModelBus modellerini diğer Araçları'ndan ve modelleri arasında bağlantılar oluşturmak için bir yöntem sağlar. Örneğin, etki alanına özgü dil (DSL) modelleri ve UML modellerini bağlayabilirsiniz. Tümleşik bir DSL'ler kümesi oluşturabilirsiniz.  
  
 ModelBus, model veya bir model içinde belirli bir öğe için benzersiz bir başvuruyu oluşturmanızı sağlar. Bu başvuru modeli dışında Örneğin, başka bir model öğesi depolanabilir. Öğesine erişim sağlamak bir aracı bir sonraki durumlarda, istediği zaman, Model veri yolu altyapı uygun modeli yüklemek ve öğesini döndürür. İsterseniz, kullanıcıya model görüntüleyebilirsiniz. Dosyanın önceki konumuna erişilemiyor ModelBus bulmak kullanıcıya sorar. Kullanıcı dosyası bulursa, bu dosyaya yapılan tüm başvuruları ModelBus düzeltir.  
  
> [!NOTE]
>  Geçerli [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus, bağlantılı modelleri uyarlamasını öğeleri aynı olmalıdır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü.  
  
 Ek bilgi ve örnek kod için bkz:  
  
-   [Nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md)  
  
-   [Visual Studio SDK Modelleme](http://www.microsoft.com/download/details.aspx?id=40754)  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
  
##  <a name="provide"></a>Bir DSL erişim sağlama  
 Bir model veya öğeleri ModelBus başvurular oluşturabilmeniz için önce bir ModelBusAdapter için DSL tanımlamanız gerekir. Bunu yapmanın en kolay yolu kullanmaktır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komutları DSL Designer'a ekler Model veri yolu uzantısı.  
  
###  <a name="expose"></a>Model veri yolu DSL tanımına kullanıma sunmak için  
  
1.  İndirin ve Visual Studio modeli Bus uzantısı zaten yüklemiş olduğunuz sürece yükleyin. Daha fazla bilgi için bkz: [Görselleştirme ve modelleme SDK](http://go.microsoft.com/fwlink/?LinkID=185579).  
  
2.  DSL tanım dosyasını açın. Tasarım yüzeyine sağ tıklayın ve ardından **etkinleştirmek Modelbus**.  
  
3.  İletişim kutusunda seçin **bu DSL ModelBus için kullanıma sunmak istediğiniz**. Modellerinin kullanıma ve diğer DSL'ler başvurular kullanmak için bu DSL istiyorsanız, her iki seçeneği de seçebilirsiniz.  
  
4.  **Tamam**'ı tıklatın. Yeni bir proje "ModelBusAdapter" DSL çözüme eklenir.  
  
5.  Metin şablonundan DSL erişmek isterseniz, yeni projede AdapterManager.tt değiştirmeniz gerekir. Komutlar ve olay işleyicileri gibi diğer kodundan DSL erişmek istiyorsanız bu adımı atlayın. Daha fazla bilgi için bkz: [kullanarak Visual Studio ModelBus metin şablonunda](../modeling/using-visual-studio-modelbus-in-a-text-template.md).  
  
    1.  AdapterManagerBase için temel sınıfını değiştirme <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>.  
  
    2.  Dosyanın sonuna yakın, bu ek öznitelik sınıfı AdapterManager önüne ekleyin:  
  
         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`  
  
    3.  Başvurular, ModelBusAdapter projesinde ekleyin **Microsoft.VisualStudio.TextTemplating.Modeling.11.0**.  
  
     Metin şablonları ve diğer kod DSL erişmesini isterseniz, iki bağdaştırıcısı, değişiklik diğeri değiştirilmemiş gerekir.  
  
6.  Tıklatın **tüm şablonları dönüştürme**.  
  
7.  Çözümü yeniden derleyin.  
  
 Artık bu DSL örneklerini açmak ModelBus için mümkündür.  
  
 Klasör `ModelBusAdapters\bin\*` tarafından oluşturulmuş derlemeler içeren `Dsl` proje ve `ModelBusAdapters` projesi. Bu DSL başka bir DSL başvurmak için bu derlemeler almanız gerekir.  
  
### <a name="making-sure-that-elements-can-be-referenced"></a>Öğeleri başvurulabilir emin olma  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ModelBus bağdaştırıcılar, bir öğenin GUID, varsayılan olarak tanımlamak için kullanın. Bu tanımlayıcılar bu nedenle model dosyasında kalıcı gerekir.  
  
##### <a name="to-ensure-that-element-ids-are-persisted"></a>Kimlikleri kalıcı o öğeye emin olmak için  
  
1.  DslDefinition.dsl açın.  
  
2.  DSL Explorer'da genişletin **Xml serileştirme davranışı**, ardından **sınıf veri**.  
  
3.  Model veri yolu oluşturmak istediğiniz her bir sınıf için başvuruyor:  
  
     Sınıf düğümünü tıklatın ve Özellikler penceresinde olduğundan emin olun **seri kimliği** ayarlanır `true`.  
  
 Alternatif olarak, öğe adları GUID'ler yerine öğeleri tanımlamak için kullanmak istiyorsanız, oluşturulan bağdaştırıcıları bölümlerini geçersiz kılabilirsiniz. Bağdaştırıcı sınıfı aşağıdaki yöntemleri geçersiz kıl:  
  
-   Geçersiz kılma `GetElementId` kullanmak istediğiniz tanımlayıcı dönün. Bu yöntem, başvuru oluştururken çağrılır.  
  
-   Geçersiz kılma `ResolveElementReference` bir Model veri yolu başvuru doğru öğeyi bulmak için.  
  
##  <a name="editRef"></a>Başka bir DSL DSL erişme  
 Model veri yolu başvuruları DSL etki alanı özelliğinde depolayabilirsiniz ve bunları kullanan özel kod yazabilirsiniz. Ayrıca kullanıcının bir model dosyası ve bir öğede seçerek bir model veri yolu başvurusu oluşturmasını sağlayabilirsiniz.  
  
 Başka bir DSL başvurular kullanılacak DSL etkinleştirmek için öncelikle bunu olmalısınız bir *tüketici* model veri yolu başvuruları.  
  
#### <a name="to-enable-a-dsl-to-consume-references-to-an-exposed-dsl"></a>Sunulan DSL başvurular tüketmeye DSL etkinleştirmek için  
  
1.  DSL tanımı diyagramında diyagram ana bölümünü sağ tıklayın ve ardından **etkinleştirmek Modelbus**.  
  
2.  İletişim kutusunda **model veri yolu başvuruları kullanmak bu modeli etkinleştirmek istediğiniz**.  
  
3.  Süren DSL Dsl projesinde aşağıdaki derlemeler için proje başvuruları ekleyin. Bu derlemeler (.dll dosyaları) ModelBusAdapter\bin bulacaksınız\\* gösterilen DSL dizininde.  
  
    -   Örneğin gösterilen DSL derleme **Fabrikam.FamilyTree.Dsl.dll**  
  
    -   Oluşturulan model bağdaştırıcısı derleme, örneğin veri yolu **Fabrikam.FamilyTree.ModelBusAdapter.dll**  
  
4.  Aşağıdaki .NET derlemelerini Süren DSL proje proje başvuruları ekleyin.  
  
    1.  **Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0.dll**  
  
    2.  **Microsoft.VisualStudio.Modeling.Sdk.Integration.Shell.11.0.dll**  
  
#### <a name="to-store-a-model-bus-reference-in-a-domain-property"></a>Bir etki alanı özelliğinde bir Model veri yolu başvurusu depolamak için  
  
1.  Süren DSL DSL tanımı, bir etki alanı özelliği için bir etki alanı sınıf ekleyin ve adını ayarlayın.  
  
2.  Özelliklerinde penceresinde seçili, etki alanı özelliğiyle ayarlamak **türü** için `ModelBusReference`.  
  
 Bu aşamada, program kodu özellik değeri ayarlanmış, ancak Özellikler penceresinde salt okunurdur.  
  
 Bir özel ModelBus başvurusu düzenleyicisiyle özelliğini ayarlamak kullanıcıların izin verebilirsiniz. Bu düzenleyicinin iki sürümü vardır veya *Seçici:* bir model dosyası seçmek kullanıcıların sağlar ve başka bir model dosyası ve bir öğe modelindeki seçmelerini sağlar.  
  
#### <a name="to-allow-the-user-to-set-a-model-bus-reference-in-a-domain-property"></a>Bir etki alanı özelliğinde bir Model veri yolu başvurusu ayarlamak izin vermek için  
  
1.  Etki alanı özelliği sağ tıklayın ve ardından **Düzenle ModelBusReference özgü özellikleri**. Bir iletişim kutusu açılır. Bu *Model veri yolu Seçici*.  
  
2.  Uygun seçin **tür ModelBusReference**: bir model veya bir model içinde bir öğe.  
  
3.  Dosya iletişim filtre dizesinde gibi bir dize girin `Family Tree files |*.ftree`. DEVICEHIGH gösterilen DSL dosya uzantısı.  
  
4.  Bir modeldeki bir öğeye başvuru seçerseniz, kullanıcı seçebilir, örneğin Company.FamilyTree.Person türlerinin bir listesini ekleyebilirsiniz.  
  
5.  Tıklatın **Tamam**ve ardından **tüm şablonları dönüştürme** Çözüm Gezgini araç çubuğunda.  
  
    > [!WARNING]
    >  Geçerli model veya varlık seçmediyseniz, etkin görünse de Tamam düğmesine hiçbir etkisi olmaz.  
  
6.  Company.FamilyTree.Person gibi hedef türlerinin bir listesini belirtilmişse, ardından DSL projeniz için bir derleme başvurusu hedef DSL, örneğin Company.FamilyTree.Dsl.dll DLL başvuran eklemeniz gerekir  
  
#### <a name="to-test-a-model-bus-reference"></a>Bir Model veri yolu başvurusu sınamak için  
  
1.  Kullanıma sunulan ve alan DSL'ler oluşturun.  
  
2.  F5 veya CTRL + F5 tuşuna basarak DSL'ler birini Deneysel modunda çalıştırın.  
  
3.  Deneysel örneği hata ayıklama projede [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], her DSL örnekleri olan dosyaları ekleyin.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ModelBus yalnızca aynı öğeleridir modellere başvurular çözmek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü. Örneğin, dosya sisteminizi başka bir kısmında bir model dosyası başvuru oluşturulamıyor.  
  
4.  Bazı öğeler ve bağlantıları gösterilen DSL örneğinde oluşturun ve kaydedin.  
  
5.  Süren DSL örneği açın ve bir model veri yolu başvuru özelliği olan bir model öğeyi seçin.  
  
6.  Özellikler penceresinde model veri yolu başvuru özelliği çift tıklayın. Seçici iletişim kutusu açılır.  
  
7.  Tıklatın **Gözat** ve sunulan DSL örneğini seçin.  
  
     Model veri yolu başvurusu öğesi özgü tür belirtilmişse Seçici aynı zamanda, modeldeki bir öğe seçin olanak tanır.  
  
## <a name="creating-references-in-program-code"></a>Program kodunda başvuru oluşturma  
 Bir model veya bir model içinde bir öğe için bir başvuru depolamak istediğinizde, oluşturduğunuz bir `ModelBusReference`. İki tür vardır, `ModelBusReference`: model başvuruları ve öğesi başvuruları.  
  
 Bir model başvurusu oluşturmak için model olduğu bir örneği ve dosya adı DSL AdapterManager gerekir veya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] modelinin proje öğesi.  
  
 Bir öğe başvurusu oluşturmak için model dosyası ve bunlara başvurmak istediğinizde öğesi için bir bağdaştırıcı gerekir.  
  
> [!NOTE]
>  İle [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus, oluşturabileceğiniz yalnızca öğelere başvurular aynı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözümü.  
  
### <a name="import-the-exposed-dsl-assemblies"></a>Sunulan DSL derlemeleri alma  
 Süren projesinde sunulan DSL DSL ve ModelBusAdapter derlemeler için proje başvuruları ekleyin.  
  
 Örneğin, bir MusicLibrary DSL öğelerinde ModelBus başvurularını depolamak istediğinizi varsayalım. FamilyTree DSL öğelerine ModelBus başvurular başvurur. İçinde `Dsl` proje MusicLibrary çözümün başvurular düğümünü aşağıdaki derlemelerine başvurular ekleyin:  
  
-   Fabrikam.FamilyTree.Dsl.dll - gösterilen DSL.  
  
-   Fabrikam.FamilyTree.ModelBusAdapters.dll - gösterilen DSL ModelBus bağdaştırıcısı.  
  
-   Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0  
  
-   Microsoft.VisualStudio.Modeling.Sdk.Integration.Shell.11.0  
  
 Bu derlemeler bulunabilir `ModelBusAdapters` gösterilen DSL projenin altında `bin\*`.  
  
 Burada başvuruları oluşturacak kod dosyasında genellikle bu ad alanlarını alma gerekecektir:  
  
```  
// The namespace of the DSL you want to reference:  
using Fabrikam.FamilyTree;  // Exposed DSL  
using Fabrikam.FamilyTree.ModelBusAdapters;  
using Microsoft.VisualStudio.Modeling.Integration;  
using System.Linq;  
...  
```  
  
### <a name="to-create-a-reference-to-a-model"></a>Bir başvuru bir model oluşturmak için  
 Bir model başvurusu oluşturmak için AdapterManager için sunulan DSL erişmek ve model için bir başvuru oluşturmak için kullanın. Herhangi bir dosya yolu belirtin veya bir `EnvDTE.ProjectItem`.  
  
 AdapterManager modelinde ayrı ayrı öğeler erişim sağlayan bir bağdaştırıcı elde edebilirsiniz.  
  
> [!NOTE]
>  Kendisiyle tamamladığınızda bağdaştırıcıyı dispose gerekir. Bunu elde etmenin en kolay yolu olan bir `using` deyimi. Aşağıdaki örnek bunu göstermektedir.  
  
```  
// The file path of a model instance of the FamilyTree DSL:  
string targetModelFile = "TudorFamilyTree.ftree";  
// Get the ModelBus service:  
IModelBus modelBus =   
    this.Store.GetService(typeof(SModelBus)) as IModelBus;  
// Get an adapterManager for the target DSL:  
FamilyTreeAdapterManager manager =   
    (modelbus.GetAdapterManager(FamilyTreeAdapter.AdapterId)   
     as FamilyTreeAdapterManager;  
// or: (modelBus.FindAdapterManagers(targetModelFile).First())  
// or could provide an EnvDTE.ProjectItem  
  
// Create a reference to the target model:  
// NOTE: the target model must be a file in this project.  
ModelBusReference modelReference =  
     manager.CreateReference(targetModelFile);  
// or can use an EnvDTE.ProjectItem instead of the filename  
  
// Get the root element of this model:  
using (FamilyTreeAdapter adapter =   
     modelBus.CreateAdapter(modelReference) as FamilyTreeAdapter)  
{  
  FamilyTree modelRoot = adapter.ModelRoot;  
  // Access elements under the root in the usual way:  
  foreach (Person p in modelRoot.Persons) {...}  
  // You can create adapters for individual elements:  
  ModelBusReference elementReference =  
     adapter.GetElementReference(person);  
  ...  
} // Dispose adapter  
  
```  
  
 Kullanmak istiyorsanız `modelReference` daha sonra dış türüne sahip bir etki alanı özelliğinde depolayabilirsiniz `ModelBusReference`:  
  
```  
using Transaction t = this.Store.TransactionManager  
    .BeginTransaction("keep reference"))  
{  
  artist.FamilyTreeReference = modelReference;  
  t.Commit();  
}  
```  
  
 Kullanıcıların bu etki alanı özelliği düzenlemesine izin vermek için kullanın `ModelReferenceEditor` Düzenleyici özniteliğini de parametre olarak. Daha fazla bilgi için bkz: [başvuru düzenlemek kullanıcı izin](#editRef).  
  
### <a name="to-create-a-reference-to-an-element"></a>Bir öğenin bir başvuru oluşturmak için  
 Model için oluşturduğunuz bağdaştırıcısı oluşturmak ve başvuruları çözümlemek için kullanılabilir.  
  
```  
// person is an element in the FamilyTree model:  
ModelBusReference personReference =   
  adapter.GetElementReference(person);  
```  
  
 Kullanmak istiyorsanız `elementReference` daha sonra dış türüne sahip bir etki alanı özelliğinde depolayabilirsiniz `ModelBusReference`. Düzenlemek kullanıcılara izin vermek için kullanın `ModelElementReferenceEditor` Düzenleyici özniteliğini de parametre olarak. Daha fazla bilgi için bkz: [başvuru düzenlemek kullanıcı izin](#editRef).  
  
### <a name="resolving-references"></a>Başvuruları çözme  
 Varsa bir `ModelBusReference` (MBR) modeli ya da başvurduğu model öğesi edinebilirsiniz. Öğe bir diyagram ya da diğer görünüm üzerinde sunulan görünümü açın ve öğeyi seçin.  
  
 Bağdaştırıcıyı bir MBR'yi oluşturabilirsiniz. Bağdaştırıcısından modelin kökü elde edebilirsiniz. Model içinde belirli öğeleri başvurmak MBRs de çözebilirsiniz.  
  
```  
using Microsoft.VisualStudio.Modeling.Integration; ...  
ModelBusReference elementReference = ...;  
  
// Get the ModelBus service:  
IModelBus modelBus =   
    this.Store.GetService(typeof(SModelBus)) as IModelBus;  
// Use a model reference or an element reference  
// to obtain an adapter for the target model:  
using (FamilyTreeAdapter adapter =   
   modelBus.CreateAdapter(elementReference) as FamilyTreeAdapter)  
   // or CreateAdapter(modelReference)  
{  
  // Get the root of the model:  
  FamilyTree tree = adapter.ModelRoot;  
  
  // Get a model element:  
  MyDomainClass mel =  
    adapter.ResolveElementReference<MyDomainClass>(elementReference);  
  if (mel != null) {...}  
  
  // Get the diagram or other view, if there is one:  
  ModelBusView view = adapter.GetDefaultView();  
  if (view != null)   
  {  
   view.Open();  
   // Display the diagram:  
   view.Show();   
   // Attempt to select the shape that presents the element:  
   view.SetSelection(elementReference);  
  }  
} // Dispose the adapter.  
```  
  
##### <a name="to-resolve-modelbus-references-in-a-text-template"></a>Metin şablonu ModelBus başvuruları çözümlemek için  
  
1.  Erişmek istediğiniz DSL erişimi için metin şablonları tarafından yapılandırılan bir ModelBus bağdaştırıcısı olmalıdır. Daha fazla bilgi için bkz: [DSL erişim sağlayan](#provide).  
  
2.  Genellikle, bir Model veri yolu başvurusu (MBR) kullanarak DSL kaynağında DSL depolanan bir hedef erişecek. Şablonunuz, bu nedenle MBR çözümlemek için yönergesi kaynak DSL artı kodu içerir. Metin şablonları hakkında daha fazla bilgi için bkz: [bir etki alanına özgü dil oluşturma koddan](../modeling/generating-code-from-a-domain-specific-language.md).  
  
    ```  
    <#@ template debug="true" hostspecific="true"   
    inherits="Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation" #>   
    <#@ SourceDsl processor="SourceDslDirectiveProcessor" requires="fileName='Sample.source'" #>  
    <#@ output extension=".txt" #>  
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0" #>  
    <#@ assembly name = "System.Core" #>  
    <#@ assembly name = "Company.CompartmentDragDrop.Dsl.dll" #>  
    <#@ assembly name = "Company.CompartmentDragDrop.ModelBusAdapter.dll" #>  
    <#@ import namespace="Microsoft.VisualStudio.Modeling.Integration" #>  
    <#@ import namespace="System.Linq" #>  
    <#@ import namespace="Company.CompartmentDragDrop" #>  
    <#@ import namespace="Company.CompartmentDragDrop.ModelBusAdapters" #>  
    <# // Get source root from directive processor:  
      ExampleModel source = this.ExampleModel;   
      // This DSL has a MBR in its root:  
    using (ModelBusAdapter adapter = this.ModelBus.CreateAdapter(source.ModelReference) as ModelBusAdapter)   
      {  
      ModelBusAdapterManager manager = this.ModelBus.FindAdapterManagers(this.Host.ResolvePath("Sample.compDD1")).FirstOrDefault();  
      ModelBusReference modelReference =  
        manager.CreateReference(this.Host.ResolvePath("Sample.compDD1"));  
  
      // Get the root element of this model:  
      using (CompartmentDragDropAdapter adapter =   
         this.ModelBus.CreateAdapter(modelReference) as CompartmentDragDropAdapter)  
      {  
        ModelRoot root = adapter.ModelRoot;  
    #>  
    [[<#= root.Name #>]]  
    <#  
      }  
    #>  
  
    ```  
  
 Daha fazla bilgi ve bir kılavuz için bkz: [kullanarak Visual Studio ModelBus metin şablonunda](../modeling/using-visual-studio-modelbus-in-a-text-template.md)  
  
## <a name="serializing-a-modelbusreference"></a>Bir ModelBusReference seri hale getirme  
 Saklamak isterseniz bir `ModelBusReference` (MBR), seri bir dize biçiminde:  
  
```  
string serialized = modelBus.SerializeReference(elementReference);  
// Store it anywhere, then get it back again:  
ModelBusReference elementReferenceRestored =  
    modelBus.DeserializeReference(serialized, null);  
```  
  
 Bu şekilde sıralanmış bir MBR bağlamında bağımsızdır. Basit dosya tabanlı Model veri yolu bağdaştırıcısı kullanıyorsanız, MBR mutlak bir dosya yolu içerir. Bu örnek modeli dosyaları hiçbir zaman taşınacaksa yeterlidir. Ancak, model dosyalar öğeleri genellikle olacak bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesi. Kullanıcılarınız farklı kısımlarını dosya sistemi için tüm proje taşımak ister. Ayrıca projenin kaynak denetimi altında tutun ve farklı bilgisayarlarda açmak bekledikleri. Yol adları, bu nedenle dosyaları içeren proje konumuna göre serileştirilmelidir.  
  
### <a name="serializing-relative-to-a-specified-file-path"></a>Belirtilen dosya yolu göreli seri hale getirme  
 A `ModelBusReference` içeren bir `ReferenceContext`, hangi depolayabileceğiniz göre serileştirildiği dosya yolu gibi bilgileri bir sözlük olduğu.  
  
 Göreli bir yol seri hale getirmek için:  
  
```  
elementReference.ReferenceContext.Add(  
   ModelBusReferencePropertySerializer.FilePathSaveContextKey,   
   currentProjectFilePath);  
string serialized = modelBus.SerializeReference(elementReference);  
```  
  
 Dizeden başvuru almak için:  
  
```  
ReferenceContext context = new ReferenceContext();  
context.Add(ModelBusReferencePropertySerializer.FilePathLoadContextKey,  
    currentProjectFilePath);  
ModelBusReference elementReferenceRestored =  
    modelBus.DeserializeReference(serialized, context);  
```  
  
### <a name="modelbusreferences-created-by-other-adapters"></a>Diğer bağdaştırıcıları tarafından oluşturulan ModelBusReferences  
 Aşağıdaki bilgiler, kendi bağdaştırıcısı oluşturmak istiyorsanız yararlıdır.  
  
 A `ModelBusReference` (MBR) iki bölümden oluşur: model veri yolu tarafından seri durumdan, MBR üstbilgi ve belirli bağdaştırıcı Yöneticisi tarafından işlenen bir bağdaştırıcıya özgü. Bu, kendi bağdaştırıcısı seri hale getirme biçimi sağlamanıza olanak tanır. Örneğin, bir dosya yerine bir veritabanına başvurabilir veya ek bilgi bağdaştırıcısı başvurusunda saklayabilirsiniz. Kendi bağdaştırıcısı ek bilgileri yerleştirebilirsiniz `ReferenceContext`.  
  
 Bir MBR seri durumdan, ardından MBR nesnesinde depolanan bir ReferenceContext sağlamanız gerekir. Bir MBR seri, depolanan ReferenceContext bağdaştırıcı tarafından dizesi oluşturun yardımcı olmak için kullanılır. Seri durumdan çıkarılmış dizesi ReferenceContext tüm bilgileri içermiyor. Örneğin, basit dosya tabanlı bağdaştırıcısında ReferenceContext serileştirilmiş MBR dizesinde depolanmaz bir kök dosya yolu içerir.  
  
 MBR iki aşamada seri:  
  
-   `ModelBusReferencePropertySerializer`MBR üstbilgiyle ilgilenir standart seri hale getirici ' dir. Standart DSL kullanan `SerializationContext` depolanan özellik paketi `ReferenceContext` anahtar kullanılarak `ModelBusReferencePropertySerializer.ModelBusLoadContextKey`. Özellikle, `SerializationContext` örneği içermelidir `ModelBus`.  
  
-   ModelBus bağdaştırıcınızı MBR bağdaştırıcıya özgü parçası ile ilgilidir. MBR ReferenceContext içinde depolanan ek bilgileri kullanabilirsiniz. Anahtarlar kullanılarak kök dosya yolları basit dosya tabanlı bağdaştırıcısı tutar `FilePathLoadContextKey` ve `FilePathSaveContextKey`.  
  
     Yalnızca kullanıldığında, bir model dosyası bağdaştırıcısı başvurusunda serisi.  
  
## <a name="to-create-a-model"></a>Bir Model oluşturmak için  
  
### <a name="creating-opening-and-editing-a-model"></a>Oluşturma, açma ve bir modeli düzenleme  
 Aşağıdaki parça Durum makinesi örnekten VMSDK Web sitesinde alınır. ModelBusReferences oluşturmak ve bir modeli açmak ve modeli ile ilişkili diyagramı edinmek için kullanımını göstermektedir.  
  
 Bu örnekte, Durum makinesi DSL hedef adıdır. Birden fazla ad içerik modeli sınıfı adı ve ModelBusAdapter adı gibi türetilir.  
  
```  
using Fabrikam.StateMachine.ModelBusAdapters;   
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Integration;  
using Microsoft.VisualStudio.Modeling.Integration.Shell;  
using Microsoft.VisualStudio.Modeling.Shell;  
...  
// Create a new model.  
ModelBusReference modelReference =   
   StateMachineAdapterManager    .CreateStateMachineModel(modelName, fileName);  
//Keep reference of new model in this model.  
using (Transaction t = ...)  
{  
  myModelElement.ReferenceProperty = modelReference;  
  t.Commit();  
}  
// Get the ModelBus service from Visual Studio.  
IModelBus modelBus = Microsoft.VisualStudio.Shell.Package.  
    GetGlobalService(typeof(SModelBus)) as IModelBus;  
// Get a modelbus adapter on the new model.  
ModelBusAdapter modelBusAdapter;  
modelBus.TryCreateAdapter(modelReference,   
    this.ServiceProvider, out modelBusAdapter);  
using (StateMachineAdapter adapter =   
      modelBusAdapter as StateMachineAdapter)  
{  
    if (adapter != null)  
    {  
        // Obtain a Diagram from the adapter.  
        Diagram targetDiagram =   
           ((StandardVsModelingDiagramView)  
                 adapter.GetDefaultView()  
            ).Diagram;  
  
        using (Transaction t =   
             targetDiagram.Store.TransactionManager  
                .BeginTransaction("Update diagram"))  
        {  
            DoUpdates(targetDiagram);  
            t.Commit();  
        }  
  
        // Display the new diagram.  
        adapter.GetDefaultView().Show();  
    }  
}  
```  
  
## <a name="validating-references"></a>Başvuruları doğrulanıyor  
 BrokenReferenceDetector tüm etki alanı özellikleri ModelBusReferences tutabilen bir depoda sınar. Eylemi çağıran, herhangi bir eylem bulunduğu sağlayın. Bu doğrulama yöntemleri için özellikle yararlıdır. Aşağıdaki doğrulama yöntemi modeli kaydedin girişimi deponuzu sınar ve hataları penceresinde bozuk başvurularda raporları:  
  
```  
[ValidationMethod(ValidationCategories.Save)]  
public void ValidateModelBusReferences(ValidationContext context)  
{  
  BrokenReferenceDetector.DetectBrokenReferences(this.Store,  
    delegate(ModelElement element, // parent of property  
             DomainPropertyInfo property, // identifies property  
             ModelBusReference reference) // invalid reference  
    {   
      context.LogError(string.Format(INVALID_REF_FORMAT,   
             property.Name,   
             referenceState.Name,   
             new ModelBusReferenceTypeConverter().  
                 ConvertToInvariantString(reference)),   
         "Reference",   
         element);  
      });  
}}  
private const string INVALID_REF_FORMAT =   
    "The '{0}' domain property of ths ReferenceState instance "  
  + "named '{1}' contains reference value '{2}' which is invalid";  
```  
  
## <a name="actions-performed-by-the-modelbus-extension"></a>ModelBus uzantısı tarafından gerçekleştirilen eylemler  
 Aşağıdaki bilgiler gerekli değildir, ancak ModelBus kapsamlı kullanımını yaparsanız yararlı olabilir.  
  
 ModelBus uzantısı DSL çözümünüzde aşağıdaki değişiklikleri yapar.  
  
 DSL tanımı Diyagramı sağ tıklattığınızda tıklatın **etkinleştirmek Modelbus**ve ardından **ModelBus kullanmak bu DSL etkinleştirme**:  
  
-   Bir başvuru eklenir DSL projesinde **Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0.dll**  
  
-   DSL tanımında dış türü başvurusu eklenir: `Microsoft.VisualStudio.Modeling.Integration.ModelBusReference`.  
  
     Başvurusuna bakın **DSL Explorer**altında **etki alanı türleri**. Dış tür başvuruları el ile eklemek için kök düğüme sağ tıklayın.  
  
-   Yeni bir şablon dosyası eklenir, **Dsl\GeneratedCode\ModelBusReferencesSerialization.tt**.  
  
 Ne zaman, ModelBusReference için bir etki alanı özelliği türünü ayarlayın ve ardından özelliği sağ tıklatıp **etkinleştirmek ModelBusReference özgü özellikleri**:  
  
-   Birkaç CLR öznitelikleri etki alanı özelliğine eklenir. Özel öznitelikler alanında Özellikleri penceresinde görebilirsiniz. İçinde **Dsl\GeneratedCode\DomainClasses.cs**, öznitelikler özelliği bildiriminde görebilirsiniz:  
  
    ```  
    [System.ComponentModel.TypeConverter(typeof(  
    Microsoft.VisualStudio.Modeling.Integration.ModelBusReferenceTypeConverter))]  
    [System.ComponentModel.Editor(typeof(  
      Microsoft.VisualStudio.Modeling.Integration.Picker  
      .ModelReferenceEditor // or ModelElementReferenceEditor  
      ), typeof(System.Drawing.Design.UITypeEditor))]  
    [Microsoft.VisualStudio.Modeling.Integration.Picker  
      .SupplyFileBasedBrowserConfiguration  
      ("Choose a model file", "Target model|*.target")]  
    ```  
  
 DSL tanımı Diyagramı sağ tıklattığınızda, tıklatın **etkinleştirmek ModelBus**seçip **bu DSL ModelBus için kullanıma**:  
  
-   Yeni bir proje `ModelBusAdapter` çözüme eklendi.  
  
-   Bir başvuru `ModelBusAdapter` eklenen `DslPackage` projesi. `ModelBusAdapter`bir başvuru içeriyor `Dsl` projesi.  
  
-   İçinde **DslPackage\source.extention.tt**, `|ModelBusAdapter|` MEF Bileşeni olarak eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Program kodundaki dosyasından bir Model açın](../modeling/how-to-open-a-model-from-file-in-program-code.md)   
 [Nasıl yapılır: bir Sürükle ve bırak işleyici ekleme](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [Visual Studio ModelBus bir metin şablonu kullanma](../modeling/using-visual-studio-modelbus-in-a-text-template.md)
