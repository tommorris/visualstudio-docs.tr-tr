---
title: "Bir etki alanına özgü dil doğrulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, constraints
- Domain-Specific Language, validation
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ce2d578bb9a7fbee167b3e45224a1309e75ec0b7
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="validation-in-a-domain-specific-language"></a>Etki Alanına Özgü bir Dilde Doğrulama
Bir etki alanına özgü dil (DSL) yazar olarak, kullanıcı tarafından oluşturulan model anlamlı olduğunu doğrulamak için doğrulama kısıtlamaları tanımlayabilirsiniz. Örneğin, kişiler ve kendi üst öğelerinden ailesi ağacının çizmek kullanıcılar, DSL izin veriyorsa, alt öğe üst sonraki Doğum tarihleri sahip olmasını sağlar bir kısıtlama yazabilirsiniz.  
  
 Model kaydedildiğinde açıldığında ve kullanıcı açıkça çalıştırdığında yürütmek doğrulama kısıtlamaları olabilir **doğrulama** menü komutu. Doğrulama programı denetimi altında da çalıştırabilirsiniz. Örneğin, yanıt olarak bir özellik değeri veya ilişki değişikliği doğrulama yürütebilir.  
  
 Doğrulama metin şablonları ya da kullanıcılarınızın modelleri işlem diğer araçları yazıyorsanız, özellikle önemlidir. Doğrulama modelleri bu araçları tarafından kabul önkoşulları karşılamak sağlar.  
  
> [!WARNING]
>  Ayrıca, uzantı menü komutları ve hareket işleyicileri yanı sıra, DSL ayrı uzantıları tanımlanması için doğrulama kısıtlamaları de izin verebilirsiniz. Kullanıcılar bu uzantılar, DSL ek olarak yüklemeyi seçebilirsiniz. Daha fazla bilgi için bkz: [MEF kullanarak, DSL genişletme](../modeling/extend-your-dsl-by-using-mef.md).  
  
## <a name="running-validation"></a>Çalışan doğrulama  
 Diğer bir deyişle, bir kullanıcı bir model düzenlerken, etki alanına özgü dil örneği doğrulama aşağıdaki eylemleri çalıştırabilirsiniz:  
  
-   Diyagram sağ tıklatıp **doğrulamak tüm**.  
  
-   En üstteki düğümü seçin ve DSL Explorer'da sağ **tüm doğrula**  
  
-   Modeli kaydedin.  
  
-   Model açın.  
  
-   Buna ek olarak, doğrulama, örneğin, menü komutu veya bir değişikliğe yanıt parçası olarak çalışan program kod yazabilirsiniz.  
  
 Tüm doğrulama hatalarını görünür **hata listesi** penceresi. Kullanıcı, hatanın nedeni, model öğelerini seçmek için bir hata iletisi çift tıklayabilirsiniz.  
  
## <a name="defining-validation-constraints"></a>Doğrulama kısıtlamaları tanımlama  
 Etki alanı sınıfları veya, DSL ilişkilerini doğrulama yöntemleri ekleyerek doğrulama kısıtlamaları tanımlama. Doğrulama, kullanıcı veya program denetimindeki çalıştırıldığında bazılarını veya tümünü doğrulama yöntemlerinin yürütülür. Her sınıf birkaç doğrulama yöntemlerini olabilir ve her yöntemin kendi sınıfın her örneği için uygulanır.  
  
 Her bir doğrulama yöntemi, bulduğu herhangi bir hata bildirir.  
  
> [!NOTE]
>  Doğrulama yöntemlerinin hata raporu, ancak model değiştirmeyin. İstiyorsanız, ayarlama veya bazı değişiklikleri önlemek için bkz: [doğrulama alternatifleri](#alternatives).  
  
#### <a name="to-define-a-validation-constraint"></a>Doğrulama kısıtlamaları tanımlamak için  
  
1.  Doğrulamayı etkinleştirmek **Editor\Validation** düğümü:  
  
    1.  Açık **Dsl\DslDefinition.dsl**.  
  
    2.  DSL Explorer'da genişletin **Düzenleyicisi** düğümü ve select **doğrulama**.  
  
    3.  Özellikler penceresinde ayarlayın **kullanan** özelliklerine `true`. Bu özellikleri ayarlamak en kullanışlıdır.  
  
    4.  Tıklatın **tüm şablonları dönüştürme** Çözüm Gezgini araç çubuğunda.  
  
2.  Bir veya daha fazla etki alanı sınıflar ya da etki alanı ilişkiler için parçalı sınıf tanımları yazma. Yeni bir kod dosyasında bu tanımları yazma **Dsl** projesi.  
  
3.  Bu öznitelik her sınıfıyla öneki:  
  
    ```csharp  
    [ValidationState(ValidationState.Enabled)]  
    ```  
  
    -   Varsayılan olarak, bu öznitelik da türetilen sınıflar için doğrulamayı etkinleştirir. Belirli bir türetilmiş sınıf için doğrulama devre dışı bırakmak istiyorsanız kullanabileceğiniz `ValidationState.Disabled`.  
  
4.  Doğrulama yöntemlerinin sınıfları ekleyin. Her bir doğrulama yöntemi herhangi bir ada sahip ancak türünde bir parametreye sahip <xref:Microsoft.VisualStudio.Modeling.Validation.ValidationContext>.  
  
     Bir veya daha fazla ile eklenmelidir `ValidationMethod` öznitelikleri:  
  
    ```csharp  
    [ValidationMethod (ValidationCategories.Open | ValidationCategories.Save | ValidationCategories.Menu ) ]  
    ```  
  
     ValidationCategories yöntemi zaman yürütülür belirtin.  
  
 Örneğin:  
  
```csharp  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Validation;  
  
// Allow validation methods in this class:  
[ValidationState(ValidationState.Enabled)]  
// In this DSL, ParentsHaveChildren is a domain relationship  
// from Person to Person:  
public partial class ParentsHaveChildren  
{  
  // Identify the method as a validation method:  
  [ValidationMethod  
  ( // Specify which events cause the method to be invoked:  
    ValidationCategories.Open // On file load.  
  | ValidationCategories.Save // On save to file.  
  | ValidationCategories.Menu // On user menu command.  
  )]  
  // This method is applied to each instance of the   
  // type (and its subtypes) in a model:   
  private void ValidateParentBirth(ValidationContext context)     
  {  
    // In this DSL, the role names of this relationship  
    // are "Child" and "Parent":   
     if (this.Child.BirthYear < this.Parent.BirthYear   
        // Allow user to leave the year unset:  
        && this.Child.BirthYear != 0)  
      {  
        context.LogError(  
             // Description:  
                       "Child must be born after Parent",  
             // Unique code for this error:  
                       "FAB001ParentBirthError",   
              // Objects to select when user double-clicks error:  
                       this.Child,   
                       this.Parent);  
    }  
  }  
```  
  
 Bu kodu hakkında aşağıdaki noktaları dikkat edin:  
  
-   Etki alanı sınıfları veya etki alanı ilişkilerini doğrulama yöntemlerini ekleyebilirsiniz. Bu tür için kod **Dsl\Generated Code\Domain\*.cs**.  
  
-   Her bir doğrulama yöntemi, sınıf ve onun alt sınıfların her bir örneğine uygulanır. Bir etki alanı ilişkisi söz konusu olduğunda, her iki model öğesi arasında bir bağlantı örneğidir.  
  
-   Doğrulama yöntemlerinin belirtilen herhangi bir sırada uygulanmaz ve her yöntemin herhangi bir tahmin edilebilir sırayla kendi sınıfının örnekleri için uygulanmaz.  
  
-   Bu tutarsız sonuçlara neden olduğundan, genellikle hatalı deposu içeriği güncelleştirmek bir doğrulama yöntemi için uygulamadır. Bunun yerine, yöntemi herhangi bir hata çağırarak bildirmesi `context.LogError`, `LogWarning` veya `LogInfo`.  
  
-   LogError çağrısında model öğelerini veya kullanıcı hata iletisi tıklattığında seçilir ilişki bağlantılarının bir listesini sağlayabilirsiniz.  
  
-   Program kodundaki modeli okuma hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
 Örneğin, aşağıdaki etki alanı modeli için geçerlidir. ParentsHaveChildren ilişki alt ve üst adlı rol yok.  
  
 ![DSL tanımı diyagramı &#45; Aile Ağacı Modeli](../modeling/media/familyt_person.png "FamilyT_Person")  
  
## <a name="validation-categories"></a>Doğrulama kategorileri  
 İçinde <xref:Microsoft.VisualStudio.Modeling.Validation.ValidationMethodAttribute> özniteliği, belirttiğiniz doğrulama yöntemini yeniden çalıştırıldığında.  
  
|Kategori|Yürütme|  
|--------------|---------------|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Ne zaman kullanıcı doğrulama menü komutunu çağırır.|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Model dosyası açıldığında.|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Ne zaman dosya kaydedilmiş kalır. Doğrulama hatası varsa kullanıcıya kaydetme iptal etme seçeneği verilir işlemi.|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Ne zaman dosya kaydedilmiş kalır. Bu kategorideki yöntemleri hatalar varsa, bu dosyayı yeniden açmak mümkün olmayabilir, kullanıcı uyarılır.<br /><br /> Bu kategori test doğrulama yöntemlerini yinelenen adları veya kimlikleri için ya da yükleme hatalara neden olabilecek diğer koşullar için kullanın.|  
|<xref:Microsoft.VisualStudio.Modeling.Validation.ValidationCategories>|Ne zaman ValidateCustom yöntemi çağrılır. Bu kategorideki doğrulamaları yalnızca program kodundan çağrılabilir.<br /><br /> Daha fazla bilgi için bkz: [özel doğrulama kategoriler](#custom).|  
  
## <a name="where-to-place-validation-methods"></a>Doğrulama yöntemlerinin nereye yerleştireceğinizi  
 Genellikle farklı bir türde bir doğrulama yöntemi koyarak aynı sonucu elde edebilirsiniz. Örneğin, kişi sınıfı ParentsHaveChildren ilişki yerine bir yöntem ekleyin ve sahip bağlantılar aracılığıyla yinelemek:  
  
```  
[ValidationState(ValidationState.Enabled)]  
public partial class Person  
{[ValidationMethod  
 ( ValidationCategories.Open   
 | ValidationCategories.Save  
 | ValidationCategories.Menu  
 )  
]  
  private void ValidateParentBirth(ValidationContext context)     
  {  
    // Iterate through ParentHasChildren links:  
    foreach (Person parent in this.Parents)  
    {  
        if (this.BirthYear <= parent.BirthYear)  
        { ...  
  
```  
  
 **Doğrulama kısıtlamaları toplama.** Doğrulama tahmin edilebilir bir sırayla uygulamak için bu tür bir kök öğe modelinizin bir sahibi sınıf tek doğrulama yöntemi tanımlayın. Bu teknik Ayrıca, tek bir iletiye birden çok hata raporlarını toplamak olanak tanır.  
  
 Dezavantajları olan birleşik yöntemi yönetmek daha az kolay olduğundan ve kısıtlamalar tüm aynı olması gerektiğini `ValidationCategories`. Bu nedenle, her kısıtlaması ayrı bir yöntem mümkünse tutmanızı öneririz.  
  
 **Değerleri içerik önbelleğinde geçirme.** Bağlam parametresi rastgele değerler yerleştireceğiniz bir sözlük sahiptir. Sözlük doğrulama çalışması yaşam süreleri boyunca devam ettirir. Belirli doğrulama yöntemi, örneğin, bir hata sayısı bağlamda tutmak ve yinelenen iletileri hata penceresiyle taşmasını önlemek için kullanın. Örneğin:  
  
```csharp  
List<ParentsHaveChildren> erroneousLinks;  
if (!context.TryGetCacheValue("erroneousLinks", out erroneousLinks))  
erroneousLinks = new List<ParentsHaveChildren>();  
erroneousLinks.Add(this);  
context.SetCacheValue("erroneousLinks", erroneousLinks);  
if (erroneousLinks.Count < 5) { context.LogError( ... ); }  
  
```  
  
## <a name="validation-of-multiplicities"></a>Çeşitlilikler doğrulanması  
 Minimum Çokluk denetleme doğrulama yöntemlerinin, DSL için otomatik olarak oluşturulur. Kod yazılır **Dsl\Generated Code\MultiplicityValidation.cs**. Doğrulama etkinleştirdiğinizde, bu yöntemleri etkili **Editor\Validation** DSL Gezgininde düğümü.  
  
 1 olacak şekilde bir etki alanı ilişkisinin bir role çokluğu ayarlarsanız.. * veya 1..1 ancak kullanıcı oluşturmaz, bu ilişkinin bağlantı bir doğrulama hata iletisi görüntülenir.  
  
 Örneğin, DSL varsa, kişinin ve şehir ve bir ilişkisi olan bir ilişki PersonLivesInTown sınıfları **1..\***  Şehir rolde hiçbir Şehir sahip her kişi için bir hata iletisi görüntülenir.  
  
## <a name="running-validation-from-program-code"></a>Program koddan çalışan doğrulama  
 Doğrulama erişme veya bir ValidationController oluşturma çalıştırabilirsiniz. Hata penceresinde kullanıcıya görüntülenecek hataları istiyorsanız, diyagramın DocData bağlı ValidationController kullanın. Örneğin, bir menü komutu yazıyorsanız `CurrentDocData.ValidationController` komut kümesi sınıfta kullanılabilir:  
  
```csharp  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Validation;  
using Microsoft.VisualStudio.Modeling.Shell;  
...  
partial class MyLanguageCommandSet   
{  
  private void OnMenuMyContextMenuCommand(object sender, EventArgs e)   
  {   
   ValidationController controller = this.CurrentDocData.ValidationController;   
...  
  
```  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: bir komut için kısayol menüsü ekleme](../modeling/how-to-add-a-command-to-the-shortcut-menu.md).  
  
 Ayrı doğrulama denetleyicisi oluşturmak ve hataları kendiniz yönetebilirsiniz. Örneğin:  
  
```csharp  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Validation;  
using Microsoft.VisualStudio.Modeling.Shell;  
...  
Store store = ...;  
VsValidationController validator = new VsValidationController(s);  
// Validate all elements in the Store:  
if (!validator.Validate(store, ValidationCategories.Save))  
{  
  // Deal with errors:  
  foreach (ValidationMessage message in validator.ValidationMessages) { ... }  
}  
  
```  
  
## <a name="running-validation-when-a-change-occurs"></a>Bir değişiklik olduğunda çalışan doğrulama  
 Model geçersiz hale gelir, kullanıcı hemen uyarılır emin olmak istiyorsanız, doğrulama çalıştıran bir depolama olay tanımlayabilirsiniz. Mağaza olaylar hakkında daha fazla bilgi için bkz: [olay işleyicileri yayılması değişiklikleri dışında modeli](../modeling/event-handlers-propagate-changes-outside-the-model.md).  
  
 Doğrulama kodu ek olarak, bir özel kod dosyasına ekleyin, **DslPackage** projeyle içeriği aşağıdaki örneğe benzer. Bu kodu kullanır `ValidationController` belgeye eklenir. Bu denetleyici doğrulama hataları görüntüler [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hata listesi.  
  
```csharp  
using System;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Validation;  
namespace Company.FamilyTree  
{  
  partial class FamilyTreeDocData // Change name to your DocData.  
  {  
    // Register the store event handler:   
    protected override void OnDocumentLoaded()  
    {  
      base.OnDocumentLoaded();  
      DomainClassInfo observedLinkInfo = this.Store.DomainDataDirectory  
         .FindDomainClass(typeof(ParentsHaveChildren));  
      DomainClassInfo observedClassInfo = this.Store.DomainDataDirectory  
         .FindDomainClass(typeof(Person));  
      EventManagerDirectory events = this.Store.EventManagerDirectory;  
      events.ElementAdded  
         .Add(observedLinkInfo, new EventHandler<ElementAddedEventArgs>(ParentLinkAddedHandler));  
      events.ElementDeleted.Add(observedLinkInfo, new EventHandler<ElementDeletedEventArgs>(ParentLinkDeletedHandler));  
      events.ElementPropertyChanged.Add(observedClassInfo, new EventHandler<ElementPropertyChangedEventArgs>(BirthDateChangedHandler));  
    }  
    // Handler will be called after transaction that creates a link:  
    private void ParentLinkAddedHandler(object sender,  
                                ElementAddedEventArgs e)  
    {  
      this.ValidationController.Validate(e.ModelElement,  
           ValidationCategories.Save);  
    }  
    // Called when a link is deleted:  
    private void ParentLinkDeletedHandler(object sender,   
                                ElementDeletedEventArgs e)  
    {  
      // Don't apply validation to a deleted item!   
      // - Validate store to refresh the error list.  
      this.ValidationController.Validate(this.Store,  
           ValidationCategories.Save);  
    }  
    // Called when any property of a Person element changes:  
    private void BirthDateChangedHandler(object sender,  
                      ElementPropertyChangedEventArgs e)  
    {  
      Person person = e.ModelElement as Person;  
      // Not interested in changes in other properties:  
      if (e.DomainProperty.Id != Person.BirthYearDomainPropertyId)  
          return;  
  
      // Validate all parent links to and from the person:  
      this.ValidationController.Validate(  
        ParentsHaveChildren.GetLinksToParents(person)  
        .Concat(ParentsHaveChildren.GetLinksToChildren(person))  
        , ValidationCategories.Save);  
    }  
  }  
}  
  
```  
  
 İşleyicileri bağlantıları veya öğeleri etkileyen geri alma veya yineleme işlemlerinden sonra da denir.  
  
##  <a name="custom"></a>Özel doğrulama kategorileri  
 Menü ve açık gibi standart doğrulama kategorilerin yanı sıra kendi kategorileri tanımlayabilir. Program kodunda Bu kategorilerden çağırabilirsiniz. Kullanıcı bunları doğrudan çağrılamaz.  
  
 Bir tipik özel kategorileri için belirli bir aracı önkoşulları model karşılayıp karşılamadığını testleri bir kategori tanımlamak için kullanılır.  
  
 Bir doğrulama yöntemi için belirli bir kategoriye eklemek için böyle bir özniteliği olan öneki:  
  
```csharp  
[ValidationMethod(CustomCategory = "PreconditionsForGeneratePartsList")]  
[ValidationMethod(ValidationCategory.Menu)]   
private void TestForCircularLinks(ValidationContext context)   
{...}  
  
```  
  
> [!NOTE]
>  Bir yöntemle sayıda önek `[ValidationMethod()]` istediğiniz öznitelikler. Hem özel hem de standart kategorileri için bir yöntem ekleyebilirsiniz.  
  
 Özel doğrulama çağırmak için:  
  
```csharp  
  
// Invoke all validation methods in a custom category:   
validationController.ValidateCustom  
  (store, // or a list of model elements  
   "PreconditionsForGeneratePartsList");  
```  
  
##  <a name="alternatives"></a>Doğrulama alternatifleri  
 Doğrulama kısıtlamaları hata raporu, ancak model değiştirmeyin. Geçersiz hale modeli engellemek istiyorsanız bunun yerine, diğer teknikleri kullanabilirsiniz.  
  
 Ancak, bu teknikler önerilmez. Geçersiz model düzeltmek nasıl karar kullanıcı izin vermek genellikle daha iyi olur.  
  
 **Model için geçerlilik geri yüklemek için Değiştir'i ayarlayın.** Örneğin, kullanıcı izin verilen en üstünde bir özellik ayarlarsa, maksimum değer özelliği sıfırlanamadı. Bunu yapmak için bir kural tanımlayın. Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).  
  
 **Geçersiz bir değişikliği denenmesi durumunda işlemi geri.** Bir kural bu amaçla tanımlayabilirsiniz, ancak bazı durumlarda bir özellik işleyicisi geçersiz kılmanıza olanak **OnValueChanging()**, veya bir yöntem gibi geçersiz kılmak için `OnDeleted().` bir işlemi geri almak için kullanmak `this.Store.TransactionManager.CurrentTransaction.Rollback().` daha fazla bilgi için bilgi, bkz: [etki alanı özellik değeri değişiklik işleyicileri](../modeling/domain-property-value-change-handlers.md).  
  
> [!WARNING]
>  Kullanıcı değişiklik ayarlanmış veya bırakıldığı geri olduğunu bilir emin olun. Örneğin, kullanın`System.Windows.Forms.MessageBox.Show("message").`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gezinme ve bir modeli Program kodunda güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Değişiklikleri Modelin Dışına Yayan Olay İşleyicileri](../modeling/event-handlers-propagate-changes-outside-the-model.md)