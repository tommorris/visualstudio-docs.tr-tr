---
title: Geliştirici Visual Studio Test Araçları
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 89d09a8b01dc4179f3b9de4cbdbf1905846f7002
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691865"
---
# <a name="developer-testing-tools-scenarios-and-capabilities"></a>Geliştirici Araçları, senaryolarını ve özelliklerini test etme

Kod sistem birim testi korur. Çok çeşitli güçlü araçları ve teknikleri uygulamaları test ederken kullanılacak geliştiriciler için Visual Studio sağlar:

## <a name="avoid-regressions-and-achieve-code-coverage-with-intellitest"></a>Gerileme önlemek ve kod kapsamı Intellitest ile elde

Geleneksel birim test paketlerini, her test çalışması bir örnek kullanım senaryosu temsil eder ve onaylar giriş ve çıkış arasındaki ilişkiyi gerçekleştirir.  Birkaç tür senaryoların yanı sıra doğrulama yeterli olabilir, ancak deneyimli geliştiriciler bilmeniz bile iyi test edilen kodu, doğru olduğunda hataları ne zaman ortaya ancak sınanmamış girişleri yanlış yanıtları yol açabilirsiniz.

Kapsamı geliştirmek ve Intellitest ile gerileme kaçının. Intellitest oluşturmak ve yeni veya var olan kod için birim testleri korumak için çaba önemli ölçüde azaltır.

![Eylem Intellitest](media/devtest-intellitest.png)

* [Visual Studio ile Intellitest giriş](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Introduction%20to%20IntelliTest%20with%20Visual%20Studio%20Enterprise%202015.docx)
* [Intellitest – tümünü kural için bir sınama](http://blogs.msdn.com/b/visualstudioalm/archive/2015/07/05/intellitest-one-test-to-rule-them-all.aspx)
* [Intellitest videolar](https://channel9.msdn.com/Series/Test-Tools-in-Visual-Studio)
* [Intellitest ile çalışmaya başlama](generate-unit-tests-for-your-code-with-intellitest.md)
* [Intellitest başvuru kılavuzu](intellitest-manual/index.md)

## <a name="user-interface-testing-with-coded-ui-and-selenium"></a>Kodlanmış UI ve Selenium ile test kullanıcı arabirimi

Kullanıcı Arabirimi (UI) türünün en iyi ile test veya topluluk UI testi onaylandı.
Kodlanmış UI testleri işlevsellik ve uygulamanızın kullanıcı arabirimi davranışını doğrulamak için tam olarak otomatikleştirilmiş test oluşturmak için bir yol sağlar.
Bunlar, çeşitli teknolojiler XAML tabanlı UWP uygulamaları, tarayıcı uygulamalar ve SharePoint uygulamalar dahil olmak üzere, arasında UI testi otomatik hale getirebilirsiniz.

Kodlanmış UI testleri türünün en iyi seçin veya Selenium ile UI testi genel tarayıcı tabanlı olup, Visual Studio ihtiyacınız olan araçları sağlar.

![Kullanıcı Arabirimi ile kodlanmış UI testi](media/devtest-codeduitest.png)

* [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](use-ui-automation-to-test-your-code.md)
* [Oluşturma, düzenleme ve kodlanmış UI testini sürdürme kullanmaya başlama](walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)
* [Kodlanmış UI testleriyle UWP uygulamaları sınama](test-uwp-app-with-coded-ui-test.md)
* [Kodlanmış UI testleriyle SharePoint uygulamaları sınama](testing-sharepoint-2010-applications-with-coded-ui-tests.md)
* [Visual Studio Enterprise (Lab) kodlanmış UI testleriyle giriş](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Introduction%20to%20Coded%20UI%20Tests%20with%20Visual%20Studio%20Enterprise%202015.docx)

## <a name="effective-unit-testing-with-visual-studio-code-coverage"></a>Etkin birim testi ile Visual Studio kod kapsamı

Projenizin kodunun ne oranda gerçekte birim testleri gibi kodlanmış testleri tarafından test edildiğini belirlemek için Visual Studio'nun kod kapsamı özelliğini kullanabilirsiniz. Etkili bir şekilde hatalar karşı koruma sağlamak için testlerinizi alıştırma veya 'kodunuzu büyük bir kısmının kapak'.

Yönetilen ve yönetilmeyen (yerel) kod için kod kapsamı çözümlemeyi uygulanabilir.

Test yöntemlerini Test Gezgini'ni kullanarak çalıştırdığınızda kod kapsamı bir seçenektir. Sonuçlar tablosu, her derleme sınıfı ve yöntemi içinde çalışan kod yüzdesini gösterir. Ayrıca, kaynak düzenleyici hangi kodun test edildiğini gösterir.

![Team Foundation Server ve Visual Studio Team Services ile test](media/devtest-codecoverage.png)

* [Ne Kadar Kodun Test Edildiğini Belirlemek için Kod Kapsamını Kullanma](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [Birim testi, kod kapsamı ve Visual Studio (Lab) ile kod kopya çözümleme](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Unit%20Testing,%20Code%20Coverage%20and%20Code%20Clone%20Analysis%20with%20Visual%20Studio%202015.docx)
* [Kod Kapsamı Çözümlemeyi Özelleştirme](customizing-code-coverage-analysis.md)

## <a name="unit-testing-with-any-framework-using-the-high-performance-test-explorer"></a>Birim testi herhangi framework yüksek performansı Test Gezgini kullanma

Geliştiriciler oluşturmak, yönetmek ve en fazla birim testi elde Explorer Yardımı sınayın.

![Visual Studio Test Gezgini](media/devtest-testexplorer.png)

* [Birim testi ile çalışmaya başlama](unit-test-your-code.md)
* [Test Gezgini ile birim testleri çalıştırma](run-unit-tests-with-test-explorer.md)
* [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)
* [Üçüncü taraf birim testi çerçevelerini yükleme](install-third-party-unit-test-frameworks.md)

Visual Studio ayrıca genişletilebilirdir ve üçüncü taraf birim testi NUnit ve xUnit.net gibi bağdaştırıcıları kapısının açar. Ayrıca, kodu kopya yetenek el eldeki gider ortak hata düzeltmeleri için aday olabilen anlamsal olarak benzer bir kod bloklarını tanımlamanıza yardımcı ya da yeniden düzenleme yüksek kaliteli yazılım teslim ile.

![Üçüncü taraf test tümleştirme](media/devtest-thirdparty.png)

## <a name="see-also"></a>Ayrıca bkz.

* [Birim testi ile çalışmaya başlama](getting-started-with-unit-testing.md)
* [Team Foundation Server'da Birim Test yürütmesi hızlandırma](http://blogs.msdn.com/b/visualstudioalm/archive/2015/07/30/speeding-up-test-execution-in-tfs.aspx)
* [Paralel ve bağlama duyarlı Birim Test yürütmesi](https://blogs.msdn.microsoft.com/visualstudioalm/2016/02/08/parallel-and-context-sensitive-test-execution-with-visual-studio-2015-update-1/)
* [Birim testi, kod kapsamı ve Visual Studio (Lab) ile kod kopya çözümleme](http://download.microsoft.com/download/6/2/B/62B60ECE-B9DC-4E8A-A97C-EA261BFB935E/Docs/Unit%20Testing,%20Code%20Coverage%20and%20Code%20Clone%20Analysis%20with%20Visual%20Studio%202015.docx)
