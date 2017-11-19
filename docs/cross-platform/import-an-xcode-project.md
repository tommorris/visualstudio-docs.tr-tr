---
title: Bir XCode projesi alma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa4b8161-d98f-4a1a-9db3-520133bfc82f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 07dc7d8eefb7ab1183d5e5532f13a5cfdac8de80
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="import-an-xcode-project"></a>Bir XCode projesi alma
Platformlar arası Mobil Geliştirme için Microsoft Visual C++ XCode projelerinizi Visual burada platformlar arası kitaplıkları oluşturmak ve diğer projelerle kod paylaşmak Studio taşınmasını için destek içerir. XCode Sihirbazından Al projeleri içeri aktarma işlemini basitleştirir ve statik kitaplık olarak kullanın veya kod projesi paylaşılan XCode hedefler için C++ kod çıkışı bölme. Visual Studio iOS özgü kodunuzda yönetebilir ve hala film şeritleri ve yapılar yapmak için XCode kullanın. Değişiklikleri XCode arasında taşımak ve Visual Studio kolayca kod geri ve İleri Visual Studio ve XCode arasında taşıma hakkında daha fazla bilgi için bkz.  
  
## <a name="using-the-import-from-xcode-wizard"></a>XCode gelen İçeri Aktarma Sihirbazı'nı kullanma  
 Bu konu bir XCode projesi kod paylaşımını ve platformlar arası çözümleri yararlanmak için Visual Studio'ya taşıma gösterir. Bir önkoşul olarak Mac alma, verme ve projenizi derleme için Visual Studio eşleştirin gerekir. Eşleştirme ayarlama hakkında daha fazla yönerge için bkz: [yükleme ve yapılandırma araçları iOS kullanılarak derleme](../cross-platform/install-and-configure-tools-to-build-using-ios.md). Ayrıca, ağ üzerinden XCode projenizi paylaşın veya taşımak XCode Sihirbazından Al kullanmak için Visual Studio bilgisayarınıza gerekir.  
  
#### <a name="import-from-xcode"></a>XCode alma  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni**, **alma**, **XCode alma**. Bu başlatır **XCode alma** Sihirbazı iletişim.  
  
     ![İçeri aktarmak için XCode hedef proje seçme](../cross-platform/media/cppmdd_u2_importxcode_choose.PNG "CPPMDD_U2_ImportXCode_Choose")  
  
2.  İçinde **bir proje seçme** bölmesinde, bir XCode .pbxproj dosyasını seçmek için Gözat düğmesini seçin. Proje dosyasında gidin **seçin XCode proje dosyası** iletişim kutusunda ve ardından **açık**.  
  
     ![Proje dosyasını Xcode seçin proje dosyası iletişim kutusunda seçin](../cross-platform/media/cppmdd_u2_importxcode_browse.PNG "CPPMDD_U2_ImportXCode_Browse")  
  
     XCode Sihirbazından Al'ı seçin **sonraki**.  
  
3.  İçinde **hedef hedefleri** bölmesinde, Visual Studio projelerine içeri XCode projeden hedefleri seçin. Visual Studio projelerine XCode hedefleri benzer; Çoğu kod ve bir ikili üretmek kaynakları koleksiyonudur. XCode Sihirbazından Al yalnızca ikili dosya, ancak statik bir kitaplık değil, hedef hedefleri olarak üretmek hedefler alma izin verir. XCode statik kitaplık hedefleri sonraki adım konusunun ' dir.  
  
     ![XCode Sihirbazı Hedef hedefleri bölmesinden alma](../cross-platform/media/cppmdd_u2_importxcode_destination.jpg "CPPMDD_U2_ImportXCode_Destination")  
  
     Seçilen her hedef için **almak için hedefleri**, sihirbaz otomatik olarak ayrı statik kitaplık projesine bölünebilir C++ kod dosyaları algılar ve bunları koyar **C++ proje öğeleri** bölümü. İçinde sol diğer kod ve kaynakları **XCode proje öğeleri** bölümü. Sihirbaz içeri aktarma işlemi tamamlandığında bu ayrı statik kitaplık ve Visual Studio'da Uygulama projeleri haline gelir. Varsayılan olarak, birim sınama ve framework hedefleri ayrı projelere sihirbaz tarafından bölünür değil.  
  
     Hangi dosyaların her projede olduğunu değiştirmek için yukarı ve aşağı düğmelerini. Her proje dosyalarında tatmin olduğunuzda seçin **sonraki** devam etmek için.  
  
4.  İçinde **kitaplığı hedefleri** bölmesinde, Visual Studio projelerine içeri XCode projeden hangi statik kitaplık hedefler seçin. Bu bölmede hangi dosyaların bir paylaşılan kod projesinde yerleştirilir ve bu bir statik kitaplık projesinde yerleştirilir seçebilirsiniz. Her birinde hedeflerinin **almak için hedefleri** listesinde denetleyebilir, dosyaları yerleştirilir **paylaşılan kod proje öğeleri** ve **statik kitaplık proje öğeleri** kullanarak Yukarı ve aşağı düğmeleri.  
  
     ![XCode kitaplığı hedefleri bölmesinden alma](../cross-platform/media/cppmdd_u2_importxcode_library.jpg "CPPMDD_U2_ImportXCode_Library")  
  
     Paylaşılan kod projesi Visual Studio'da projeler arasında kaynak kodu dosyaları kümesini paylaşımı bir yoludur. Kod, proje kendi olarak değil, içerdiği projesinin bir parçası olarak oluşturulmuştur. Paylaşılan kod dahil projeleri farklı mimari ve yapılandırmaları olabileceğinden, çok çeşitli platformlar için yerleşik kod içeren tek bir proje sağlamak için en iyi yolu budur.  
  
     Her proje dosyalarında tatmin olduğunuzda seçin **sonraki** devam etmek için.  
  
5.  **Genel özellikleri** bölmesinde framework arama yolu ve bir dahil etme üstbilgi arama yolu tüm iOS projeleri için Visual Studio'da ayarlamak için kullanılabilir. Visual Studio kaynak kod tarama ve IntelliSense için bu yolları kullanır. Üstbilgiler ve çerçeveleri ortak bir dizi kullanan iOS projeleri oluşturduğunuzda, bu genel yolları yararlı olur.  
  
     ![XCode genel özellikler bölmesinden alma](../cross-platform/media/cppmdd_u2_importxcode_global.jpg "CPPMDD_U2_ImportXCode_Global")  
  
     Bu genel yolları da Visual Studio ayarlanabilir **seçenekleri** iletişim. Bunları, üzerinde bulmak için **Araçları** menüsünde, select **seçenekleri**. İçinde **seçenekleri** iletişim kutusunda, genişletin **Çapraz Platform**, **C++**, **iOS**, **genel özellikleri**.  
  
     Seçin **sonraki** devam etmek için.  
  
6.  **Çerçeveler** bölmesinde göz atmak için Visual Studio tarafından kullanılan yolları yapılandırmak için kullanılır ve IntelliSense projeniz için. Yollar XCode projenizi tarafından başvurulan her framework için Visual Studio için erişilebilir olmalıdır. Sihirbaz framework XCode projeleri başvuruyor ve Visual Studio framework bulup bulamayacağını görüntüler denetler. Genel Özellikler ayarladığınız herhangi bir yol Visual Studio tarafından bulunması gerekir. Özel durumlar çerçeveleri listesinde listelenir. Bir X listelenen her çerçevesi için bir PC erişilebilir yol framework bulmak Visual Studio için belirtin. Gözat düğmesini [...] kullanmak için kullanabileceğiniz bir **klasörü seçin** iletişim yolu bulunamadı. Framework yol, yerel bir kopya için veya Mac üzerindeki ağ üzerinden erişilebilen bir paylaşıma olabilir  
  
     ![XCode çerçeveleri bölmesinden alma](../cross-platform/media/cppmdd_u2_importxcode_frameworks.jpg "CPPMDD_U2_ImportXCode_Frameworks")  
  
     Seçin **sonraki** devam etmek için.  
  
7.  **Proje ayarları** bölmesinde çerçevesini değiştirebilir ve Sihirbazın oluşturduğu her proje için üstbilgi arama yolu ayarları dahil olanak tanır. Genel ayarlardan farklı projeye özgü yollarını ayarlamak için bu bölmesini kullanın.  
  
     Belirli bir proje için bir yol ayarlamak için **hedef proje** açılır, proje dosyasını seçin ve ardından değerleri kümesinde **Framework arama yolu** ve **üstbilgi arama yoluiçerir** kontrol eder. Her denetim yanındaki Gözat düğmesine [...] kullanmak için kullanabileceğiniz bir **Klasör Seç** iletişim yolu bulunamadı.  
  
     ![XCode projeleri bölmesinden alma](../cross-platform/media/cppmdd_u2_importxcode_projects.jpg "CPPMDD_U2_ImportXCode_Projects")  
  
     Uzak hiçbir Mac Visual Studio'da bu PC ile eşlenmiş, yapılandırma uzak makine bağlantısı görüntülenir. Eşleştirme ayarlama hakkında daha fazla yönerge için bkz: [yükleme ve yapılandırma araçları iOS kullanılarak derleme](../cross-platform/install-and-configure-tools-to-build-using-ios.md).  
  
     XCode projesi Sihirbazı ayarları kullanarak içeri aktarmak için **alma**.  
  
 XCode Sihirbazından Al, seçili XCode projesi hedefe karşılık gelen Visual Studio projeleri oluşturur. Diğer C++ projeleri ile paylaşılan kod ayrı paylaşılan kod ve statik kitaplık projeleri olarak ayrılır. Kalan kod iOS uzaktan Visual Studio tarafından oluşturulmuş kitaplığı ve uygulama projeleri yerleştirilir. Visual Studio ve XCode arasında kod taşıma hakkında daha fazla bilgi için bkz: [arasında eşitleme değişiklikleri XCode ve Visual Studio](../cross-platform/sync-changes-between-xcode-and-visual-studio.md).