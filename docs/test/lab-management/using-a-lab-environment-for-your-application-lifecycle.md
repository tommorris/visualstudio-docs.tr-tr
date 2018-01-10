---
title: "Devops için bir laboratuvar ortamında kullanın | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: lab environment, test lab
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 227068197de1d953ae6f3729888a1b6d2dfc164c
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="use-a-lab-environment-for-your-devops"></a>Bir laboratuvar ortamı, devops için kullanın

Bir laboratuvar ortamı, geliştirmek ve uygulamaları test etmek için kullanabileceğiniz, sanal ve fiziksel makineler koleksiyonudur. Bir laboratuvar ortamı, iş istasyonları, web sunucuları ve veritabanı sunucuları gibi çok katmanlı uygulamaları test etmek için gereken birden çok rol içerebilir. Ayrıca, Laboratuvar ortamınız ile bir derleme, dağıtma, test iş akışı oluşturmak, dağıtmak ve uygulamanızda otomatikleştirilmiş testleri çalıştırma işlemini otomatikleştirmek için kullanabilirsiniz.

* **Otomatikleştirilmiş testleri çalıştırmak için bir test planı kullanma** -adlı otomatikleştirilmiş testleri koleksiyonu çalıştırabilirsiniz bir *test planı*, ilerleme durumunu görüntüleyin.  
  
* **Derleme, dağıtma, test iş akışı kullanmayı** -çok katmanlı uygulamaların otomatik olarak test etmek için bir derleme, dağıtma, test iş akışı kullanabilirsiniz. Tipik bir örnek, bir yapı başlar, laboratuvar ortamında uygun makinelere derleme dosyalarını dağıtır ve ardından otomatikleştirilmiş testleri gerçekleştiren bir iş akışıdır. Ayrıca, iş akışınızı belirli aralıklarla çalışacak şekilde zamanlayabilirsiniz.  
  
* **Hatta manuel test sırasında tüm makinelerden tanılama verisi toplama** -aynı anda birden çok makinelerden tanılama verilerini toplayabilir. Örneğin, bir tek testi sırasında IntelliTrace Topla, etki ve bir web sunucusu, bir veritabanı sunucusu ve istemci verilerini başka biçimlerde test.  
  
Laboratuvar ortamları ortak türlerinin örnekleri şunlardır:  
  
| Topoloji | Açıklama |  
|---|---|  
|![Sunucu yalnızca topolojisi](../media/topology_backend.png)| Bu laboratuar ortamını sahip bir *sunucu topolojisi*, genellikle sunucu uygulamalarını el ile testleri çalıştırmak için kullanılan ve kendi istemci makineleri Ortamı'nda hataları doğrulamak için kullanılan sınayıcılar izin verir. Bir arka uç topolojisinde Laboratuvar ortamınız yalnızca sunucuları içerir. Bu topoloji türünü kullandığınızda, sunuculara genellikle bağlanın laboratuvar ortamında ortamı değil parçası olan bir istemci makine kullanarak.|  
|![Bulut laboratuvar ortamı](../media/topology_cloud.png)| Bu laboratuar ortamını benzer özellikleri sağlar ve olarak özellikleri _sunucu topolojisi_, ancak fiziksel veya sanal yerel bir ortamda; çalışan kurulum süresini azaltabilir, basitleştirmek makineler için gerekliliğini ortadan kaldırır Bakım ve maliyeti en aza indirin. Birden çok Web siteleri ve sanal makineler, özel ağı ayarlamak hızlı ve kolay bir bulut ortamında Microsoft Azure gibi. [Daha fazla ayrıntı](#usebandrm).|  
|![İstemci-sunucu laboratuvar ortamı](../media/topology_clientserver.png)| Bu laboratuar ortamını sahip bir *istemci-sunucu topolojisi*, sık kullanılan sunucu ve istemci bileşenleri olan bir uygulama test etmek için. Bir istemci/sunucu topolojisinde uygulamanızı test etmek için kullanılan istemci ve sunucu makinelerini Laboratuvar ortamınızda tümü. Bu topoloji kullandığınızda, testlerinizi etkiler her makineden test verilerini toplayabilir.|  
  
Bkz: [Video: Test laboratuvar ortamları yönetme](http://go.microsoft.com/fwlink/?LinkID=252614).  
  
Laboratuvar ortamını ayarlama için tipik teknikler şunlardır: 
  
* **[Bulut Team Services veya Team Foundation Server yapı kullanmak &amp; sürüm](#usebandrm)**

* **[Microsoft Test Yöneticisi'nin Visual Studio Laboratuvar Yönetimi özelliklerini kullanma](#usemtmlm)**

<a name="usebandrm"></a>
## <a name="use-the-cloud-with-team-services-or-team-foundation-server-build-amp-release"></a>Bulut Team Services veya Team Foundation Server yapı kullanmak &amp; sürüm

Otomatikleştirilmiş test ve derleme, dağıtma, test otomasyonu kullanarak gerçekleştirebilirsiniz [yapı &amp; sürüm](https://www.visualstudio.com/team-services/continuous-integration/) Team Foundation Server (TFS) ve Visual Studio Team Services özellikleri. Avantajlarından bazıları şunlardır:

* Yapı denetleyicisi veya Test denetleyicisi gerekmez.
* Test Aracısı aracılığıyla bir görev oluşturma veya yayın parçası olarak yüklenir.
* Dağıtım adımları özelleştirmek basittir. Artık tek bir komut dosyası kullanmak için kısıtlanır. Ayrıca Visual Studio Market'te olduğu gibi üründe kullanılabilir birçok görev yararlanabilirsiniz.
* Test paketlerini korumak gerekmez. Bu gibi durumlarda, testleri doğrudan ikili dosyaları çalıştırabilirsiniz.
* Her bir yapı veya yayın içinde çalıştırılan testlerin deneyimi raporlama daha zengin bir satır içi alın.
* Hangi varlıklar izleyebilirsiniz (sürüm, yapı, iş öğelerini işlemeleri) şu anda dağıtılan ve her ortamda test.
* Özelleştirme ve birden çok test ortamları ve hatta üretim kolayca dağıtmak için Otomasyon genişletir.
* Bir giriş veya yürütme olduğunda veya belirli bir zamanda her gün gerçekleşecek şekilde Otomasyon zamanlayabilirsiniz.

[Daha fazla bilgi](use-build-or-rm-instead-of-lab-management.md).

<a name="usemtmlm"></a>
## <a name="use-the-visual-studio-lab-management-features-of-microsoft-test-manager"></a>Microsoft Test Yöneticisi'nin Visual Studio Laboratuvar Yönetimi özelliklerini kullanma

Oluşturun ve Visual Studio Enterprise veya Visual Studio Test uzmanı kullandığınızda laboratuvar ortamları Microsoft Test Yöneticisi'nin Visual Studio Laboratuvar Yönetimi özellikleri ile yönetin.

Laboratuvar Yönetimi test aracılarını, ortamınızdaki her makinede otomatik olarak yükler.  
  
Laboratuvar Yönetimi birlikte System Center Virtual Machine Manager (SCVMM) kullanırsanız, laboratuvar ortamları kullandığınızda avantajlar alabilirsiniz:  
  
* **Makine yapılandırmalarını hızlı bir şekilde yeniden** -koleksiyonlar, tipik bir üretim ortamlarını şekilde yapılandırılmış sanal makineler depolayabilirsiniz. Ardından, depolanmış bir ortamın yeni bir kopya çalıştırmak olan her sınamanın gerçekleştirebilirsiniz.  
  
* **Hatanın tam koşullarını yeniden** - bir testi başarısız olursa, Laboratuvar ortamınız durumunu bir kopyasını saklamak ve yapı sonuçlarınızı ya da bir iş öğesi erişmek olduğunda.  
  
* **Bir laboratuvar ortamında birden çok kopyasının aynı anda çalıştırmak** -adlandırma çakışmaları olmadan Laboratuvar ortamınız birden çok kopyasının aynı anda çalıştırabilirsiniz.  
  
### <a name="standard-environments-and-scvmm-environments"></a>Standart ortamları ve SCVMM ortamları

Visual Studio Laboratuvar Yönetimi ile oluşturabileceğiniz laboratuvar ortamları iki tür vardır: **standart ortamları** ve **SCVMM ortamları**.
Bununla birlikte, her tür bir ortamda yeteneklerini farklıdır.  
  
> **Not**: Laboratuvar Yönetimi **yok** SCVMM 2016 destekler. SCVMM hakkında daha fazla bilgi için bkz: [Sanal Makine Yöneticisi](http://go.microsoft.com/fwlink/?LinkId=226332). 
  
**Standart ortamları:** sanal ve fiziksel makineler bir karışımını içerebilir. Sanal makineler, üçüncü taraf sanallaştırma çerçeveleri tarafından yönetilen standart bir ortama da ekleyebilirsiniz. Ayrıca, standart ortamları bir SCVMM sunucusu gibi ek sunucu kaynaklarına gerektirmez.  
  
**SCVMM ortamları:** SCVMM ortamlardaki sanal makineler yalnızca Hyper-V sanallaştırma Framework'te çalıştırabilmeniz için (System Center Virtual Machine Manager), SCVMM tarafından yönetilen sanal makineler yalnızca içerebilir. Ancak, SCVMM ortamlarını standart ortamlarında kullanılabilir değil aşağıdaki otomasyon ve yönetim özellikleri sağlar:  
  
- **Ortam anlık görüntülerini:** ortam anlık görüntülerini hızla, temiz bir ortam geri yükleyin veya değiştirilmiş bir ortam durumunu kaydetmek için bir laboratuvar ortamında durumunu içerir. Derleme, dağıtma, test iş akışı, kaydetme ve Ortam anlık görüntülerini geri yükleme işlemini otomatikleştirmek için de kullanabilirsiniz.  
  
- **Depolanan ortamları:** SCVMM ortamını kopyasını depolayın ve sonra bu ortam birden çok kopyasını dağıtın.  
  
- **Ağ yalıtımı:** ağ yalıtımı aynı anda birden çok aynı kopyasını bilgisayar adı çakışmalarını olmadan SCVMM ortamını çalıştırmanıza olanak sağlar.  
  
- **Sanal makine şablonları:** bir sanal makine şablonu adı değiştirilmiş bir sanal makine ve diğer tanımlayıcıları kaldırıldı. Bir VM şablonu SCVMM ortamında dağıtıldığında, Microsoft Test Yöneticisi'ni yeni tanımlayıcıları oluşturur. Bu, bir sanal makinenin aynı ortamda birden çok kopya veya birden çok ortamı dağıtmak ve sanal makineleri aynı anda çalıştırmak sağlar.  
  
- **Depolanan sanal makineler:** , takım projesi kitaplığında depolanan ve benzersiz tanımlayıcıları içeren bir sanal makine.  
  
Bu özellikler hakkında daha fazla bilgi için bkz: [oluşturma ve yönetme SCVMM ortamları için yönergeler](https://msdn.microsoft.com/en-gb/library/ee830480.aspx).  
  
Standart ortamları ve SCVMM ortamları aynı özelliklerinin çoğunu destekler. Ancak, dikkate alınması gereken önemli bazı farklar vardır. Aşağıdaki tabloda standart ortamları ve SCVMM ortamları için kullanılabilen özellikleri karşılaştırılmaktadır.  
  
|Özellik|SCVMM ortamları|Standart ortamları|  
|----------------|------------------------|---------------------------|  
|**Test etme**|||  
|El ile testleri çalıştırma|Desteklenir|Desteklenir|  
|Kodlanmış UI ve diğer otomatikleştirilmiş testleri çalıştırma|Desteklenir|Desteklenir|  
|Tanılama bağdaştırıcısını kullanarak dosya zengin hataları|Desteklenir|Desteklenir|  
|**Derleme dağıtımı**|||  
|Otomatik derleme, dağıtma, test iş akışları|Desteklenir|Desteklenir|  
|**Ortamı oluşturulması ve Yönetimi**|||  
|Sanal makineler yanı sıra fiziksel makineleri kullanın|Desteklenmez|Desteklenir|  
|Üçüncü taraf sanal makineler kullanın|Desteklenmez|Desteklenir|  
|Laboratuvar ortamında test aracılarını makinelere otomatik olarak yükle|Desteklenir|Desteklenir|  
|Kaydedin ve Ortam anlık görüntülerini kullanan bir laboratuar ortamında durumunu dağıtın|Desteklenir|Desteklenmez|  
|VM şablonlarından laboratuvar ortamları oluşturma|Desteklenir|Desteklenmez|  
|Başlat/Durdur/anlık görüntü ortamı|Desteklenir|Desteklenmez|  
|Ortam Görüntüleyicisi'ni kullanarak ortama bağlanma|Desteklenir|Desteklenir|  
|Ağ yalıtımı kullanarak aynı anda bir ortamın birden çok kopyasını çalıştırın|Desteklenir|Desteklenmez|  
  
### <a name="lab-management-concepts"></a>Laboratuvar Yönetimi Kavramları

Devam etmeden önce konusunda bilgi sahibi olmanız bazı ek kavramları şunlardır:  
  
|Terim|Açıklama|  
|----------|-----------------|  
|Laboratuvar Merkezi|Microsoft Test oluşturduğunuz ve Laboratuvar ortamlarını yöneticisinin alan.|  
|Takım projesi laboratuvarı|Bağlanabilmesi için onlara ayarlama ve bunların sanal makineleri çalıştırmak laboratuvar ortamları koleksiyonu.|  
|Takım projesi kitaplık|Bir arşiv depolanan sanal makineler, şablonları ve takım projenizin konak grubuna içe saklı laboratuvar ortamları. SCVMM ortamları ile kitaplığınızdaki öğeleri kullanabilirsiniz; Ancak, bunları doğrudan standart ortam için ekleyemezsiniz. Kitaplığınızdaki öğeleri çalışamaz; Bunun yerine, bunları yeni bir ortam dağıtmak için kullanın.|  
|Dağıtılan ortamı|Böylece bağlanmak ve onun makineleri çalıştırmak, takım projesi Laboratuvarınızı dağıtılan bir laboratuvar ortamı.|  

#### <a name="related-topics"></a>İlgili konular

* [Laboratuvarınızı Planlama](https://msdn.microsoft.com/library/ff756575%28v=vs.140%29.aspx) 
* [Laboratuvarınızı yönetme](https://msdn.microsoft.com/library/dd936084%28v=vs.140%29.aspx) 
* [SCVMM ortamları için ayarlama](https://msdn.microsoft.com/library/dd380687%28v=vs.140%29.aspx) 
* [SCVMM 2008 R2’yi SCVMM 2012’ye yükseltme](upgrade-scvmm-2008-r2-scvmm-2012.md) 
* [İzinleri yönetme](https://msdn.microsoft.com/library/dd380760%28v=vs.140%29.aspx) 
* [Değişiklik Kurulumu](https://msdn.microsoft.com/library/ee704508%28v=vs.140%29.aspx) 
* [Sorun giderme](https://msdn.microsoft.com/library/ee853230%28v=vs.140%29.aspx)
  
### <a name="set-up-environments"></a>Ortamları ayarlama

* [Yapı &amp; yayın bulut ortamları](use-build-or-rm-instead-of-lab-management.md)
* [Standart laboratuvar ortamları](https://msdn.microsoft.com/en-gb/library/ee390842.aspx)
* [SCVMM (sanal) ortamları](https://msdn.microsoft.com/en-gb/library/ee943322.aspx)
* [Oluşturma ve ağ yalıtımlı ortam kullanma](https://msdn.microsoft.com/en-gb/library/ee518924.aspx)
  
## <a name="see-also"></a>Ayrıca bkz.
  
* [Test aracılarını yükleme ve yapılandırma](install-configure-test-agents.md)
* [Visual Studio Laboratuvar Yönetimi Kılavuzu](http://go.microsoft.com/fwlink/?LinkID=230951)  
* [Test laboratuvar ortamları yönetme](http://go.microsoft.com/fwlink/?LinkID=252614)  
* [Visual Studio devops + Team Foundation Server blogu](http://go.microsoft.com/fwlink/?LinkID=254496)  
