---
title: "Nasıl yapılır: Visual Studio'da tanılama veri bağdaştırıcısı oluşturma"
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, creating
ms.assetid: bd7ad36c-54cb-4d2a-9aea-9d10ad98d7ba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 923296a6eaed79edc345b9071d5e1d4e2ececefe
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844748"
---
# <a name="how-to-create-a-diagnostic-data-adapter"></a>Nasıl yapılır: Tanılama Veri Bağdaştırıcısı Oluşturma

Oluşturmak için bir *tanılama veri bağdaştırıcısı*, Visual Studio kullanarak bir sınıf kitaplığı oluşturmak ve ardından tanılama veri bağdaştırıcısı API'leri Visual Studio kuruluş tarafından sağlanan Sınıf Kitaplığı'na ekleyin. Bir akış veya dosya olarak istediğiniz herhangi bir bilgi Gönder <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink> test çalıştırma sırasında oluşturulan olayları işlerken framework tarafından sağlanan. Akışlar veya gönderilen dosyaları <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink> test tamamlandığında test sonuçlarına ek olarak depolanır. Oluşturursanız, bu hatadan test sonuçları veya kullandığınızda [!INCLUDE[mtrlong](../test/includes/mtrlong_md.md)], dosyalar hataya bağlanır.

 Testlerinizi çalıştırdığı makine ya da test altındaki uygulamanızı çalıştırmak için kullandığınız ortamının bir parçası olan bir makineye etkileyen tanılama veri bağdaştırıcısı oluşturabilirsiniz. Örneğin, burada testler dosyalarını test makinenizde toplama veya uygulamanız için Web sunucusu rolündeki sunan makinedeki dosyaları toplama.

 Microsoft Test Yöneticisi'ni veya Visual Studio kullanarak test ayarlarınızı oluşturduğunuzda görüntüleyen bir kolay ad tanılama veri bağdaştırıcınızın verebilirsiniz. Test ayarları testlerinizi çalıştırdığınızda, ortamınızda hangi makine rolü özel tanılama veri bağdaştırıcıları çalıştıracağını tanımlamanıza olanak sağlar. Test ayarlarınızı oluşturduğunuzda, tanılama veri bağdaştırıcıları de yapılandırabilirsiniz. Örneğin, Web sunucunuzdan özel günlükleri toplayan tanılama veri bağdaştırıcısı oluşturabilir. Test ayarlarınızı oluşturduğunuzda, bu tanılama veri bağdaştırıcısı makine ya da bu Web sunucusu rolü gerçekleştiren makineler çalıştırmayı seçebilirsiniz ve oluşturulan son üç günlükleri toplamak için test ayarlarınızı yapılandırmasını değiştirebilirsiniz. Test ayarları hakkında daha fazla bilgi için bkz: [toplamak tanılama bilgileri kullanarak Test ayarlarını](../test/collect-diagnostic-information-using-test-settings.md).

 Tanılama veri bağdaştırıcınızın görevleri bu noktada testinde gerçekleştirebilmeleri için testlerinizi çalıştırdığınızda olaylar oluşturulur.

> [!IMPORTANT]
> Özellikle birden çok makinelerde çalışan testleri olduğunda bu olayları farklı iş parçacıklarında, yükseltilmiş. Bu nedenle, olası iş parçacığı sorunlarının farkında ve istemeden özel bağdaştırıcının iç verileri bozuk. Tanılama veri bağdaştırıcınızın iş parçacığı güvenli olduğundan emin olun.

 Tanılama veri bağdaştırıcınızın oluştururken kullanabileceğiniz anahtar olayların kısmi bir listesi verilmiştir. Tanılama veri bağdaştırıcısı olaylarının tam bir listesi için bkz: Özet <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents> sınıfı.

|Olay|Açıklama|
|-----------|-----------------|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.SessionStart>|Test çalışması başlangıcı|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.SessionEnd>|Test çalışması sonu|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseStart>|Test çalışması her testte başlangıcı|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseEnd>|Test çalışması her testte sonu|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestStepStart>|Her bir test adımını bir test başlangıcı|
|<xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestStepEnd>|Her bir test adımını bir test sonu|

> [!NOTE]
> El ile test tamamlandığında, hiçbir daha fazla veri toplama olayları için tanılama veri bağdaştırıcısı gönderilir. Bir test yeniden çalıştırıldığında yeni bir test durumu tanımlayıcısına sahip olur. Bir kullanıcı bir test sırasında test sıfırlar varsa (hangi başlatır <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents.TestCaseReset> olay), veya değişiklikleri test adımı sonucunu, veri koleksiyonu olayı için tanılama veri bağdaştırıcısı gönderilir, ancak test çalışması tanımlayıcısını aynı kalır. Bir test çalışması sıfırlama olup olmadığını belirlemek için tanılama veri bağdaştırıcınızın test çalışması tanımlayıcısını izlemeniz gerekir.

 Test ayarlarınızı oluşturduğunuzda, yapılandırma bilgilerine dayalı bir veri dosyası toplayan tanılama veri bağdaştırıcısı oluşturmak için aşağıdaki yordamı kullanın.

 Özel yapılandırma düzenleyicisi de dahil olmak üzere bir tam örnek tanılama veri bağdaştırıcısı projesi için bkz: [tanılama veri bağdaştırıcısı oluşturmak için örnek proje](../test/sample-project-for-creating-a-diagnostic-data-adapter.md).

##  <a name="CreateAdapter"></a> Oluşturma ve tanılama veri bağdaştırıcısı yükleme

#### <a name="to-create-and-install-a-diagnostic-data-adapter"></a>Tanılama veri bağdaştırıcısı oluşturmak ve yüklemek için

1.  Yeni bir sınıf kitaplığı oluşturun.

    1.  Üzerinde **dosya** menüsünde seçin **yeni**, üzerine gelin ve ardından **yeni proje**.

    2.  Gelen **proje türleri**, kullanılacak dili seçin.

    3.  Gelen **Visual Studio yüklenmiş şablonlar**seçin **sınıf kitaplığı**.

    4.  Tanılama veri bağdaştırıcısı için bir ad yazın.

    5.  Seçin **Tamam**.

2.  Derleme ekleyin **Microsoft.VisualStudio.QualityTools.ExecutionCommon**.

    1.  Çözüm Gezgini'nde sağ **başvuruları** ve **Başvuru Ekle** komutu.

    2.  Seçin **.NET** ve bulun **Microsoft.VisualStudio.QualityTools.ExecutionCommon.dll**.

    3.  Seçin **Tamam**.

3.  Derleme ekleyin **Microsoft.VisualStudio.QualityTools.Common**.

    1.  Çözüm Gezgini'nde sağ **başvuruları** seçip **Başvuru Ekle** komutu.

    2.  Seçin **/.NET**, bulun **Microsoft.VisualStudio.QualityTools.Common.dll**.

    3.  Seçin **Tamam**.

4.  Aşağıdakileri ekleyin `using` deyimlerini Sınıf dosyanıza ekleyin:

    ```csharp
    using Microsoft.VisualStudio.TestTools.Common;
    using Microsoft.VisualStudio.TestTools.Execution;
    using System.Linq;
    using System.Text;
    using System.Xml;
    using System;
    ```

5.  Ekleme <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorTypeUriAttribute> için tanılama veri bağdaştırıcısı tanımlamak tanılama veri bağdaştırıcınızın sınıfa değiştirme **şirket**, **ürün**, ve **sürüm** ile Tanılama veri bağdaştırıcınızı uygun bilgileri:

    ```csharp
    [DataCollectorTypeUri("datacollector://Company/Product/Version")]
    ```

6.  Ekleme <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorFriendlyNameAttribute> özniteliği parametreleri tanılama veri bağdaştırıcınızı için uygun bilgilerle değiştirerek sınıfına:

    ```csharp
    [DataCollectorFriendlyName("Collect Log Files", false)]
    ```

     Bu kolay adı test ayarları etkinliğinde görüntülenir.

    > [!NOTE]
    > Ayrıca ekleyebileceğiniz <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> belirtmek için `Type` Düzenleyicisi kullanmak için özel yapılandırma düzenleyicisi bu veri bağdaştırıcısı için ve isteğe bağlı olarak Yardım dosyasını belirtmek için.
    >
    > Ayrıca uygulayabilirsiniz <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorEnabledByDefaultAttribute> , her zaman etkin olması gerektiğini belirtmek için.

7.  Tanılama veri bağdaştırıcısı sınıfınız öğesinden devralmalıdır <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector> gibi sınıfı:

    ```csharp
    public class MyDiagnosticDataAdapter : DataCollector
    ```

8.  Yerel değişkenler aşağıdaki şekilde ekleyin:

    ```csharp
    private DataCollectionEvents dataEvents;
    private DataCollectionLogger dataLogger;
    private DataCollectionSink dataSink;
    private XmlElement configurationSettings;
    ```

9. Ekleme <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector.Initialize*> yöntemi ve **Dispose** yöntemi. İçinde `Initialize` , Initialize yöntemi, veri havuzu, tüm yapılandırma verilerini test ayarlarını ve kullanmak istediğiniz olay işleyicileri şu şekilde Kaydet:

    ```csharp
    public override void Initialize(
        XmlElement configurationElement,
        DataCollectionEvents events,
        DataCollectionSink sink,
        DataCollectionLogger logger,
        DataCollectionEnvironmentContext environmentContext)
    {
           dataEvents = events;  // The test events
           dataLogger = logger;  // The error and warning log
           dataSink = sink;      // Saves collected data
           // Configuration from the test settings
           configurationSettings = configurationElement;

           // Register common events for the data collector
           // Not all of the events are used in this class
        dataEvents.SessionStart +=
            new EventHandler<SessionStartEventArgs>(OnSessionStart);
        dataEvents.SessionEnd +=
            new EventHandler<SessionEndEventArgs>(OnSessionEnd);
        dataEvents.TestCaseStart +=
            new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
        dataEvents.TestCaseEnd +=
            new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
    }

    public override void Dispose(bool disposing)
    {
        if (disposing)
        {
            // Unregister the registered events
            dataEvents.SessionStart -=
                new EventHandler<SessionStartEventArgs>(OnSessionStart);
            dataEvents.SessionEnd -=
                new EventHandler<SessionEndEventArgs>(OnSessionEnd);
            dataEvents.TestCaseStart -=
                new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
            dataEvents.TestCaseEnd -=
                new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
        }
    }
    ```

10. Test sırasında oluşturulan günlük dosyasını toplamak için aşağıdaki olay işleyici kod ve özel yöntemi kullanın:

    ```csharp
    public void OnTestCaseEnd(sender, TestCaseEndEventArgs e)
    {
        // Get any files to be collected that are
        // configured in your test settings
        List<string> files = getFilesToCollect();

        // For each of the files, send the file to the data sink
        // which will attach it to the test results or to a bug
        foreach (string file in files)
        {
            dataSink.SendFileAsync(e.Context, file, false);
        }
    }

    // A private method that returns the file names
    private List<string> getFilesToCollect()
    {
        // Get a namespace manager with our namespace
        XmlNamespaceManager nsmgr =
            new XmlNamespaceManager(
                configurationSettings.OwnerDocument.NameTable);
        nsmgr.AddNamespace("ns",
            "http://MyCompany/schemas/MyDataCollector/1.0");

        // Find all of the "File" elements under our configuration
        XmlNodeList files =
            configurationSettings.SelectNodes(
                "//ns:MyDataCollector/ns:File");

        // Build the list of files to collect from the
        // "FullPath" attributes of the "File" nodes.
        List<string> result = new List<string>();
        foreach (XmlNode fileNode in files)
        {
            XmlAttribute pathAttribute =
                fileNode.Attributes["FullPath"];
            if (pathAttribute != null &&
                !String.IsNullOrEmpty(pathAttribute.Value))
            {
                result.Add(pathAttribute.Value);
            }
        }

        return result;
    }
    ```

     Bu dosyalar test sonuçlarına eklenir. Oluşturursanız, bu hatadan test sonuçları veya kullandığınızda [!INCLUDE[mtrlong](../test/includes/mtrlong_md.md)], dosyalar hataya eklenir.

     Test ayarlarınızda kullanmak için bkz: için veri toplamak üzere kendi Düzenleyicisi kullanmak istiyorsanız, [nasıl yapılır: tanılama veri bağdaştırıcısı bilgisayarınızı veri için bir özel düzenleyici oluşturma](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md).

11. Bir test test ayarları'nda yapılandırılmış kullanıcı göre tamamlandığında, bir günlük dosyasını toplamak için oluşturmalısınız bir `App.config` dosya ve çözümünüze ekleyin. Bu dosya, aşağıdaki biçime sahiptir ve tanımlamak tanılama veri bağdaştırıcınızın URI'sini içermelidir. Gerçek değerler "Şirket/ProductName/sürüm için" değiştirin.

    > [!NOTE]
    > Ardından, tanılama veri bağdaştırıcısı için herhangi bir bilgi yapılandırmak gerekmiyorsa, bir yapılandırma dosyası oluşturmak gerekmez.

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <configuration>
      <configSections>
        <section name="DataCollectorConfiguration" type="Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationSection, Microsoft.VisualStudio.QualityTools.ExecutionCommon, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a "/>
      </configSections>
      <DataCollectorConfiguration xmlns="http://microsoft.com/schemas/VisualStudio/TeamTest/2010">
        <DataCollector typeUri="datacollector://MyCompany/MyProduct/1.0">
          <DefaultConfiguration>
            <!-- Your default config settings -->
            <Binaries>
              <Binary FullPath="C:\Example\Example.dll"/>
              <Binary FullPath="\\Server2\Example2.dll"/>
            </Binaries>
            <Symbols>
              <Symbol FullPath="\\ExampleServer\ExampleSymbol.pdb"/>
            </Symbols>
          </DefaultConfiguration>
        </DataCollector>
      </DataCollectorConfiguration>
    </configuration>
    ```

    > [!NOTE]
    > Varsayılan yapılandırma öğesi, ihtiyaç duyduğunuz tüm verileri içerebilir. Kullanıcı test ayarlarında tanılama veri bağdaştırıcısı yapılandırmaz, çalıştırıldığında sonra varsayılan veri tanılama veri bağdaştırıcınızın geçirilir. Eklediğiniz XML çünkü `<DefaultConfigurations>` bölümü bildirilen şema parçası olması olası değil, ürettiği herhangi bir XML hatasını yoksayabilirsiniz.
    >
    > Yapılandırma dosyaları, yükleme dizinine göre aşağıdaki yolundaki diğer örnekler vardır: **Program Files\Microsoft Visual Studio 10.0\Common7\IDE\PrivateAssemblies\DataCollectors**.

     Testlerinizi çalıştırdığınızda, bir ortam kullanmak için test ayarlarını yapılandırma hakkında daha fazla bilgi için bkz: [el ile testlerde (VSTS) Tanılama verileri toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

     Yapılandırma dosyası yükleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: özel tanılama veri bağdaştırıcısı yükleme](../test/how-to-install-a-custom-diagnostic-data-adapter.md)

12. Tanılama veri bağdaştırıcısı derlemenizi oluşturmak için çözümünüzü oluşturun.

13. Özel düzenleyicinizi yükleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: özel tanılama veri bağdaştırıcısı yükleme](../test/how-to-install-a-custom-diagnostic-data-adapter.md).

14. Testlerinizi çalıştırdığınızda, bir ortam kullanmak için test ayarlarını yapılandırma hakkında daha fazla bilgi için bkz: [el ile testlerde (VSTS) Tanılama verileri toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

15. Tanılama veri bağdaştırıcınızı seçmek için önce varolan test ayarlarını seçin veya Microsoft Test Yöneticisi'ni ya da Visual Studio yeni bir tane oluşturun. Bağdaştırıcı gösterilir **veri ve tanılama** sekmesinde test ayarlarınızı sınıfa atadığınız kolay adı.

16. Bu test ayarlarını etkin olması için ayarlama. Test ayarları hakkında daha fazla bilgi için bkz: [toplamak tanılama bilgileri kullanarak Test ayarlarını](../test/collect-diagnostic-information-using-test-settings.md).

17. Seçilen tanılama veri bağdaştırıcısı ile test ayarlarını kullanarak testleri çalıştırın.

   Belirtilen veri dosyası test sonuçlarınızı eklenir.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionEvents>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollector>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorTypeUriAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorFriendlyNameAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorEnabledByDefaultAttribute>
- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)
- [El ile testlerde (VSTS) tanılama verisi toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)
- [(VSTS) test ederken tanılama verisi toplama](/vsts/manual-test/collect-diagnostic-data)
- [Nasıl yapılır: tanılama veri bağdaştırıcınızın verileri için bir özel düzenleyici oluşturma](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)