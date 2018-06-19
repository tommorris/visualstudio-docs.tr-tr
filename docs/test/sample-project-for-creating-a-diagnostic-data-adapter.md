---
title: Visual Studio tanılama veri bağdaştırıcısı oluşturmak için örnek proje
ms.date: 10/19/2016
ms.topic: sample
helpviewer_keywords:
- Diagnostic Data Adapter [Visual Studio ALM]
- samples. Diagnostic Data Adapter [Visual Studio ALM]
- Diagnostic Data Adapter, sample
ms.assetid: 548bdc5e-338f-4be7-a555-e6a2efb1df6b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: b7d2cd30faa5cbc5b4f8626c17de77c68bdf8bae
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31977121"
---
# <a name="sample-project-for-creating-a-diagnostic-data-adapter"></a>Tanılama Veri Bağdaştırıcısı Oluşturmak için Örnek Proje

"MyDiagnosticDataAdapter" testlerinizi çalıştırdığınızda, bir günlük dosyası için test sonuçları iliştirebilirsiniz basit tanılama veri bağdaştırıcısı var.

 Herhangi bir makinede yönetici izinleri gerekir burada Tanılama Veri Toplayıcı veya yapılandırma Düzenleyicisi yüklenir.

## <a name="example-data-adapter"></a>Örnek veri bağdaştırıcısı

Bu örnek aşağıdaki görevlerin nasıl gerçekleştirileceğini gösterir:

-   Bir sınıf için Microsoft Test Yöneticisi tanılama veri bağdaştırıcısı olarak bulunabilir olması için öznitelik uygulayın.

-   Bir kullanıcı denetimi sınıfı bulunabilirlik Microsoft Test Yöneticisi için tanılama veri bağdaştırıcısı yapılandırmasını değiştirmek için kullanmak üzere düzenleyici olarak olması için öznitelik uygulayın.

-   Varsayılan yapılandırma verilerine erişin.

-   Özel tanılama veri toplama olayları için kaydolun.

-   Günlük dosyası için göndererek ekleme <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink>.

```csharp
// My Data Collector Class
using Microsoft.VisualStudio.TestTools.Common;
using Microsoft.VisualStudio.TestTools.Execution;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Xml;
using System;

namespace MyCompany.MyDiagnosticDataAdapters
{
    // Provide a URI and friendly name for your diagnostic data adapter
    [DataCollectorTypeUri("datacollector://MyCompany/MyDataCollector/1.0")]
    [DataCollectorFriendlyName("Collect Log Files sample", false)]
    // Designate your chosen configuration editor
    [DataCollectorConfigurationEditor(
        "configurationeditor://MyCompany/MyDataConfigEditor/1.0")]
    public class MyDataCollector : DataCollector
    {
        private DataCollectionEvents dataEvents;
        private DataCollectionLogger dataLogger;
        private DataCollectionSink dataSink;
        private XmlElement configurationSettings;

        // Required method called by the testing framework
        public override void Initialize(
            XmlElement configurationElement,
            DataCollectionEvents events,
            DataCollectionSink sink,
            DataCollectionLogger logger,
            DataCollectionEnvironmentContext environmentContext)
        {
            dataEvents = events; // The test events
            dataLogger = logger; // The error and warning log
            dataSink = sink;     // Saves collected data
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
            dataEvents.DataRequest +=
                new EventHandler<DataRequestEventArgs>(OnDataRequest);
        }

        protected override void Dispose(bool disposing)
        {
            if (disposing)
            {
                dataEvents.SessionStart -=
                    new EventHandler<SessionStartEventArgs>(OnSessionStart);
                dataEvents.SessionEnd -=
                    new EventHandler<SessionEndEventArgs>(OnSessionEnd);
                dataEvents.TestCaseStart -=
                    new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
                dataEvents.TestCaseEnd -=
                    new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
                dataEvents.DataRequest -=
                    new EventHandler<DataRequestEventArgs>(OnDataRequest);
            }
        }

        #region Event Handlers
        public void OnSessionStart(object sender, SessionStartEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnSessionEnd(object sender, SessionEndEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnTestCaseStart(object sender, TestCaseEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnTestCaseEnd(object sender, TestCaseEndEventArgs e)
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

        public void OnDataRequest(object sender, DataRequestEventArgs e)
        {
            // TODO: Provide implementation
            // Most likely this occurs because a bug is being filed
        }
        #endregion

        // A private method to collect the configured file names
        private List<string> getFilesToCollect()
        {
            // Seetup namespace manager with our namespace
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
    }
}
```

## <a name="example-configuration-editor"></a>Örnek yapılandırma Düzenleyicisi

Bu tanılama veri bağdaştırıcısı için örnek bir yapılandırma düzenleyicisidir. Bir kullanıcı denetimi projenize ekleyin ve bir etiketi olan çok basit bir form oluşturun ("günlük dosyasının adı:") ve "etiketiyle Basit" adlı bir metin kutusu.

```csharp
using Microsoft.VisualStudio.TestTools.Common;
using Microsoft.VisualStudio.TestTools.Execution;
using System.Collections.Generic;
using System.ComponentModel;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
using System.Xml;
using System;

namespace MyCompany.DiagnosticDataAdapters.ConfigurationEditors
{
    [DataCollectorConfigurationEditorTypeUri(
        "configurationeditor://MyCompany/MyConfigEditor/1.0")]
    public partial class MyDataConfigEditor :
        UserControl, IDataCollectorConfigurationEditor
    {
        private DataCollectorSettings collectorSettings;

        // Create a private property for the service provider
        private IServiceProvider ServiceProvider { get; set; }

        // Constructor
        public MyConfigurationEditor()
        {
            InitializeComponent();
        }

        // Required method called by the testing framework
        public void Initialize(
            IServiceProvider svcProvider,
            DataCollectorSettings settings)
        {
            ServiceProvider = svcProvider;
            collectorSettings = settings;

            // Display the file name as listed in the settings file.
            // If the configuration has not been updated before, this
            // data will be provided by the default configuration
            // section from <nameofcollector>.dll.config:
            // <DefaultConfiguration>
            //   <MyCollectorName
            //       xmlns="http://MyCompany/schemas/ProductName/Version");
            //     <File FullPath="C:\temp\logfile1.txt" />
            //   </MyCollectorName>
            // </DefaultConfiguration>
            this.SuspendLayout();
            this.FileTextBox.Text = GetText(collectorSettings.Configuration);
            this.ResumeLayout();
        }

        // Can be used to verify data before saving it
        public bool VerifyData()
        {
            // Not currently verifying data
            return true;
        }

        // Reset to default value from XML configuration
        // using a custom method
        public void ResetToAgentDefaults()
        {
            this.FileTextBox.Text =
                getText(collectorSettings.DefaultConfiguration);
        }

        // Saves data changed in the editor to the test configuration
        // settings. Does not change the default value.
        public DataCollectorSettings SaveData()
        {
            collectorSettings.Configuration.InnerXml =
                String.Format(
                    @"<MyCollectorName
      xmlns=""http://MyCompany/schemas/MyDataCollector/1.0"">
  <File FullPath=""{0}"" />
</MyCollectorName>",
                    FileTextBox.Text);
            return collectorSettings;
        }

        // Reads the configuration settings
        private string getText(XmlElement element)
        {
            // Setup namespace manager with our namespace
            XmlNamespaceManager nsmgr =
                new XmlNamespaceManager(
                    element.OwnerDocument.NameTable);

            // Find all the "File" elements under our configuration
            XmlNodeList files = element.SelectNodes("//ns:MyDataCollector/ns:File", nsmgr);

            string result = String.Empty;
            if (files.Count > 0)
            {
                XmlAttribute pathAttribute = files[0].Attributes["FullPath"];
                if (pathAttribute != null &&
                    !String.IsNullOrEmpty(pathAttribute.Value))
                {
                    result = pathAttribute.Value;
                }
            }

            return result;
        }
    }
}
```

## <a name="example-configuration-file"></a>Örnek yapılandırma dosyası

Tanılama Veri Toplayıcı yapılandırma Düzenleyicisi için örnek bir yapılandırma dosyası verilmiştir.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <section
      name="DataCollectorConfiguration"
      type="Microsoft.VisualStudio.QualityTools.Execution.DataCollectorConfigurationSection,
        Microsoft.visualStudio.QualityTools.ExecutionCommon,
        Version=4.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f7f11d50a3a" />
  </configSections>
  <DataCollectorConfiguration
      xmlns="http://microsoft.com/schemas/VisualStudio/TeamTest/11">
    <DataCollector
        typeUri="datacollector://MyCompany/MyDataCollector/1.0">
      <DefaultConfiguration>
        <!-- Your default config settings-->
        <File FullPath="c:\temp\logfile1.txt" />
      </DefaultConfiguration>
    </DataCollector>
  </DataCollectorConfiguration>
</configuration>

```

## <a name="compiling-the-code"></a>Kod Derleniyor

### <a name="to-create-the-code-project-for-this-diagnostic-adapter"></a>Bu tanılama bağdaştırıcısı kodunu projeyi oluşturmak için

1.  "MyDataCollector" adlı yeni bir sınıf kitaplığı projesi oluşturun.

2.  İçinde **Çözüm Gezgini**, projeye sağ tıklayın ve ardından **özellikleri**. Eklemek için bir klasör seçmek için Seç **başvuru yollarını** ve üç nokta seçin (**...** ).

     **Select Reference Path** iletişim kutusu görüntülenir.

3.  Yükleme dizinine göre aşağıdaki yolu seçin: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies*. Seçin **Tamam**.

4.  Başvuru yolunuza klasörü eklemek için **klasörü Ekle**.

     Klasör başvurusu yolları listesinde görüntülenir.

5.  Seçin **Tümünü Kaydet** başvuru yollarını kaydetmek için simge.

6.  Derleme ekleyin **Microsoft.VisualStudio.QualityTools.ExecutionCommon**.

    1.  İçinde **Çözüm Gezgini**, sağ **başvuruları** ve ardından **Başvuru Ekle**.

    2.  Seçin **Gözat** ve bulun **Microsoft.VisualStudio.QualityTools.ExecutionCommon.dll**.

         Bu derleme içinde bulunan *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies*.

    3.  Seçin **Tamam**.

7.  Derleme ekleyin **Microsoft.VisualStudio.QualityTools.Common**.

    1.  Çözüm Gezgini'nde sağ **başvuruları** seçip **Başvuru Ekle**.

    2.  Seçin **Gözat** ve bulun **Microsoft.VisualStudio.QualityTools.Common.dll**.

         Bu derleme içinde bulunan *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies*.

    3.  Seçin **Tamam**.

8.  Listelenen tanılama veri bağdaştırıcısı sınıf sınıfı için sınıf kitaplığı için bu belgenin önceki bölümlerinde kopyalayın. Bu sınıf kaydedin.

9. Proje, sağ MyDataCollector projesindeki Çözüm Gezgini'nde, bir kullanıcı denetimi eklemek için işaret **Ekle**ve ardından **kullanıcı denetimi**. Seçin **eklemek**.

10. Araç kutusunu kullanarak kullanıcı denetimi için bir etiket eklemek ve metin özelliğini değiştirin **dosya adı:**.

11. Araç kutusunu kullanarak kullanıcı denetimi için bir metin kutusu ekleyin ve adla değiştirin **textBoxFileName**.

12. İçinde **Çözüm Gezgini**, kullanıcı denetimi sağ tıklatın ve ardından **görünümü kodu.** Bu belgede daha önce listelenen kullanıcı denetimi sınıfıyla bu kullanıcı denetimi sınıfını değiştirin. Bu sınıf kaydedin.

    > [!NOTE]
    > Varsayılan olarak, kullanıcı denetimi UserControl1 adı verilir. Kullanıcı denetimi sınıf kodunun kullanıcı denetiminin adını kullandığından emin olun.

13. Yapılandırma dosyası oluşturmak için **Çözüm Gezgini** çözüme sağ tıklayın, fareyle **Ekle**ve ardından **yeni öğe**. Seçmek istediğinizde **uygulama yapılandırma dosyası**ve ardından **Ekle**. Bu adlı bir dosyayı ekler **App.config** çözümünüze.

14. XML dosyasına daha önce sağlanan örnek XML kopyalayın. Dosyayı kaydedin.

15. Çözümü derlemek ve yerleşik bütünleştirilmiş kopyalayın ve `App.config` içine dosya *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors* dizini.

16. Bu özel veri tanılama bağdaştırıcısını kullanmak test ayarları oluşturma. Varolan bir dosyayı toplamak için test ayarlarını yapılandırın.

     Microsoft Test Yöneticisi'nden testlerinizi çalıştırıyorsanız, bu atayabilirsiniz testleri çalıştırma veya test ayarlarınızı atamak ve geçersiz kılma seçenekleri komutuyla Çalıştır kullanmadan önce test planınız için test ayarlarını. Test ayarları hakkında daha fazla bilgi için bkz: [toplamak tanılama bilgileri kullanarak Test ayarlarını](../test/collect-diagnostic-information-using-test-settings.md).

17. Seçilen tanılama veri bağdaştırıcısı ile test ayarlarını kullanarak testleri çalıştırın.

     Test çalıştırıldığında, belirtilen veri dosyası test sonuçlarınızı eklenir.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: tanılama veri bağdaştırıcısı oluşturma](../test/how-to-create-a-diagnostic-data-adapter.md)
- [Nasıl yapılır: tanılama veri bağdaştırıcınızın verileri için bir özel düzenleyici oluşturma](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [Nasıl yapılır: özel tanılama veri bağdaştırıcısı yükleme](../test/how-to-install-a-custom-diagnostic-data-adapter.md)
- [Özel veri toplayan veya Test makinesini etkileyen tanılama veri bağdaştırıcısı oluşturma](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)