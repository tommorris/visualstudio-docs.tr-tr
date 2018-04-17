---
title: Visual Studio'da bir özel HTTP Gövde Düzenleyicisi için Web Performans Testi Düzenleyicisi oluşturma | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, custom HTTP body editor
ms.assetid: a0b2d8ff-3e2a-487e-9172-90047174f336
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: c53d4db3f413ad8cf4f0b615db18bd5fb6368128
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-custom-http-body-editor-for-the-web-performance-test-editor"></a>Nasıl yapılır: Web Başarım Testi Düzenleyicisi için bir Özel HTTP Gövde Düzenleyicisi Oluşturma

Dize gövde içerik veya Web hizmeti isteğine, örneğin, SOAP, REST, asmx, wcf, RIA ve diğer Web hizmeti istek türlerinin ikili gövde içeriğini düzenlemenize olanak tanır özel bir içerik düzenleyici oluşturabilirsiniz.

 Bu tür düzenleyicileri uygulayabilirsiniz:

-   **Dize içerik Düzenleyicisi** bu kullanılarak uygulanan <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> arabirimi.

-   **İkili içerik Düzenleyicisi** bu kullanılarak uygulanan <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> arabirimi.

Bu arabirimleri bulunan <xref:Microsoft.VisualStudio.TestTools.WebTesting> ad alanı.

## <a name="create-a-windows-control-library-project"></a>Bir Windows Denetim Kitaplığı projesi oluşturma

### <a name="create-a-user-control-by-using-a-windows-control-library-project"></a>Bir Windows Denetim Kitaplığı projesi kullanarak bir kullanıcı denetimi oluşturma

1.  Visual Studio'da üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje**.

     **Yeni proje** iletişim kutusu görüntülenir.

2.  Altında **yüklü şablonlar**, şunlardan birini seçin **Visual Basic** veya **Visual C#** tercihinize göre programlama ve ardından **Windows**.

    > [!NOTE]
    > Bu örnek, Visual C# kullanmaktadır.

3.  Şablonları listesinde seçin **Windows Forms Denetim Kitaplığı**.

4.  Örneğin, adı metin kutusuna bir ad yazın `MessageEditors`ve seçin **Tamam**.

    > [!NOTE]
    > Bu örnek, MessageEditors kullanmaktadır.

     Proje yeni çözüme eklenir ve <xref:System.Windows.Forms.UserControl> adlı UserControl1.cs Tasarımcı içinde sunulur.

5.  Gelen **araç**altında **ortak denetimler** kategorisi, sürükle bir <xref:System.Windows.Forms.RichTextBox> UserControl1 yüzeyine.

6.  Eylem etiket karakterini seçin (![akıllı etiket karakteri](../test/media/vs_winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) sağ üst köşesindeki <xref:System.Windows.Forms.RichTextBox> denetlemek ve ardından seçin ve **Anakapsayıcıdayerleştir**.

7.  Çözüm Gezgini'nde, Windows Forms kitaplık projesine sağ tıklatın ve **özellikleri**.

8.  Özellikleri seçin **uygulama** sekmesi.

9. İçinde **hedef framework** aşağı açılan listesinden, **.NET Framework 4**.

10. Hedef Framework Değiştir iletişim kutusu görüntülenir.

11. Seçin **Evet**.

12. Çözüm Gezgini'nde sağ **başvuruları** düğümü ve select **Başvuru Ekle**.

13. **Başvuru Ekle** iletişim kutusu görüntülenir.

14. ' I seçin. **NET** sekmesinde, aşağı kaydırın ve seçin **Microsoft.VisualStudio.QualityTools.WebTestFramework** ve ardından **Tamam**.

15. Görünüm Tasarımcısı Çözüm Gezgini'nde, hala açık değilse, sağ **UserControl1.cs** ve ardından **Görünüm Tasarımcısı**.

16. Tasarım yüzeyine sağ tıklatıp **görünümü kodu**.

17. (İsteğe bağlı) Sınıf ve oluşturucu adını UserControl1'den, örneğin, MessageEditorControl gibi anlamlı bir ad ile değiştirin:

    > [!NOTE]
    > Örnek MessageEditorsControl kullanır.

    ```csharp
    namespace MessageEditors
    {
        public partial class MessageEditorControl : UserControl
        {
            public MessageEditorControl()
            {
                InitializeComponent();
            }
        }
    }
    ```

18. Metin içinde RichTextBox1 ayarlama ve alma etkinleştirmek için aşağıdaki özellikleri ekleyin. <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> Arabirimi EditString ve <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> EditByteArray öğesini kullanır:

   ```csharp
   public String EditString
   {
       get
       {
           return this.richTextBox1.Text;
       }
       set
       {
           this.richTextBox1.Text = value;
       }
   }

   public byte[] EditByteArray
   {
       get
       {
           return System.Convert.FromBase64String(richTextBox1.Text);
       }
       set
       {
           richTextBox1.Text = System.Convert.ToBase64String(value, 0, value.Length);
       }
   }
   ```

## <a name="add-a-class-for-to-the-windows-control-library-project"></a>Windows Denetim Kitaplığı proje için bir sınıf ekleyin

Bir sınıf projeye ekleyin. Uygulamak için kullanılacak <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> ve <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> arabirimleri.

**Bu yordamdaki kod genel bakış**

MessageEditorControl <xref:System.Windows.Forms.UserControl> oluşturulan önceki yordamı messageEditorControl örneği olarak oluşturulur:

```csharp
private MessageEditorControl messageEditorControl
```

 MessageEditorControl örneği tarafından oluşturulan eklenti iletişim içinde barındırılan <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin.CreateEditor*> yöntemi. Ayrıca, messageEditorControl'un <xref:System.Windows.Forms.RichTextBox> içeriğini doldurulur <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody>. Ancak, eklenti oluşturulmasını sürece gerçekleşemez <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin.SupportsContentType*> döndürür `true`. Bu düzenleyici, söz konusu olduğunda <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin.SupportsContentType*> döndürür `true` varsa <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody.ContentType*> içinde <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody> "xml" içerir.

 Dize gövdesinin düzenlenmesi tamamlandığında ve kullanıcı tıklama **Tamam** eklenti iletişim kutusunda, <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin.GetNewValue*> bir dize ve güncelleştirme düzenlenmiş metni almak için çağrılır **dize gövde** Web istekteki Test performans Düzenleyici.

### <a name="to-create-a-class-and-implement-the-istringhttpbodyeditorplugin-interface-code"></a>Bir sınıf oluşturun ve IStringHttpBodyEditorPlugin arabirimi kodunu uygulamak için

1.  Çözüm Gezgini'nde, Windows Forms Denetim Kitaplığı projesine sağ tıklatın ve **Yeni Öğe Ekle**.

2.  **Yeni Öğe Ekle** iletişim kutusu görüntülenir.

3.  Seçin **sınıfı**.

4.  İçinde **adı** metin kutusunda, sınıf için anlamlı bir ad yazın, örneğin, `MessageEditorPlugins`.

5.  Seçin **eklemek**.

     Class1 projeye eklendi ve Kod Düzenleyicisi'nde gösterilir.

6.  Kod Düzenleyicisi'nde aşağıdaki ekleme deyimini kullanarak:

    ```csharp
    using Microsoft.VisualStudio.TestTools.WebTesting;
    ```

7.  Başlatmak sınıfından örneği oluşturmak için aşağıdaki kodu yazın veya kopyalayın <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> arabirim ve gerekli yöntemleri uygulayın:

    ```csharp
    /// <summary>
    /// Editor for generic text based hierarchical messages such as XML and JSON.
    /// </summary>
    public class XmlMessageEditor : IStringHttpBodyEditorPlugin
    {
        public XmlMessageEditor()
        {
        }

        /// <summary>
        /// Determine if this plugin supports the content type.
        /// </summary>
        /// <param name="contentType">The content type to test.</param>
        /// <returns>Returns true if the plugin supports the specified content type.</returns>
        public bool SupportsContentType(string contentType)
        {
            return contentType.ToLower().Contains("xml");
        }

        /// <summary>
        /// Create a UserControl to edit the specified bytes.
        /// This control will be hosted in the
        /// plugin dialog which provides OK and Cancel buttons.
        /// </summary>
        /// <param name="contentType">The content type of the BinaryHttpBody.</param>
        /// <param name="initialValue">The bytes to edit.  The bytes are the payload of a BinaryHttpBody.</param>
        /// <returns>A UserControl capable of displaying and editing the byte array value of the specified content type.</returns>
        public object CreateEditor(string contentType, string initialValue)
        {
            messageEditorControl = new MessageEditorControl();
            messageEditorControl.EditString = initialValue;
            return this.messageEditorControl;
        }

        /// <summary>
        /// Gets the edited bytes after the OK button is clicked on the plugin dialog.
        /// </summary>
        public string GetNewValue()
        {
            return messageEditorControl.EditString;
        }

        private MessageEditorControl messageEditorControl;
    }
    ```

## <a name="add-a-ibinaryhttpbodyeditorplugin-to-the-class"></a>Bir IBinaryHttpBodyEditorPlugin sınıfına ekleyin

Uygulama <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> arabirimi.

**Bu yordamdaki kod genel bakış**

Kod uygulamasını <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> arabirimi benzer <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin> önceki yordamda işlenen. Ancak, ikili dosya sürümü bir dize yerine ikili verileri işlemek için bir bayt dizisi kullanır.

MessageEditorControl <xref:System.Windows.Forms.UserControl> oluşturulan ilk yordamı messageEditorControl örneği olarak:

```csharp
private MessageEditorControl messageEditorControl
```

MessageEditorControl örneği tarafından oluşturulan eklenti iletişim içinde barındırılan <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin.CreateEditor*> yöntemi. Ayrıca, messageEditorControl'un <xref:System.Windows.Forms.RichTextBox> içeriğini doldurulur <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody>. Ancak, eklenti oluşturulmasını sürece gerçekleşemez <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin.SupportsContentType*> döndürür `true`. Bu düzenleyici, söz konusu olduğunda <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin.SupportsContentType*> döndürür `true` varsa <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody.ContentType*> içinde <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody> "msbin1" içerir.

Dize gövdesinin düzenlenmesi tamamlandığında ve kullanıcı tıklama **Tamam** eklenti iletişim kutusunda, <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin.GetNewValue*> bir dize ve güncelleştirme düzenlenmiş metni almak için çağrılır **BinaryHttpBody.Data** isteği Web testi performans Düzenleyicisi'nde.

### <a name="to-add-the-ibinaryhttpbodyeditorplugin-to-the-class"></a>IBinaryHttpBodyEditorPlugin'i sınıfa eklemek için

-   Msbin1MessageEditor sınıfından örneği oluşturmak için önceki yordamda eklenen başlatmak sınıfı altında aşağıdaki kodu yazın veya kopyalayın <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin> arabirim ve gerekli yöntemleri uygulayın:

    ```csharp
    /// <summary>
        /// Editor for MSBin1 content type (WCF messages)
        /// </summary>
        public class Msbin1MessageEditor : IBinaryHttpBodyEditorPlugin
        {
            /// <summary>
            ///
            /// </summary>
            public Msbin1MessageEditor()
            {
            }

            /// <summary>
            /// Determine if this plugin supports a content type.
            /// </summary>
            /// <param name="contentType">The content type to test.</param>
            /// <returns>Returns true if the plugin supports the specified content type.</returns>
            public bool SupportsContentType(string contentType)
            {
                return contentType.ToLower().Contains("msbin1");
            }

            /// <summary>
            /// Create a UserControl to edit the specified bytes.  This control will be hosted in the
            /// plugin dialog which provides OK and Cancel buttons.
            /// </summary>
            /// <param name="contentType">The content type of the BinaryHttpBody.</param>
            /// <param name="initialValue">The bytes to edit.  The bytes are the payload of a BinaryHttpBody.</param>
            /// <returns>A UserControl capable of displaying and editing the byte array value of the specified content type.</returns>
            public object CreateEditor(string contentType, byte[] initialValue)
            {
                messageEditorControl = new MessageEditorControl();
                messageEditorControl.EditByteArray = initialValue;
                return messageEditorControl;
            }

            /// <summary>
            /// Gets the edited bytes after the OK button is clicked on the plugin dialog.
            /// </summary>
            public byte[] GetNewValue()
            {
                return messageEditorControl.EditByteArray;
            }

            private MessageEditorControl messageEditorControl;
            private object originalMessage;
        }
    ```

## <a name="build-and-deploy-the-plug-ins"></a>Derleme ve eklentiler dağıtma

### <a name="to-build-and-deploy-the-resulting-dll-for-the-istringhttpbodyeditorplugin-and-ibinaryhttpbodyeditorplugin"></a>Derleme ve sonuçta elde edilen dll IStringHttpBodyEditorPlugin ve IBinaryHttpBodyEditorPlugin dağıtmak için

1.  Yapı menüsünde, **yapı \<Windows Form denetimi kitaplığı proje adı >**.

2.  Visual Studio tüm örneklerini kapatın.

    > [!NOTE]
    > Visual Studio kapatma emin olur *.dll* kopyalanması denemeden önce dosyası kilitli değil.

3.  Elde edilen kopyalama *.dll* projelerinizi dosyasından *bin\debug* klasörünü (örneğin, *MessageEditors.dll*) %ProgramFiles%\Microsoft Visual Studio\2017 için\\ <edition>\Common7\IDE\PrivateAssemblies\WebTestPlugins.

4.  Visual Studio'yu açın.

     *.Dll* artık Visual Studio ile kaydedilir.

## <a name="verify-the-plug-ins-using-a-web-performance-test"></a>Web performans testine kullanarak eklentileri doğrulayın

### <a name="to-test-your-plug-ins"></a>Eklentilerinizi test etmek için

1.  Bir Test projesi oluşturun.

2.  Web performans testi oluşturma ve örneğin, bir Web hizmeti için bir URL tarayıcıda girin http://dev.virtualearth.net/webservices/v1/metadata/searchservice/dev.virtualearth.net.webservices.v1.search.wsdl.

3.  Kaydı bitirdikten sonra Web Performans Testi Düzenleyicisi'nde, Web hizmeti isteği'ni genişletin ve seçin bir **dize gövde** veya **ikili gövde**.

4.  Özellikleri penceresinde dize gövde ya da İkili Gövde seçin ve üç nokta (...) belirtin.

     **HTTP gövdesi verilerini düzenleme** iletişim kutusu görüntülenir.

5.  Şimdi verileri düzenleyin ve Tamam'ı seçin. Bu içeriği güncelleştirmek için uygun GetNewValue yöntemini çağırır <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody>.

## <a name="compile-the-code"></a>Kod derleme

Windows Denetim Kitaplığı projesini hedeflenen çerçevesini .NET Framework 4.5 olduğunu doğrulayın. Varsayılan olarak, Windows Denetim Kitaplığı projeleri Microsoft.VisualStudio.QualityTools.WebTestFramework başvuru ekleme izin vermez .NET Framework 4.5 istemci framework hedefleyin.

Daha fazla bilgi için bkz: [uygulama sayfası, Proje Tasarımcısı (C#)](../ide/reference/application-page-project-designer-csharp.md).

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.IStringHttpBodyEditorPlugin>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.IBinaryHttpBodyEditorPlugin>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.IHttpBody>
- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.RichTextBox>
- [Özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Nasıl yapılır: istek düzeyi eklentisi oluşturma](../test/how-to-create-a-request-level-plug-in.md)
- [Web performans testi için özel ayıklama kuralı kodlama](../test/code-a-custom-extraction-rule-for-a-web-performance-test.md)
- [Web performans testi için özel doğrulama kuralı kodlama](../test/code-a-custom-validation-rule-for-a-web-performance-test.md)
- [Nasıl yapılır: yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md)
- [Oluşturma ve kodlanmış web performans testini çalıştırma](../test/generate-and-run-a-coded-web-performance-test.md)
- [Nasıl yapılır: Web Performans Testi Sonuçları Görüntüleyicisi için Visual Studio eklentisi oluşturma](../test/how-to-create-an-add-in-for-the-web-performance-test-results-viewer.md)