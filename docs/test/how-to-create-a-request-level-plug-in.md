---
title: İstek düzeyi eklentisi web performans testleri için Visual Studio'da oluşturma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- request-level plug-in, creating
- Web performance tests, requests
ms.assetid: d0b5b23c-7e94-4637-be6c-2620a5442d46
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: ac50f956ed45f42f77638146c1340c0ed90f68fa
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-request-level-plug-in"></a>Nasıl yapılır: İstek Düzeyi Eklentisi Oluşturma

*İstekleri* Web performans testleri oluşturan bildirim temelli deyimleri. Web performans testi eklentileri, Web performans testinde ana bildirim deyimleri dışındaki kodu yeniden kullanma ve yalıtmak etkinleştirin. Eklentiler oluşturabilir ve bunları ayrı bir istek de içerdiği Web performans testi için ekleyin. Özelleştirilmiş *istek eklentisi* belirli bir istek bir Web performans testinde çalışacak şekilde kodu çağırmak için bir yol sunar.

Her Web performans testi istek eklentisi PreRequest yöntemi ve bir de PostRequest yöntemine sahiptir. Belirli http isteği için bir istek eklentisi ekledikten sonra PreRequest olay istek ve yanıt alındıktan sonra PostRequest harekete önce şu.

Kendi sınıfından türetilen, özelleştirilmiş bir Web performans testi isteği eklentisi oluşturabilirsiniz <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin> temel sınıfı.

Web performans testleri kaydettiğiniz özelleştirilmiş Web performans testi isteği eklentileri kullanabilirsiniz. Özelleştirilmiş Web performans testi isteği eklentileri kod, Web performans testleri üzerinde denetim büyük bir düzeyde elde etmek için en az miktarda yazmanıza olanak sağlar. Ancak, bunları kodlanmış Web performans testleri ile de kullanabilirsiniz. Bkz: [oluşturma ve çalıştırma kodlanmış web performans testine](../test/generate-and-run-a-coded-web-performance-test.md).

## <a name="to-create-a-request-level-plug-in"></a>İstek düzeyi eklentisi oluşturmak için

1.  Çözüm Gezgini'nde çözüme sağ tıklayın. seçin **Ekle** ve ardından **yeni proje**.

     **Yeni Proje Ekle** iletişim kutusu görüntülenir.

2.  Altında **yüklü şablonlar**seçin **Visual C#**.

3.  Şablonları listesinde seçin **sınıf kitaplığı**.

4.  İçinde **adı** metin kutusuna seçin ve sınıf için bir ad yazın **Tamam**.

     Çözüm Gezgini'ne yeni sınıf kitaplığı proje eklenir ve yeni sınıf Kod Düzenleyicisi'nde görüntülenir.

5.  Çözüm Gezgini'nde sağ **başvuruları** seçin ve yeni bir sınıf kitaplığı klasöründe **Başvuru Ekle**.

     **Başvuru Ekle** iletişim kutusu görüntülenir.

6.  Seçin **.NET** sekmesinde, aşağı kaydırın, seçin **Microsoft.VisualStudio.QualityTools.WebTestFramework** ve ardından **Tamam**

     Başvuru **Microsoft.VisualStudio.QualityTools.WebTestFramework** eklenen **başvuru** Çözüm Gezgininde klasör.

7.  Çözüm Gezgini'nde Web performansının üst düğümünü sağ tıklatın ve Web performans testi isteği test eklentisini eklemek istediğiniz yük testini içeren test projesini yükleyin.  Seçin **başvuru ekleme**.

     **Başvuru Ekle iletişim kutusu görüntülenir**.

8.  Seçin **projeleri** sekmesinde, sınıf kitaplığı projesini seçin ve ardından **Tamam** .

9. Kod Düzenleyicisi'nde eklentinizin kodunu yazın. İlk olarak, türetilen yeni bir ortak sınıf oluşturun <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>.

10. Uygulama içinde bir veya iki kod <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin.PreRequest*> ve <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin.PostRequest*> olay işleyicileri. Örnek uygulama için aşağıdaki örnek bölümüne bakın.

11. Kodu yazdıktan sonra yeni proje oluşturun.

12. İstek eklentisini eklemek istediğiniz Web performans testi açın.

13. Eklenti ve select isteği eklemek istediğiniz isteği sağ **istek eklentisi Ekle**.

     **Web testi isteği eklentisi** iletişim kutusu görüntülenir.

14. Altında **bir eklenti seçin**, yeni seçin eklentisi.

15. İçinde **özelliklerini seçili eklenti** bölmesinde, eklentinin çalışma zamanında kullanılacak başlangıç değerlerini ayarlayın.

    > [!NOTE]
    > Eklentilerinizi istediğiniz sayıda özelliği getirebilir; Yalnızca bunları ortak, ayarlanabilir ve tamsayı, Boole veya dize gibi bir temel türden yapın. Özellikler penceresini kullanarak Web performans testi eklentisi özelliklerini daha sonra da değiştirebilirsiniz.

16. Seçin **Tamam**.

     Eklenti eklenen **isteği eklentileri** HTTP isteğinin bir alt klasörü klasörü.

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

İki iletişim kutularını görüntüleyen bir özelleştirilmiş Web performans testi eklentisi oluşturmak için aşağıdaki kodu kullanabilirsiniz. İletişim kutusu İstek eklentisini eklediğiniz istekle ilişkili URL'yi görüntüler. İkinci bir iletişim kutusu aracı için bilgisayar adını görüntüler.

> [!NOTE]
> Aşağıdaki kod System.Windows.Forms bir başvuru eklemeniz gerekir.

```csharp
using System;
using System.Collections.Generic;
using System.Windows.Forms;
using Microsoft.VisualStudio.TestTools.WebTesting;

namespace RequestPluginNamespace
{
    public class MyWebRequestPlugin : WebTestRequestPlugin
    {
        public override void PostRequest(object sender, PostRequestEventArgs e)
        {
            MessageBox.Show(e.WebTest.Context.AgentName);
        }
        public override void PreRequest(object sender, PreRequestEventArgs e)
        {
            MessageBox.Show(e.Request.Url);
        }
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>
- [Özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Web performans testi için özel ayıklama kuralı kodlama](../test/code-a-custom-extraction-rule-for-a-web-performance-test.md)
- [Web performans testi için özel doğrulama kuralı kodlama](../test/code-a-custom-validation-rule-for-a-web-performance-test.md)
- [Nasıl yapılır: yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md)
- [Oluşturma ve kodlanmış web performans testini çalıştırma](../test/generate-and-run-a-coded-web-performance-test.md)