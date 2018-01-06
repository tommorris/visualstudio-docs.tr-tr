---
title: "Benim için en uygun Yayımlama seçenekleri nelerdir? | Microsoft Docs"
ms.custom: 
ms.date: 03/09/2017
ms.reviewer: riande
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ASP.NET, web applications, deployment, publishing
ms.assetid: 3A13F685-531C-457D-A98E-631888011E4B
caps.latest.revision: "1"
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 10cb0ca2d5190ce73f0fd67da5b1f795d5aa8dd1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# Benim için en uygun Yayımlama seçenekleri nelerdir?

Gelen Visual Studio Web uygulamaları için doğrudan aşağıdaki hedefleri yayımlanabilir:

- [Azure uygulama hizmeti](#azure-app-service)
- [Azure sanal makineler](#azure-virtual-machines)
- [Dosya sistemi](#file-system)
- [Özel hedefleri (IIS, FTP, vb.) ](#custom-targets), tüm rasgele web sunucuları içerir.

Üzerinde **Yayımla** sekmesi, varolan bir yayımlama profili seçin, mevcut bir alma veya açıklanan seçenekler burada kullanarak yeni bir tane oluşturun.

## Azure uygulama hizmeti

[Azure uygulama hizmeti](https://azure.microsoft.com/documentation/articles/app-service-value-prop-what-is/) altyapı korumadan çeşitli ölçeklenebilir web uygulamaları ve Hizmetleri hızlı bir şekilde oluşturmak geliştiriciler yardımcı olur.

Web uygulamaları için özel olarak, bir uygulama hizmeti için bir kapsayıcıdır bir [ *Web uygulaması*](https://azure.microsoft.com/en-us/documentation/articles/app-service-web-overview/), hangi yakından eşleşen ne geleneksel web ana bilgisayar olarak düşünmeniz. Diğer bir deyişle, bir Web uygulaması, sunucu tarafı kodunuzu çalıştırmak ve Internet'e kullanılabilir hale getirmek gerekli işlem kaynaklarını sağlar.

Ne kadar güç bir Web uygulaması computing seçerek sahip belirleyin bir [katmanı veya plan fiyatlandırması](https://azure.microsoft.com/documentation/articles/azure-web-sites-web-hosting-plans-in-depth-overview/) içeren uygulama hizmeti için. Birden çok sahip Web uygulamaları (ve diğer uygulama türleri) aynı App Service fiyatlandırma katmanı değiştirmeden paylaşın. Örneğin, geliştirme, hazırlama ve üretim Web uygulamalarında birlikte aynı uygulama hizmeti barındırabilir.

Bulutta barındırılan sanal makineleri Azure üzerinde bir uygulama hizmeti çalışır, ancak bu sanal makineleri sizin için yönetilir. Her bir App Service'in Web uygulamasında benzersiz bir atanacak \*. azurewebsites.net URL; sitesine özel etki alanı adları atama izin tüm fiyatlandırma katmanlarına serbest dışında.

### Ne zaman Azure uygulama hizmeti seçin

- Internet üzerinden erişilebilen bir web uygulaması dağıtmak istediğiniz.
- Otomatik olarak yeniden dağıtmak gerek kalmadan, web uygulamanızın isteğe göre ölçeklendirmek istiyorsunuz.
- Sunucu altyapı (yazılım güncelleştirmeleri de dahil olmak üzere) korumak istemiyorsanız.
- Makine düzeyi özelleştirmeler, web uygulamanızı barındıran sunuculara gerek yoktur.


> Azure uygulama hizmeti, kendi veri merkezi veya diğer şirket içi bilgisayarları kullanmak istiyorsanız, bunu kullanarak yapabilirsiniz [Azure yığın](https://azure.microsoft.com/overview/azure-stack/).


## Azure sanal makineler

[Azure sanal makineleri (VM'ler)](https://azure.microsoft.com/documentation/services/virtual-machines/) oluşturma ve herhangi bir sayıda bulut bilgi işlem kaynakları yönetmenize olanak tanır. Tüm yazılım ve güncelleştirmeler VM'ler sorumluluğu üstlenerek, bunları, web uygulamanızın gerektirdiği gibi istenen kadar özelleştirebilirsiniz. Sanal makineler doğrudan Uzak Masaüstü aracılığıyla erişebilir ve her biri atanan IP adresini istenen sürece barındırır.

Sanal makineler üzerinde barındırılan bir web uygulaması ölçeklendirmeyi isteğe göre ek Vm'leri yedekleme dönen ve gerekli yazılımı dağıtma kapsar. Bu ek düzeyi denetim sağlar, genel farklı bölgelerde farklı şekilde ölçeklendirilir. Örneğin, uygulamanızın bölgesel ofislere çeşitli çalışanlar çalışıyorsa, bu bölgeler olası maliyetlerini azaltma çalışanların sayısını göre Vm'leriniz ölçeklendirebilirsiniz.

Ek bilgi için bkz [ayrıntılı karşılaştırması](https://azure.microsoft.com/documentation/articles/choose-web-site-cloud-service-vm/) Azure App Service, Azure sanal makineleri ve Visual Studio'da özel seçeneğini kullanarak bir dağıtım hedefi olarak kullanabileceğiniz diğer Azure hizmetleri arasında.

### Ne zaman Azure App sanal makineleri seçin

- Atanmış IP adresleri ömrü üzerinde tam denetim Internet üzerinden erişilebilen bir web uygulaması dağıtmak istediğiniz.
- Sunucularınız üzerinde ağ yapılandırmaları, disk bölümleri ve benzeri belirli özel veritabanı sistemi gibi ek yazılım içeren makine düzeyi özelleştirmeleri gerekir.
- Web uygulamanızın ölçekleme üzerinde denetim ince düzeyini istiyor.
- Uygulamanız herhangi bir nedenden dolayı barındıran sunucular için doğrudan erişmeniz gerekir.

> Azure sanal makineler kendi veri Merkezinize veya diğer şirket içi bilgisayarları kullanmak istiyorsanız, bunu kullanarak yapabilirsiniz [Azure yığın](https://azure.microsoft.com/overview/azure-stack/).


## Dosya sistemi

Yalnızca belirli bir klasöre kendi bilgisayarınızda web uygulamanızın dosyaları kopyalamak, dosya sistemine dağıtma anlamına gelir. Bu çoğunlukla test amacıyla ya da bilgisayarda da bir web sunucusu çalışıyorsa, kişiler, sınırlı sayıda tarafından kullanılmak üzere uygulamayı dağıtmak için kullanılır. Hedef klasör bir ağda paylaşılıyorsa, dosya sistemine dağıtma web uygulama dosyaları sonra belirli sunuculara dağıtabilirsiniz başkalarına sunabilirsiniz.

Bir web sunucusu çalıştıran herhangi bir yerel makine uygulamanızı Internet veya Intranet nasıl yapılandırıldığına bağlı olarak ve bağlı olduğu ağlara aracılığıyla kullanılabilir hale getirebilirsiniz. (Doğrudan Internet'e bir bilgisayara bağlarsanız, dış güvenlik tehditlerine karşı korumak özellikle dikkatli olun.) Bu makineleri yönetmek için yazılım ve donanım yapılandırmaları tam denetiminde demektir.

Herhangi bir nedenle (örneğin, makine erişimi), Azure App Service ya da Azure sanal makineleri gibi bulut hizmetlerine kullanmanız mümkün değilse, kullanabileceğiniz Not [Azure yığın](https://azure.microsoft.com/overview/azure-stack/) , kendi veri merkezinizdeki. Azure yığın yönetmek ve şirket içi henüz her şeyi tutarken Azure App Service ve Azure sanal makineler bilgi işlem kaynaklarına kullanmanıza olanak sağlar.

### Ne zaman dosya sistemi dağıtımı seçin

- Yalnızca, diğerleri onu farklı sunuculara dağıtacağınız bir dosya paylaşımı uygulamayı dağıtmak.
- Yalnızca yerel test dağıtımını gerekir.
- İnceleyin ve potansiyel olarak uygulama dosyaları bağımsız olarak başka bir dağıtım hedef göndermeden önce değiştirmek istediğiniz.



## Özel hedefleri

Özel bir hedef web uygulamanızı Azure App Service, Azure sanal makineleri veya yerel dosya sistemi dışında bir hedef dağıtmanıza olanak tanır. Bir dosya sistemi veya diğer bulut Hizmetleri dahil olmak üzere, erişimi olan herhangi bir sunucuyu (Internet veya Intranet) dağıtabilirsiniz. Web ile çalışabilirsiniz dağıtma (dosyaları veya. ZIP) ve FTP.

Özel bir hedef seçerken, Visual Studio, bir profil adı ve ardından toplama ek isteyen **bağlantı** hedef sunucu veya konumu, bir site adı ve kimlik bilgileri gibi bilgiler. Aşağıdaki davranışları kontrol edebilirsiniz **ayarları** sekmesi:

- Dağıtmak istediğiniz yapılandırma.
- Var olan dosyaları hedef kaldırılıp kaldırılmayacağını belirtir.
- Yayımlama sırasında ön derleme yap görüntülenmeyeceğini belirtir.
- Dağıtımdan App_Data klasöründeki dosyaları dışarıda bırak görüntülenmeyeceğini belirtir.

Visual Studio'da farklı ayarlarla profillerini yönetmek olası hale getirerek, herhangi bir sayıda özel profillerde dağıtım oluşturabilirsiniz.

### Özel dağıtım seçmek ne zaman

- Bulut hizmetleri sağlama URL'ler erişilen Azure dışında üzerinde kullanıyorsunuz.
- Visual Studio içinde kullanın ya da Azure hesaplarınızı doğrudan bağlı olanlar dışındaki kimlik bilgilerini kullanarak dağıtmak istediğiniz.
- Dağıttığınız her zaman hedef dosyaları silmek istiyor.
