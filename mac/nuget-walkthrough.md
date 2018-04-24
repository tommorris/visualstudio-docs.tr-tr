---
title: İzlenecek yol - NuGet paketini projenize dahil
description: Bu belge, bir Xamarin projesinde bir NuGet paketi ekleme kapsar. Bulma ve bir paket indirilirken, yanı sıra aracılığıyla IDE tümleştirme özelliklerine giriş anlatılmaktadır.
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 5C800815-0B13-4B27-B017-95FCEF1A0EA2
ms.openlocfilehash: 05762df8b06a69647c6c7a628db54ac499248374
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="including-a-nuget-package-in-your-project"></a>NuGet paketini projenize dahil

NuGet .NET geliştirme için en popüler Paket Yöneticisi ise ve Mac ve Windows Visual Studio için Visual Studio için yerleşik. Arama ve IDE ya da kullanarak Xamarin.iOS ve Xamarin.Android projelerinize paketleri ekleyin.

Bu belgede bir projede bir NuGet paketi ekleme bakar ve sorunsuz bir hale getirir ve aracı zincir gösterir.

## <a name="nuget-in-visual-studio-for-mac"></a>Mac için Visual Studio'da NuGet

NuGet paket işlevselliğini göstermek için biz öncelikle yeni bir uygulama oluşturma ve bir paket eklemeyi yol. Sonra şu paketleri yönetmeye yardımcı IDE özellikleri ele alacağız.

## <a name="create-a-new-project"></a>Yeni bir proje oluşturma

İlk olarak, adlandırılmış bir proje oluşturun `HelloNuget` aşağıda gösterildiği gibi. Bu örnek iOS tek görünüm uygulaması şablonu gösterir, ancak herhangi bir desteklenen proje türü çalışır:

![Yeni iOS projesi oluşturma](media/nuget-walkthrough-NewProject.png)

<a name="Adding_a_Package" class="injected"></a>

## <a name="adding-a-package"></a>Bir paketi ekleme

Proje Mac için Visual Studio'da Aç sağ tıklayın **paketleri** klasöründe **çözüm paneli** seçip **paketleri Ekle...** :

![Yeni NuGet paketi bağlam eylemi Ekle](media/nuget-walkthrough-PackagesMenu.png)

Bu başlatır _paketleri Ekle..._  penceresi. Kaynak açılan listeyi ayarlandığından emin olun `nuget.org`:

![Kaynak listesi açılır](media/nuget-walkthrough-Source.png)

Bu yükler paketlerin listesini varsayılandan penceresi açılır paketi kaynak: nuget.org. İlk sonuçlar şöyle görünür:

![Liste NuGet paketleri](media/nuget-walkthrough-AddPackages1.png)

Belirli bir paket örneğin bulmak için arama kutusunu sağ üst köşedeki kullanın `azure`. Kullanmak istediğiniz bir paket buldunuz, seçin ve **Paketi Ekle** yüklemeyi başlatmak için düğmesi.


[Azure NuGet paketi ekleme](media/nuget-walkthrough-AddPackages2.png)

Paketi İndirildikten sonra projenize eklenir. Çözüm aşağıdaki gibi değişir:

*   **Başvuruları** düğümü NuGet paketinin parçası olan tüm derlemelerin bir listesini içerir.
*   **Paketleri** düğümü yüklediğiniz her NuGet paketi görüntüler. Güncelleştirmek veya bir paket bu listeden kaldırın.
*   A **packages.config** dosyası projeye eklenir. Bu XML dosyası tarafından IDE izlemek için hangi paketi sürümleri bu projede başvurulan kullanılır. Bu dosyayı el ile düzenleyebilirsiniz olmamalıdır, ancak sürüm denetimindeki tutmanız gerekir. Project.json dosyası yerine packages.config dosyasında kullanılabileceğini unutmayın. Geçişli geri yükleme destekleyen NuGet 3 ile sunulan yeni bir paket dosyası biçimi project.json dosyasıdır. Project.json hakkında daha ayrıntılı bilgi bulunabilir [NuGet belgelerine](http://docs.microsoft.com/NuGet/Schema/Project-Json). Project.json dosyasına el ile eklenmesi gerekir ve projeyi kapalı ve Mac için project.json dosyasına Visual Studio'da kullanılmadan önce yeniden açıldı

## <a name="using-nuget-packages"></a>NuGet paketlerini kullanma

Tüm proje başvurusuyla gibi NuGet paketi eklendi ve proje başvuruları güncelleştirilen sonra API'leri karşı programlama yapabilirsiniz.

Gerekli eklemeyi `using` yönergelerini dosyanızın en üstüne:


    using Newtownsoft.json;

Çoğu NuGet Nuget kaynağı Benioku ya da proje sayfa bağlantısı gibi ek bilgileri sağlayın. Bu bağlantı normalde paket blurb paketleri Ekle sayfasında bulabilirsiniz:

[Görünümü proje sayfası bağlantısı](media/nuget-walkthrough-project-page.png)

<a name="Package_Updates" class="injected"></a>

## <a name="package-updates"></a>Paket güncelleştirmesi

Paket güncelleştirmesi yapılabilir ya da tümü aynı anda üzerinde sağ tıklayarak **paketleri** düğümünde veya tek tek her bileşen.

Sağ **paketleri** bağlam menüsüne erişmek için:

![Paketleri menüsü](media/nuget-walkthrough-PackagesMenu.png)

*   **Paket ekleme** -daha fazla paket projeye eklemek için penceresi açılır.
*   **Güncelleştirme** - her paket için kaynak sunucuyu kontrol eder ve daha yeni sürümlerini yükler.
*   **Geri yükleme** -(var olan paketler daha yeni sürümleri için güncelleştirme olmadan) tüm eksik paketleri yükler.

Güncelleştirme ve geri yükleme seçenekleri çözüm düzeyinde de mevcuttur ve Çözümdeki tüm projeleri etkiler. 

Ayrıca, bir bağlam menüsü erişmek için tek paketler sağ:

![Paketleri menüsü](media/nuget-walkthrough-PackageMenu.png)

*   **Sürüm numarası** -sürüm numarasını devre dışı menü öğesi - yalnızca bilgilendirme amacıyla sağlanmıştır.
*   **Güncelleştirme** - kaynak sunucu denetler ve (varsa) daha yeni sürümü indirir.
*   **Kaldırma** - paketi bu projeden kaldırır ve ilgili derlemeleri proje başvuruları kaldırır.


## <a name="adding-package-sources"></a>Paket kaynaklarını ekleme

Yükleme için kullanılabilir paket başlangıçta nuget.org alınır. Ancak, diğer paket konumları için Visual Studio Mac için ekleyebilirsiniz. Bu, kendi NuGet paketlerini geliştirilme veya özel bir NuGet sunucusu şirketiniz veya kuruluşunuz içinde kullanmak için test etmek için yararlı olabilir.

Mac için Visual Studio'da gidin **Visual Studio > tercihleri... > NuGet > kaynakları** paket kaynaklarının listesini görüntülemek ve düzenlemek için. Kaynakları (bir URL tarafından belirtilen) bir uzak sunucu ya da yerel bir dizine olabileceğini unutmayın. 

![Paket kaynaklarını](media/nuget-walkthrough-PackageSource.png)

Tıklatın **Ekle** Kurulum yeni bir kaynak için. Paket kaynağı için bir kolay ad ve URL (veya dosya yolu) girin. Kaynak güvenli web sunucusu ise, kullanıcı adını ve parolasını de, aksi takdirde bu girişler boş bırakın:

![Paket kaynaklarını ekleyin](media/nuget-walkthrough-PackageSource2.png)

Farklı kaynaklar paketler için arama yaparken seçilebilir:

![Paket kaynaklarını ekleyin](media/nuget-walkthrough-PackageSource3.png)

## <a name="version-control"></a>Sürüm Denetimi

NuGet belgelerine anlatılmaktadır [NuGet paketleri kaynak denetimine kaydetmeden kullanarak](https://docs.microsoft.com/nuget/consume-packages/packages-and-source-control). İkili dosyaları ve kullanılmayan bilgi kaynak denetiminde depolamamayı tercih ederseniz, Visual Studio paketlerini sunucudan otomatik olarak geri yüklemek Mac için yapılandırabilirsiniz. Bu bir geliştirici, projenin kaynak denetiminden ilk kez aldığında, Mac için Visual Studio otomatik olarak karşıdan yükle ve gerekli paketleri yüklemek anlamına gelir.

![Otomatik olarak paketler geri yükle](media/nuget-walkthrough-AutoRestore.png)

Dışlama hakkında ayrıntılar için belirli kaynak denetimi belgelerinize başvurun `packages` izlenmekte olan gelen dizin.

