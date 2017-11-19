---
title: "Birim testi ile çalışmaya başlama - test planları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: unit testing, create unit test plans
ms.assetid: 2171CD69-FBB1-4994-9DCC-3BFFDFD26662
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.openlocfilehash: 17113215615ff87ef0af611a5bc2061ca0126911
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="get-started-with-unit-testing"></a>Birim testi ile çalışmaya başlama

Visual Studio kod sistem durumu bakımını, kod kapsamı emin olun ve müşterilerinizin önce hataları ve hataları bulmak için birim testleri çalıştırma ve tanımlamak için kullanın.

<a name="create-tests"></a>
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

Birim testi ile yöntemi saplamalar oluşturabilirsiniz [ **birim testleri oluşturma** komutu](create-unit-tests-menu.md).
Veya, kullanabileceğiniz bir [farklı birim test çerçevesi](#frameworks) farklı kod dilleri için testler oluşturmak için.

![Create birim testleri komutu kullanma](media/createunittestcommand2.png)

## <a name="run-unit-tests"></a>Birim testleri çalıştırma

1. Test Explorer'ı açın.
        
   ![Test menüsünde Test Gezgini](media/rununittest1.png) 

1. Birim testleri çalıştırın.
        
   ![Test Gezgini birim testleri çalıştırma](media/rununittest2.png) 

   Birim geçen veya Test Explorer'da Başarısız testleri görebilirsiniz.
      
   ![Test Gezgini birim testi sonuçlarını gözden geçirin](media/rununittest3.png) 

## <a name="view-live-unit-test-results"></a>Dinamik birim test sonuçlarını görüntüleme

Mstest'i, xUnit ya da Visual Studio 2017 veya üzerini framework sınama NUnit kullanıyorsanız, Visual Studio kullanıcı Arabirimi içinden birim testleri Canlı sonuçlarını görebilirsiniz.

1. Dinamik birim gelen testi Aç **Test** menüsü.

   ![Üzerinde dinamik birim testi Aç](media/live-test-results-start.png) 

1. Yazma ve kod düzenleme kod düzenleyici penceresini içinde test sonuçlarını görüntüleyin.

   ![Üzerine gelin ve test sonucu göstergeleri](media/live-test-results-ui.png) 

1. Üzerine gelin ve daha fazla bilgi için test sonucu göstergelerini'ı tıklatın.

   ![Test sonuçlarını görüntülemek](media/live-test-results-details.png) 

Daha fazla ayrıntı için bkz: [Canlı birim testi Visual Studio'da](https://blogs.msdn.microsoft.com/visualstudio/2016/11/18/live-unit-testing-visual-studio-2017-rc/).

<a name="intellitest"></a>
## <a name="generate-unit-tests-with-intellitest"></a>Intellitest ile birim testleri oluşturma

Intellitest çalıştırdığınızda, hangi testlerin başarısız oluyor ve bunları düzeltmek için tüm gerekli kodu eklemek kolayca görebilirsiniz. Hangi regresyon suite sağlamak amacıyla bir test projesi kaydetmek için oluşturulan testleri seçebilirsiniz. Kodunuzu değiştirmek gibi oluşturulan testleri kod değişikliklerinizin ile senkronize tutmaya Intellitest yeniden çalıştırın. Bilgi edinmek için bkz [Intellitest ile kodunuz için birim testleri oluşturma](https://docs.microsoft.com/visualstudio/test/generate-unit-tests-for-your-code-with-intellitest).

![Intellitest ile oluşturma birim testleri](media/intellitest.png)

<a name="unit-tests"></a>
## <a name="run-unit-tests-with-test-explorer"></a>Test Gezgini ile birim testleri çalıştırma

Visual Studio ya da üçüncü taraf birim testi projelerini birim testleri çalıştırma, testleri kategoriler halinde gruplandırabilirsiniz, test listesini filtrelemek ve oluşturmak, kaydetme ve çalma testleri çalıştırmak için test Gezgini'ni kullanın. Ayrıca testleri hata ayıklama ve test performans ve kod kapsamını çözümleme. Bilgi edinmek için bkz [Test Gezgini ile birim testleri çalıştırma](https://docs.microsoft.com/visualstudio/test/run-unit-tests-with-test-explorer).

![Test Gezgini ile birim testleri](media/testexplorer.png)

<a name="code-coverage"></a>
## <a name="use-code-coverage-to-determine-how-much-code-is-being-tested"></a>Ne kadar kodun test edildiğini belirlemek için kod kapsamı kullanın

Proje kodunuzun ne oranda aslında birim testleri gibi kodlanmış testler tarafından test edilen belirlemek için Visual Studio kod kapsamı özelliğini kullanabilirsiniz. Etkin hatalara karşı koruma sağlamak için testleriniz çalışmalı veya kodunuzun büyük bir kısmını 'kapsamalıdır'. Bilgi edinmek için bkz [belirlemek ne kadar kodun için kullanım kod kapsamını test](https://docs.microsoft.com/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested).

![Ne kadar kodun test edildiğini belirlemek için kod kapsamını kullanma](media/codecoverage.png)

## <a name="q--a"></a>Soru - Yanıt

<!-- BEGINSECTION class="m-qanda" -->

<a name="frameworks"></a>
####S: farklı bir birim kullanırsanız, birim testleri Visual Studio'da test çerçevesi çalıştırabilirim?

A: Bu Visual Studio'nun test Çalıştırıcısı'nda bu framework ile çalışabilmek için Evet eklenti o çerçevesi için kullanın. Bazıları aşağıda verilmiştir [birim framework eklentiler için Visual Studio testi](http://go.microsoft.com/fwlink/?LinkID=246630).

1. Eklentinizin indirmek için Visual Studio'nun Uzantı Yöneticisi'ni kullanın.
        
   ![Uzantı Yöneticisi ile 3. taraf birim testi eklentileri seçin](media/install3rdpartyunittestframeworks1.png) 

1. Visual Studio Galerisi Araçlar/test altında eklentinizin indirin veya adını biliyorsanız için arama yapın.
        
   ![Eklentinizin indirin](media/install3rdpartyunittestframeworks2.png) 

1. Bir sınıf kitaplığı projesi oluşturun.
        
   ![Sınıf kitaplığı proje oluşturma](media/create3rdpartyunittest1.png) 

   Proje çözümünüze ekleyin.
    
   ![Sınıf kitaplığı proje adı ve bunu ekleyin](media/create3rdpartyunittest3.png) 

1. Sınıf kitaplığı projesinde eklentisini yüklemek için NuGet çalıştırın.

   ![Eklentisini yüklemek için NuGet paketlerini Yönet](media/create3rdpartyunittest3a.png) 

   [NuGet](https://www.nuget.org/) eklemek ve kitaplıkları ve projelerinizi araçlarını güncelleştirmek için kullanabileceğiniz Visual Studio uzantısıdır.

1. Eklentinizin yükleyin. Adını biliyorsanız, bunun için çevrimiçi arama yapabilirsiniz.

   ![3. taraf Framework'ü yükleme](media/create3rdpartyunittest4.png) 

   Framework projenizde başvuruluyor.
        
   ![3. taraf birim test çerçevesi için başvuru çözümünüze eklenir](media/create3rdpartyunittest6.png) 

1. Sınıf kitaplığı projesinde test etmek istediğiniz projesine bir başvuru ekleyin.
        
   ![Projesine bir başvuru ekleyin](media/createunittest6.png) 

1. Test edeceksiniz kodunu projeyi seçin.
        
   ![Test etmeniz için kodunu projeyi seçin](media/createunittest7.png) 

1. Birim testi kodu.

   ![Kod, birim testine ekleme](media/create3rdpartyunittest7.png)   

<!-- ENDSECTION -->

## <a name="see-also"></a>Ayrıca bkz.

* [Birim testleri komut oluşturma](create-unit-tests-menu.md)
* [Intellitest ile testleri oluşturma](generate-unit-tests-for-your-code-with-intellitest.md)
* [Test Gezgini ile testleri çalıştırma](run-unit-tests-with-test-explorer.md)
* [Kod kapsamı belirleme](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [Kod kalitesini geliştirme](improve-code-quality.md)
