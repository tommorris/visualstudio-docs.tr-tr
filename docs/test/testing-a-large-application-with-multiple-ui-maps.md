---
title: Birden çok kullanıcı Arabirimi ile büyük bir uygulama eşlemeleri Visual Studio Testi | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, multiple UI maps
- coded UI tests, for large applications
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 640de34044f539dddd43579f672af1b98dfdd715
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="testing-a-large-application-with-multiple-ui-maps"></a>Birden Çok UI Eşlemesi Bulunan Büyük Uygulamaları Sınama

Bu konuda, birden çok UI eşlemesi kullanarak büyük bir uygulamayı test ederken kodlanmış UI testleri kullanma açıklanmaktadır.

 **Gereksinimler**

-   Visual Studio Enterprise

 Visual Studio test çerçevesi kod test için yeni bir kodlanmış UI testi oluşturduğunuzda, varsayılan olarak oluşturur. bir <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfı. Kodlanmış UI testlerini nasıl kaydedileceği hakkında daha fazla bilgi için bkz: [kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md) ve [kodlanmış UI testinin anatomisi](../test/anatomy-of-a-coded-ui-test.md).

 UI eşlemesi için oluşturulan kod testin etkileşimde her nesne için bir sınıf içerir. Oluşturulan her yöntemi için Yöntem parametreleri için bir yardımcı sınıf özellikle bu yöntem için oluşturulur. Çok sayıda nesneleri, sayfalar ve formlar ve denetimler, uygulamanızda varsa, UI eşlemesi çok fazla büyüyebilir. Ayrıca, birkaç kişiye testleri üzerinde çalışıyorsanız, uygulama, tek bir büyük UI eşleme dosyası ile yönetilmeleri haline gelir.

 Birden çok UI haritası dosyalarını kullanarak aşağıdaki faydaları sağlayabilir:

-   Her eşleme mantıksal bir alt uygulama ile ilişkili olabilir. Bu değişiklikleri yönetmeyi kolaylaştırır.

-   Her tester uygulamanın bir bölüm çalışma ve diğer uygulama bölümleri üzerinde çalışan diğer sınayıcılar müdahale olmaksızın kendi kodunda denetleyin.

-   Uygulama kullanıcı Arabirimi eklemeler, artımlı olarak UI diğer bölümleri için en az düzeyde etkisi testleri ile genişletilebilir.

## <a name="do-you-need-multiple-ui-maps"></a>Birden çok UI eşlemesi gerekiyor mu?
 Birden çok UI eşlemesi her durumlarda bu tür oluşturun:

-   Birlikte bir Web sitesinde bir kayıt sayfası veya satın alma sayfası alışveriş sepeti gibi mantıksal bir işlemi gerçekleştirme bileşik UI denetimlerinin birkaç karmaşık ayarlar.

-   Uygulama birkaç sayfa işlem sihirbazla gibi çeşitli noktalarından erişilen denetimlerinin bağımsız ayarlayın. Sihirbazın her sayfasını özellikle karmaşık ise, her bir sayfa için ayrı UI haritaları oluşturabilirsiniz.

## <a name="adding-multiple-ui-maps"></a>Birden çok UI eşlemesi ekleme

#### <a name="to-add-a-ui-map-to-your-coded-ui-test-project"></a>Kodlanmış UI test projenize UI eşlemesi eklemek için

1.  İçinde **Çözüm Gezgini**, tüm UI eşlemesi depolamak için kodlanmış UI test projesi dosyasını sağ tıklatın, işaret kodlanmış UI test projenizdeki bir klasör oluşturmak için **Ekle** ve ardından **yeni klasör**. Örneğin, adlandırabilirsiniz `UIMaps`.

     Yeni klasör kodlanmış UI test projesi altında görüntülenir.

2.  Sağ `UIMaps` klasörünü **Ekle**ve ardından **yeni öğe**.

     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.

    > [!NOTE]
    > Yeni bir kodlanmış UI test eşlemesi eklemek için kodlanmış UI test projede olmalıdır.

3.  Seçin **kodlanmış UI Test eşlemesi** listeden.

     İçinde **adı** kutusuna, yeni UI eşlemesi için bir ad girin. Bileşen veya harita, örneğin, temsil edecek sayfa adını kullanmak `HomePageMap`.

4.  Seçin **eklemek**.

     Visual Studio penceresinin en aza indirir ve **kodlanmış UI Test derleyicisini** iletişim kutusu görüntülenir.

5.  İlk yöntem için eylemleri kaydedin ve seçin **kodu oluştur**.

6.  Kaydedilen tüm eylemler ve ilk bileşen veya sayfa için onaylar ve yöntemler halinde gruplandırdıktan sonra kapatın **kodlanmış UI Test derleyicisini** iletişim kutusu.

7.  UI eşlemesi oluşturmaya devam edin. Eylemleri ve onaylamaları kaydedin, her bileşen için yöntemlerde gruplandırın ve kod oluşturma.

 Çoğu durumda, tüm sihirbazlar, formlar ve sayfalar için uygulamanızın en üst düzey penceresi sabit kalır. Her UI eşlemesi üst düzey penceresi için bir sınıf olsa da, tüm eşlemeler büyük olasılıkla çalıştırmak, uygulamanızın hangi tüm bileşenleri aynı üst düzey pencereye başvuruyordur. En üst düzey penceresinden başlangıç kodlanmış UI testleri için arama denetimleri hiyerarşik olarak yukarıdan aşağıya doğru karmaşık bir uygulamada gerçek üst düzey pencere her UI eşlemesi yinelenen şekilde. Gerçek üst düzey pencere yineleniyorsa Bu pencere değiştiğinde birden fazla değişiklik neden olur. UI eşlemesi arasında geçiş yaptığınızda bu performans sorunlarına neden olabilir.

 Bu etkiyi en aza indirmek için kullanabileceğiniz `CopyFrom()` yöntemi UI eşlenen yeni üst düzey penceresinde ana üst düzey penceresi ile aynı olduğundan emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, her bileşen ve çeşitli UI haritaları'nda oluşturulan sınıflar tarafından temsil edilen kendi alt denetimleri için erişim sağlayan bir yardımcı sınıfı bir parçasıdır.

Bu örnekte, bir Web uygulaması adlı `Contoso` bir giriş sayfası, bir ürün sayfası ve bir alışveriş sepeti sayfası vardır. Bu sayfaların her biri bir tarayıcı penceresi olan ortak bir üst düzey penceresini paylaşır. Her bir sayfa için bir kullanıcı Arabirimi eşleme yoktur ve yardımcı program sınıfı aşağıdakine benzer bir kod içerir:

```csharp
using ContosoProject.UIMaps;
using ContosoProject.UIMaps.HomePageClasses;
using ContosoProject.UIMaps.ProductPageClasses;
using ContosoProject.UIMaps.ShoppingCartClasses;

namespace ContosoProject
{
    public class TestRunUtility
    {
        // Private fields for the properties
        private HomePage homePage = null;
        private ProductPage productPage = null;
        private ShoppingCart shoppingCart = null;

        public TestRunUtility()
        {
            homePage = new HomePage();
        }

        // Properties that get each UI Map
        public HomePage HomePage
        {
            get { return homePage; }
            set { homePage = value; }
        }

        // Gets the ProductPage from the ProductPageMap.
        public ProductPage ProductPageObject
        {
            get
            {
                if (productPage == null)
                {
                    // Instantiate a new page from the UI Map classes
                    productPage = new ProductPage();

                    // Since the Product Page and Home Page both use
                    // the same browser page as the top level window,
                    // get the top level window properties from the
                    // Home Page.
                    productPage.UIContosoFinalizeWindow.CopyFrom(
                        HomePage.UIContosoWindowsIWindow);
                }
                return productPage;
            }
        }

    // Continue to create properties for each page, getting the
    // page object from the corresponding UI Map and copying the
    // top level window properties from the Home Page.
}
```

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>
- <xref:Microsoft.VisualStudio.TestTools.UITesting.BrowserWindow.CopyFrom%2A>
- [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md)
- [Kodlanmış UI Testinin Anatomisi](../test/anatomy-of-a-coded-ui-test.md)
