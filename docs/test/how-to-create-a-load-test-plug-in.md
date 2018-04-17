---
title: Bir yük testi Visual Studio eklentisi oluşturma | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.load.loadtestplugin
helpviewer_keywords:
- code, load tests
- plug-ins, load test
- load tests, plug-ins
ms.assetid: 27806972-1b15-4388-833d-6d0632816f1f
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 6e585fe66bde573f8bb133b0c8cda0900b0d6d16
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-load-test-plug-in"></a>Nasıl yapılır: Yük Testi Eklentisi Oluşturma

Bir yük testi eklentisi yük testi çalışırken kodu farklı zamanlarda çalışmak üzere oluşturabilirsiniz. Üzerine genişletmek veya yerleşik yük testi işlevindeki değiştirmek için bir eklenti oluşturun. Örneğin, ayarlamak veya yük testi çalışırken yük testi düzeni değiştirmek için bir yük testi eklentisi kodlayabilirsiniz. Bunu yapmak için devralınan bir sınıf oluşturun <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> arabirimi. Bu sınıf uygulamalıdır <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin.Initialize*> bu arabirimin yöntemi. Daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>.

> [!NOTE]
> Web performans testleri için eklentileri de oluşturabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Web performans testi eklentisi oluşturma](../test/how-to-create-a-web-performance-test-plug-in.md)

## <a name="to-create-a-load-test-plug-in-by-using-visual-c"></a>Visual C# kullanarak bir yük testi eklentisi oluşturma

1.  Bir Web performansı ve Web performansı testi içeren bir yük testi projesi açın.

2.  Bir yük testi için test projesi ekleyin ve bir Web performans testi çalıştırmak için yapılandırın.

     Daha fazla bilgi için bkz: [hızlı başlangıç: yük testi projesi oluşturma](../test/quickstart-create-a-load-test-project.md).

3.  Çözüm Gezgini'nde sağ tıklatın ve çözüm **Ekle** ve ardından **yeni proje**.

     **Yeni Proje Ekle** iletişim kutusu görüntülenir.

4.  Altında **yüklü şablonlar**seçin **Visual C#**.

5.  Şablonları listesinde seçin **sınıf kitaplığı**.

6.  İçinde **adı** metin kutusuna, sınıf için bir ad yazın.

7.  Seçin **Tamam**.

8.  Çözüm Gezgini'ne yeni sınıf kitaplığı proje eklenir ve yeni sınıf Kod Düzenleyicisi'nde görüntülenir.

9. Çözüm Gezgini'nde sağ **başvuruları** seçin ve yeni bir sınıf kitaplığı klasöründe **Başvuru Ekle**.

10. **Başvuru Ekle** iletişim kutusu görüntülenir.

11. Seçin **.NET** sekmesinde, aşağı kaydırın ve ardından **Microsoft.VisualStudio.QualityTools.LoadTestFramework**.

12. Seçin **Tamam**.

     Başvuru **Microsoft.VisualStudio.QualityTools.LoadTestFramework** eklenen **başvuru** Çözüm Gezgininde klasör.

13. Çözüm Gezgini'nde Web performansı ve yük testi eklentisi ve select eklemek istediğiniz yük testi içeren yük test projesinin üst düğümünü sağ **Başvuru Ekle**.

14. **Başvuru Ekle iletişim kutusu görüntülenir**.

15. Seçin **projeleri** sekmesinde ve sınıf kitaplığı projesini seçin.

16. Seçin **Tamam**.

17. Kod Düzenleyicisi'nde eklemek bir `using` bildirimi <xref:Microsoft.VisualStudio.TestTools.LoadTesting> ad alanı.

18. Uygulama <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> sınıf kitaplığı projesinde oluşturulan sınıf için arabirim. Örnek uygulama için aşağıdaki örnek bölümüne bakın.

19. Kodu yazdıktan sonra yeni proje oluşturun.

20. Yük testi üst düğümüne sağ tıklayın ve ardından **Yük Testi Eklentisi Ekle**.

     **Yük Testi Eklentisi Ekle** iletişim kutusu görüntülenir.

21. Altında **bir eklenti seçin**seçin, yük testi eklentisi sınıfı.

22. İçinde **özelliklerini seçili eklenti** bölmesinde, eklentinin çalışma zamanında kullanılacak başlangıç değerlerini ayarlayın.

    > [!NOTE]
    > Eklentilerinizi istediğiniz sayıda özelliği getirebilir; Yalnızca bunları ortak, ayarlanabilir ve tamsayı, Boole veya dize gibi bir temel türden yapın. Özellikler penceresini kullanarak Web performans testi eklentisi özelliklerini daha sonra da değiştirebilirsiniz.

23. Seçin **Tamam**.

     Eklenti eklenen **yük testi eklentileri** klasör.

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

Aşağıdaki kod özel kod LoadTestFinished olayı gerçekleştikten sonra çalıştırılan bir yük testi eklentisi gösterir. Bu kod, test aracısı uzak makinede çalışır ve test aracısı localhost SMTP hizmeti yüklü değil yük testi bir ileti kutusu açık olduğundan "Sürüyor" durumunda kalır.

> [!NOTE]
>  Aşağıdaki kod System.Windows.Forms bir başvuru eklemeniz gerekir.

```csharp
using System;
using Microsoft.VisualStudio.TestTools.LoadTesting;
using System.Net.Mail;
using System.Windows.Forms;

namespace LoadTestPluginTest
{
    public class MyLoadTestPlugin : ILoadTestPlugin
    {
        LoadTest myLoadTest;

        public void Initialize(LoadTest loadTest)
        {
            myLoadTest = loadTest;
            myLoadTest.LoadTestFinished += new
                EventHandler(myLoadTest_LoadTestFinished);
        }

        void myLoadTest_LoadTestFinished(object sender, EventArgs e)
        {
            try
            {
                // place custom code here
                MailAddress MyAddress = new MailAddress("someone@example.com");
                MailMessage MyMail = new MailMessage(MyAddress, MyAddress);
                MyMail.Subject = "Load Test Finished -- Admin Email";
                MyMail.Body = myLoadTest..Name + " has finished.";

                SmtpClient MySmtpClient = new SmtpClient("localhost");
                MySmtpClient.Send(MyMail);
            }

            catch (SmtpException ex)
            {
                MessageBox.Show(ex.InnerException.Message +
                    ".\r\nMake sure you have a valid SMTP.", "LoadTestPlugin", MessageBoxButtons.OK, MessageBoxIcon.Warning, MessageBoxDefaultButton.Button1);
            }
        }
    }
}
```

Sekiz olay eklentisinin yükleme testiyle özel kodu çalıştırmak için yük testi işlenebilir bir yük testi ile ilişkilidir. Yük testi farklı dönemlerini erişim sağlamak olaylarının bir listesi verilmiştir:

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.LoadTestStarting>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.LoadTestFinished>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.LoadTestWarmupComplete>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.TestStarting>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.TestFinished>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.ThresholdExceeded>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.Heartbeat>

-   <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest.LoadTestAborted>

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>
- [Özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Nasıl yapılır: Web başarım testi eklentisi oluşturma](../test/how-to-create-a-web-performance-test-plug-in.md)