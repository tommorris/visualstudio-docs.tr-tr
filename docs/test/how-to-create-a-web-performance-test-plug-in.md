---
title: Web performans testi için Visual Studio eklentisi oluşturma
ms.date: 10/03/2016
ms.topic: conceptual
f1_keywords:
- vs.test.web.webtestplugin
helpviewer_keywords:
- Web performance tests, creating plug-ins
- plug-ins, creating in Web performance tests
ms.assetid: a612f2d2-9806-477d-a126-12842f07da6e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 57fab4ee4205e9b1aaf7aaa44218134649257598
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974981"
---
# <a name="how-to-create-a-web-performance-test-plug-in"></a>Nasıl yapılır: Web Başarım Testi Eklentisi Oluşturma

Web performans testleri eklentileri yalıtmak ve Web performans testinde ana bildirim deyimleri dışındaki kodu yeniden etkinleştirin. Özelleştirilmiş bir Web performans testi eklentisi Web performans testini çalıştırma gibi bazı kodlar çağırmak için bir yol sunar. Web performans testi eklentisi her test yineleme için bir kez çalıştırılır. Testi Eklentisi PreRequest veya PostRequest yöntemlerini geçersiz kılarsanız, ayrıca, bu istek eklentileri önce veya sonra her istek sırasıyla çalıştırın.

Kendi sınıfından türetilen, özelleştirilmiş bir Web performans testi eklentisi oluşturabilirsiniz <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin> temel sınıfı.

Özelleştirilmiş Web performans testi eklentileri kodu daha büyük bir Web performans testleri üzerinde denetim düzeyini elde etmek için en az miktarda yazmanızı sağlayan bir Web performans testleri kaydetmiş olduğunuz kullanabilirsiniz. Ancak, bunları kodlanmış Web performans testleri ile de kullanabilirsiniz. Daha fazla bilgi için bkz: [oluşturma ve çalıştırma kodlanmış web performans testine](../test/generate-and-run-a-coded-web-performance-test.md).

> [!NOTE]
> Yük testi eklentileri de oluşturabilirsiniz. Bkz: [nasıl yapılır: yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md).

## <a name="to-create-a-custom-web-performance-test-plug-in"></a>Özel bir Web performans testi eklentisi oluşturmak için

1.  Bir Web performansı ve Web performansı testi içeren bir yük testi projesi açın.

2.  Çözüm Gezgini'nde sağ tıklatın ve çözüm **Ekle** ve ardından **yeni proje**.

     **Yeni Proje Ekle** iletişim kutusu görüntülenir.

3.  Altında **yüklü şablonlar**seçin **Visual C#**.

4.  Şablonları listesinde seçin **sınıf kitaplığı**.

5.  İçinde **adı** metin kutusuna, sınıf için bir ad yazın.

6.  Seçin **Tamam**.

7.  Çözüm Gezgini'ne yeni sınıf kitaplığı proje eklenir ve yeni sınıf Kod Düzenleyicisi'nde görüntülenir.

8.  Çözüm Gezgini'nde sağ **başvuruları** seçin ve yeni bir sınıf kitaplığı klasöründe **Başvuru Ekle**.

9. **Başvuru Ekle** iletişim kutusu görüntülenir.

10. Seçin **.NET** sekmesinde, aşağı kaydırın ve seçin **Microsoft.VisualStudio.QualityTools.WebTestFramework**

11. Seçin **Tamam**.

     Başvuru **Microsoft.VisualStudio.QualityTools.WebTestFramework** eklenen **başvuru** Çözüm Gezgininde klasör.

12. Çözüm Gezgini'nde Web performansı ve Web başarım testi eklentisi ve select eklemek istediğiniz yük testi içeren yük test projesinin üst düğümü üzerinde sağ **Başvuru Ekle**.

13. **Başvuru Ekle iletişim kutusu görüntülenir**.

14. Seçin **projeleri** sekmesinde ve sınıf kitaplığı projesini seçin.

15. Seçin **Tamam**.

16. Kod Düzenleyicisi'nde eklentinizin kodunu yazın. İlk olarak, türetilen yeni bir ortak sınıf oluşturun <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>.

17. Bir veya daha fazla olay işleyicileri içinde kod uygulayın. Örnek uygulama için aşağıdaki örnek bölümüne bakın.

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostWebTestRecordingEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostWebTestEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PreRequestEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostRequestEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PrePageEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostPageEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PreTransactionEventArgs>

    - <xref:Microsoft.VisualStudio.TestTools.WebTesting.PostTransactionEventArgs>

18. Kodu yazdıktan sonra yeni proje oluşturun.

19. Web performans testine açın.

20. Web performans testi eklentisi eklemek için **Web Testi Eklentisi Ekle** araç çubuğunda.

     **Web Testi Eklentisi Ekle** iletişim kutusu görüntülenir.

21. Altında **bir eklenti seçin**seçin, Web performans testi eklentisi sınıfı.

22. İçinde **özelliklerini seçili eklenti** bölmesinde, eklentinin çalışma zamanında kullanılacak başlangıç değerlerini ayarlayın.

    > [!NOTE]
    > Eklentilerinizi istediğiniz sayıda özelliği getirebilir; Yalnızca bunları ortak, ayarlanabilir ve tamsayı, Boole veya dize gibi bir temel türden yapın. Özellikler penceresini kullanarak Web performans testi eklentisi özelliklerini daha sonra da değiştirebilirsiniz.

23. Seçin **Tamam**.

     Eklenti eklenen **Web testi eklentileri** klasör.

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

Aşağıdaki kod bir öğesiyle ekleyen bir özelleştirilmiş Web performans testi eklentisi oluşturur <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestContext> test yineleme temsil eden.

Web performans testi çalıştırdıktan sonra bunu kullanarak eklenti adlı eklenen öğeyi gördüğünüz **TestIteratnionNumber** içinde **bağlamı** Web Performans Sonuçları Görüntüleyicisi sekmesindedir.

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.ComponentModel;
using Microsoft.VisualStudio.TestTools.WebTesting;

namespace SampleRules
{
    [Description("This plugin can be used to set the ParseDependentsRequests property for each request")]
    public class SampleWebTestPlugin : WebTestPlugin
    {
        private bool m_parseDependents = true;

        public override void PreWebTest(object sender, PreWebTestEventArgs e)
        {
            // TODO: Add code to execute before the test.
        }

        public override void PostWebTest(object sender, PostWebTestEventArgs e)
        {
            // TODO: Add code to execute after the test.
        }

        public override void PreRequest(object sender, PreRequestEventArgs e)
        {
            // Code to execute before each request.
            // Set the ParseDependentsRequests value on the request
            e.Request.ParseDependentRequests = m_parseDependents;
        }

        // Properties for the plugin.
        [DefaultValue(true)]
        [Description("All requests will have their ParseDependentsRequests property set to this value")]
        public bool ParseDependents
        {
            get
            {
                return m_parseDependents;
            }
            set
            {
                m_parseDependents = value;
            }
        }
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>
- [Özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Nasıl yapılır: istek düzeyi eklentisi oluşturma](../test/how-to-create-a-request-level-plug-in.md)
- [Web performans testi için özel ayıklama kuralı kodlama](../test/code-a-custom-extraction-rule-for-a-web-performance-test.md)
- [Web performans testi için özel doğrulama kuralı kodlama](../test/code-a-custom-validation-rule-for-a-web-performance-test.md)
- [Nasıl yapılır: yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md)
- [Oluşturma ve kodlanmış web performans testini çalıştırma](../test/generate-and-run-a-coded-web-performance-test.md)