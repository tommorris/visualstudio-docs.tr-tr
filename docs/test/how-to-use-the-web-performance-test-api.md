---
title: Web performans testi API'si Visual Studio'da | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Web performance tests, using the API
- APIs, Web performance tests
ms.assetid: 93a6a1dd-663b-4ab5-8760-7d6b081561d3
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: ed7cbc7375cbf416d82a56c140479925569dad8d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-the-web-performance-test-api"></a>Nasıl yapılır: Web Başarım Testi API'si Kullanma

Web performans testleri için kod yazabilirsiniz. API oluşturmak için kullanılan Web performans testi kodlanmış Web performans testleri, Web performans testi eklentileri, istek eklentileri, istekleri, ayıklama kuralları ve doğrulama kuralları. Bu türleri oluşturan sınıflar API'deki çekirdek sınıflarıdır. Bu API diğer türler oluşturma desteklemek için kullanılan <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTest>, <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>, <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>, <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequest>, <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule>, ve <xref:Microsoft.VisualStudio.TestTools.WebTesting.ValidationRule> nesneleri. Kullandığınız <xref:Microsoft.VisualStudio.TestTools.WebTesting> ad alanı oluşturmak için özelleştirilmiş Web performans testlerini.

 Web performans testi API'sini, programlı olarak oluşturun ve bildirim temelli Web performans testleri kaydetmek için de kullanabilirsiniz. Bunu yapmak için kullanın <xref:Microsoft.VisualStudio.TestTools.WebTesting.DeclarativeWebTest> ve <xref:Microsoft.VisualStudio.TestTools.WebTesting.DeclarativeWebTestSerializer> sınıfları.

> [!TIP]
>  İncelemek için nesne tarayıcısı kullanın <xref:Microsoft.VisualStudio.TestTools.WebTesting> ad alanı. Visual C# ve Visual Basic düzenleyicileri ad alanındaki sınıflar ile kodlamak için IntelliSense desteği sunar.

 Yük testleri için eklentileri de oluşturabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: yük testi API'si kullanma](../test/how-to-use-the-load-test-api.md) ve [nasıl yapılır: yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md).

## <a name="to-use-the-webtesting-namespace"></a>WebTesting ad alanını kullanmak için

1.  Bir Web performansı ve Web performansı testi içeren bir yük testi projesi açın.

2.  Visual C# veya Visual Basic sınıf kitaplığı proje test çözümünüze ekleyin.

3.  Bir başvuru sınıf kitaplığı projesi için Web performansı ve yük testi projeye ekleyin.

4.  Sınıf kitaplığı projesinde Microsoft.VisualStudio.QualityTools.WebTestFramework DLL bir başvuru ekleyin.

5.  Sınıf kitaplığı projesinde bulunan sınıf dosyasına ekleyin bir `using` bildirimi <xref:Microsoft.VisualStudio.TestTools.WebTesting> ad alanı.

6.  Arabirimini uygulayan bir sınıf oluşturun <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin> arabirimi.

7.  Projeyi oluşturun.

8.  Web Performans Testi Düzenleyicisi'ni kullanarak yeni Web performans testi eklentisi ekleyin:

    1.  Seçin **Web Testi Eklentisi Ekle** araç çubuğunda.

         **Web Testi Eklentisi Ekle** iletişim kutusu görüntülenir.

    2.  Altında **bir eklenti seçin**seçin, Web performans testi eklentisi sınıfı.

    3.  İçinde **özelliklerini seçili eklenti** bölmesinde, eklentinin çalışma zamanında kullanılacak başlangıç değerlerini ayarlayın.

        > [!NOTE]
        > Eklentilerinizi istediğiniz sayıda özelliği getirebilir; Yalnızca bunları ortak, ayarlanabilir ve tamsayı, Boole veya dize gibi bir temel türden yapın. Özellikler penceresini kullanarak Web performans testi eklentisi özelliklerini daha sonra da düzenleyebilirsiniz.

    4.  Seçin **Tamam**.

9. Web performans testi çalıştırın.

     Bir örnek uygulama için <xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>, bkz: [nasıl yapılır: Web performans testi eklentisi oluşturma](../test/how-to-create-a-web-performance-test-plug-in.md).

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.WebTesting>
- [Özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Nasıl yapılır: yük testi API'si kullanma](../test/how-to-use-the-load-test-api.md)
- [Nasıl yapılır: Web başarım testi eklentisi oluşturma](../test/how-to-create-a-web-performance-test-plug-in.md)