---
title: Özel bir Visual Studio'da veri Düzenleyicisi için tanılama veri bağdaştırıcısı oluşturma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, creating custom editor
ms.assetid: 24970227-d1ea-4f6d-9839-e911478848ba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 6141defb2248cf79888b0ed94824a827bd36815f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976314"
---
# <a name="how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter"></a>Nasıl yapılır: Tanılama Veri Bağdaştırıcınızın Verileri için Bir Özel Düzenleyici Oluşturma

Tanılama veri bağdaştırıcısı oluşturduğunuzda, özel tanılama veri bağdaştırıcınızı test ayarlarını seçildiğinde belirli verileri yapılandırmak son kullanıcı etkinleştirmek isteyebilirsiniz. Örneğin, hangi kayıt defteri anahtarlarını ayıklamak için benzetimini yapmak için Ağ Yükü veya geçici dosyaları bulmak veya iliştirilecek dosyaları çalışması için hangi dizinde seviyesi belirten yapılandırma verilerini seçebilirsiniz.

Tanılama veri bağdaştırıcınızın ilk değerleri ayarlamak için bir yapılandırma dosyası kullanmanız gerekir. Yapılandırma verilerini değiştirmek kullanıcının etkinleştirmek için özel bir düzenleyici sağlayabilir.

Kendi düzenleyicinizi oluşturmak üzere uygulayan bir kullanıcı denetimi oluşturacağı <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>.

Tanılama veri bağdaştırıcınızın kullanabileceğiniz bir <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> tanılama verisi yapılandırma ayarlarını düzenlemek için kullanılacak düzenleyici sınıfı belirlemek için.

Ayrıca, kullanmak istediğiniz varsayılan yapılandırma verilerini de belirtin.  Bkz: [tanılama veri bağdaştırıcısı oluşturmak için örnek proje](../test/sample-project-for-creating-a-diagnostic-data-adapter.md) varsayılan yapılandırma örneği için.

Özel veri tanılama bağdaştırıcınız kullanıldığında test ayarlarınız için verileri güncelleştirmek için özel bir düzenleyici oluşturmak için aşağıdaki yordamı kullanın.

> [!NOTE]
> Özel bir düzenleyici oluşturmak için öncelikle olan tanılama veri bağdaştırıcısı oluşturmalısınız <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> sınıfına uygulanan. Kullanabileceğiniz isteğe bağlı <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute.HelpUri*> Düzenleyicisi için Yardım içerik kaynağını belirtmek için bu öznitelik bir özellik. Tanılama veri bağdaştırıcısı oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: tanılama veri bağdaştırıcısı oluşturma](../test/how-to-create-a-diagnostic-data-adapter.md).

Özel yapılandırma düzenleyicisi de dahil olmak üzere bir tam örnek tanılama veri bağdaştırıcısı projesi için bkz: [tanılama veri bağdaştırıcısı oluşturmak için örnek proje](../test/sample-project-for-creating-a-diagnostic-data-adapter.md).

## <a name="to-create-a-custom-editor-for-your-diagnostic-data-adapter"></a>Tanılama veri bağdaştırıcısı için özel bir düzenleyici oluşturmak için

1.  Proje, veri tanılama bağdaştırıcısı için bir kullanıcı denetimi oluşturun:

    1.  Tanılama veri bağdaştırıcısı sınıfınız içeren kod projeye sağ tıklayın, fareyle **Ekle** üzerine gelin ve ardından **kullanıcı denetimi**.

    2.  Bu örnekte, bu metin içeren bir forma bir etiket ekleyin: **veri dosyası adı:** ve adlı bir metin kutusu **etiketiyle basit** gerekli verileri girmesini etkinleştirecek.

    > [!NOTE]
    > Yalnızca Windows Forms kullanıcı denetimi şu anda desteklenir.

2.  Bildirim bölümüne aşağıdaki satırları ekleyin:

    ```csharp
    using System.Xml;
    using Microsoft.VisualStudio.TestTools.Common;
    using Microsoft.VisualStudio.TestTools.Execution;
    ```

3.  Bu kullanıcı denetimi özel bir düzenleyici olun.

    1.  Kullanıcı denetimi kod projenize sağ tıklayın ve fareyle **görüntülemek kod**.

    2.  Set sınıfı Düzenleyicisi arabirimini uygulayan <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor> gibi:

    ```csharp
    public partial class MyDataConfigEditor :
         UserControl, IDataCollectorConfigurationEditor
    ```

    1.  Sağ <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor> kodu ve select **arabirimi uygulama** komutu. Bu arabirim için uygulamanız gereken yöntemler sınıfınıza eklenir.

    2.  Ekleme <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> düzenleyicinizi değiştirerek bir tanılama veri bağdaştırıcısı Düzenleyicisi tanımlamak için kullanıcı denetimi için **şirket**, **ürün**, ve **sürüm** ile tanılama veri bağdaştırıcısı için uygun bilgileri:

        ```csharp
        [DataCollectorConfigurationEditorTypeUri(
            "configurationeditor://MyCompany/MyConfigEditor/1.0")]
        ```

4.  İki özel değişkenler aşağıdaki şekilde ekleyin:

    ```csharp
    private DataCollectorSettings collectorSettings;
    private IServiceProvider ServiceProvider { get; set; }
    ```

5.  Tanılama veri bağdaştırıcınızın düzenleyicinizi başlatmak için kodu ekleyin. Varsayılan değerleri ayarlar değişkeninde bulunan verileri kullanarak, kullanıcı denetimi alanları ekleyebilirsiniz. Bu içinde verilerdir `<DefaultConfiguration>` bağdaştırıcınızın XML yapılandırma dosyası öğesi.

    ```csharp
    public void Initialize(
        IServiceProvider svcProvider,
        DataCollectorSettings settings)
    {
        ServiceProvider = svcProvider;
        collectorSettings = settings;

        // Display the default file name as listed in the settings file.
        this.SuspendLayout();
        this.FileTextBox.Text = getText(collectorSettings.Configuration);
        this.ResumeLayout();
    }
    ```

6.  Verileri denetimlerinizi düzenleyicinizde tanılama veri bağdaştırıcısı API gibi gerekli geri XML biçimine kaydetmek için kodu ekleyin:

    ```csharp
    public DataCollectorSettings SaveData()
    {
        collectorSettings.Configuration.InnerXml =
            String.Format(
    @"<MyCollectorName
        xmlns=""http://MyCompany/schemas/MyDiagnosticDataCollector/1.0"">
      <File FullPath=""{0}"" />
    </MyCollectorName>",
        FileTextBox.Text);
        return collectorSettings;
    }
    ```

7.  Sizin için önemli olan, verileri doğru olduğunu doğrulamak için kodu ekleyin `VerifyData` yöntemi veya dönüş yöntemi olabilir `true`.

    ```csharp
    public bool VerifyData()
    {
        // Not currently verifying data
        return true;
    }
    ```

8.  (İsteğe bağlı) XML yapılandırma dosyasında sağlanan ilk ayarları veri sıfırlamak için kod ekleyebilirsiniz `ResetToAgentDefaults()` özel kullanan yöntemi `getText()` yöntemi.

    ```csharp
    // Reset to default value from XML configuration
    // using a custom getText() method
    public void ResetToAgentDefaults()
    {
        this.FileTextBox.Text = getText(collectorSettings.DefaultConfiguration);
    }

    // Local method to read the configuration settings
    private string getText(XmlElement element)
    {
        // Setup namespace manager with our namespace
        XmlNamespaceManager nsmgr =
            new XmlNamespaceManager(
                element.OwnerDocument.NameTable);

        // Find all the "File" elements under our configuration
        XmlNodeList files = element.SelectNodes("//ns:MyCollectorName/ns:File", nsmgr);

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
    ```

9. Çözümünüzü oluşturun. Veri tanılama bağdaştırıcısı derlemesini ve XML yapılandırma dosyasını kopyalayın (`<diagnostic data adapter name>.dll.config`) yükleme dizinine göre aşağıdaki konuma: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\ PrivateAssemblies\DataCollectors*.

    > [!NOTE]
    > Yapılandırma Düzenleyicisi'ni bir proje ve tanılama veri bağdaştırıcısı farklı bir derlemeyi olabilse de aynı bütünleştirilmiş kodda olabilir.

10. Tanılama veri bağdaştırıcınızın sınama sırasında kullanılacak, varolan test ayarlarını listesinden seçin veya yeni bir Microsoft Test Yöneticisi'ni ya da Visual Studio oluşturmalı ve tanılama veri bağdaştırıcısı seçin.

     Bağdaştırıcı gösterilir **veri ve tanılama** sekmesinde test ayarlarınızı sınıfa atadığınız kolay adı.

11. Test ayarlarınız için tanılama veri bağdaştırıcınızı yapılandırmak için tercih **yapılandırma** bağdaştırıcısı adının yanındaki.

     Özel düzenleyici şimdi görüntülenir.

12. Alanları özel düzenleyicinizde gerektiği gibi düzenleyin ve ardından **kaydetmek**.

13. Microsoft Test Yöneticisi'nden testlerinizi çalıştırıyorsanız, bu atayabilirsiniz testleri çalıştırma veya kullanmadan önce test ayarları test planınıza **seçenekleriyle çalıştırın** test ayarlarınızı atamak ve geçersiz kılmak için komut test ayarları. Test ayarları hakkında daha fazla bilgi için bkz: [toplamak tanılama bilgileri kullanarak Test ayarlarını](../test/collect-diagnostic-information-using-test-settings.md).

14. Tanılama veri bağdaştırıcısı ile yeni yapılandırma düzenleyicinizi kullanmadan önce uygulamalısınız <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> Düzenleyicisi'ni kullanın ve yeniden derleyin ve istemci bilgisayarda yeniden istediğiniz her bir tanılama veri bağdaştırıcısı sınıfa. Tanılama veri bağdaştırıcıları ve yapılandırma düzenleyicileri nasıl yükleneceği hakkında daha fazla bilgi için bkz: [nasıl yapılır: özel tanılama veri bağdaştırıcısı yükleme](../test/how-to-install-a-custom-diagnostic-data-adapter.md).

15. Seçilen tanılama veri bağdaştırıcısı ile test ayarlarını kullanarak testleri çalıştırın.

     Düzenleyicinizde belirtilen veri dosyası test sonuçlarınızı eklenir.

 Testlerinizi çalıştırdığınızda, bir ortam kullanmak için test ayarlarını yapılandırma hakkında daha fazla bilgi için bkz: [(VSTS) test ederken Tanılama verileri toplama](/vsts/manual-test/collect-diagnostic-data) veya [el ile testlerde (VSTS)Tanılamaverileritoplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests).

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- [Özel veri toplayan veya Test makinesini etkileyen tanılama veri bağdaştırıcısı oluşturma](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)
- [Tanılama veri bağdaştırıcısı oluşturmak için örnek proje](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)