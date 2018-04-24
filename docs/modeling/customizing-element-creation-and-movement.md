---
title: Öğe Oluşturma ve Hareketini Özelleştirme
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.elementmergedirective
helpviewer_keywords:
- Domain-Specific Language, element merge directives
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4747d41377d3f7cccce9142d0659251d3199714a
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="customizing-element-creation-and-movement"></a>Öğe Oluşturma ve Hareketini Özelleştirme
Bir öğenin başka araç veya bir Yapıştır sürüklenen veya taşıma işlemi için izin verebilirsiniz. Belirttiğiniz ilişkilerini kullanarak hedef öğelerine bağlı taşınan öğeler bulunabilir.

 Bir öğenin birleştirme yönergesi (EMD) bir model öğesi olduğunda ne olacağını belirtir *birleştirilmiş* başka bir model öğesi içine. Böyle olduğunda:

-   Diyagram veya bir şekli Kutusu'ndan kullanıcının sürüklediği.

-   Kullanıcı Ekle menüsü Gezgini'nde ya da bir bölme şekli kullanarak bir öğe oluşturur.

-   Kullanıcı bir öğeyi bir Kulvar diğerine taşır.

-   Kullanıcı bir öğeyi gönderebilir.

-   Program kodunuzu öğesi birleştirme yönergesi çağırır.

 Oluşturma işlemleri kopyalama işlemlerini farklı olması gibi görünse de, bunlar aslında aynı şekilde çalışır. Örneğin bir öğe eklendiğinde, araç kutusu'ndan bir prototipini çoğaltılır. Prototip başka bir modelin parçası kopyalandı öğeleri aynı şekilde modeline birleştirilir.

 Bir EMD nasıl nesne veya grup nesne modelinde belirli bir konuma birleştirilmesini karar vermek için sorumluluğundadır. Özellikle, birleştirilmiş Grup modele bağlanmak için hangi ilişkileri örneği karar verir. Bu özellikleri ayarlamak ve ek nesneleri oluşturmak için de özelleştirebilirsiniz.

 ![DSL&#45;EMD&#95;birleştirme](../modeling/media/dsl-emd_merge.png "DSL EMD_Merge") birleştirme bir Element Directive rolü

 Katıştırma bir ilişki tanımlamak bir EMD otomatik olarak oluşturulur. Kullanıcılar yeni alt örnekleri üst eklediğinizde, bu varsayılan EMD ilişki örneği oluşturur. Özel kod ekleyerek bu varsayılan EMDs örneğin değiştirebilirsiniz.

 Kendi EMDs sürükleyin veya birleştirilmiş ve alıcı sınıfları farklı birleşimlerini yapıştırın kullanıcıların izin verecek şekilde DSL tanımında de ekleyebilirsiniz.

## <a name="defining-an-element-merge-directive"></a>Bir öğenin birleştirme yönergesi tanımlama
 Etki alanı sınıfları, etki alanı ilişkilerini, şekiller, bağlayıcılar ve diyagramları öğesi birleştirme yönergeleri ekleyebilirsiniz. Ekleyebilir veya bunları DSL Gezgini'nde alıcı etki alanı sınıfının altında bulun. Alıcı sınıfı modelinde ve yeni ya da kopyalanan öğesi birleştirilecek üzerine zaten öğenin etki alanı sınıftır.

 ![DSL&#45;EMD&#95;ayrıntıları](../modeling/media/dsl-emd_details.png "DSL EMD_Details")

 **Dizin sınıfı** alıcı sınıfı üyeleri birleştirilebilir öğelerinin etki alanı sınıftır. Alt sınıfların dizin oluşturma sınıfının örneklerini de birleştirilir bu EMD tarafından ayarladığınız sürece **alt sınıfların uygulandığı** false.

 Birleştirme yönergesi iki tür vardır:

-   A **işlem birleştirme** yönergesi olarak yeni öğe bağlı olmaları ağacına ilişkileri belirtir.

-   A **İleri birleştirme** yönergesi başka bir alan öğesi, genellikle bir üst yeni öğe yönlendirir.

 Yönergeleri birleştirmek için özel kod ekleyebilirsiniz:

-   Ayarlama **kullandığı özel kabul** belirli bir dizin oluşturma öğesi örneği hedef öğeye birleştirilmiş olup olmadığını belirlemek için kendi kodunuzu eklemek için. Kullanıcı Araç Kutusu'ndan sürüklendiğinde kodunuzu birleştirme izin vermez, "geçersiz" işaretçi gösterir.

     Örneğin, yalnızca alıcı öğesi belirli bir durumda olduğunda birleştirme izin verebilir.

-   Ayarlama **kullandığı özel birleştirme** eklemek için birleştirme gerçekleştirildiğinde modelinde yapılan değişiklikleri tanımlamak için kendi kodu girin.

     Örneğin, yeni konumundan modeldeki verileri kullanarak birleştirilmiş öğe özellikleri ayarlayabilirsiniz.

> [!NOTE]
>  Özel birleştirme kodu yazarsanız, bu EMD kullanılarak gerçekleştirilen yalnızca birleştirmeler etkiler. Aynı nesne türünü birleştirme diğer EMDs varsa veya bu nesneleri EMD kullanmadan oluşturan diğer özel kod ise, ardından bunlar özel birleştirme kodunuz tarafından etkilenmez.
>
>  Yeni bir öğe veya yeni bir ilişki her zaman özel kodunuz tarafından işlendiğinden emin olmak istiyorsanız, tanımlama göz önünde bulundurun bir `AddRule` katıştırma ilişkideki ve `DeleteRule` öğenin etki alanı sınıfı üzerinde. Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).

## <a name="example-defining-an-emd-without-custom-code"></a>Örnek: bir EMD özel kod olmadan tanımlama
 Aşağıdaki örnek, varolan bir şekli Kutusu'ndan sürükleyerek aynı anda bir öğe ve bir bağlayıcı oluşturmasına olanak verir. Örnek bir EMD DSL tanımına ekler. Bu değişiklikten önce kullanıcıların araçları diyagram üzerine ancak değil varolan şekillerin üzerine sürükleyin.

 Kullanıcılar ayrıca diğer öğeler üzerine öğeleri yapıştırabilirsiniz.

#### <a name="to-let-users-create-an-element-and-a-connector-at-the-same-time"></a>Kullanıcıların bir öğe bir bağlayıcı aynı anda oluşturup izin vermek için

1.  Kullanarak yeni bir DSL oluşturma **en az bir dil** çözüm şablonu.

     Bu DSL çalıştırdığınızda, şekilleri ve şekiller arasında bağlayıcıları oluşturmanızı sağlar. Yeni bir sürükleyin olamaz **ExampleElement** varolan bir şekli Kutusu'ndan şekli.

2.  Kullanıcıların öğelerini birleştirme izin vermek için `ExampleElement` şekilleri oluşturmak, yeni bir EMD `ExampleElement` etki alanı sınıfı:

    1.  İçinde **DSL Explorer**, genişletin **etki alanı sınıflarını**. Sağ `ExampleElement` ve ardından **yeni öğe birleştirme yönergesi eklemek**.

    2.  Olduğundan emin olun **DSL ayrıntıları** penceresi açıksa, böylece yeni EMD ayrıntılarını görebilirsiniz. (Menü: **Görünüm**, **diğer Windows**, **DSL ayrıntıları**.)

3.  Ayarlama **sınıfı dizin** hangi sınıfın öğelerinin üzerine birleştirilebilir tanımlamak için DSL Ayrıntıları penceresinde `ExampleElement` nesneleri.

     Bu örnek için select `ExampleElements`, böylece kullanıcı varolan öğeleri yeni öğeleri sürükleyin.

     Dizin oluşturma sınıfı DSL Explorer'da EMD adını duruma dikkat edin.

4.  Altında **bağlantılar oluşturarak işlem birleştirme**, iki yolu ekleyin:

    1.  Bir yol yeni öğe üst modeli bağlar. Girmenize gerek yol ifadesi varolan öğeyi yukarı katıştırma ilişki üst modeline gider. Son olarak, rolü yeni öğe atanacak yeni bağlantıya belirtir. Yol aşağıdaki gibidir:

         `ExampleModelHasElements.ExampleModel/!ExampleModel/.Elements`

    2.  Başka bir yol varolan öğeyi yeni öğe bağlar. Yol ifadesi başvuru ilişkisi ve yeni öğe atanacak rolü belirtir. Bu yolu aşağıdaki gibidir:

         `ExampleElementReferencesTargets.Sources`

     Her yol oluşturmak için yol Gezinti aracı kullanabilirsiniz:

    1.  Altında **yollarında bağlantılar oluşturarak işlem birleştirme**, tıklatın  **\<yolu Ekle >**.

    2.  Liste öğesinin sağındaki açılan oku tıklatın. Ağaç görünümünde görüntülenir.

    3.  Belirtmek istediğiniz yolun form için ağacında düğümleri genişletin.

5.  DSL test edin:

    1.  Yeniden oluşturun ve çözümü çalıştırmak için F5 tuşuna basın.

         Oluşturulan kod metin şablonlardan yeni DSL tanımına uyacak şekilde güncelleştirilmiş olduğundan yeniden normalden daha uzun sürer.

    2.  Zaman deneysel örneği [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sahip başlatıldığından, DSL bir model dosyasını açın. Bazı örnek öğeleri oluşturun.

    3.  Sürükleyin **örnek öğesi** varolan bir şekli üzerine aracı.

         Yeni bir şekli görünür ve varolan bir şekli bir bağlayıcı ile bağlanır.

    4.  Varolan bir şekli kopyalayın. Başka bir şekil seçin ve yapıştırın.

         İlk şekli bir kopyası oluşturulur.  Yeni bir adı olan ve ikinci şekli bir bağlayıcı ile bağlanır.

 Bu yordam aşağıdaki noktalarından dikkat edin:

-   Öğe birleştirme yönergeleri oluşturarak, diğer kabul öğesinin herhangi bir sınıf izin verebilirsiniz. Alıcı etki alanı sınıfında EMD oluşturulur ve kabul edilen etki alanı sınıf içinde belirtilmiş **dizin sınıfı** alan.

-   Yolları tanımlayarak, hangi bağlantılar gerektiğini belirtebilirsiniz yeni öğe varolan modele bağlanmak için kullanılır.

     Belirttiğiniz bağlantılar bir katıştırma ilişki içermelidir.

-   Araç kutusu ve ayrıca yapıştırma işlemleri oluşturmaya EMD etkiler.

     Yeni öğeler oluşturur özel kod yazarsanız, açıkça EMD kullanarak çağırabilirsiniz `ElementOperations.Merge` yöntemi. Bu, kodunuzu yeni öğeler modeline diğer işlemleri aynı şekilde bağlantı emin olur. Daha fazla bilgi için bkz: [kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md).

## <a name="example-adding-custom-accept-code-to-an-emd"></a>Örnek: Bir EMD özel kabul kod ekleme
 Özel kod bir EMD ekleyerek, daha karmaşık birleştirme davranışı tanımlayabilirsiniz. Bu basit örnekte, kullanıcı diyagrama öğe sayısından daha eklemesini engeller. Örnek bir katıştırma ilişkisi eşlik EMD varsayılan değiştirir.

#### <a name="to-write-custom-accept-code-to-restrict-what-the-user-can-add"></a>Hangi kullanıcı ekleyebilir kısıtlamak için kod özel kabul yazma

1.  Kullanarak bir DSL oluşturma **en az bir dil** çözüm şablonu. DSL tanımı diyagramı açın.

2.  DSL Explorer'da genişletin **etki alanı sınıflarını**, `ExampleModel`, **öğesi birleştirme yönergeleri**. Adlı öğeyi birleştirme yönergesi seçin `ExampleElement`.

     Kullanıcı yeni nasıl oluşturabileceğinizi bu EMD denetimleri `ExampleElement` Araç Kutusu'ndan sürükleyerek Örneğin bu modeldeki nesneleri.

3.  İçinde **DSL ayrıntıları** penceresinde, seçin **kullandığı özel kabul**.

4.  Çözümü yeniden derleyin. Oluşturulan kod modelden güncelleştirileceği çünkü bu normalden daha uzun sürer.

     Bir derleme hatası bildirilen, benzer: "Company.ElementMergeSample.ExampleElement içermiyor bir tanımı için CanMergeExampleElement..."

     Yöntem uygulamalıdır `CanMergeExampleElement`.

5.  Yeni bir kod dosyasını içinde oluşturmak **Dsl** projesi. İçeriğini aşağıdaki kodla değiştirin ve projenizin ad alanına ad alanı değiştirin.

    ```csharp
    using Microsoft.VisualStudio.Modeling;

    namespace Company.ElementMergeSample // EDIT.
    {
      partial class ExampleModel
      {
        /// <summary>
        /// Called whenever an ExampleElement is to be merged into this ExampleModel.
        /// This happens when the user pastes an ExampleElement
        /// or drags from the toolbox.
        /// Determines whether the merge is allowed.
        /// </summary>
        /// <param name="rootElement">The root element in the merging EGP.</param>
        /// <param name="elementGroupPrototype">The EGP that the user wants to merge.</param>
        /// <returns>True if the merge is allowed</returns>
        private bool CanMergeExampleElement(ProtoElementBase rootElement, ElementGroupPrototype elementGroupPrototype)
        {
          // Allow no more than 4 elements to be added:
          return this.Elements.Count < 4;
        }
      }
    }

    ```

     Bu basit örnekte üst modeline birleştirilebilir öğe sayısını kısıtlar. Daha ilginç koşullarını yöntemi özelliklerinden herhangi birini ve alıcı nesnesinin bağlantılar inceleyebilirsiniz. Taşınırlar birleştirme öğelerin özellikleri inceleyebilirsiniz bir <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype>. Hakkında daha fazla bilgi için `ElementGroupPrototypes`, bkz: [kopyalama davranışını özelleştirme](../modeling/customizing-copy-behavior.md). Model okuyan kod yazma hakkında daha fazla bilgi için bkz: [gezinme ve Program kodundaki bir modeli güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md).

6.  DSL test edin:

    1.  Çözümü yeniden derleyin için F5 tuşuna basın. Zaman deneysel örneği [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] açıldığında, DSL örneği açın.

    2.  Yeni öğeler çeşitli yollarla oluşturun:

        1.  Sürükleyin **örnek öğesi** diyagram üzerine aracı.

        2.  İçinde **örnek Model Gezgini**, kök düğüme sağ tıklayın ve ardından **ekleme yeni bir örnek öğesi**.

        3.  Kopyalayın ve bir öğe diyagramı yapıştırın.

    3.  Modele dörtten fazla öğeler eklemek için bu yollardan herhangi birini kullanamazsınız doğrulayın. Tüm birleştirme Element Directive kullandıkları olmasıdır.

## <a name="example-adding-custom-merge-code-to-an-emd"></a>Örnek: Özel birleştirme kodu bir EMD ekleme
 Özel birleştirme kodda, kullanıcı bir aracı sürüklediği veya bir öğenin üstüne gönderebilir ne olur tanımlayabilirsiniz. Özel bir birleştirme tanımlamak için iki yolu vardır:

1.  Ayarlama **kullanan özel birleştirme** ve gerekli kodu girin. Kodunuzu oluşturulan birleştirme kodunu değiştirir. Tamamen birleştirme yaptığı yeniden tanımlamak istiyorsanız bu seçeneği kullanın.

2.  Geçersiz kılma `MergeRelate` yöntemi ve isteğe bağlı olarak `MergeDisconnect` yöntemi. Bunu yapmak için ayarlamalısınız **oluşturur çift türetilmiş** etki alanı sınıfının özelliği. Kodunuzu taban sınıf içinde oluşturulan birleştirme kod çağırabilir. Birleştirme işlemi gerçekleştirildikten sonra ek işlemleri gerçekleştirmek istiyorsanız bu seçeneği kullanın.

 Bu yaklaşım, yalnızca bu EMD kullanılarak gerçekleştirilen birleştirmeler etkiler. Tüm yollar, birleştirilmiş öğesi oluşturulabilir etkileyen istiyorsanız, bir alternatif tanımlamaktır bir `AddRule` katıştırma ilişkideki ve `DeleteRule` birleştirilmiş etki alanı sınıfı. Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).

#### <a name="to-override-mergerelate"></a>MergeRelate geçersiz kılmak için

1.  DSL tanımı'nda kod eklemek istediğiniz EMD tanımladığınızdan emin olun. İstiyorsanız, yolu ekleyin ve tanımlayın önceki bölümlerde açıklandığı gibi özel kabul kodu.

2.  DslDefinition şemada birleştirme alıcı sınıfını seçin. Genellikle, bir katıştırma ilişkisi kaynak sonunda sınıftır.

     Örneğin, en az bir dil çözümden oluşturulan bir DSL içinde seçin `ExampleModel`.

3.  İçinde **özellikleri** penceresindeki ayarlayın **oluşturur çift türetilmiş** için **doğru**.

4.  Çözümü yeniden derleyin.

5.  İçeriğini incelemek **Dsl\Generated Files\DomainClasses.cs**. Adlı yöntemleri için arama `MergeRelate` ve içeriklerini inceleyin. Bu, kendi sürümleri yazmanıza yardımcı olur.

6.  Yeni bir kod dosyası alıcı sınıfı için bir parçalı sınıf yazma ve geçersiz kılma `MergeRelate` yöntemi. Temel yöntemini çağırmayı unutmayın. Örneğin:

    ```csharp
    partial class ExampleModel
    {
      /// <summary>
      /// Called when the user drags or pastes an ExampleElement onto the diagram.
      /// Sets the time of day as the name.
      /// </summary>
      /// <param name="sourceElement">Element to be added</param>
      /// <param name="elementGroup">Elements to be merged</param>
      protected override void MergeRelate(ModelElement sourceElement, ElementGroup elementGroup)
      {
        // Connect the element according to the EMD:
        base.MergeRelate(sourceElement, elementGroup);

        // Custom actions:
        ExampleElement mergingElement = sourceElement as ExampleElement;
        if (mergingElement != null)
        {
          mergingElement.Name = DateTime.Now.ToLongTimeString();
        }
      }
    }

    ```

#### <a name="to-write-custom-merge-code"></a>Özel birleştirme kod yazma

1.  İçinde **Dsl\Generated Code\DomainClasses.cs**, adlı yöntemleri inceleyin `MergeRelate`. Bu yöntem yeni bir öğesi ile varolan modelini arasındaki bağlantıları oluşturun.

     Ayrıca, adlı yöntemleri inceleyin `MergeDisconnect`. Silinecek olduğunda bu yöntemler bir öğeyi model bağlantısını.

2.  İçinde **DSL Explorer**özelleştirmek istediğiniz öğe birleştirme yönergesi oluşturun veya seçin. İçinde **DSL ayrıntıları** penceresindeki ayarlayın **kullanan özel birleştirme**.

     Bu seçeneği ayarlarken **işlem birleştirme** ve **İleri birleştirme** seçenekler yok sayılır. Kodunuzu yerine kullanılır.

3.  Çözümü yeniden derleyin. Oluşturulan kod dosyaları modelden güncelleştirileceği nedeniyle normalden daha uzun sürer.

     Hata iletileri görüntülenir. Oluşturulan kodun'ndaki yönergeleri görmek için hata iletileri çift tıklayın. Bu yönergeleri iki yöntem sağlamanız istenir `MergeRelate` *YourDomainClass* ve `MergeDisconnect` *YourDomainClass*

4.  Yöntemleri ayrı kod dosyasındaki bir parçalı sınıf tanımını yazın. Daha önce Denetlenmekte örnekler gerekenler önermek.

 Özel birleştirme kod nesneleri ve ilişkileri doğrudan oluşturan kodunu etkilemez ve diğer EMDs etkilemez. Ek değişikliklerinizi öğesi nasıl oluşturulduğuna bakılmaksızın uygulandığından emin olmak için yazma göz önünde bulundurun. bir `AddRule` ve `DeleteRule` yerine. Daha fazla bilgi için bkz: [kuralları yayılması değişiklikleri içindeki Model](../modeling/rules-propagate-changes-within-the-model.md).

## <a name="redirecting-a-merge-operation"></a>Bir birleştirme işlemi yeniden yönlendirme
 İleri birleştirme yönergesi hedefi bir birleştirme işlemi yönlendirir. Genellikle, yeni ilk hedef katıştırma üst hedefidir.

 Örneğin, bileşen diyagramı şablonuyla oluşturulmuş bir DSL içinde bağlantı noktaları bileşenlerinde katıştırılır. Bağlantı noktaları, bir bileşen şekli kenarında küçük şekiller olarak görüntülenir. Kullanıcı, bağlantı noktası aracını bir bileşen şekli sürükleyerek bağlantı noktaları oluşturur. Ancak bazı durumlarda, kullanıcının bağlantı noktası aracı yanlışlıkla bileşen yerine varolan bir bağlantı üzerine sürüklediği ve işlem başarısız olur. Çeşitli var olan bağlantı noktaları olduğunda kolay hata budur. Bu rahatsızlığı kullanıcıya yardımcı olmak için varolan bir bağlantı sürüklediğiniz, ancak üst bileşenine yeniden yönlendirilen eylem bağlantı noktalarını izin verebilirsiniz. İşlem, hedef öğe bileşen değilmiş gibi çalışır.

 Bileşen modeli çözümde İleri birleştirme yönergesi oluşturabilirsiniz. Derleme ve özgün çözümde çalıştırırsanız, kullanıcıların herhangi bir sayıda sürükleyebilirsiniz görmelisiniz **giriş bağlantı noktası** veya **çıkış bağlantı noktasına** öğelerinden **araç** bir için**Bileşen** öğesi. Ancak, bunlar bir bağlantı noktasını varolan bir bağlantı noktasına sürükleyin olamaz. Bu taşıma bunları etkin kullanılamaz işaretçi uyarılar. Ancak, bir bağlantı noktası, kasıtsız olarak böylece İleri birleştirme yönergesi oluşturabilirsiniz var olan bırakılan **giriş bağlantı noktası** iletilir **bileşen** öğesi.

#### <a name="to-create-a-forward-merge-directive"></a>İleri birleştirme yönergesi oluşturmak için

1.  Oluşturma bir [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] bileşen modeli şablonunu kullanarak çözümü.

2.  Görüntü **DSL Explorer** DslDefinition.dsl açarak.

3.  İçinde **DSL Explorer**, genişletin **etki alanı sınıflarını**.

4.  **ComponentPort** soyut etki alanı sınıftır hem temel sınıfını **InPort** ve **OutPort**. Sağ **ComponentPort** ve ardından **yeni öğe birleştirme yönergesi eklemek**.

     Yeni bir **öğesi birleştirme yönergesi** düğümü altında görünmektedir **öğesi birleştirme yönergeleri** düğümü.

5.  Seçin **öğesi birleştirme yönergesi** düğümü ve açık **DSL ayrıntıları** penceresi.

6.  Dizin oluşturma sınıfı listeden seçin **ComponentPort**.

7.  Seçin **İleri birleştirme farklı bir etki alanı sınıfına**.

8.  Yol seçim listesinde genişletin **ComponentPort**, genişletin **ComponentHasPorts**ve ardından **bileşen**.

     Yeni yol bunu benzemelidir:

     **ComponentHasPorts.Component/!Component**

9. Çözüm kaydedin ve ardından sağdaki düğmesine tıklayarak şablonları dönüştürme **Çözüm Gezgini** araç.

10. Derleme ve çözümü çalıştırın. Yeni bir örneğini [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] görüntülenir.

11. İçinde **Çözüm Gezgini**, Sample.mydsl açın. Diyagram ve **ComponentLanguage araç** görünür.

12. Sürükleme bir **giriş bağlantı noktası** gelen **araç** diğerine **giriş bağlantı noktası.** Ardından, sürükleyin bir **OutputPort** için bir **InputPort** ve ardından üzere başka bir **OutputPort**.

     Kullanılamayan işaretçi görülmemelidir ve yeni bırakma gerekir **giriş bağlantı noktası** mevcut bir. Yeni **giriş bağlantı noktası** ve onu başka bir noktaya sürükleyin **bileşen**.

## <a name="see-also"></a>Ayrıca Bkz.

- [Program Kodunda Modeli Gezinme ve Güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)
- [Araçları ve Araç Kutusunu Özelleştirme](../modeling/customizing-tools-and-the-toolbox.md)
- [Bağlantı hattı diyagramları örnek DSL](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)