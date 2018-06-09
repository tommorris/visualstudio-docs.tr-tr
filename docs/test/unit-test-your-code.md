---
title: Birim testi Visual Studio'da
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, unit tests
- unit tests, verifying code with
- testing code, automated tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 487c5b4c730a4b49188857c2681aae6ff87a61e5
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/08/2018
ms.locfileid: "35237337"
---
# <a name="unit-test-your-code"></a>Birim testi kodunuz

Birim testleri geliştiriciler ve sınayıcılar mantık hataları C#, Visual Basic ve C++ projelerine sınıfların yöntemler aramak için hızlı bir yol sağlar.

Birim testi araçları şunları içerir:

* **Test Gezgini**&mdash;birim testleri çalıştırma ve bunların sonuçları görmek **Test Gezgini**. İçin bir bağdaştırıcı olan üçüncü taraf framework dahil olmak üzere tüm birim testi çerçevesi kullanabilirsiniz **Test Gezgini**.

* **Yönetilen kod için Microsoft birim test çerçevesi**&mdash;yönetilen kod için Microsoft birim test çerçevesi ile Visual Studio yüklü olduğundan ve .NET kodu test etmek için bir çerçeve sağlar.

* **C++ için Microsoft birim test çerçevesi**&mdash;C++ için Microsoft birim test çerçevesi parçası olarak yüklü **C++ ile masaüstü geliştirme** iş yükü. Yerel kod test etmek için bir çerçeve sağlar. Google Test, Boost.Test ve CTest çerçeveleri de dahil edilir ve üçüncü taraf bağdaştırıcıları için ek sınama çerçeveleri kullanılabilir. Daha fazla bilgi için bkz: [C/C++ için birim testleri yazma](../test/writing-unit-tests-for-c-cpp.md).

* **Kod kapsamı Araçları**&mdash;ürün kodu, Birim Test Gezgini'nde bir komutundan alıştırma testleri miktarını belirleyebilir.

* **Microsoft Fakes yalıtım framework**&mdash;sınıfları ve bağımlılıkları test altındaki kod oluşturma yöntemleri için üretim ve sistem kodu yerine Microsoft Fakes yalıtım framework oluşturabilirsiniz. Bir işlev için sahte temsilciler uygulayarak, bağımlılık nesnesinin davranışını ve çıkışını denetlersiniz.

Aynı zamanda [Intellitest](../test/generate-unit-tests-for-your-code-with-intellitest.md) test verileri ve birim testleri dizisi oluşturmak için .NET kodunuzu keşfetmek için. Koddaki her deyim için bir test giriş oluşturulan bu deyim yürütülecek. Servis talebi çözümleme kodda koşullu her dal için gerçekleştirilir.

## <a name="key-tasks"></a>Ana görevler

Birim testlerini anlamaya ve oluşturmaya yardımcı olmaları için aşağıdaki konuları kullanın:

|Görevler|İlişkili Konular|
|-----------|-----------------------|
|**Hızlı başlar ve izlenecek yollar:** birim Visual Studio'da kod örneklerinden testi öğrenmek için aşağıdaki konuları kullanın.|-   [Yönetilen kod için birim testleri izlenecek yol: Oluşturma ve çalıştırma](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)<br />-   [Hızlı Başlangıç: Test Gezgini teste dayalı geliştirme](../test/quick-start-test-driven-development-with-test-explorer.md)<br />-   [Mevcut C++ uygulamalarına birim testleri ekleme](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)|
|**Test Gezgini ile birim testi:** Test Gezgini daha üretken ve verimli birim testleri oluşturma nasıl yardımcı olabileceğini öğrenin.|-   [Birim testi temelleri](../test/unit-test-basics.md)<br />-   [Birim testi projesi oluşturma](../test/create-a-unit-test-project.md)<br />-   [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)<br />-   [Üçüncü şahıs birim test çerçevelerini yükleme](../test/install-third-party-unit-test-frameworks.md)|
|**Birim testi yönetilen kodu:**|-   [Yönetilen kod için Microsoft Birim Test Çerçevesi ile .NET Framework için birim testleri yazma](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)|
|**Birim testi C++ kodu**|-   [C++ için Microsoft birim testi çerçevesi ile C/C++ için birim testleri yazma](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)|
|**Yalıtmak birim testleri**|-   [Microsoft Fakes ile Test edilen kodu yalıtma](../test/isolating-code-under-test-with-microsoft-fakes.md)|
|**Projenizin kodunun ne oranda test belirlemek için kod kapsamı kullanın:** Visual Studio Test Araçları'nın kod kapsamı özelliği hakkında bilgi edinin.|-   [Test edildiğini belirlemek ne kadar kodun için kod kapsamını kullanma](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)|
|**Yük testleri kullanarak stres ve Performans Analizi gerçekleştirebilir:** bir yük testi oluşturma ve yalıtmak performans ve stres uygulamanızdaki sorunları gidermek için birim testleri ekleyin.|-   [Test (VSTS ve TFS) yükleme](/vsts/load-test/)|
|**Kalite kapıları ayarlayın:** kalite kapıları kodu iade önce testleri çalıştırmak zorlamak için kod kalitesini sağlamaya yardımcı olmak için oluşturabilirsiniz.|-   [İade ilkeleri (VSTS)](/vsts/tfvc/add-check-policies)|
|**Testi seçenekleri ayarlayın:** Örneğin, test sonuçları nerede depolanacağını belirtebilirsiniz.|[.runsettings dosyasını kullanarak birim testlerini yapılandırma](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)|

## <a name="api-reference-documentation"></a>API başvuru belgeleri

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting> öznitelikler, özel durumlar, onaylar ve diğer Bu destek birim testi sınıfları sağlar UnitTesting ad açıklar.
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Web> UnitTesting.Web ad alanı, ASP.NET ve Web hizmeti ünite testleri için destek sağlayan UnitTesting ad alanı genişletir açıklar.

## <a name="see-also"></a>Ayrıca bkz.

- [Kod kalitesini geliştirme](../test/improve-code-quality.md)
