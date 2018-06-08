---
title: Derleme veya yayın Yönetimi otomatikleştirilmiş Visual Studio'da Test için kullanın
ms.date: 03/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- automated testing, lab management, test lab
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 454407c3572f7a7c7a1c0f795462d2aec539049a
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845385"
---
# <a name="use-build-and-release-management-instead-of-lab-management-for-automated-testing"></a>Derleme ve sürüm Yönetimi yerine Laboratuvar Yönetimi otomatikleştirilmiş test için kullanın.

Otomatik test için veya derleme, dağıtma, test otomasyonu için Microsoft Test Yöneticisi'ni (MTM) ve Laboratuvar Yönetimi kullanıyorsanız, bu konuda, kullanarak aynı hedefleri nasıl elde edebilirsiniz açıklanmaktadır [derleme ve sürüm](/vsts/build-release/) Team Foundation'da özellikleri Server (TFS) ve Visual Studio Team Services (VSTS).

## <a name="build-deploy-test-automation"></a>Derleme, dağıtma, test Otomasyonu

MTM ve Laboratuvar Yönetimi derleme, dağıtma ve uygulamalarınızın test otomatikleştirmek için bir XAML yapı tanımına kullanır. XAML yapı içindeki bir laboratuvar ortamı, test paketlerini ve test ayarları gibi oluşturulan çeşitli yapılar ve yapı denetleyicisi, yapı aracıları, Test denetleyicisi ve Test aracılarını bu hedefe ulaşmak için gibi çeşitli altyapı bileşenlerini dayanır. Derleme veya TFS ve Team Services yayın yönetimini kullanarak daha az adım ile aynı gerçekleştirebilirsiniz.

| Adımlar | XAML yapı ile | Derleme veya yayın Yönetimi |
|-------|----------------------|-----------------|
| Yapı dağıtmak ve testleri çalıştırmak için makineler tanımlayın. | Standart laboratuvar ortamı ile bu makineleri MTM içinde oluşturun. | yok |
| Çalıştırılacak testleri tanımlayın. | MTM içinde bir test paketi oluşturun, test durumları oluşturmak ve Otomasyon her test çalışması ile ilişkilendirebilirsiniz. Test ayarları makineleri testleri çalıştırmalısınız laboratuvar ortamında rol tanımlayan MTM oluşturun. | Test planları test yönetmeyi planlıyorsanız otomatikleştirilmiş test paketi MTM aynı şekilde oluşturun. Alternatif olarak, doğrudan test ikili dosyaları derlemeleriniz tarafından üretilen gelen testleri çalıştırmak istiyorsanız, bunu atlayabilirsiniz. Test ayarları her iki durumda da oluşturmak için gerek yoktur. |
| Dağıtım ve sınama otomatikleştirin. | LabDefaultTemplate.*.xaml kullanarak bir XAML yapı tanımı oluşturun. Derleme, test paketleri ve laboratuvar ortamında yapı tanımında belirtin. | Oluşturma bir [yapı veya serbest tanımı](/vsts/build-release/) tek bir ortamı. Komut satırı görevini kullanarak aynı dağıtım komut dosyası (XAML yapı tanımından) ve Test aracısı dağıtımı ve işlevsel Testleri Çalıştır görevlerini kullanarak otomatikleştirilmiş testleri çalıştırın. Bu görevler için girdi olarak makine ve kimlik bilgilerini listesini belirtin. |

Bu senaryo için derleme veya yayın Yönetimi kullanmanın avantajları bazıları şunlardır:

* Yapı denetleyicisi veya Test denetleyicisi gerekmez.
* Test Aracısı aracılığıyla bir görev oluşturma veya yayın parçası olarak yüklenir.
* Dağıtım adımları özelleştirmek basittir. Artık tek bir komut dosyası kullanmak için kısıtlanır. Ayrıca Visual Studio Market'te olduğu gibi üründe kullanılabilir birçok görev yararlanabilirsiniz.
* Test paketlerini korumak gerekmez. Bu gibi durumlarda, testleri doğrudan ikili dosyaları çalıştırabilirsiniz.
* Her bir yapı veya yayın içinde çalıştırılan testlerin deneyimi raporlama daha zengin bir satır içi alın.
* Hangi varlıklar izleyebilirsiniz (sürüm, yapı, iş öğelerini işlemeleri) şu anda dağıtılan ve her ortamda test.
* Özelleştirme ve birden çok test ortamları ve hatta üretim kolayca dağıtmak için Otomasyon genişletir.
* Bir giriş veya yürütme olduğunda veya belirli bir zamanda her gün gerçekleşecek şekilde Otomasyon zamanlayabilirsiniz.

## <a name="self-service-management-of-scvmm-environments"></a>SCVMM ortamları Self Servis Yönetimi

[Test Center Microsoft Test Yöneticisi'nde](/vsts/manual-test/mtm/guidance-mtm-usage) yanı sıra bir ortam şablonları kitaplığı yönetme kullanarak isteğe bağlı üzerinde ortamları sağlama yeteneği destekleyen bir [SCVMM sunucusu](/system-center/vmm/overview?view=sc-vmm-1801).

Self Servis sağlama özelliklerini Laboratuvar Merkezi iki ayrı amacı vardır:

* Altyapısını yönetmek için daha basit bir yolunu sağlar. VM ve ortam şablonları yönetmek ve otomatik olarak kopyalar ortamlarının birbirinden ayırmak için özel ağlar oluşturma altyapı Yönetimi örnekleri yoktu.

* Test ve dağıtım etkinliklerini'nde sanal makinelerin tüketmeye ekipler için daha basit bir yolunu sağlar. Kolay kullanım örnekleri olan aynı takım projesi güvenlik modeli üzerinden erişilebilir ve tümleşik ortamları test senaryolarda bu sanal makineleri kullanımı Laboratuvar yapılıyor.

Ancak, daha zengin genel ve özel bulut evrimi yönetim sistemleri gibi verilen [Microsoft Azure](https://azure.microsoft.com/) ve [Microsoft Azure yığın](https://azure.microsoft.com/overview/azure-stack/), altyapı yönetimi özelliklerine hiçbir evrimi yok TFS 2017 ve ötesine. Bunun yerine, kolay gibi bulut altyapılar aracılığıyla yönetilen kaynaklarının kullanımını odaklanmak devam eder.

(Test veya dağıtım etkinlikleri olmaları durumunda) Laboratuvar Merkezi ve (altyapı yönetimi etkinlikleri olmaları durumunda) nasıl, bunları SCVMM veya Azure yapabilirsiniz veya TFS ve Team Services aracılığıyla gerçekleştirmek tipik etkinlikleri aşağıdaki tabloda özetlenmiştir:

| Adımlar | Laboratuvar Merkezi ile | Derleme veya yayın Yönetimi |
|-------|----------------------|-----------------|
| Bir ortam şablonları kitaplığı yönetin. | Bir laboratuvar ortamı oluşturun. Sanal makinelerde gerekli yazılımı yükleyin. Sysprep ve depolama ortamı Kitaplığı'nda bir şablon olarak. | SCVMM Yönetim konsolunu doğrudan oluşturmak ve sanal makine şablonları veya hizmet şablonları yönetmek için kullanın. Azure kullanırken aşağıdakilerden birini seçin [Azure hızlı başlangıç şablonlarını](https://azure.microsoft.com/resources/templates/). |
| Bir laboratuvar ortamı oluşturun. | Kitaplıkta bir ortam şablonunu seçin ve dağıtın. Sanal makine yapılandırmalarının özelleştirmek için gerekli parametreleri belirtin. | Doğrudan şablonlardan sanal makineler veya hizmet örnekleri oluşturmak için SCVMM Yönetim konsolunu kullanın. Doğrudan kaynak oluşturmak için Azure portalını kullanın. Veya bir yayın tanımı bir ortam oluşturabilirsiniz. Kullanım Azure görevler veya gelen görevleri [SCVMM Tümleştirme Uzantısı](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) yeni sanal makineler oluşturmak için. Bu tanım yeni bir sürüm oluşturma, Laboratuvar Merkezi'nde yeni bir ortam oluşturmaya eşdeğerdir. |
| Makinelere bağlayın. | Laboratuvar ortamını Ortam Görüntüleyicisi'nde açın. | Doğrudan sanal makinelere bağlanmak için SCVMM Yönetim konsolunu kullanın. Alternatif olarak, uzak masaüstü oturumları açmak için IP adresi veya sanal makinelerin DNS adlarını kullanın. |
| Bir ortamın bir denetim noktası almak veya bir ortam için temiz bir kontrol noktası geri yükleyin. | Laboratuvar ortamını Ortam Görüntüleyicisi'nde açın. Bir denetim noktası almak için veya bir önceki kontrol noktasına geri yüklemek için seçeneği seçin. | Doğrudan sanal makinelerde bu işlemleri gerçekleştirmek için SCVMM Yönetim konsolunu kullanın. Veya daha büyük bir Otomasyon bir parçası olarak bu adımları gerçekleştirmek için denetim noktası görevlerden dahil [SCVMM Tümleştirme Uzantısı](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) yayın tanımında ortamının bir parçası olarak. |

## <a name="creation-of-network-isolated-environments"></a>Yalıtılmış ağ ortamları oluşturma

Ağ yalıtılmış laboratuvar ortamında ağ çakışmalarına neden olmadan güvenli bir şekilde kopyalanabilen SCVMM sanal makineler grubudur. Bu MTM içinde bir dizi ortak bir ağda sanal makineleri yapılandırmak için özel bir ağda sanal makineleri yapılandırmak için ağ arabirim kartları kümesi ve başka bir ağ arabirimi kartları kümesi kullanılan yönergeleri kullanarak gerçekleştirilir.

Ancak, VSTS SCVMM birlikte TFS yapı ve görev dağıtmak, SCVMM ortamlarını yönetebilir, yalıtılmış sanal ağlara sağlamak için kullanılır ve derleme, dağıtma, test senaryolarını uygulayan. Örneğin, görevi kullanabilirsiniz:

* Oluştur, geri yükleme ve kontrol noktalarını silin
* Bir şablon kullanarak yeni sanal makineler oluşturun
* Sanal makineler durdurup başlatın
* SCVMM özel PowerShell betikleri çalıştırmak

Daha fazla bilgi için bkz: [derleme, dağıtma, test senaryoları için sanal ağ yalıtımlı ortam oluşturma](/vsts/build-release/actions/virtual-networks/create-virtual-network).
