---
title: Kodlanmış UI testi Visual Studio'da veri güdümlü oluşturma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, data-driven
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 442e37dfac8e7eb022ee12bfaadacae548625793
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36303046"
---
# <a name="create-a-data-driven-coded-ui-test"></a>Veri tabanlı kodlanmış UI testi oluşturma

Farklı koşullarda test etmek için farklı parametre değerleri ile birden çok kez testleri çalıştırabilirsiniz. Veri tabanlı kodlanmış UI testleri bunu yapmak için uygun bir yöntemdir. Kodlanmış UI Test yineleme veri kaynağındaki her satır olduğundan ve bir veri kaynağı, parametre değerleri tanımlayın. Genel test sonucu, tüm yinelemeleri sonucunu dayalı olacak. Örneğin, bir test yineleme başarısız olursa genel test sonucu başarısız olur.

**Gereksinimler**

- Visual Studio Enterprise
- Kodlanmış UI test bileşeni

## <a name="create-a-test-project"></a>Bir test projesi oluşturma

Bu örnek Windows hesap makinesi uygulamanın çalıştığı kodlanmış bir UI testi oluşturur. İki sayıyı toplar ve toplamı doğru olduğunu doğrulamak için onayı ifade kullanır. Ardından, onaylama ve iki sayının parametre değerlerini verilere ve virgülle ayrılmış bir değer depolanan olmasını kodlanmıştır (*.csv*) dosyası.

### <a name="step-1---create-a-coded-ui-test"></a>1. adım - kodlanmış UI testi oluşturma

1.  Bir proje oluşturun.

     ![Kodlanmış UI testi projesi oluşturma](../test/media/cuit_datadriven_.png)

   > [!NOTE]
   > Görmüyorsanız, **kodlanmış UI Test projesine** şablonu, gereken [kodlanmış UI test bileşeni](../test/use-ui-automation-to-test-your-code.md#install-the-coded-ui-test-component).

2.  Tercih **eylemleri kaydetmek**.

     ![Eylemleri kaydetmek seçin](../test/media/cuit_datadriven_generatecodedialog.png)

3.  Hesaplayıcı uygulamasını açın ve test kaydı başlatın.

     ![Kayıt Eylemler](../test/media/cuit_datadriven_cuitbuilder.png)

4.  1 ve 2 ekleyin, kaydedici duraklatma ve test yöntemi oluşturun. Daha sonra bir veri dosyasından gelen değerlerle Biz bu kullanıcı girişi değerlerini değiştirirsiniz.

     ![Genetate test yöntemi](../test/media/cuit_datadriven_cuitbuildergencode.png)

     Test Oluşturucusu'nu kapatın. Yöntemi, test eklenir:

    ```csharp
    [TestMethod]
    public void CodedUITestMethod1()
    {
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.AddNumbers();
    }
    ```

5.  Kullanım `AddNumbers()` test çalıştığını doğrulamak için yöntem. Yukarıda gösterilen test yöntemi imleci yerleştirin, bağlam menüsünü açın ve seçin **Testleri Çalıştır**. (Klavye kısayolu: **Ctrl**+**R**,**T**).

     Test geçirilen ya da başarısız olmuşsa gösterir test sonucu görüntülenir **Test Gezgini** penceresi. Gelen Test Gezgini penceresi açmak için **Test** menüsünde seçin **Windows** ve ardından **Test Gezgini**.

6.  Bir veri kaynağı onaylama parametre değerleri için de kullanılabilir olmadığından — kullanılan test tarafından beklenen değerler doğrulamak için — iki sayının toplamını doğru olduğunu doğrulamak için onayı ifade ekleyelim. Yukarıda gösterilen test yöntemi imleci yerleştirin, bağlam menüsünü açın ve seçin **kodlanmış UI testi için kod üret**ve ardından **kullanım kodlanmış UI Test oluşturucusunu**.

     Sum görüntüler hesaplayıcı metin denetiminde eşleyin.

     ![UI metin denetimini eşleme](../test/media/cuit_datadriven_addassertion.png)

7.  Toplam değeri doğru olduğunu doğrulayan bir onaylama ekleyin. Seçin **görüntü metni** değerine sahip özellik **3** ve ardından **onay Ekle**. Kullanım **AreEqual** karşılaştırıcı ve karşılaştırma değeri olduğundan emin olun **3**.

     ![Onaylama işlemi yapılandırma](../test/media/cuit_datadriven_builderaddassertion2.png)

8.  Onaylama işlemi yapılandırdıktan sonra kodu yeniden Oluşturucu oluşturur. Bu doğrulama için yeni bir yöntem oluşturur.

     ![Üretme onaylama yöntemi](../test/media/cuit_datadriven_assertiongencode.png)

     Çünkü `ValidateSum` yöntemi doğrulama sonuçlarını `AddNumbers` yöntemi, kod bloğunun altına taşıyın.

    ```csharp
    public void CodedUITestMethod1()
    {
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.AddNumbers();
        this.UIMap.ValidateSum();
    }
    ```

9. Test kullanarak çalıştığını doğrulamanız `ValidateSum()` yöntemi. Yukarıda gösterilen test yöntemi imleci yerleştirin, bağlam menüsünü açın ve seçin **Testleri Çalıştır**. (Klavye kısayolu: **Ctrl**+**R**,**T**).

     Bu noktada, tüm parametre değerleri kendi yöntemlerini sabitleri tanımlanır. Ardından, veri güdümlü bizim test yapmak için bir veri kümesi oluşturalım.

### <a name="step-2---create-a-data-set"></a>2. adım - bir veri kümesi oluşturma

1.  Bir metin dosyası adlı dataDrivenSample projeye ekleyin *data.csv*.

     ![Bir virgülle ayrılmış değer dosyası projeye ekleyin](../test/media/cuit_datadriven_addcsvfile.png)

2.  Doldurmak *.csv* aşağıdaki veri dosyası:

    |Num1|Num2|TOPLA|
    |-|-|-|
    |3|4|7|
    |5|6|11|
    |6|8|14|

     Veri eklendikten sonra dosyanın aşağıdaki gibi görünmelidir:

     ![.Csv dosyasını verilerle doldurma](../test/media/cuit_datadriven_adddatatocsvfile.png)

3.  Kaydetmek önemlidir *.csv* doğru kodlama kullanılarak dosya. Üzerinde **dosya** menüsünde seçin **Gelişmiş kaydetme seçenekleri** ve **Unicode (UTF-8 imza olmadan) - Codepage 65001** kodlama olarak.

4.  *.Csv* dosya, çıktı dizinine kopyalanmalıdır veya test çalışamaz. Kullanım **özellikleri** penceresi kopyalayın.

     ![.Csv dosyasını dağıtın](../test/media/cuit_datadriven_deploycsvfile.png)

     Şimdi biz oluşturulan veri kümesi sahip olduğunuza göre verileri test bağlayın.

### <a name="step-3---add-data-source-binding"></a>3. adım - veri kaynağına bağlama ekleme

1.  Veri kaynağı bağlamak için add bir `DataSource` varolan içinde öznitelik `[TestMethod]` hemen test yöntemi bir öznitelik.

    ```csharp
    [DataSource("Microsoft.VisualStudio.TestTools.DataSource.CSV", "|DataDirectory|\\data.csv", "data#csv", DataAccessMethod.Sequential), DeploymentItem("data.csv"), TestMethod]
    public void CodedUITestMethod1()
    {
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.AddNumbers();
        this.UIMap.ValidateSum();
    }
    ```

     Veri kaynağı artık bu test yöntemi kullanmak kullanılabilir.

    > [!TIP]
    > Bkz: [veri kaynağı özniteliği örnekleri](#CreateDataDrivenCUIT_QA_DataSourceAttributes) soru-cevap XML, SQL Express ve Excel gibi diğer veri kaynağı türleri kullanma örnekleri için bir bölüm.

2.  Testi çalıştırın.

     Üç yineleme ile test çalışmaları dikkat edin. Bağlanan veri kaynağı üç veri satırı içermesidir. Ancak, test yine sabit parametre değerlerini kullanarak ve her zaman 1 + 2 3 toplamı ile ekleyerek de görürsünüz.

     Ardından, veri kaynağı dosyasında değerleri kullanmak için test yapılandıracağız.

### <a name="step-4---use-the-data-in-the-coded-ui-test"></a>4. adım - kodlanmış UI testi verileri kullanma

1.  Ekleme `using Microsoft.VisualStudio.TestTools.UITesting.WinControls` üstüne *CodedUITest.cs* dosyası:

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Text.RegularExpressions;
    using System.Windows.Input;
    using System.Windows.Forms;
    using System.Drawing;
    using Microsoft.VisualStudio.TestTools.UITesting;
    using Microsoft.VisualStudio.TestTools.UnitTesting;
    using Microsoft.VisualStudio.TestTools.UITest.Extension;
    using Keyboard = Microsoft.VisualStudio.TestTools.UITesting.Keyboard;
    using Microsoft.VisualStudio.TestTools.UITesting.WinControls;
    ```

2.  Ekleme `TestContext.DataRow[]` içinde `CodedUITestMethod1()` değerleri veri kaynağından uygulanacak yöntemi. Veri kaynağı değerlerini denetimlerini kullanarak UIMap denetimlere atanan sabitleri geçersiz kılma `SearchProperties`:

    ```csharp
    public void CodedUITestMethod1()
    {
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.UICalculatorWindow.UIItemWindow.UIItem1Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num1"].ToString();this.UIMap.UICalculatorWindow.UIItemWindow21.UIItem2Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num2"].ToString();
        this.UIMap.AddNumbers();
        this.UIMap.ValidateSumExpectedValues.UIItem2TextDisplayText = TestContext.DataRow["Sum"].ToString();
        this.UIMap.ValidateSum();
    }
    ```

     Verileri kodlamak için hangi arama özelliklerinin tahmin için kodlanmış UI Test Düzenleyicisi'ni kullanın.

    -   Açık *UIMap.uitest* dosya.

         ![Kodlanmış UI Test Düzenleyicisi'ni açın](../test/media/cuit_datadriven_opentesteditor.png)

    -   UI eylem seçin ve ilgili kullanıcı Arabirimi denetim eşleme gözlemleyin. Nasıl eşleme koduna, örneğin, karşılık gelen fark `this.UIMap.UICalculatorWindow.UIItemWindow.UIItem1Button`.

         ![Koduyla yardımcı olmak için kodlanmış UI Test Düzenleyicisi'ni kullanın](../test/media/cuit_datadriven_testeditor.png)

    -   İçinde **özellikleri** penceresinde, açık **arama özellikleri**. Arama özellikleri **adı** değerdir'ın veri kaynağını kullanarak kod içinde ne yönetilebilir. Örneğin, `SearchProperties` her veri satırının ilk sütununu değerler atanır: `UIItem1Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num1"].ToString();`. Üç yineleme için bu sınama değiştirir **adı** 3, ardından 5 ve son olarak 6 arama özelliği için değer.

         ![Kodlama yardımcı olmak için arama özelliklerini kullanın](../test/media/cuit_datadriven_searchproperties.png)

3.  Çözüm kaydedin.

### <a name="step-5---run-the-data-driven-test"></a>Adım 5 - verilere test çalıştırma

1.  Test şimdi test yeniden çalıştırarak veri tabanlı olduğundan emin olun.

     Değerleri kullanan üç yinelemeleri aracılığıyla testi görmelisiniz *.csv* dosya. Doğrulama de çalışması gerekir ve test Test Explorer'ın geçti olarak görüntülenmelidir.

## <a name="q--a"></a>Soru - Yanıt

###  <a name="CreateDataDrivenCUIT_QA_DataSourceAttributes"></a> SQL Express veya XML gibi diğer veri kaynağı türleri için veri kaynağı öznitelikleri nelerdir?

Kodunuza kopyalayarak ve gereken özelleştirmeleri yaparak, aşağıdaki tabloda örnek veri kaynağı dizeleri kullanabilirsiniz.

**Veri kaynağı türleri ve öznitelikleri**

-   CSV

     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.CSV", "|DataDirectory|\\data.csv", "data#csv", DataAccessMethod.Sequential), DeploymentItem("data.csv"), TestMethod]`

-   Excel

     `DataSource("System.Data.Odbc", "Dsn=ExcelFiles;Driver={Microsoft Excel Driver (*.xls)};dbq=|DataDirectory|\\Data.xls;defaultdir=.;driverid=790;maxbuffersize=2048;pagetimeout=5;readonly=true", "Sheet1$", DataAccessMethod.Sequential), DeploymentItem("Sheet1.xls"), TestMethod]`

-   Team Foundation Server'da test durumu

     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.TestCase", "http://vlm13261329:8080/tfs/DefaultCollection;Agile", "30", DataAccessMethod.Sequential), TestMethod]`

-   XML

     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.XML", "|DataDirectory|\\data.xml", "Iterations", DataAccessMethod.Sequential), DeploymentItem("data.xml"), TestMethod]`

-   SQL Express

     `[DataSource("System.Data.SqlClient", "Data Source=.\\sqlexpress;Initial Catalog=tempdb;Integrated Security=True", "Data", DataAccessMethod.Sequential), TestMethod]`

### <a name="q-why-cant-i-modify-the-code-in-the-uimapdesigner-file"></a>S: neden UIMap.Designer dosyasındaki kodu değiştirilemez?

**Y:** herhangi bir kod, yaptığınız değişiklikleri *UIMapDesigner.cs* UIMap - Kodlanmış UI Test derleyicisini kullanarak kod oluşturma her zaman dosya yazılır. Bu örnekte ve çoğu durumda, bir veri kaynağı kullanmak bir test etkinleştirmek için gereken kod değişikliği testin kaynak kodu dosyasına yapılabilir (diğer bir deyişle, *Codeduıtest1.cs*).

Kayıtlı bir yöntemi değiştirmeniz gerekiyorsa, kendisine kopyalamalısınız *UIMap.cs* dosya ve yeniden adlandırın. *UIMap.cs* dosya, yöntemleri ve özellikleri geçersiz kılmak için kullanılabilir *UIMapDesigner.cs* dosya. Kodlanmış özgün yöntemi referansı kaldırmalısınız *UITest.cs* dosya ve adlandırılan yöntem adıyla değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>
- [UI otomasyonunu kullanarak kodunuzu test etme](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI testleri için en iyi yöntemler](../test/best-practices-for-coded-ui-tests.md)
- [Kodlanmış UI testleri ve eylem kayıtları için desteklenen yapılandırmalar ve platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)