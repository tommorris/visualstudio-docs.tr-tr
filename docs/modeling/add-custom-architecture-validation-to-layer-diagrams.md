---
title: Bağımlılık diyagramlarına özel mimari doğrulaması ekleme
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, adding custom validation
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2599a0c9e4390ed3d25cfc6393a32d72d803bd0e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31952550"
---
# <a name="add-custom-architecture-validation-to-dependency-diagrams"></a>Bağımlılık diyagramlarına özel mimari doğrulaması ekleme
Kaynak kodu bağımlılık diyagramında bağımlılıklara doğrulayabilir Visual Studio'da katman modeli karşı bir proje kaynak kodunda kullanıcılar doğrulayabilirsiniz. Standart doğrulama algoritması yoktur, ancak kendi doğrulama uzantıları tanımlayabilirsiniz.

 Kullanıcı seçtiğinde **Mimariyi Doğrula** standart doğrulama yöntemi çağrıldığında, yüklü olan tüm doğrulama uzantıları tarafından izlenen bir bağımlılık diyagramda komutu.

> [!NOTE]
>  Bir bağımlılık diyagramında diyagramı program kod çözümün diğer bölümleri ile karşılaştırmak için doğrulama ana amacı budur.

 İçine bir Visual Studio Tümleştirme Uzantısı (hangi diğer Visual Studio kullanıcılara dağıtabilirsiniz VSIX), katman doğrulama uzantınızı paketleyebilirsiniz. Doğrulayıcı içinde VSIX içine tek başına yerleştirebilirsiniz veya başka bir uzantısı olarak aynı VSIX birleştirebilirsiniz. Doğrulayıcı kodunu kendi Visual Studio projesi, başka bir uzantısı olarak aynı projede değil yazmalısınız.

> [!WARNING]
>  Doğrulama projesi oluşturduktan sonra kopyalama [örnek kod](#example) sonunda bu konu ve kendi için ihtiyaç duyduğu ardından düzenleyin.

## <a name="requirements"></a>Gereksinimler
 Bkz: [gereksinimleri](../modeling/extend-layer-diagrams.md#prereqs).

## <a name="defining-a-layer-validator-in-a-new-vsix"></a>Yeni bir VSIX bir katman Doğrulayıcı tanımlama
 Bir doğrulayıcı oluşturma en hızlı yöntemdir proje şablonu kullanmaktır. Bu seçenek, kod ve VSIX bildirimini aynı projeye yerleştirir.

#### <a name="to-define-an-extension-by-using-a-project-template"></a>Bir proje şablonu kullanarak bir uzantısı tanımlamak için

1.  Kullanarak yeni bir çözümde bir proje oluşturma **yeni proje** komutunu **dosya** menüsü.

2.  İçinde **yeni proje** iletişim kutusunda **modelleme projeleri**seçin **katman Tasarımcısı doğrulama uzantısı**.

     Şablon küçük bir örnek içeren bir proje oluşturur.

    > [!WARNING]
    >  Okunabilmesini sağlamak şablonu için iş düzgün:
    >
    >  -   Çağrı Düzenle `LogValidationError` isteğe bağlı bağımsız değişkenler kaldırmak için `errorSourceNodes` ve `errorTargetNodes`.
    > -   Özel özellikler kullanırsanız, belirtilen güncelleştirmesini [bağımlılık diyagramlarına özel özellikler ekleme](../modeling/add-custom-properties-to-layer-diagrams.md).

3.  Doğrulama tanımlamak için kodu düzenleyin. Daha fazla bilgi için bkz: [programlama doğrulama](#programming).

4.  Uzantı sınamak için bkz: [hata ayıklama katman doğrulaması](#debugging).

    > [!NOTE]
    >  Yalnızca belirli durumlarda yönteminiz olarak adlandırılır ve kesme noktaları otomatik olarak çalışmaz. Daha fazla bilgi için bkz: [hata ayıklama katman doğrulaması](#debugging).

5.  Ana örneğinde Visual Studio'nun ya da başka bir bilgisayarda uzantıyı yüklemek için bulma **.vsix** dosyasını **bin\\\***. Yüklemek istediğiniz bilgisayara kopyalayın ve ardından çift tıklatın. Kaldırmak için kullanın **Uzantılar ve güncelleştirmeler** üzerinde **Araçları** menüsü.

## <a name="adding-a-layer-validator-to-a-separate-vsix"></a>Bir katman doğrulayıcı için ayrı bir VSIX ekleme
 Katman doğrulayıcıları, komutları ve diğer uzantıları içeren bir VSIX oluşturmak istiyorsanız, VSIX tanımlamak için bir proje ve işleyicileri için ayrı projeler oluşturmanızı öneririz.

#### <a name="to-add-layer-validation-to-a-separate-vsix"></a>Katman doğrulaması için ayrı bir VSIX eklemek için

1.  Bir sınıf kitaplığı proje yeni veya varolan bir Visual Studio çözümünde oluşturun. İçinde **yeni proje** iletişim kutusu, tıklatın **Visual C#** ve ardından **sınıf kitaplığı**. Bu proje katman doğrulama sınıfı içerir.

2.  Çözümünüzde VSIX projesi oluşturun veya tanımlayın. Bir VSIX proje adlı bir dosyayı içeren **source.extension.vsixmanifest**. VSIX proje eklemeniz gerekiyorsa, şu adımları izleyin:

    1.  İçinde **yeni proje** iletişim kutusunda, seçin **Visual C#**, **genişletilebilirlik**, **VSIX proje**.

    2.  İçinde **Çözüm Gezgini**, VSIX proje kısayol menüsünde **başlangıç projesi olarak ayarla**.

3.  İçinde **source.extension.vsixmanifest**altında **varlıklar**, MEF Bileşeni olarak katman doğrulama projesi ekleyin:

    1.  Seçin **yeni**.

    2.  İçinde **ekleme yeni varlık** iletişim kutusu, ayarla:

         **Type** = **Microsoft.VisualStudio.MefComponent**

         **Kaynak** = **geçerli çözümdeki bir proje ile**

         **Proje** = *Doğrulayıcı projenizi*

4.  Bu katman doğrulama da eklemelisiniz:

    1.  Seçin **yeni**.

    2.  İçinde **ekleme yeni varlık** iletişim kutusu, ayarla:

         **Tür** = **Microsoft.VisualStudio.ArchitectureTools.Layer.Validator**. Bu seçenekler aşağı açılan listesinde biri değil. Klavyeden girmelisiniz.

         **Kaynak** = **geçerli çözümdeki bir proje ile**

         **Proje** = *Doğrulayıcı projenizi*

5.  Katman doğrulaması projeye dönün ve aşağıdaki proje başvurularını ekleyin:

    |**Başvuru**|**Ne bu yapmanıza izin verir**|
    |-------------------|------------------------------------|
    |Microsoft.VisualStudio.GraphModel.dll|Mimari grafiği okuma|
    |Microsoft.VisualStudio.ArchitectureTools.Extensibility.CodeSchema.dll|Kod DOM katmanlarıyla ilişkili okuma|
    |Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.dll|Katman modeli okuma|
    |Microsoft.VisualStudio.ArchitectureTools.Extensibility|Okuma ve şekiller ve diyagramları güncelleyebilir.|
    |System.ComponentModel.Composition|Yönetilen Genişletilebilirlik Çerçevesi (MEF) kullanarak doğrulama bileşeni tanımlayın|
    |Microsoft.VisualStudio.Modeling.Sdk.[version]|Model uzantılarını tanımlayın|

6.  Kod örneği, bu konunun sonunda, doğrulama kodunu içeren için Doğrulayıcı kitaplığı projenizdeki sınıfı dosyasına kopyalayın. Daha fazla bilgi için bkz: [programlama doğrulama](#programming).

7.  Uzantı sınamak için bkz: [hata ayıklama katman doğrulaması](#debugging).

    > [!NOTE]
    >  Yalnızca belirli durumlarda yönteminiz olarak adlandırılır ve kesme noktaları otomatik olarak çalışmaz. Daha fazla bilgi için bkz: [hata ayıklama katman doğrulaması](#debugging).

8.  VSIX ana örneğinde Visual Studio veya başka bir bilgisayara yüklemek için bulma **.vsix** dosyasını **bin** VSIX proje dizininde. VSIX yüklemek istediğiniz bilgisayara kopyalayın. Windows Gezgini'nde VSIX dosyasını çift tıklatın.

     Kaldırmak için kullanın **Uzantılar ve güncelleştirmeler** üzerinde **Araçları** menüsü.

##  <a name="programming"></a> Programlama doğrulama
 Katman doğrulaması uzantısı tanımlamak için aşağıdaki özelliklere sahip bir sınıf tanımlama:

-   Genel form bildirimiyle aşağıdaki gibidir:

    ```

    using System.ComponentModel.Composition;
    using Microsoft.VisualStudio.ArchitectureTools.Extensibility.CodeSchema;
    using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;
    using Microsoft.VisualStudio.GraphModel;
    ...
     [Export(typeof(IValidateArchitectureExtension))]
      public partial class Validator1Extension :
                      IValidateArchitectureExtension
      {
        public void ValidateArchitecture(Graph graph)
        {
           GraphSchema schema = graph.DocumentSchema;
          ...
      } }
    ```

-   Bir hata bulduğunuzda, bunu kullanarak bildirebilirsiniz `LogValidationError()`.

    > [!WARNING]
    >  İsteğe bağlı parametreleri kullanmayın `LogValidationError`.

 Kullanıcı ne zaman çağırır **Mimariyi Doğrula** menü komutu, katman çalışma zamanı sistem analizleri yaparken katmanları ve bir grafik oluşturmak için kendi yapıları. Grafik dört bölümden oluşur:

-   Düğümleri ve bağlantıları grafikte olarak temsil edilir katman modellerini Visual Studio çözümü.

-   Kod, proje öğeleri ve diğer çözümde tanımlanır ve düğümler ve çözümleme işlemi tarafından bulunan bağımlılıkları temsil bağlantılar olarak gösterilen mimarilere.

-   Kod yapı düğümlerinin bağlantılar katman düğümlerinden.

-   Doğrulayıcı tarafından bulunan hataların temsil eden düğümleri.

 Grafik oluşturulan, standart doğrulama yöntemi çağrılır. Bu tamamlandığında, herhangi bir yüklü uzantısı doğrulama yöntem belirtilmemiş sırayla denir. Grafik için her geçirilen `ValidateArchitecture` grafiği tarayabilir ve bulduğu herhangi bir hata raporu yöntemi.

> [!NOTE]
>  Bu etki alanına özgü dillerde kullanılabilir doğrulama işlemi ile aynı değildir.

 Doğrulama yöntemlerinin katman modeli veya Doğrulanmakta olan kodu değiştirmemelisiniz.

 Grafik modeli tanımlanan <xref:Microsoft.VisualStudio.GraphModel>. Kendi asıl sınıflardır <xref:Microsoft.VisualStudio.GraphModel.GraphNode> ve <xref:Microsoft.VisualStudio.GraphModel.GraphLink>.

 Her düğüm ve her bir bağlantının öğesi veya temsil ettiği ilişki türünü belirten bir veya daha fazla kategoriye sahip. Tipik bir grafiği aşağıdaki kategorilerde düğümünüz:

-   Dsl.LayerModel

-   Dsl.Layer

-   Dsl.Reference

-   CodeSchema_Type

-   CodeSchema_Namespace

-   CodeSchema_Type

-   CodeSchema_Method

-   CodeSchema_Field

-   CodeSchema_Property

 Kodda öğelerine bağlantılar katmanlardan "Temsil eder" kategorisi vardır.

##  <a name="debugging"></a> Doğrulama hata ayıklama
 Katman doğrulaması uzantınızı hata ayıklamak için CTRL + F5 tuşuna basın. Visual Studio Deneysel bir örneğini açar. Bu örnekte, bir katman modeli oluşturun veya açın. Bu model kodu ile ilişkilendirilmelidir ve en az bir bağımlılığa sahip olması gerekir.

### <a name="test-with-a-solution-that-contains-dependencies"></a>Bağımlılıklar içeren bir çözüm ile test
 Aşağıdaki özelliklere yoksa doğrulama yürütülmedi:

-   Bağımlılık diyagramı en az bir bağımlılık bağlantısı yoktur.

-   Kod öğelerle ilişkili olan model Katmanlar vardır.

 Doğrulama uzantınızı test etmek için Visual Studio deneysel örneği ilk başlattığınızda bu özelliklere sahip bir çözüm oluşturun veya açın.

### <a name="run-clean-solution-before-validate-architecture"></a>Önce çalışma temiz çözüm mimarisi doğrula
 Doğrulama kodunuzu güncelleştirdiğinizde kullanmak **temiz çözüm** komutunu **yapı** Deneysel çözümde doğrulama komutu test önce menüsü. Doğrulama sonuçlarını önbelleğe alındığı için bu gereklidir. Test bağımlılık diyagramı veya kendi kod gerçekleştirmediyseniz doğrulama yöntemlerinin çalıştırılmayacak.

### <a name="launch-the-debugger-explicitly"></a>Hata ayıklayıcı açıkça başlatma
 Doğrulama ayrı bir işlemde çalıştırır. Bu nedenle, doğrulama yönteminde kesme noktaları tetiklenir değil. Doğrulama başlatıldığında işleme hata ayıklayıcı açık olarak iliştirin gerekir.

 Hata ayıklayıcı doğrulama işlemine eklemek üzere bir çağrı ekleyin `System.Diagnostics.Debugger.Launch()` doğrulama yönteminizi başlangıcında. Hata ayıklama iletişim kutusu göründüğünde, Visual Studio ana örneğini seçin.

 Alternatif olarak, bir çağrı ekleyebilirsiniz `System.Windows.Forms.MessageBox.Show()`. İleti kutusu göründüğünde Visual Studio ve ana örneğine gidin **hata ayıklama** menüsünü tıklatın **ekleme işlemi için**. Adlı işlemini seçin **Graphcmd.exe**.

 Her zaman CTRL + F5'e basarak Deneysel örneğini başlatın (**hata ayıklama olmadan Başlat**).

### <a name="deploying-a-validation-extension"></a>Bir doğrulama uzantısı dağıtma
 Doğrulama uzantınızın Visual Studio uygun bir sürümü yüklü olduğu bir bilgisayara yüklemek için hedef bilgisayarda VSIX dosyasını açın. Bir bilgisayara yüklemek için [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)] olan yüklü, el ile VSIX içeriğini uzantıları klasörüne ayıklamanız gerekir. Daha fazla bilgi için bkz: [katman modeli uzantısı dağıtma](../modeling/deploy-a-layer-model-extension.md).

##  <a name="example"></a> Örnek kod

```csharp
using System;
using System.ComponentModel.Composition;
using System.Globalization;
using System.Linq;
using System.Text.RegularExpressions;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.CodeSchema;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;
using Microsoft.VisualStudio.GraphModel;

namespace Validator3
{
    [Export(typeof(IValidateArchitectureExtension))]
    public partial class Validator3Extension : IValidateArchitectureExtension
    {
        /// <summary>
        /// Validate the architecture
        /// </summary>
        /// <param name="graph">The graph</param>
        public void ValidateArchitecture(Graph graph)
        {
            if (graph == null) throw new ArgumentNullException("graph");

            // Uncomment the line below to debug this extension during validation
            // System.Windows.Forms.MessageBox.Show("Attach 2 to GraphCmd.exe with process id " + System.Diagnostics.Process.GetCurrentProcess().Id);

            // Get all layers on the diagram
            foreach (GraphNode layer in graph.Nodes.GetByCategory("Dsl.Layer"))
            {
                System.Threading.Thread.Sleep(100);
                // Get the required regex property from the layer node
                string regexPattern = "^[a-zA-Z]+$"; //layer[customPropertyCategory] as string;
                if (!string.IsNullOrEmpty(regexPattern))
                {
                    Regex regEx = new Regex(regexPattern);

                    // Get all referenced types in this layer including those from nested layers so each
                    // type is validated against all containing layer constraints.
                    foreach (GraphNode containedType in layer.FindDescendants().Where(node => node.HasCategory("CodeSchema_Type")))
                    {
                        // Check the type name against the required regex
                        CodeGraphNodeIdBuilder builder = new CodeGraphNodeIdBuilder(containedType.Id, graph);
                        string typeName = builder.Type.Name;
                        if (!regEx.IsMatch(typeName))
                        {
                            // Log an error
                            string message = string.Format(CultureInfo.CurrentCulture, Resources.InvalidTypeNameMessage, typeName);
                            this.LogValidationError(graph, typeName + "TypeNameError", message, GraphErrorLevel.Error, layer);
                        }
                    }
                }

            }

        }
    }
}
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Bağımlılık diyagramlarını genişletme](../modeling/extend-layer-diagrams.md)
