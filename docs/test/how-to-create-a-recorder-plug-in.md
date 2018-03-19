---
title: "Kaydedici eklentisi web performans testleri için Visual Studio'da oluşturma | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Web performance tests, recorder plug-in
ms.assetid: 6fe13be1-aeb5-4927-9bff-35950e194da9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: b61da58ca621f04628697382e83c209187016f5d
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-create-a-recorder-plug-in"></a>Nasıl yapılır: Kaydedici Eklentisi Oluşturma

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin> Kaydedilen Web performans testine değiştirmenize olanak tanır. Seçtiğiniz sonra değişikliği oluşur **durdurmak** Kaydedici araç ancak test edilen öncesi test kaydedilen ve Web Performans Testi Düzenleyicisi'nde sunulan Web performans.

Kaydedici eklentisi, kendi özel bağıntı üzerinde dinamik parametreleri gerçekleştirmenizi sağlar. Yerleşik bağıntı işlevselliği ile Web performans testleri dinamik parametreleri Web kayıt tamamlandıktan sonra veya kullandığınızda algılamak **dinamik parametreleri Web testi parametrelerine yükseltme** Web performansı Testi Düzenleyicisi araç. Ancak, yerleşik algılama işlevselliği tüm dinamik parametreleri her zaman bulmaz. Örneğin, genellikle 5 ila 30 dakika arasında bir değer alır oturum kimliği bulmaz. Bu nedenle, bağıntı işlemini el ile yapmanız gerekir.

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin> Eklenti kendi özel kod yazmanıza olanak sağlar. Bu eklenti bağıntı yapabilir veya kaydedilip Web Performans Testi Düzenleyicisi'nde sunulan önce birçok yolu Web performans testinde değiştirin. Bu nedenle, dinamik bir değişken için kayıtlarınızı çok ilintili olması gerektiğini belirlerseniz, süreci otomatik hale getirebilirsiniz.

Kaydedici eklentisi kullanılabilir diğer bir yol ekleme ayıklama ve doğrulama kuralları, bağlam parametreleri ekleme veya dönüştürme yorumları işlemlere Web performans testi.

Aşağıdaki yordamlar, ilkel kodunun kaydedici eklentisi oluşturma, eklenti dağıtmak ve eklenti yürütmek açıklar. Yordamlar aşağıdaki örnek kod, Visual C# özel dinamik parametre bağıntı kaydedici eklentisi oluşturma için nasıl kullanılacağını göstermektedir.

## <a name="creating-a-recorder-plug-in"></a>Kaydedici eklentisi oluşturma

### <a name="to-create-a-recorder-plug-in"></a>Kaydedici eklentisi oluşturmak için

1.  Web performans testi kaydedici eklentisi oluşturmak istediğiniz Web performansı ve yük testi projesi içeren bir çözüm açın.

2.  Çözüm Gezgini'nde çözüme sağ tıklayın, seçin **Ekle**ve ardından **yeni proje**.

     **Yeni Proje Ekle** iletişim kutusu görüntülenir.

3.  Altında **yüklü şablonlar**seçin **Visual C#**.

4.  Şablonları listesinde seçin **sınıf kitaplığı**.

5.  İçinde **adı** metin kutusuna kaydedici eklentisi için bir ad yazın.

     Sınıf kitaplığı çözüm Gezgini'ne eklenir ve yeni sınıf Kod Düzenleyicisi'nde açılır.

6.  Çözüm Gezgini'nde, yeni sınıf kitaplığı proje klasörünü sağ tıklatın **başvuruları** klasörü ve select **Başvuru Ekle**.

    > [!TIP]
    > Yeni bir sınıf kitaplığı proje klasöründe örneğidir **RecorderPlugins**.

     **Başvuru Ekle** iletişim kutusu görüntülenir.

7.  Seçin **.NET** sekmesi.

8.  Seçin ve aşağı kaydırma **Microsoft.VisualStudio.QualityTools.WebTestFramework** ve ardından **Tamam**.

     **Microsoft.VisualStudio.QualityTools.WebTestFramework** eklenir **başvuruları** Çözüm Gezgininde klasör.

9. Kaydedici eklentiniz için bir kod yazın. İlk olarak, türetilen yeni bir ortak sınıf oluşturun <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin>.

10. Geçersiz kılma <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin.PostWebTestRecording*> yöntemi.

    ```csharp
    public class Class1 : WebTestRecorderPlugin
        {
            public override void PostWebTestRecording(object sender, PostWebTestRecordingEventArgs e)
            {
                base.PostWebTestRecording(sender, e);
            }
        }
    ```

     Olay bağımsız değişkenleri ile çalışmak için iki nesne verecektir: kaydedilen sonuç ve kaydedilen Web performans testi. Bu, belirli değerleri aynı istekte sonra atlama değişiklikler yapmak için Web performans testinde arayışında sonuç yinelemek olanak tanır. Bir bağlam parametresi eklemek veya URL'nin parçalarını Parametreleştirme istemeniz durumunda, yalnızca Web performans testi değiştirebilirsiniz.

    > [!NOTE]
    > Web performans testi değiştirirseniz, aynı zamanda ayarlamanız gerekir <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostWebTestRecordingEventArgs.RecordedWebTestModified*> özelliği true olarak: `e.RecordedWebTestModified = true;`

11. Kaydedici eklentisi Web kaydı gerçekleştikten sonra yürütülecek istediğinize göre daha fazla kodu ekleyin. Örneğin, aşağıdaki örnekte gösterildiği gibi özel bağıntı işlemek için kod ekleyebilirsiniz. Yorumları işlemlere dönüştürme veya doğrulama kuralları ekleme Web performansı test ayrıca kaydedici eklentisi gibi işlemler için oluşturabilirsiniz.

12. Üzerinde **yapı** menüsünde yapı seçin \<sınıf kitaplığı proje adı >.

13. Ardından, kaydedici eklentisi için Visual Studio ile kaydetmek bu dağıtmanız gerekir.

### <a name="deploy-the-recorder-plug-in"></a>Kaydedici eklentisi dağıtma

Kaydedici eklentisi derledikten sonra ortaya çıkan DLL'i iki konumdan birinde yerleştirin gerekir:

-   %ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\WebTestPlugins

-   %USERPROFILE%\My Documents\Visual Studio \< *sürüm*> \WebTestPlugins

> [!WARNING]
> Kaydedici eklentisi iki konumlardan birine kopyaladıktan sonra Visual Studio eklentisinin kaydedilmesi için Kaydedici için yeniden başlatmanız gerekir.

### <a name="to-execute-the-recorder-plug-in"></a>Kaydedici eklentisi yürütmek için

1.  Yeni bir Web performans testi oluşturun.

     **WebTestRecordPlugins'i Etkinleştir** iletişim kutusunu görüntüler.

2.  Kaydedici eklentisi için onay kutusunu seçin ve Tamam'ı seçin.

     Web performans testi kayıt tamamlandıktan sonra yeni kaydedici eklentisi yürütülür.

    > [!WARNING]
    > Web performans testi ya da eklentisini kullanan yük testi çalıştırdığınızda, aşağıdakine benzer bir hata alabilirsiniz:
    >
    > **İsteği başarısız oldu: özel durum \<eklenti > olay: dosya veya derleme yüklenemedi '\<"Eklenti adı".dll dosyası >, sürüm =\<n.n.n.n >, Culture = neutral, PublicKeyToken = = null' ya da bağımlılıklarından biri. Sistem belirtilen dosyayı bulamıyor.**
    >
    > Kod değişikliklerini eklentilerinizi birini yapın ve yeni bir DLL sürümü oluşturursanız Bunun nedeni **(sürüm 0.0.0.0 =)**, ancak eklenti hala özgün eklenti sürümüne başvuruyor. Bu sorunu gidermek için şu adımları izleyin:
    >
    > 1.  Web performans ve yük testi projesi içinde başvurularda bir uyarı görürsünüz. Kaldırın ve yeniden eklentisi DLL'sini başvurusunu ekleyin.
    > 2.  Testinizi veya uygun konumdan eklentiyi kaldırın ve yeniden ekleyin.

## <a name="example"></a>Örnek

Bu örnek, özelleştirilmiş bir Web Performans Testi Kaydedicisi özel parametre bağıntısı yapmak için eklentisi oluşturma gösterilmiştir.

> [!NOTE]
> Örnek kod için tam bir listesi, bu konu altında bulunur.

 **Örnek kod gözden geçirme**

## <a name="iterate-through-the-result-to-find-first-page-with-reportsession"></a>Rapor oturumu ile ilk sayfa bulmak için sonuç yinelemek

Bu kod örneği parçası kaydedilmiş her nesne boyunca yinelenir ve rapor oturumu için yanıt gövdesini arar.

```csharp
foreach (WebTestResultUnit unit in e.RecordedWebTestResult.Children)
 {
     WebTestResultPage page = unit as WebTestResultPage;
     if (page != null)
     {
         if (!foundId)
         {
             int indexOfReportSession = page.RequestResult.Response.BodyString.IndexOf("ReportSession");
             if (indexOfReportSession > -1)
             {
```

## <a name="add-an-extraction-rule"></a>Bir ayıklama kuralı ekleme

Bir yanıt bulunamadı, bir ayıklama kuralı eklemeniz gerekir. Ayıklama kuralı kullanarak bu kod örneği parçası oluşturur <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRuleReference> sınıfı ve ayıklama kuralı eklemek için Web performans testinde doğru isteği bulur. Her sonuç nesnesinin yeni bir sahip eklenen özellik ne kodda Web performans testinden doğru isteği almak için kullanılan olan DeclarativeWebTestItemId çağrılır.

```csharp
ExtractionRuleReference ruleReference = new ExtractionRuleReference();
     ruleReference.Type = typeof(ExtractText);
     ruleReference.ContextParameterName = "SessionId";
     ruleReference.Properties.Add(new PluginOrRuleProperty("EndsWith", "&ControlID="));
     ruleReference.Properties.Add(new PluginOrRuleProperty("HtmlDecode", "True"));
     ruleReference.Properties.Add(new PluginOrRuleProperty("IgnoreCase", "True"));
     ruleReference.Properties.Add(new PluginOrRuleProperty("Index", "0"));
     ruleReference.Properties.Add(new PluginOrRuleProperty("Required", "True"));
     ruleReference.Properties.Add(new PluginOrRuleProperty("StartsWith", "ReportSession="));
     ruleReference.Properties.Add(new PluginOrRuleProperty("UseRegularExpression", "False"));

     WebTestRequest requestInWebTest = e.RecordedWebTest.GetItem(page.DeclarativeWebTestItemId) as WebTestRequest;
     if (requestInWebTest != null)
     {
         requestInWebTest.ExtractionRuleReferences.Add(ruleReference);
         e.RecordedWebTestModified = true;
     }
```

## <a name="replace-query-string-parameters"></a>Sorgu dizesi parametreleri değiştirin

Şimdi kod tüm sorgu rapor oturumu adı ve değeri {{SessionID}} Bu kod örneği bölümünde gösterildiği gibi değiştirme dizesi parametreleri bulur:

```csharp
WebTestRequest requestInWebTest = e.RecordedWebTest.GetItem(page.DeclarativeWebTestItemId) as WebTestRequest;
if (requestInWebTest != null)
{
    foreach (QueryStringParameter param in requestInWebTest.QueryStringParameters)
    {
         if (param.Name.Equals("ReportSession"))
         {
             param.Value = "{{SessionId}}";
         }
     }
 }
```

```csharp
using System.ComponentModel;
using Microsoft.VisualStudio.TestTools.WebTesting;
using Microsoft.VisualStudio.TestTools.WebTesting.Rules;

namespace RecorderPlugin
{
    [DisplayName("Correlate ReportSession")]
    [Description("Adds extraction rule for Report Session and binds this to querystring parameters that use ReportSession")]
    public class CorrelateSessionId : WebTestRecorderPlugin
    {
        public override void PostWebTestRecording(object sender, PostWebTestRecordingEventArgs e)
        {
            //first find the session id
            bool foundId = false;
            foreach (WebTestResultUnit unit in e.RecordedWebTestResult.Children)
            {
                WebTestResultPage page = unit as WebTestResultPage;
                if (page != null)
                {
                    if (!foundId)
                    {
                        int indexOfReportSession = page.RequestResult.Response.BodyString.IndexOf("ReportSession");
                        if (indexOfReportSession > -1)
                        {
                            //add an extraction rule to this request
                            // Get the corresponding request in the Declarative Web performance test
                            ExtractionRuleReference ruleReference = new ExtractionRuleReference();

                            ruleReference.Type = typeof(ExtractText);
                            ruleReference.ContextParameterName = "SessionId";
                            ruleReference.Properties.Add(new PluginOrRuleProperty("EndsWith", "&ControlID="));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("HtmlDecode", "True"));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("IgnoreCase", "True"));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("Index", "0"));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("Required", "True"));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("StartsWith", "ReportSession="));
                            ruleReference.Properties.Add(new PluginOrRuleProperty("UseRegularExpression", "False"));

                            WebTestRequest requestInWebTest = e.RecordedWebTest.GetItem(page.DeclarativeWebTestItemId) as WebTestRequest;
                            if (requestInWebTest != null)
                            {
                                requestInWebTest.ExtractionRuleReferences.Add(ruleReference);
                                e.RecordedWebTestModified = true;
                            }
                            foundId = true;

                        }
                    }
                    else
                    {
                        //now update query string parameters
                        WebTestRequest requestInWebTest = e.RecordedWebTest.GetItem(page.DeclarativeWebTestItemId) as WebTestRequest;
                        if (requestInWebTest != null)
                        {
                            foreach (QueryStringParameter param in requestInWebTest.QueryStringParameters)
                            {
                                if (param.Name.Equals("ReportSession"))
                                {
                                    param.Value = "{{SessionId}}";
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin.PostWebTestRecording*>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRuleReference>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin.PostWebTestRecording*>
- [Özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Oluşturma ve kodlanmış web performans testini çalıştırma](../test/generate-and-run-a-coded-web-performance-test.md)