---
title: Dağıtım genel bakış - Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: overview
dev_langs:
- FSharp
- VB
- CSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7346de998052ba68dfadf74a09fe0d4339be1614
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757168"
---
# <a name="overview-of-deployment-in-visual-studio"></a>Visual Studio'da dağıtımına genel bakış

Bir uygulamayı, hizmeti ya da bileşeni dağıtarak bunu diğer bilgisayarlardaki, cihazlardaki, sunuculardaki ya da buluttaki yükleme için dağıtmış olursunuz. İhtiyacınız olan dağıtım türü için uygun yöntemi Visual Studio'da seçebilirsiniz.

Birçok ortak uygulama türleri için Visual Studio'daki Çözüm Gezgini'nden uygulama hak dağıtabilirsiniz. Bu özellik hızlı turuna için bkz: [ilk dağıtım sırasında bakış](../deployment/deploying-applications-services-and-components.md).

![Yayımlama bir seçenek belirleyin](../deployment/media/quickstart-publish-azure.png)

## <a name="what-publishing-options-are-right-for-me"></a>Benim için en uygun Yayımlama seçenekleri nelerdir?

Gelen Visual Studio içinde uygulamaları doğrudan aşağıdaki hedefleri yayımlanabilir:

- [Azure uygulama hizmeti](#azure-app-service)
- [Azure sanal makineler](#azure-virtual-machines)
- [Dosya sistemi](#file-system)
- [Özel hedefleri (IIS, FTP, vb.) ](#custom-targets), tüm rasgele web sunucuları içerir.

Üzerinde **Yayımla** sekmesi, varolan bir yayımlama profili seçin, mevcut bir alma veya açıklanan seçenekler burada kullanarak yeni bir tane oluşturun. Yayımlama seçeneklerini farklı uygulama türleri için IDE içinde gezinmek için bkz: [ilk dağıtım sırasında bakış](../deployment/deploying-applications-services-and-components.md).

## <a name="azure-app-service"></a>Azure uygulama hizmeti

[Azure uygulama hizmeti](/azure/app-service/app-service-web-overview) altyapı korumadan çeşitli ölçeklenebilir web uygulamaları ve Hizmetleri hızlı bir şekilde oluşturmak geliştiriciler yardımcı olur.

Ne kadar güç bir uygulama hizmeti computing seçerek sahip belirleyin bir [katmanı veya plan fiyatlandırması](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview) içeren uygulama hizmeti için. Birden çok Web sahip uygulamaları (ve diğer uygulama türleri) paylaşmak aynı App Service fiyatlandırma katmanı değiştirmeden. Örneğin, geliştirme, hazırlama ve üretim Web uygulamalarında birlikte aynı uygulama hizmeti barındırabilir.

Bulutta barındırılan sanal makineleri Azure üzerinde bir uygulama hizmeti çalışır, ancak bu sanal makineleri sizin için yönetilir. Bir uygulama hizmeti her uygulamada benzersiz bir atanacak \*. azurewebsites.net URL; sitesine özel etki alanı adları atama izin tüm fiyatlandırma katmanlarına serbest dışında.

### <a name="when-to-choose-azure-app-service"></a>Ne zaman Azure uygulama hizmeti seçin

- Internet üzerinden erişilebilen bir web uygulaması dağıtmak istediğiniz.
- Otomatik olarak yeniden dağıtmak gerek kalmadan, web uygulamanızın isteğe göre ölçeklendirmek istiyorsunuz.
- Sunucu altyapı (yazılım güncelleştirmeleri de dahil olmak üzere) korumak istemiyorsanız.
- Makine düzeyi özelleştirmeler, web uygulamanızı barındıran sunuculara gerek yoktur.

> Azure uygulama hizmeti, kendi veri merkezi veya diğer şirket içi bilgisayarları kullanmak istiyorsanız, bunu kullanarak yapabilirsiniz [Azure yığın](https://azure.microsoft.com/overview/azure-stack/).

Uygulama hizmeti yayımlama hakkında daha fazla bilgi için bkz: [hızlı başlangıç - Azure App Service'te yayımlama](quickstart-deploy-to-azure.md).

## <a name="azure-virtual-machines"></a>Azure sanal makineler

[Azure sanal makineleri (VM'ler)](https://azure.microsoft.com/documentation/services/virtual-machines/) oluşturma ve herhangi bir sayıda bulut bilgi işlem kaynakları yönetmenize olanak tanır. Tüm yazılım ve güncelleştirmeler VM'ler sorumluluğu üstlenerek, bunları uygulamanızın gerektirdiği gibi istenen kadar özelleştirebilirsiniz. Sanal makineler doğrudan Uzak Masaüstü aracılığıyla erişebilir ve her biri atanan IP adresini istenen sürece barındırır.

Sanal makineler üzerinde barındırılan bir uygulamayı ölçeklendirme isteğe göre ek Vm'leri yedekleme dönen ve gerekli yazılımı dağıtma içerir. Bu ek düzeyi denetim sağlar, genel farklı bölgelerde farklı şekilde ölçeklendirilir. Örneğin, uygulamanızın bölgesel ofislere çeşitli çalışanlar çalışıyorsa, bu bölgeler olası maliyetlerini azaltma çalışanların sayısını göre Vm'leriniz ölçeklendirebilirsiniz.

Ek bilgi için bkz [ayrıntılı karşılaştırması](https://azure.microsoft.com/documentation/articles/choose-web-site-cloud-service-vm/) Azure App Service, Azure sanal makineleri ve Visual Studio'da özel seçeneğini kullanarak bir dağıtım hedefi olarak kullanabileceğiniz diğer Azure hizmetleri arasında.

### <a name="when-to-choose-azure-app-virtual-machines"></a>Ne zaman Azure App sanal makineleri seçin

- Atanmış IP adresleri ömrü üzerinde tam denetim Internet üzerinden erişilebilen bir web uygulaması dağıtmak istediğiniz.
- Sunucularınız üzerinde ağ yapılandırmaları, disk bölümleri ve benzeri belirli özel veritabanı sistemi gibi ek yazılım içeren makine düzeyi özelleştirmeleri gerekir.
- Web uygulamanızın ölçekleme üzerinde denetim ince düzeyini istiyor.
- Uygulamanız herhangi bir nedenden dolayı barındıran sunucular için doğrudan erişmeniz gerekir.

> Azure sanal makineler kendi veri Merkezinize veya diğer şirket içi bilgisayarları kullanmak istiyorsanız, bunu kullanarak yapabilirsiniz [Azure yığın](https://azure.microsoft.com/overview/azure-stack/).

## <a name="file-system"></a>Dosya sistemi

Yalnızca belirli bir klasöre kendi bilgisayarınızda uygulamanızın dosyaları kopyalamak, dosya sistemine dağıtma anlamına gelir. Bu çoğunlukla test amacıyla ya da bilgisayar bir sunucu da çalıştırıyorsa, kişiler, sınırlı sayıda tarafından kullanılmak üzere uygulamayı dağıtmak için kullanılır. Hedef klasör bir ağda paylaşılıyorsa, dosya sistemine dağıtma web uygulama dosyaları sonra belirli sunuculara dağıtabilirsiniz başkalarına sunabilirsiniz.

Çalıştıran bir sunucu herhangi bir yerel makine uygulamanızı Internet veya Intranet nasıl yapılandırıldığına bağlı olarak ve bağlı olduğu ağlara aracılığıyla kullanılabilir hale getirebilirsiniz. (Doğrudan Internet'e bir bilgisayara bağlarsanız, dış güvenlik tehditlerine karşı korumak özellikle dikkatli olun.) Bu makineleri yönetmek için yazılım ve donanım yapılandırmaları tam denetiminde demektir.

Herhangi bir nedenle (örneğin, makine erişimi), Azure App Service ya da Azure sanal makineleri gibi bulut hizmetlerine kullanmanız mümkün değilse, kullanabileceğiniz Not [Azure yığın](https://azure.microsoft.com/overview/azure-stack/) , kendi veri merkezinizdeki. Azure yığın yönetmek ve şirket içi henüz her şeyi tutarken Azure App Service ve Azure sanal makineler bilgi işlem kaynaklarına kullanmanıza olanak sağlar.

### <a name="when-to-choose-file-system-deployment"></a>Ne zaman dosya sistemi dağıtımı seçin

- Yalnızca, diğerleri onu farklı sunuculara dağıtacağınız bir dosya paylaşımı uygulamayı dağıtmak.
- Yalnızca yerel test dağıtımını gerekir.
- İnceleyin ve potansiyel olarak uygulama dosyaları bağımsız olarak başka bir dağıtım hedef göndermeden önce değiştirmek istediğiniz.

Daha fazla bilgi için bkz: [hızlı başlangıç - yerel bir klasöre dağıtma](quickstart-deploy-to-local-folder.md)

## <a name="custom-targets-iis-ftp"></a>Özel hedefleri (IIS, FTP)

Özel bir hedef uygulamanızı Azure App Service, Azure sanal makineleri veya yerel dosya sistemi dışında bir hedef dağıtmanıza olanak tanır. Bir dosya sistemi veya diğer bulut Hizmetleri dahil olmak üzere, erişimi olan herhangi bir sunucuyu (Internet veya Intranet) dağıtabilirsiniz. Web ile çalışabilirsiniz dağıtma (dosyaları veya. ZIP) ve FTP.

Özel bir hedef seçerken, Visual Studio, bir profil adı ve ardından toplama ek isteyen **bağlantı** hedef sunucu veya konumu, bir site adı ve kimlik bilgileri gibi bilgiler. Aşağıdaki davranışları kontrol edebilirsiniz **ayarları** sekmesi:

- Dağıtmak istediğiniz yapılandırma.
- Var olan dosyaları hedef kaldırılıp kaldırılmayacağını belirtir.
- Yayımlama sırasında ön derleme yap görüntülenmeyeceğini belirtir.
- Dağıtımdan App_Data klasöründeki dosyaları dışarıda bırak görüntülenmeyeceğini belirtir.

Visual Studio'da farklı ayarlarla profillerini yönetmek olası hale getirerek, herhangi bir sayıda özel profillerde dağıtım oluşturabilirsiniz.

### <a name="when-to-choose-custom-deployment"></a>Özel dağıtım seçmek ne zaman

- Bulut Hizmetleri sağlayıcısında URL'ler erişilen Azure dışında kullanıyorsunuz.
- Visual Studio içinde kullanın ya da Azure hesaplarınızı doğrudan bağlı olanlar dışındaki kimlik bilgilerini kullanarak dağıtmak istediğiniz.
- Dağıttığınız her zaman hedef dosyaları silmek istiyor.

Daha fazla bilgi için bkz: [hızlı başlangıç - bir web sitesine dağıtma](quickstart-deploy-to-a-web-site.md)

## <a name="next-steps"></a>Sonraki adımlar

Öğreticiler:

- [Yayımla aracı ile .NET Core uygulama dağıtma](/dotnet/core/deploying/deploy-with-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Azure için ASP.NET core uygulama yayımlama](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Visual C++ üzerinde Dağıtım](/cpp/ide/deployment-in-visual-cpp)
- [UWP uygulamaları dağıtma](/windows/uwp/packaging/packaging-uwp-apps?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Web dağıtımı kullanarak Azure'da bir Node.js uygulaması yayımlama](https://github.com/Microsoft/nodejstools/wiki/Publish-to-Azure-Website-using-Web-Deploy?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [Azure App Service'e bir Python uygulama yayımlama](/visualstudio/python/publishing-python-web-applications-to-azure-from-visual-studio?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
