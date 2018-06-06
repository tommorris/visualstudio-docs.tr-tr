---
title: Visual Studio'da C/C++ için birim testleri yazma
ms.date: 11/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: mblome
manager: douge
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: f0315027d6b0a3b57acc7b1651f0788d0b30bba1
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752085"
---
# <a name="write-unit-tests-for-cc-in-visual-studio"></a>Visual Studio'da C/C++ için birim testleri yazma

Yazma ve kullanarak, C++ birim testleri çalıştırma **Test Gezgini** penceresinde, diğer diller için olduğu gibi. Kullanma hakkında daha fazla bilgi için **Test Gezgini**, bkz: [Test Gezgini ile birim testleri çalıştırma](run-unit-tests-with-test-explorer.md).

> [!NOTE]
> C++ için birim testi canlı, kodlanmış UI testleri ve Intellitest gibi bazı özellikler desteklenmez.

Visual Studio bu C++ test çerçevelerini hiçbir ek indirmeler gerekli içerir:

- Microsoft Framework sınama C++ için birim
- Google Test
- Boost.Test
- CTest

Yüklü çerçeveleri yanı sıra, Visual Studio içinde kullanmak istediğiniz her çerçevesi için kendi test bağdaştırıcısı yazabilirsiniz. Bir test bağdaştırıcısı ile birim testleri tümleştirebilirsiniz **Test Gezgini** penceresi. Bazı üçüncü taraf bağdaştırıcıları kullanılabilir [Visual Studio Market'te](https://marketplace.visualstudio.com). Daha fazla bilgi için bkz: [üçüncü taraf birim test çerçevelerini yükleme](install-third-party-unit-test-frameworks.md).

**Visual Studio 2017 sürüm 15.5**

- **Google Test bağdaştırıcısı** varsayılan bileşeni olarak bulunur **C++ ile masaüstü geliştirme** iş yükü. Bir çözüm ekleyebileceğiniz bir proje şablonu sahip **Yeni Proje Ekle** çözüm düğümünde bağlam menüsünde **Çözüm Gezgini**ve yoluyla yapılandırabileceğiniz seçenekleri **Araçlar | Seçenekler**. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Google Test kullanın](how-to-use-google-test-for-cpp.md).

- **Boost.Test** varsayılan bileşeni olarak bulunur **C++ ile masaüstü geliştirme** iş yükü. İle tümleşik **Test Gezgini** ancak şu anda proje şablonu sahip değilse, bu nedenle onu el ile yapılandırılması gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Boost.Test kullanın](how-to-use-boost-test-for-cpp.md).

- **CTest** desteği ile birlikte [CMake araçları Visual Studio için](/cpp/ide/cmake-tools-for-cpp) parçası olan bileşen, **C++ ile masaüstü geliştirme** iş yükü. Ancak, CTest henüz tam olarak tümleşiktir değil **Test Gezgini**. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da CTest kullanın](how-to-use-ctest-for-cpp.md).

**Visual Studio 2015 ve önceki**

Visual Studio Market'ten Boost.Test bağdaştırıcısı uzantılarını ve Google Test bağdaştırıcısı indirebilirsiniz [Boost.Test için Test bağdaştırıcısı](https://marketplace.visualstudio.com/items?itemName=VisualCPPTeam.TestAdapterforBoostTest) ve [Google testi için Test bağdaştırıcısı](https://marketplace.visualstudio.com/items?itemName=VisualCPPTeam.TestAdapterforGoogleTest).

## <a name="basic-test-workflow"></a>Temel test iş akışı

Aşağıdaki bölümlerde C++ birim testi başlamanıza yardımcı olmak için temel adımlar gösterir. Temel yapılandırması için Microsoft ve Google Test çerçeveler çok benzer. El ile testi projesi oluşturma Boost.Test gerektirir.

### <a name="create-a-test-project"></a>Bir test projesi oluşturma

Test etmek istediğiniz kod olarak aynı çözüme bulunan bir veya daha fazla test projeleri içinde testler ve tanımlayın. Varolan bir çözüme yeni bir test projesi eklemek için'nde çözüme sağ tıklayın **Çözüm Gezgini** ve **Ekle | Yeni proje**. Sol bölmede seçin **Visual C++ Test** ve merkezi bölmesinden proje türlerinden birini seçin. Ne zaman kullanılabilir test projeleri aşağıda gösterilmiştir **C++ ile masaüstü geliştirme** iş yükü yüklenir:

![C++ Test projeleri](media/cpp-new-test-project.png)

### <a name="create-references-to-other-projects-in-the-solution"></a>Bir çözümde diğer projelere başvurular oluşturun

Sınanacak proje işlevlerde erişmek test kodunuzu etkinleştirmek için test projenizde projesine bir başvuru ekleyin. ' Nde test proje düğümüne sağ tıklayın **Çözüm Gezgini** ve **Ekle | Başvuru**. Ardından iletişim kutusunda, test etmek istediğiniz proje seçin.

![Başvuru ekleme](media/cpp-add-ref-test-project.png)

### <a name="add-include-directives-for-header-files"></a>Ekleme #include yönergelerini üstbilgi dosyaları

Ardından, birim testi .cpp dosyanızda ekleyin bir `#include` test etmek istediğiniz türler ve İşlevler bildiren üstbilgi dosyaları için yönerge. Tür `#include "` ve seçmenize yardımcı olmak için IntelliSense sonra etkinleşir. Tüm ek üstbilgi için yineleyin.

![Ekleme yönergeleri içerir](media/cpp-add-includes-test-project.png)

### <a name="write-test-methods"></a>Test yöntemleri yazma

> [!NOTE]
> Bu bölümde, C/C++ için Microsoft birim testi çerçevesi için sözdizimi gösterilmektedir. Burada belgelenen: [Microsoft.VisualStudio.TestTools.CppUnitTestFramework API Başvurusu](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md). Google Test belgeler için bkz: [Google Test Primer](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md). Boost.Test için bkz: [artırma Test kitaplığı: birim testi çerçevesi](http://www.boost.org/doc/libs/1_46_0/libs/test/doc/html/utf.html).

Test projenizin .cpp dosyasında saplama sınıf ve size nasıl yazılacağını örneği olarak tanımlanan yöntemi kodu test içeriyor. İmzaları yöntemleri Test Gezgini penceresinden bulunabilir duruma TEST_CLASS ve TEST_METHOD makroları kullandığını unutmayın.

![Ekleme yönergeleri içerir](media/cpp-write-test-methods.png)

TEST_CLASS ve TEST_METHOD parçası olan [Microsoft Yerel Test Framework](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md). **Test Gezgini** desteklenen diğer çerçeveler test yöntemleri benzer şekilde bulur.

Bir TEST_METHOD void döndürür. Test sonucu oluşturmak için statik yöntemleri kullanın `Assert` test gerekenin karşı gerçek sonuçları sınıfı. Aşağıdaki örnekte, varsayalım `MyClass` alan bir oluşturucuya sahip bir `std::string`. Biz Oluşturucu beklendiği gibi sınıfı başlatır test sözlüğüdür:

```cpp
        TEST_METHOD(TestClassInit)
        {
            std::string name = "Bill";
            MyClass mc(name);
            Assert::AreEqual(name, mc.GetName());
        }
```
Önceki örnekte, sonucu `Assert::AreEqual` çağrısı testin başarılı veya başarısız olup olmadığını belirler. Assert sınıfı gerçek sonuçları beklenen karşılaştırmak için birçok yöntem içerir.

Ekleyebileceğiniz *nitelikler* yöntemleri test sahipleri, öncelik ve diğer bilgileri belirtmek için test etmek için. Ardından bu değerleri sıralamak ve testlerinde grup için kullanabileceğiniz **Test Gezgini**. Daha fazla bilgi için bkz: [Test Gezgini ile birim testleri çalıştırma](run-unit-tests-with-test-explorer.md).

### <a name="run-the-tests"></a>Testleri çalıştırma

1. Üzerinde **Test** menüsünde seçin **Windows** > **Test Gezgini**. Aşağıdaki çizimde olan testleri henüz çalıştırılmamış test projesi gösterir.

   ![Testleri çalıştırmadan önce test Gezgini](media/cpp-test-explorer.png)

   > [!NOTE]
   > İle CTest tümleştirme **Test Gezgini** henüz kullanılabilir değil. CMake ana menüden CTest testleri çalıştırın.

1. Tüm testleri penceresinde görünür değilse, kendi düğümünde sağ tıklayarak test projesi derleme **Çözüm Gezgini** ve seçme **yapı** veya **yeniden**.

1. Test Gezgini seçin **tümünü Çalıştır**, veya çalıştırmak istediğiniz belirli testleri seçin. Bir test ile kesme noktaları etkin hata ayıklama modunda çalışan dahil olmak üzere diğer seçenekler için sağ tıklayın. Tüm testler çalıştırıldıktan sonra penceresi geçirilen hangi testlerin ve hangilerinin başarısız gösterir:

![Testler çalıştıktan sonra test Gezgini](media/cpp-test-explorer-passed.png)

Başarısız testler için ileti nedeni tanılamanıza yardımcı olan ayrıntılar sunar. Başarısız test sağ tıklatın ve seçin **seçili Testlerde Hata Ayıkla** hatanın oluştuğu işlevi aracılığıyla adıma.

Kullanma hakkında daha fazla bilgi için **Test Gezgini**, bkz: [Test Gezgini ile birim testleri çalıştırma](run-unit-tests-with-test-explorer.md).

Birim testi ile ilgili en iyi yöntemler için bkz: [birim testi temelleri](unit-test-basics.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kodunuza Birim Testi Uygulama](unit-test-your-code.md)
