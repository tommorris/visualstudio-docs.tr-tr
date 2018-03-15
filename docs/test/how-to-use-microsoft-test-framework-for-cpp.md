---
title: "Microsoft Visual Studio'da C++ Framework sınama birim kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
author: mikeblome
ms.openlocfilehash: 00a20dbcabc8e1e0a6f72ec54badc5645a5c1cbb
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="use-the-microsoft-unit-testing-framework-for-c-in-visual-studio"></a>Microsoft Visual Studio'da C++ Framework sınama birim kullanın

C++ için Microsoft birim testi çerçevesi varsayılan olarak dahil **C++ ile masaüstü geliştirme** iş yükü.

##  <a name="separate_project"></a> Ayrı bir proje ile birim testleri yazma
Genellikle, test kodunuzu test etmek istediğiniz kod olarak aynı çözüme kendi projesinde çalıştırın. Kurmak ve yeni bir test projesi yapılandırmak için bkz: [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md).

##  <a name="same_project"></a> Aynı projede birim testleri yazma
İşlevleri dışarı olmayan bir DLL'de sınarken örneğin bazı durumlarda, test ettiğiniz program aynı projede testler oluşturmak gerekebilir. Birim testleri aynı projede yazmak için:

1.  Üstbilgiler ve birim testi için gerekli olan kitaplık dosyalarını eklemek için proje özelliklerini değiştirin.

    1.  Çözüm Gezgini'nde, test ve ardından program için proje düğümüne sağ tıklayın **özellikleri | Yapılandırma özellikleri | VC ++ dizinleri**.

    3.  Aşağıdaki satırları aşağı oka tıklayın ve seçin  **<Edit>**  :

        |||
        |-|-|
        |**Yönergeleri dahil etme**|**$(VCInstallDir)UnitTest\include;$(IncludePath)**|
        |**Kitaplık dizinleri**|**$(VCInstallDir)UnitTest\lib;$(LibraryPath)**|

2.  C++ birim testi dosyasına ekleyin:

    -   ' Nde proje düğümüne sağ tıklayın **Çözüm Gezgini** ve **Ekle | Yeni öğe | C++ birim testi**.

## <a name="write-the-tests"></a>Testleri yazma
Test sınıfları .cpp dosya "CppUnitTest.h" içerir ve bir kullanarak bildirimi `using namespace Microsoft::VisualStudio::CppUnitTestFramework`. Test projesi için zaten yapılandırıldı. Ayrıca bir ad alanı tanımını içerir ve TEST_CLASS sağlamak için bir TEST_METHOD ile başlatıldı. Parantez içinde sınıf ve yöntemi makroları adları yanı sıra ad alanı adını değiştirebilirsiniz.

Testleri tamamlandığında özel makroları resoures temizlenmesi ve test modülleri, sınıflar ve yöntemler başlatma için tanımlanır. Bu makroları bir sınıf veya yöntemin ilk erişmeden önce ve son test çalışması bittikten sonra yürütülen kod oluşturur. Daha fazla bilgi için bkz: [başlatma ve Temizleme](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#Initialize_and_cleanup).

Statik yöntemleri kullanın [Assert](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#general_asserts) test koşullarını tanımlamak için sınıf. Kullanım [Günlükçü](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md#logger) iletileri yazmak için sınıf **çıktı penceresi**. Test yöntemleri öznitelikleri ekleme

## <a name="run-the-tests"></a>Testleri çalıştırma

1.  Üzerinde **Test** menüsünde seçin **Windows**, **Test Gezgini**.
2. Tüm testleri penceresinde görünür değilse, kendi düğümünde sağ tıklayarak test projesi derleme **Çözüm Gezgini** ve seçme **yapı** veya **yeniden**.

2.  Test Gezgini seçin **tümünü Çalıştır**, veya çalıştırmak istediğiniz belirli testleri seçin. Bir test ile kesme noktaları etkin hata ayıklama modunda çalışan dahil olmak üzere diğer seçenekler için sağ tıklayın.
3. İçinde **çıktı penceresi** seçin **testleri** tarafından yazılan iletileri görüntüleme aşağı açılan `Logger` sınıfı:

  ![C++ çıktı penceresi sınama iletilerini gösteren](media/cpp-test-output-window.png "çıktı penceresi")

## <a name="define-traits-to-enable-grouping"></a>Gruplandırma etkinleştirmek için özellikleri tanımlayın
Kategorilere ayırmak ve testlerinde Grup sağlayan test yöntemlerinde nitelikler tanımlayabilirsiniz **Test Gezgini**. Bir ayırdedici nitelik tanımlamak için `TEST_METHOD_ATTRIBUTE` makrosu. Örneğin, bir ayırdedici nitelik tanımlamak için adlandırılmış `TEST_MY_TRAIT`:

```cpp
#define TEST_MY_TRAIT(traitValue) TEST_METHOD_ATTRIBUTE(L"MyTrait", traitValue)
```

 Birim testlerinde tanımlı ayırdedici nitelik kullanmak için:

```
BEGIN_TEST_METHOD_ATTRIBUTE(Method1)
    TEST_OWNER(L"OwnerName")
    TEST_PRIORITY(1)
    TEST_MY_TRAIT(L"thisTraitValue")
END_TEST_METHOD_ATTRIBUTE()

TEST_METHOD(Method1)
{
    Logger::WriteMessage("In Method1");
    Assert::AreEqual(0, 0);
}
```

### <a name="c-trait-attribute-macros"></a>C++ ayırdedici nitelik özniteliği makroları
  Aşağıdaki önceden tanımlanmış nitelikler bulunan `CppUnitTest.h`. Daha fazla bilgi için bkz: [Microsoft birim testi çerçevesi C++ API Başvurusu için](microsoft-visualstudio-testtools-cppunittestframework-api-reference.md).

|Makrosu|Açıklama|
|-----------|-----------------|
|`TEST_METHOD_ATTRIBUTE(attributeName, attributeValue)`|TEST_METHOD_ATTRIBUTE makrosu bir ayırdedici nitelik tanımlamak için kullanın.|
|`TEST_OWNER(ownerAlias)`|Test yöntemi sahibini belirlemek için önceden tanımlanmış sahibi ayırdedici nitelik kullanın.|
|`TEST_PRIORITY(priority)`|Önceden tanımlanmış öncelik ayırdedici nitelik göreli önceliklerini test yöntemlerinizi atamak için kullanın.|


## <a name="see-also"></a>Ayrıca bkz.
[Hızlı Başlangıç: Test Gezgini ile Test Güdümlü Geliştirme](../test/quick-start-test-driven-development-with-test-explorer.md)

