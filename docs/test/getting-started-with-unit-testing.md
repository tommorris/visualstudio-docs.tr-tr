---
title: "Birim testi ile çalışmaya başlama - test planları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unit testing, create unit test plans
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 9ed998150223010ccc7517852a6da20ec04fc6bc
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="get-started-with-unit-testing"></a>Birim testi ile çalışmaya başlama

Visual Studio kod sistem durumu bakımını, kod kapsamı emin olun ve müşterilerinizin önce hataları ve hataları bulmak için birim testleri çalıştırma ve tanımlamak için kullanın.

## <a name="create-unit-tests"></a>Birim testleri oluşturma

Birim testleri oluşturma ve bunları sık kodunuzu düzgün çalıştığından emin olmak için çalıştırın.

1. Birim testi projesi oluşturun.

   ![Birim testi projesi çözümünüze ekleyin](media/createunittest1.png)

1. Projenizin adı.

   ![Birim testi proje şablonu](media/createunittest2.png)

   Proje çözümünüze eklenir.

   ![Çözüm Gezgini'nde birim testi projesi](media/createunittest5.png)

1. Birim testi projesi test etmek istediğiniz projesine bir başvuru ekleyin.

   ![Birim testi projesi için bir başvuru ekleyin](media/createunittest6.png)

1. Test edeceksiniz kodunu projeyi seçin.

   ![Başvuru eklemek için seçin](media/createunittest7.png)

1. Birim testi kodu.

   ![Kod, birim testine ekleme](media/createunittest8.png)

Birim testi ile yöntemi saplamalar oluşturabilirsiniz **birim testleri oluşturma** [komutu](create-unit-tests-menu.md).

![Create birim testleri komutu kullanma](media/createunittestcommand2.png)

## <a name="run-unit-tests"></a>Birim testleri çalıştırma

1. Test Explorer'ı açın.

   ![Test menüsünde Test Gezgini](media/rununittest1.png)

1. Birim testleri çalıştırın.

   ![Test Gezgini birim testleri çalıştırma](media/rununittest2.png)

   Birim geçen veya Test Explorer'da Başarısız testleri görebilirsiniz.

   ![Test Gezgini birim testi sonuçlarını gözden geçirin](media/rununittest3.png)

## <a name="view-live-unit-test-results"></a>Dinamik birim test sonuçlarını görüntüleme

Mstest'i, xUnit veya NUnit test çerçevesi Visual Studio 2017 veya üzeri kullanıyorsanız, birim testleri Canlı sonuçlarını görebilirsiniz.

1. Dinamik birim gelen testi Aç **Test** menüsü.

   ![Üzerinde dinamik birim testi Aç](media/live-test-results-start.png)

1. Yazma ve kod düzenleme kod düzenleyici penceresini içinde test sonuçlarını görüntüleyin.

   ![Test sonuçlarını görüntülemek](media/live-test-results-ui.png)

1. Test sonucu göstergeleri daha fazla bilgi için seçin.

   ![Test sonucu göstergeleri seçin](media/live-test-results-details.png)

Daha fazla ayrıntı için bkz: [Canlı birim testi](../test/live-unit-testing-intro.md).

## <a name="generate-unit-tests-with-intellitest"></a>Intellitest ile birim testleri oluşturma

Intellitest çalıştırdığınızda, hangi testlerin başarısız oluyor ve bunları düzeltmek için tüm gerekli kodu eklemek kolayca görebilirsiniz. Hangi regresyon suite sağlamak amacıyla bir test projesi kaydetmek için oluşturulan testleri seçebilirsiniz. Kodunuzu değiştirmek gibi oluşturulan testleri kod değişikliklerinizin ile senkronize tutmaya Intellitest yeniden çalıştırın. Bilgi edinmek için bkz [Intellitest ile kodunuz için birim testleri oluşturma](../test/generate-unit-tests-for-your-code-with-intellitest.md).

![Intellitest ile oluşturma birim testleri](media/intellitest.png)

## <a name="run-unit-tests-with-test-explorer"></a>Test Gezgini ile birim testleri çalıştırma

Visual Studio ya da üçüncü taraf birim testi projelerini birim testleri çalıştırma, testleri kategoriler halinde gruplandırabilirsiniz, test listesini filtrelemek ve oluşturmak, kaydetme ve çalma testleri çalıştırmak için test Gezgini'ni kullanın. Ayrıca testleri hata ayıklama ve test performans ve kod kapsamını çözümleme. Bilgi edinmek için bkz [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md).

![Test Gezgini ile birim testleri](media/testexplorer.png)

## <a name="use-code-coverage-to-determine-how-much-code-is-being-tested"></a>Ne kadar kodun test edildiğini belirlemek için kod kapsamı kullanın

Proje kodunuzun ne oranda aslında birim testleri gibi kodlanmış testler tarafından test edilen belirlemek için Visual Studio kod kapsamı özelliğini kullanabilirsiniz. Etkin hatalara karşı koruma sağlamak için testleriniz çalışmalı veya kodunuzun büyük bir kısmını 'kapsamalıdır'. Bilgi edinmek için bkz [belirlemek ne kadar kodun için kullanım kod kapsamını test](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md).

![Ne kadar kodun test edildiğini belirlemek için kod kapsamını kullanma](media/codecoverage.png)

## <a name="use-a-different-unit-test-framework"></a>Farklı bir birim testi çerçevesi kullanın

Visual Studio'da artırma, Google ve nUnit gibi üçüncü taraf test çerçevelerini kullanarak, birim testleri çalıştırabilirsiniz. Bu Visual Studio'nun test Çalıştırıcısı'nda bu framework ile çalışabilmek için eklenti çerçevesi için kullanın.

Üçüncü bölümü test çerçevelerini etkinleştirmeye yönelik adımlar şunlardır:

1. Seçin **Araçları** > **Uzantılar ve güncelleştirmeler...**  menü çubuğundan.

1. İçinde **Uzantılar ve güncelleştirmeler** iletişim kutusunda, genişletin **çevrimiçi** kategori ve ardından **Visual Studio Market'te**. Ardından, **Araçları** > **test**.

   ![Visual Studio Market](media/extensions-and-updates-testing.png)

1. Framework veya yükleyin ve ardından istediğiniz bağdaştırıcıyı seçin **karşıdan**.

1. Bir sınıf kitaplığı projesi oluşturun ve çözümünüze ekleyin.

   ![Sınıf kitaplığı proje adı ve bunu ekleyin](media/create3rdpartyunittest3.png)

1. Eklentisini yükleyin. İçinde **Çözüm Gezgini**, sınıf kitaplığı proje seçin ve ardından **NuGet paketlerini Yönet...**  sağ tıklatın veya bağlam menüsünde.

   ![Eklentisini yüklemek için NuGet paketlerini Yönet](media/create3rdpartyunittest3a.png)

   [NuGet](https://www.nuget.org/) eklemek ve kitaplıkları ve projelerinizi araçlarını güncelleştirmek için kullanabileceğiniz Visual Studio uzantısıdır.

1. İçinde **NuGet Paket Yöneticisi** penceresinde aramak ve eklenti seçin ve ardından **yükleme**.

   ![3. taraf Framework'ü yükleme](media/create3rdpartyunittest4.png)

   Framework projenizde başvuruluyor.

   ![3. taraf birim test çerçevesi için başvuru çözümünüze eklenir](media/create3rdpartyunittest6.png)

1. Sınıf kitaplığı proje gelen **başvuruları** düğümü, select **Başvuru Ekle...** .

   ![Projesine bir başvuru ekleyin](media/createunittest6.png)

1. İçinde **başvuru Yöneticisi** iletişim kutusunda, test kodu içeren projesini seçin.

   ![Test etmeniz için kodunu projeyi seçin](media/createunittest7.png)

1. Birim testi kodu.

   ![Kod, birim testine ekleme](media/create3rdpartyunittest7.png)

## <a name="see-also"></a>Ayrıca bkz.

* [Birim Testleri Oluştur komutu](create-unit-tests-menu.md)
* [Intellitest ile testleri oluşturma](generate-unit-tests-for-your-code-with-intellitest.md)
* [Test Gezgini ile testleri çalıştırma](run-unit-tests-with-test-explorer.md)
* [Kod kapsamı belirleme](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [Kod Kalitesini Geliştirme](improve-code-quality.md)
