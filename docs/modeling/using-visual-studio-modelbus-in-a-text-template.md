---
title: Metin Şablonunda Visual Studio ModelBus'ı Kullanma
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 0a5eb101ccf8276b875a2ee461224bd37ebdefb4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="using-visual-studio-modelbus-in-a-text-template"></a>Metin Şablonunda Visual Studio ModelBus'ı Kullanma
İçeren modeli okuma metin şablonları yazma varsa [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus başvuruyor, hedef modelleri erişmek için başvuruları çözümlemek isteyebilirsiniz. Bu durumda, metin şablonları ve başvurulan etki alanına özgü dil (DSL'ler) uyum vardır:

-   Başvuruları hedefidir DSL metin şablonları erişim için yapılandırılmış bir ModelBus bağdaştırıcısı olmalıdır. Başka bir kod da DSL erişirse, yeniden yapılandırılan bağdaştırıcısı yanı sıra standart ModelBus bağdaştırıcısı gereklidir.

     Bağdaştırıcı Yöneticisi öğesinden devralmalıdır <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager> ve öznitelik olmalıdır `[HostSpecific(HostName)]`.

-   Şablon öğesinden devralmalıdır <xref:Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation>.

> [!NOTE]
>  ModelBus Referansları içermez DSL modelleri okuma istiyorsanız, DSL projelerinizde oluşturulan yönerge işlemcileri kullanabilirsiniz. Daha fazla bilgi için bkz: [metin şablonları erişme modellerinden](../modeling/accessing-models-from-text-templates.md).

 Metin şablonları hakkında daha fazla bilgi için bkz: [T4 metin şablonları kullanarak tasarım zamanı kodu oluşturma](../modeling/design-time-code-generation-by-using-t4-text-templates.md).

## <a name="creating-a-model-bus-adapter-for-access-from-text-templates"></a>Metin şablonları erişim için bir Model veri yolu bağdaştırıcısı oluşturma
 Metin şablonu ModelBus başvuru çözümlemek için hedef DSL uyumlu bir bağdaştırıcı olmalıdır. Metin şablonları yürütmek ayrı bir AppDomain içinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] belge düzenleyicileri ve bu yüzden DTE erişme yerine modeli yüklemek bağdaştırıcı varsa.

#### <a name="to-create-a-modelbus-adapter-that-is-compatible-with-text-templates"></a>Metin şablonları ile uyumlu bir ModelBus bağdaştırıcısı oluşturmak için

1.  Hedef DSL çözüm yoksa bir **ModelBusAdapter** proje, Modelbus Genişletme Sihirbazı'nı kullanarak bir tane oluşturun:

    1.  İndirme ve yükleme [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus, zaten bu yapmadıysanız uzantısı. Daha fazla bilgi için bkz: [Görselleştirme ve modelleme SDK](http://go.microsoft.com/fwlink/?LinkID=185579).

    2.  DSL tanım dosyasını açın. Tasarım yüzeyine sağ tıklayın ve ardından **etkinleştirmek Modelbus**.

    3.  İletişim kutusunda **bu DSL ModelBus için kullanıma sunmak istediğiniz**. Modellerinin kullanıma ve diğer DSL'ler başvurular kullanmak için bu DSL istiyorsanız, her iki seçeneği de seçebilirsiniz.

    4.  **Tamam**'ı tıklatın. Yeni bir proje "ModelBusAdapter" DSL çözüme eklenir.

    5.  Tıklatın **tüm şablonları dönüştürme**.

    6.  Çözümü yeniden derleyin.

2.  Metin şablonu ve komutu gibi başka bir kod DSL erişmesini isterseniz, yinelenen **ModelBusAdapter** proje:

    1.  Windows Gezgini'nde, kopyalayıp içeren klasörü **ModelBusAdapter.csproj**.

    2.  Proje dosyayı yeniden adlandırın (örneğin, **T4ModelBusAdapter.csproj**).

    3.  İçinde **Çözüm Gezgini**, çözüm düğümüne sağ tıklayın, fareyle **Ekle**ve ardından **mevcut proje**. Yeni bağdaştırıcısı proje bulun **T4ModelBusAdapter.csproj**.

    4.  Her `*.tt` dosya yeni projenin ad değiştirin.

    5.  Çözüm Gezgini'nde yeni projeye sağ tıklayın ve ardından Özellikler'i tıklatın. Özellikler Düzenleyicisi'nde, oluşturulan derleme ve varsayılan ad alanı adını değiştirin.

    6.  Böylece her iki bağdaştırıcı başvuruda bulunduğu DslPackage projesinde yeni bağdaştırıcısı projesine bir başvuru ekleyin.

    7.  DslPackage\source.extension.tt içinde yeni bağdaştırıcısı projeniz başvuran bir satır ekleyin.

        ```
        <MefComponent>|T4ModelBusAdapter|</MefComponent>
        ```

    8.  **Tüm Şablonları dönüştürme** ve çözümü yeniden derleyin. Derleme hata oluşmamasına.

3.  Yeni bağdaştırıcısı projesinde aşağıdaki derlemelerine başvurular ekleyin:

    -   Microsoft.VisualStudio.TextTemplating.11.0

         Microsoft.VisualStudio.TextTemplating.Modeling.11.0

4.  AdapterManager.tt içinde:

    -   AdapterManagerBase bildirimi değiştirin, böylece öğesinden devralınan <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>.

         `public partial class <#= dslName =>AdapterManagerBase :`

         `Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager { ...`

    -   Dosyanın sonuna yakın AdapterManager sınıfı önce HostSpecific özniteliği değiştirin. Aşağıdaki satırı kaldırın:

         `[DslIntegration::HostSpecific(DslIntegrationShell::VsModelingAdapterManager.HostName)]`

         Aşağıdaki satırı ekleyin:

         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`

         Bu öznitelik için bir bağdaştırıcı modelbus tüketici aradığında, kullanılabilir olan kümesinin bağdaştırıcısı filtreler.

5.  **Tüm Şablonları dönüştürme** ve çözümü yeniden derleyin. Derleme hata oluşmamasına.

## <a name="writing-a-text-template-that-can-resolve-modelbus-references"></a>ModelBus Referansları çözebilmek için bir metin şablonu yazma
 Genellikle, okuyan ve bir kaynaktan"" DSL dosyaları oluşturan bir şablonu ile başlayın. Bu şablon açıklanan şekilde kaynak modeli dosyaları okumak için kaynak DSL projesinde oluşturulan yönergesi kullanır [metin şablonları erişme modellerinden](../modeling/accessing-models-from-text-templates.md). Ancak, kaynak DSL "hedef" DSL ModelBus başvurular içeriyor. Bu nedenle başvuruları çözümlemek ve hedef DSL erişmek şablon kodu etkinleştirmek istiyor. Bu nedenle aşağıdaki adımları izleyerek şablon uyarlamanız gerekir:

-   Şablona temel sınıfını değiştirme <xref:Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation>.

-   Dahil `hostspecific="true"` şablon yönergesi.

-   Derleme başvurularını DSL hedef ve onun bağdaştırıcısı ve ModelBus etkinleştirmek için ekleyin.

-   Hedef DSL bir parçası olarak oluşturulan yönergesi gerekmez.

```
<#@ template debug="true" hostspecific="true" language="C#"
inherits="Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation" #>
<#@ SourceDsl processor="SourceDslDirectiveProcessor" requires="fileName='Sample.source'" #>
<#@ output extension=".txt" #>
<#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0" #>
<#@ assembly name = "Company.TargetDsl.Dsl.dll" #>
<#@ assembly name = "Company.TargetDsl.T4ModelBusAdapter.dll" #>
<#@ assembly name = "System.Core" #>
<#@ import namespace="Microsoft.VisualStudio.Modeling.Integration" #>
<#@ import namespace="Company.TargetDsl" #>
<#@ import namespace="Company.TargetDsl.T4ModelBusAdapters" #>
<#@ import namespace="System.Linq" #>
<#
  SourceModelRoot source = this.ModelRoot; // Usual access to source model.
  // In the source DSL Definition, the root element has a model reference:
  using (TargetAdapter adapter = this.ModelBus.CreateAdapter(source.ModelReference) as TargetAdapter)
  {if (adapter != null)
   {
      // Get the root of the target model:
      TargetRoot target = adapter.ModelRoot;
    // The source DSL Definition has a class "SourceElement" embedded under the root.
    // (Let's assume they're all in the same model file):
    foreach (SourceElement sourceElement in source.Elements)
    {
      // In the source DSL Definition, each SourceElement has a MBR property:
      ModelBusReference elementReference = sourceElement.ReferenceToTarget;
      // Resolve the target model element:
      TargetElement element = adapter.ResolveElementReference<TargetElement>(elementReference);
#>
     The source <#= sourceElement.Name #> is linked to: <#= element.Name #> in target model: <#= target.Name #>.
<#
    }
  }}
  // Other useful code: this.Host.ResolvePath(filename) gets an absolute filename
  // from a path that is relative to the text template.
#>

```

 Bu metin şablonu çalıştırıldığında `SourceDsl` yönergesi yükler dosya `Sample.source`. Şablon başlayarak, bu model öğelerini erişebilirsiniz `this.ModelRoot`. Kod, etki alanı sınıfları ve o DSL özelliklerini kullanabilirsiniz.

 Ayrıca, şablonu ModelBus Referansları çözebilirsiniz. Başvuruları hedef model noktası olduğunda, etki alanı sınıfları ve bu modelin DSL özelliklerini kullanmak kod derleme yönergeleri sağlar.

-   DSL project tarafından oluşturulan bir yönerge kullanmazsanız, ayrıca içermelidir.

    ```
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.11.0" #>
    <#@ assembly name = "Microsoft.VisualStudio.TextTemplating.Modeling.11.0" #>
    ```

-   Kullanım `this.ModelBus` ModelBus erişim elde edilir.

## <a name="walkthrough-testing-a-text-template-that-uses-modelbus"></a>İzlenecek yol: ModelBus kullanan bir metin şablonu test etme
 Bu kılavuzda, aşağıdaki adımları izleyin:

1.  İki DSL'ler oluşturun. Bir DSL *tüketici*, sahip bir `ModelBusReference` diğer DSL başvurabilir özelliği *sağlayıcı*.

2.  Sağlayıcıda iki ModelBus bağdaştırıcısı oluşturur: biri erişmek için metin şablonları sıradan kodu için diğer.

3.  DSL'ler örneği modellerinin tek bir Deneysel projesi oluşturun.

4.  Bir etki alanı özelliği diğer modele işaret etmek için bir model olarak ayarlayın.

5.  İşaret ediyor modeli açar çift işleyicisi yazma.

6.  Birinci modelin yük, diğer model referansı izleyin ve diğer modelini okuma metin şablonu yazma.

#### <a name="construct-a-dsl-that-is-accessible-to-modelbus"></a>Yapı için ModelBus erişilebilen DSL

1.  Yeni bir DSL çözümü oluşturun. Bu örnekte, Görev akışı çözüm şablonu seçin. Dil adı ayarlamak `MBProvider` ve dosya uzantısının ".provide".

2.  DSL tanımı diyagramında en üstüne yakın değil diyagramı boş bir kısmına sağ tıklayın ve ardından **etkinleştirmek Modelbus**.

    -   Görmüyorsanız, **etkinleştirmek Modelbus**, indirin ve VMSDK ModelBus uzantısını yüklemeniz gerekir. VMSDK sitesinde bulabilirsiniz: [Görselleştirme ve modelleme SDK](http://go.microsoft.com/fwlink/?LinkID=185579).

3.  İçinde **etkinleştirmek Modelbus** iletişim kutusunda **bu DSL ModelBus için kullanıma**ve ardından **Tamam**.

     Yeni bir proje `ModelBusAdapter`, çözüme eklendi.

 Metin şablonları ModelBus aracılığıyla tarafından erişilebilecek bir DSL artık sahipsiniz. Başvuru komutlar, olay işleyicileri veya kuralları, her biri modeli dosya Düzenleyicisi AppDomain içinde çalışan kodda çözülebilir. Bununla birlikte, metin şablonları ayrı bir AppDomain içinde çalıştırın ve onu düzenlenirken bir model erişemiyor. Metin şablonu bu DSL ModelBus başvuruları erişmek isterseniz ayrı ModelBusAdapter olması gerekir.

#### <a name="to-create-a-modelbus-adapter-that-is-configured-for-text-templates"></a>Metin şablonları için yapılandırılmış bir ModelBus bağdaştırıcısı oluşturmak için

1.  Windows Gezgini'nde, kopyalayıp ModelBusAdapter.csproj içeren klasöre yapıştırın.

     T4ModelBusAdapter klasörün adı.

     Proje dosyası T4ModelBusAdapter.csproj yeniden adlandırın.

2.  Çözüm Gezgini'nde T4ModelBusAdapter MBProvider çözüme ekleyin. Çözüm düğümüne sağ tıklayın, fareyle **Ekle**ve ardından **mevcut proje**.

3.  T4ModelBusAdapter proje düğümüne sağ tıklayın ve ardından Özellikler'i tıklatın. Proje Özellikleri penceresinde değiştirme **derleme adı** ve **varsayılan Namespace** için `Company.MBProvider.T4ModelBusAdapters`.

4.  Böylece satırı şuna benzer T4ModelBusAdapter her *.tt dosyasında "T4" ad alanı, son bölümüne ekleyin.

     `namespace <#= CodeGenerationUtilities.GetPackageNamespace(this.Dsl) #>.T4ModelBusAdapters`

5.  İçinde `DslPackage` proje, proje başvurusu Ekle `T4ModelBusAdapter`.

6.  DslPackage\source.extension.tt içinde altında aşağıdaki satırı ekleyin `<Content>`.

     `<MefComponent>|T4ModelBusAdapter|</MefComponent>`

7.  İçinde `T4ModelBusAdapter` proje, bir başvuru ekleyin: **Microsoft.VisualStudio.TextTemplating.Modeling.11.0**

8.  Open T4ModelBusAdapter\AdapterManager.tt:

    1.  AdapterManagerBase için temel sınıfını değiştirme <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>. Dosyasının bu bölümü aşağıdakine benzer.

        ```
        namespace <#= CodeGenerationUtilities.GetPackageNamespace(this.Dsl) #>.T4ModelBusAdapters
        {
            /// <summary>
            /// Adapter manager base class (double derived pattern) for the <#= dslName #> Designer
            /// </summary>
            public partial class <#= dslName #>AdapterManagerBase
            : Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager
            {

        ```

    2.  Dosyanın sonuna yakın aşağıdaki ek öznitelik sınıfı AdapterManager önüne ekleyin.

         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`

         Sonuç aşağıdakine benzer.

        ```
        /// <summary>
        /// ModelBus modeling adapter manager for a <#= dslName #>Adapter model adapter
        /// </summary>
        [Mef::Export(typeof(DslIntegration::ModelBusAdapterManager))]
        [Mef::ExportMetadata(DslIntegration::CompositionAttributes.AdapterIdKey,<#= dslName #>Adapter.AdapterId)]
        [DslIntegration::HostSpecific(DslIntegrationShell::VsModelingAdapterManager.HostName)]
        [Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]
        public partial class <#= dslName #>AdapterManager : <#= dslName #>AdapterManagerBase
        {
        }

        ```

9. Tıklatın **tüm şablonları dönüştürme** başlık çubuğu, Çözüm Gezgini'nde.

10. Çözümü yeniden derleyin. F5'e tıklayın.

11. F5 tuşuna basarak DSL çalıştığını doğrulayın. Deneysel projeyi açın `Sample.provider`. Deneysel örneklerini kapatın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

 Bu DSL ModelBus başvurular şimdi metin şablonları hem de normal kod çözülebilir.

#### <a name="construct-a-dsl-with-a-modelbus-reference-domain-property"></a>Yapı DSL ModelBus başvuru etki alanı özelliği

1.  En az bir dil çözüm şablonu kullanarak yeni bir DSL oluşturun. MBConsumer dil adı ve dosya uzantısının ".consume" olarak ayarlayın.

2.  DSL projesinde MBProvider DSL derlemesine başvuru ekleyin. Sağ `MBConsumer\Dsl\References` ve ardından **Başvuru Ekle**. İçinde **Gözat** sekmesinde, bulun `MBProvider\Dsl\bin\Debug\Company.MBProvider.Dsl.dll`

     Bu, diğer DSL kullanan kodu oluşturmanızı sağlar. Birkaç DSL'ler başvuruları oluşturmak istiyorsanız, bunları da ekleyin.

3.  DSL tanımı diyagramında diyagram sağ tıklayın ve ardından **etkinleştirmek ModelBus**. İletişim kutusunda **ModelBus kullanmak bu DSL etkinleştirmek**.

4.  Sınıfında `ExampleElement`, yeni bir etki alanı özellik eklemek `MBR`ve Özellikler penceresinde türünü ayarlamak `ModelBusReference`.

5.  Etki alanı özelliği diyagramda sağ tıklayın ve ardından **Düzenle ModelBusReference özgü özellikleri**. İletişim kutusunda **bir model öğesi**.

     Dosya iletişim filtresi aşağıdaki ayarlayın.

     `Provider File|*.provide`

     Alt dizeyi sonra "&#124;" dosya seçimi iletişim kutusu için bir filtredir. Herhangi bir dosya kullanarak izin verecek şekilde ayarlayabilirsiniz *.\*

     İçinde **Model öğesi türü** listesinde, sağlayıcı DSL (örneğin, Company.MBProvider.Task) bir veya daha fazla etki alanı sınıfları adlarını girin. Soyut sınıflar olabilirler. Liste boş bırakırsanız, kullanıcı herhangi bir öğeye başvuru ayarlayabilirsiniz.

6.  İletişim kutusunu kapatın ve **tüm şablonları dönüştürme**.

 Başka bir DSL öğelere başvuruları içeren DSL oluşturdunuz.

#### <a name="create-a-modelbus-reference-to-another-file-in-the-solution"></a>Bir çözümde ModelBus başvurusu başka bir dosyaya oluşturun

1.  MBConsumer çözümde CTRL + F5 tuşuna basın. Deneysel örneği [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] açılır **MBConsumer\Debugging** projesi.

2.  Sample.provide için bir kopyasını ekleme **MBConsumer\Debugging** projesi. ModelBus başvurusu aynı çözüm dosyasında başvurması gerekir çünkü bu gereklidir.

    1.  Hata ayıklama projesine sağ tıklayın, fareyle **Ekle**ve ardından **varolan öğeyi**.

    2.  İçinde **Öğe Ekle** iletişim kutusunda, filtrenin kümesine **tüm dosyalar (\*.\*)** .

    3.  Gidin `MBProvider\Debugging\Sample.provide` ve ardından **Ekle**.

3.  Açık `Sample.consume`.

4.  Bir örnek şekli tıklatın ve Özellikler penceresinde **[...]**  MBR özelliğinde. İletişim kutusunda **Gözat** seçip `Sample.provide`. Öğeleri penceresinde görev türü genişletin ve öğelerden birini seçin.

5.  Dosyayı kaydedin.

     (Henüz deneysel örneği kapatmayın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].)

 Başka bir model öğesi ModelBus başvuru içeren bir modeline oluşturdunuz.

#### <a name="resolve-a-modelbus-reference-in-a-text-template"></a>Metin şablonu ModelBus başvuru çözümleyin

1.  Deneysel örneğinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], bir örnek metin şablonu dosyasını açın. İçeriği aşağıdaki gibi ayarlayın.

    ```
    <#@ template debug="true" hostspecific="true" language="C#"
    inherits="Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation" #>
    <#@ MBConsumer processor="MBConsumerDirectiveProcessor" requires="fileName='Sample.consume'" #>
    <#@ output extension=".txt" #>
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0" #>
    <#@ assembly name = "Company.MBProvider.Dsl.dll" #>
    <#@ import namespace="Microsoft.VisualStudio.Modeling.Integration" #>
    <#@ import namespace="Company.MBProvider" #>
    <#
      // Property provided by the Consumer directive processor:
      ExampleModel consumerModel = this.ExampleModel;
      // Iterate through Consumer model, listing the elements:
      foreach (ExampleElement element in consumerModel.Elements)
      {
    #>
       <#= element.Name #>
    <#
        if (element.MBR != null)
      using (ModelBusAdapter adapter = this.ModelBus.CreateAdapter(element.MBR))
      {
              // If we allowed multiple types or DSLs in the MBR, discover type here.
        Task task = adapter.ResolveElementReference<Task>(element.MBR);
    #>
            <#= element.Name #> is linked to Task: <#= task==null ? "(null)" : task.Name #>
    <#
          }
      }
    #>

    ```

     Aşağıdaki noktaları dikkat edin:

    1.  `hostSpecific` Ve `inherits` özniteliklerini `template` yönergesi olarak ayarlanmalıdır.

    2.  Tüketici modeli normal şekilde bu DSL oluşturulan yönerge işlemcisi aracılığıyla erişilir.

    3.  Derleme ve içeri aktarma yönergeleri ModelBus ve DSL sağlayıcısı türlerine erişebilir olması gerekir.

    4.  Birçok MBRs aynı modeline bağlı olduğunu biliyorsanız, yalnızca bir kez CreateAdapter çağırmak daha iyidir.

2.  Şablonu kaydedin. Sonuçta elde edilen metin dosyası aşağıdakine benzer olduğunu doğrulayın.

    ```

    ExampleElement1
    ExampleElement2
         ExampleElement2 is linked to Task: Task2

    ```

#### <a name="resolve-a-modelbus-reference-in-a-gesture-handler"></a>Hareket işleyicisi ModelBus başvuru çözümleyin

1.  Deneysel örneklerini kapatın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], çalışıyorsa.

2.  MBConsumer\Dsl\Custom.cs adlı ve içeriği şuna ayarlanmış bir dosya ekleyin.

    ```

    namespace Company.MB2Consume
    {
      using Microsoft.VisualStudio.Modeling.Integration;
      using Company.MB3Provider;

      public partial class ExampleShape
      {
        public override void OnDoubleClick(Microsoft.VisualStudio.Modeling.Diagrams.DiagramPointEventArgs e)
        {
          base.OnDoubleClick(e);
          ExampleElement element = this.ModelElement as ExampleElement;
          if (element.MBR != null)
          {
            IModelBus modelbus = this.Store.GetService(typeof(SModelBus)) as IModelBus;
            using (ModelBusAdapter adapter = modelbus.CreateAdapter(element.MBR))
            {
              Task task = adapter.ResolveElementReference<Task>(element.MBR);
              // Open a window on this model:
              ModelBusView view = adapter.GetDefaultView();
              view.Show();
              view.SetSelection(element.MBR);
            }
          }
        }
      }
    }

    ```

3.  CTRL + F5 tuşuna basın.

4.  Deneysel örneğinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], açık `Debugging\Sample.consume`.

5.  Bir şekli çift tıklatın.

     Bu öğede MBR ayarlarsanız başvurulan model açar ve başvurulan öğenin seçilir.

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Modelbus'ı Kullanarak Modelleri Tümleştirme](../modeling/integrating-models-by-using-visual-studio-modelbus.md)
- [Kod Oluşturma ve T4 Metin Şablonları](../modeling/code-generation-and-t4-text-templates.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
