---
redirect_url: /visualstudio/test/how-to-use-microsoft-test-framework-for-cpp
ms.openlocfilehash: 7ab917a55d9a2d00a8d4635e2de45cd43cbe02f2
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="how-to-use-the-microsoft-unit-testing-framework-for-c"></a>C++ için Microsoft birim testi çerçevesi kullanma
Varolan bir uygulamayı değiştirmeden önce birim testleri ile iyi bir kapsama sahip olduğundan emin olun, öneririz. Bu değişiklikleri hatalar sunulmuştur değil, güven verir. Birim testleri uygulama zaten sahip değilse, bu konu başlığı altında gösterilen tekniklerle ekleyebilirsiniz. Bu konu, kod ve ardından oluşturma, test etme karar ile başlayarak, var olan Visual C++ kod için birim testleri ekleme işlemi açıklanmaktadır yazma ve son olarak, testleri çalıştırma.  
  
## <a name="deciding-how-to-test-your-code"></a>Kodunuzu test etmek nasıl karar verme  
 Mevcut C++ projesi açın ve birim testleri eklemek istediğiniz nasıl karar vermek için inceleyin. Koddaki bağımlılıkları görmek ve yardımcı Yardım bölümleri nasıl etkileşim anlamak bazı modelleme araçları kullanmak isteyebilirsiniz. Daha fazla bilgi için bkz: [kodu görselleştirme](../modeling/visualize-code.md).  
  
 Değişikliklerinizi küçük görevleri içine ayrı öneririz. Her önce küçük değiştirmek, aynı kalacaksa davranışının yönlerini için birim testleri yazma. Bu testler, değişikliği yaptıktan sonra geçirmeye devam eder. Örneğin, bir sıralama işlevi değiştirin, böylece bu kişilerin listesini yerine son ada göre ilk adına göre sıralar planlıyorsanız, tüm giriş adları çıkışında görünür doğrulayan birim testi yazabilirsiniz. Değişikliği yaptıktan sonra yeni davranışı için yeni birim testleri eklemek isteyebilirsiniz.  
  
 Pratik ise, dışa aktarılan işlevlerinin çoğunu veya tümünü birim testleri kullanmanız gerekir. Ancak daha sonra tüm uygulama yalnızca küçük bir bölümünü değiştiriyorsanız aktarılmaz işlevleri kullanmak isteyebilirsiniz. Örneğin, iç işlevleri çağırma testleri veya ayarlama ve iç değişkenlerin değerlerini alma testleri isteyebilirsiniz.  
  
 Test etmek istediğiniz arabirimleri kullanıma sunar, bağlı olarak, ürün kodunu test etmek için birkaç yolu vardır. Aşağıdaki yöntemlerden birini seçin:  
  
 **Birim testleri test altındaki kodundan dışarı işlevlerini çağırabilirsiniz:**  
 Ayrı bir test projeye ekleyin. Test projesinde test altındaki projesine bir başvuru ekleyin.  
  
 Yordam gidin [dışarı aktarılan işlevler test projesinden başvurmak için](#projectRef).  
  
 **Test altındaki kodun bir .exe dosyası olarak oluşturulur:**  
 Ayrı bir test projeye ekleyin. Çıktı nesne dosyasına bağlayın.  
  
 Yordam gidin [testleri için nesne veya kitaplık dosyalarını bağlamak için](#objectRef).  
  
 **Birim testleri özel işlevler ve veri kullanmanız gerekir ve test altındaki kodun bir statik kitaplık oluşturulabilir:**  
 Projeyi test altındaki .lib dosyasına derlenmiş şekilde değiştirin. Test altındaki projeye başvuruda bulunan bir ayrı test projesi ekleyin.  
  
 Bu yaklaşım testlerinizi özel üyeleri kullanır ancak ayrı bir projede testleri saklamak izin verme avantajına sahiptir. Ancak, bunu dinamik bağlantı kitaplığı (.dll) sahip olduğu gerekir bazı uygulamalar için uygun olmayabilir.  
  
 Yordam gidin [test altındaki kodun bir statik kitaplık değiştirmek için](#staticLink).  
  
 **Birim testleri özel üye işlevleri ve veri kullanmanız gerekir ve kod dinamik bağlantı kitaplığı (DLL) oluşturulmalıdır:**  
 Ürün kodu aynı projede birim testleri ekleme.  
  
 Yordam gidin [birim testleri aynı projede eklemek için](#sameProject).  
  
## <a name="creating-the-tests"></a>Testleri oluşturma  
  
###  <a name="staticLink"></a>Kodu test altındaki bir statik kitaplık değiştirmek için  
  
-   Testleri test altındaki bir proje verilmez üyeleri kullanmanız gerekir ve projeyi test altındaki dinamik kitaplık olarak oluşturulmuştur, bir statik kitaplık dönüştürme göz önünde bulundurun.  
  
    1.  Çözüm Gezgini'nde, test projesinin kısayol menüsünden seçin **özellikleri**. Proje Özellikleri penceresi açılır.  
  
    2.  Seçin **yapılandırma özellikleri**, **genel**.  
  
    3.  Ayarlama **yapılandırma türü** için **statik kitaplık (.lib)**.  
  
 Yordamla devam edin [testleri için nesne veya kitaplık dosyalarını bağlamak için](#objectRef).  
  
###  <a name="projectRef"></a>Dışa aktarılan DLL işlevleri test projesinden başvurmak için  
  
-   Ardından bir test altında test etmek istediğiniz işlevleri aktaran DLL projesiyse, test projesinin kod projesine bir başvuru ekleyebilirsiniz.  
  
    1.  C++ test projesi oluşturun.  
  
        1.  Üzerinde **dosya** menüsünde seçin **yeni**, **proje**, **Visual C++, Test**, **C++ birim testi projesi**.  
  
    2.  Çözüm Gezgini'nde, oluşturduğunuz test projesinin kısayol menüsünden seçin **başvurular**. Proje Özellikleri penceresi açılır.  
  
    3.  Seçin **ortak özellikleri**, **Framework ve başvuruları**ve ardından **Yeni Başvuru Ekle** düğmesi.  
  
    4.  Seçin **projeleri**ve ardından sınanacak projesi.  
  
         Seçin **Ekle** düğmesi.  
  
    5.  Test projesi için Özellikler'de test projesinin konumunu içeren dizinler ekleyin.  
  
         Seçin **yapılandırma özellikleri**, **VC ++ dizinleri**, **içeren dizinler**.  
  
         Seçin **Düzenle**ve ardından test altındaki projenin üstbilgi dizini ekleyin.  
  
 Git [birim testleri yazma](#addTests).  
  
###  <a name="objectRef"></a>Nesne veya kitaplık dosyalarını testleri bağlamak için  
  
-   Kodu test altında test etmek istediğiniz işlevlerini dışarı aktarma değil, çıktı ekleyebilirsiniz **.obj** veya **.lib** test projesinin bağımlılıkları dosyasına.  
  
    1.  C++ test projesi oluşturun.  
  
        1.  Üzerinde **dosya** menüsünde seçin **yeni**, **proje**, **Visual C++, Test**, **C++ birim testi projesi**.  
  
    2.  Çözüm Gezgini'nde, oluşturduğunuz test projesinin kısayol menüsünden seçin **özellikleri**. Proje Özellikleri penceresi açılır.  
  
    3.  Seçin **yapılandırma özellikleri**, **bağlayıcı**, **giriş**, **ek bağımlılıklar**.  
  
         Seçin **Düzenle**ve adlarını ekleyin **.obj** veya **.lib** dosyaları. Tam yol adları kullanmayın.  
  
    4.  Seçin **yapılandırma özellikleri**, **bağlayıcı**, **genel**, **ek kitaplık dizinleri**.  
  
         Seçin **Düzenle**ve dizin yolu Ekle **.obj** veya **.lib** dosyaları. Genellikle test projesinin yapı klasördeki yoludur.  
  
    5.  Seçin **yapılandırma özellikleri**, **VC ++ dizinleri**, **içeren dizinler**.  
  
         Seçin **Düzenle**ve ardından test altındaki projenin üstbilgi dizini ekleyin.  
  
 Git [birim testleri yazma](#addTests).  
  
###  <a name="sameProject"></a>Birim testleri aynı projede eklemek için  
  
1.  Üstbilgiler ve birim testi için gerekli olan kitaplık dosyaları dahil olmak üzere ürün kodu proje özelliklerini değiştirin.  
  
    1.  Çözüm Gezgini'nde, test projesinin kısayol menüsünden Özellikler'i seçin. Proje Özellikleri penceresi açılır.  
  
    2.  Seçin **yapılandırma özellikleri**, **VC ++ dizinleri**.  
  
    3.  Dahil et ve kitaplık dizinleri düzenleyin:  
  
        |||  
        |-|-|  
        |**Yönergeleri dahil etme**|**$(VCInstallDir)UnitTest\include;$(IncludePath)**|  
        |**Kitaplık dizinleri**|**$(VCInstallDir)UnitTest\lib;$(LibraryPath)**|  
  
2.  C++ birim testi dosyasına ekleyin:  
  
    -   Çözüm Gezgini'nde proje kısayol menüsünde seçin **Ekle**, **yeni öğe**ve ardından **C++ birim testi**.  
  
 Git [birim testleri yazma](#addTests).  
  
##  <a name="addTests"></a>Birim testleri yazma  
  
1.  Her birim testi kod dosyasında ekleyin bir `#include` test projesinin üstbilgilerinin deyimi.  
  
2.  Test sınıflar ve yöntemler için birim testi kod dosyaları ekleyin. Örneğin:  
  
    ```cpp  
    #include "stdafx.h"  
    #include "CppUnitTest.h"  
    #include "MyProjectUnderTest.h"  
    using namespace Microsoft::VisualStudio::CppUnitTestFramework;  
    namespace MyTest  
    {  
      TEST_CLASS(MyTests)  
      {  
      public:  
          TEST_METHOD(MyTestMethod)  
          {  
              Assert::AreEqual(MyProject::Multiply(2,3), 6);  
          }  
      };  
    }  
    ```  
  
 Daha fazla bilgi için bkz: [yerel kod Test Gezgini ile birim testi](http://msdn.microsoft.com/en-us/8a09d6d8-3613-49d8-9ffe-11375ac4736c).  
  
## <a name="run-the-tests"></a>Testleri çalıştırma  
  
1.  Üzerinde **Test** menüsünde seçin **Windows**, **Test Gezgini**.  
2. Tüm testleri penceresinde görünür değilse, kendi düğümünde sağ tıklayarak test projesi derleme **Çözüm Gezgini** ve seçme **yapı** veya **yeniden**.
  
2.  Test Gezgini seçin **tümünü Çalıştır**, veya çalıştırmak istediğiniz belirli testleri seçin. Bir test ile kesme noktaları etkin hata ayıklama modunda çalışan dahil olmak üzere diğer seçenekler için sağ tıklayın.
  
## <a name="see-also"></a>Ayrıca Bkz.
[Hızlı Başlangıç: Test Gezgini ile güdümlü geliştirme test etme](../test/quick-start-test-driven-development-with-test-explorer.md)

