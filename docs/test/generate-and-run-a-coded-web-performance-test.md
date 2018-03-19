---
title: "Kodlanmış web performans testleri Visual Studio'da | Microsoft Docs"
ms.date: 10/03/2016
ms.topic: article
helpviewer_keywords:
- Web performance tests, walkthroughs
- Web performance tests, creating
- code, Web performance tests
- Web performance tests, coded
ms.assetid: 169e48f9-52fd-4d0b-83d9-54913bde506b
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 7eb493667719b41d8014c1d9106328600a4aff0a
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="generate-and-run-a-coded-web-performance-test"></a>Kodlanmış web performans testi oluşturma

Web performans testleri web uygulamanız göz atarak kaydedilir. Testleri birden çok kullanıcının gerilim altında web uygulamanızın performansını ölçmek için yük testlerinde dahil edilir. Web performans testi düzenleme ve başka bir kaynak kod gibi özelleştirme olan kod tabanlı bir komut dönüştürülebilir. Örneğin, döngü ve dallanma yapıları ekleyebilirsiniz.

## <a name="generate-a-coded-web-performance-test"></a>Kodlanmış web performans testi oluşturma

1.  Web performans testine oluşturmadıysanız, bkz: [web performans testini kaydetme](/vsts/load-test/run-performance-tests-app-before-release#create-a-web-performance-and-load-test-project).

2.  Kodlanmış testi oluşturun.

     ![Kodlanmış web performans testi oluşturma](../test/media/web_test_coded_generate.png)

3.  Test adı.

     ![Kodlanmış web performans testi için bir ad girin](../test/media/web_test_coded_generate_nametest.png)

     Kodlanmış testi Yeni Kod Düzenleyicisi'nde açar.

     Hangi web performansı ve yük testi proje şablonu çözümünüze eklenen bağlı olarak kod Visual Basic veya Visual C# içinde oluşturulur.

     ![Kod Düzenleyicisi'nde yeni kodlanmış test açar](../test/media/web_test_coded_generate_opencodeeditor.png)

     Kodda GetRequestEnumerator() yönteminde C# veya Visual Basic'te Run() yöntemi recoded test edildi her doğrulama kuralı ve web isteği içerdiğini görebilirsiniz.

4.  Bazı basit kod ekleme tanıtmak için yöntemi ve son web isteği için kod sonra son gidin ve aşağıdaki kodu ekleyin:

    ```c#
    if (DateTime.Today.DayOfWeek == DayOfWeek.Wednesday)
    {
        WebTestRequest customRequest = new WebTestRequest("http://weather.msn.com/");
        yield return customRequest;
    }
    else
    {
        WebTestRequest customRequest = new WebTestRequest("http://msdn.microsoft.com/");
        yield return customRequest;
    }
    ```

    ```vb
    If DateTime.Today.DayOfWeek = DayOfWeek.Wednesday Then
        Dim customRequest As WebTestRequest = New WebTestRequest("http://weather.msn.com/")
        MyBase.Send(customRequest)
    Else
        Dim customRequest As WebTestRequest = New WebTestRequest("http://msdn.microsoft.com/")
        MyBase.Send(customRequest)
    End If
    ```

5.  Özel kod derlendiğinden emin olun için çözümü oluşturun.

6.  Testi çalıştırın.

     ![Kodlanmış web performans testi](../test/media/web_test_coded_generate_run.png "Web_Test_Coded_Generate_Run")

     Ve Çarşamba olması için bu çalıştırıldı gün oldu çünkü...

     ![Kodlanmış web performans testi sonuçları](../test/media/web_test_coded_generate_results.png "Web_Test_Coded_Generate_Results")

## <a name="qa"></a>SORU- CEVAP

### <a name="q-can-i-run-more-than-one-test-at-a-time"></a>S: aynı anda birden fazla test çalıştırabilir miyim?
 **Y:** Evet, Çözüm Gezgini'nde bağlam menüsünü kullanın.

### <a name="q-should-i-add-a-data-source-before-or-after-i-generate-a-coded-test"></a>S: bir veri kaynağı çalıştırmadan önce veya sonra kodlanmış test üretme eklemek?
 **Y:** daha kolay bir [veri kaynağı](../test/add-a-data-source-to-a-web-performance-test.md), kodu otomatik olarak sizin için oluşturulur çünkü Kodlanmış testi oluşturmadan önce.

 Veri kaynağı ile kodlanmış bir testi çalıştırdığınızda, aşağıdaki hata iletisini görebilirsiniz:

 **Test çalıştıramadı \<Test adı > aracısında \<bilgisayar adı >: nesne başvurusu bir nesnenin örneğine ayarlanmadı.**

 Karşılık gelen DataBindingAttribute olmadan test sınıfı için tanımlanmış bir DataSourceAttribute olduğundan bu durum oluşabilir. Bu hatayı gidermek için uygun bir DataBindingAttribute eklemek, silmek veya kodun dışına açıklama.

### <a name="q-should-i-add-validation-and-extraction-rules-before-or-after-i-generate-a-coded-test"></a>S: doğrulama ve ayıklama kuralları çalıştırmadan önce veya sonra kodlanmış test üretme eklemeniz gerekir?
 **Y:** Kodlanmış testi oluşturmadan önce doğrulama kuralları ve ayıklama kuralları için daha kolay olur; ancak, kullanmanızı öneririz [kodlanmış UI testleri](../test/use-ui-automation-to-test-your-code.md) doğrulama amacıyla.