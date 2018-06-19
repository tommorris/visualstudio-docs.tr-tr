---
title: Test denetleyicisi ve Visual Studio Yük testi için Test aracısı gereksinimleri
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- agents, requirements
- controllers, requirements
ms.assetid: 372d97ce-12e4-46a9-9863-da508adba68f
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 6f2a598ba816b12ca7027495e3775d160a7aefd6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974864"
---
# <a name="test-controller-and-test-agent-requirements-for-load-testing"></a>Yük Testi için Test Denetleyicisi ve Test Aracısı Gereksinimleri

Birkaç test birim, web performansı, yükleme de dahil olmak üzere türleri ve el ile testler Visual Studio'ya tümleşiktir. Visual Studio testleri test denetleyicisi kullanarak uzak bilgisayarlarda çalıştırmak için Visual Studio uygulama yaşam döngüsü yönetimi kullanıcıların ve bir veya daha fazla aracı sağlar. Bkz: [yüklemek ve test aracılarını yapılandırma](../test/lab-management/install-configure-test-agents.md).

## <a name="hardware-and-software-requirements"></a>Donanım ve yazılım gereksinimleri

Test denetleyicisi ve test aracısı bilgisayarlarının belirli donanım ve yazılım gereksinimleri vardır. Ayrıca, test denetleyicisi dağıtmak ve birden çok dil arasında aracı bilgisayarların test etmek istiyorsanız, bu dillerin nasıl destekleneceğini planlamanız gerekir.

### <a name="hardware-requirements"></a>Donanım Gereksinimleri

Aşağıdaki tabloda bir test denetleyicisi ve test aracılarını dağıtmak için önerilen donanım gereksinimlerini gösterir.

|**Yapılandırma**|**Bileşen**|**CPU**|**HD**|**Bellek**|
|-----------------------|-------------------|-------------|------------|----------------|
|< 500 sanal kullanıcılar|Test aracısı|2.6 GHz|10 GB|2 GB|
|< 1000 sanal kullanıcılar|Test aracısı|Çift işlemci 2.6 GHz|10 GB|2 GB|
|N x 1000 sanal kullanıcılar|Test aracısı|N aracılarla her çift 2.6 Ghz için genişletme|10GB|2GB|
|\< test ortamında 30 bilgisayarlar. Bu test edilen aracıları ve sunucuları içerir.|Test denetleyicisi|2.6 GHz|||
|N x test ortamında 30 bilgisayar. Bu test edilen aracıları ve sunucuları içerir.|Test denetleyicisi|N 2.6 GHz işlemci|||

> [!NOTE]
> Sanal kullanıcı sayısı, yaygın olarak gelen sınamak için değişir. Bir anahtar bu farkı varyans nedenidir *düşünme sürelerini*, veya kullanıcı gecikmeleri. Daha fazla bilgi için bkz: [benzetimini Web sitesi insan etkileşimi gecikmelerini için düşünme sürelerini düzenleme](../test/edit-think-times-in-load-test-scenarios.md). Bir yük testinde Web testleri genellikle daha verimli ve birim testleri'den daha fazla yük oluşturur. Yukarıdaki tabloda yer alan numaralarını, tipik bir Web uygulamasına 3-5 saniye düşünme süreleri ile Web testleri çalıştırmak için geçerlidir.

Burada sunulan yönergeler donanım planlama için genel bir yönerge olarak sağlanır. Test performansı önemli ölçüde test veri miktarı ve test aracılarının sayısına göre değişir. Test aracıları için kullanılabilir bellek ve CPU hızı test yükünü sınırlandırır. Test denetleyicileri test aracılarını sayısı ve testlerde bulunan veri miktarına bağlı olarak büyük kaynakları gerekir.

Visual Studio çalıştıran sunucunun 1 MB/sn ve bir gecikme süresi en fazla 350 ms'yle en düşük bant genişliğine sahip bir güvenilir ağ bağlantısı olmalıdır. Test aracılarını ve test denetleyicisi arasındaki güvenlik duvarı olmamalıdır. Test performansınız beklentilerinizi karşılamıyorsa, donanım yapılandırmanızla yükseltmeyi göz önünde bulundurun.

### <a name="additional-hardware-considerations"></a>Ek donanım konuları

Test aracıları büyük miktarda veri test süresi ve test boyutuna bağlı olarak test denetleyicileri üzerinde oluşturur. Genellikle, bir ek 10 GB sabit disk depolaması için 24 saatte test verilerinin planlamanız gerekir.

Burada önerilen donanım ek olarak, yedek güç kaynakları ve gereksiz Fanlar gibi kritik sunucular için ek donanım düşünmelisiniz.

### <a name="language-requirements"></a>Dil gereksinimleri

Karışıklığı önlemek ve işlemini basitleştirmek için test denetleyicisi ve test aracıları bilgisayarın işletim sistemi ve Team Foundation Server aynı dili kullanacak şekilde yapılandırılması gerekir. Test denetleyicisi ve test aracısı farklı bilgisayarlarda yüklediyseniz, aynı dili kullanacak şekilde yapılandırılmalıdır. Bu dil Team Foundation Server dağıtımının eşleşen sürece İngilizce işletim sisteminde, ancak, Visual Studio başka bir dil sürümünü yüklemek için.

## <a name="monitor-agent-resources"></a>İzleme Aracısı kaynakları

İzlenerek kaynak ihtiyaçlarını belirlemek için aracı makineleri izleyebilirsiniz **QTAgent\*.exe** yürütün ve testler sırasında ölçek işlemleri. En yaygın sorun QTAgent*.exe işlemler üzerinde CPU kullanımı ' dir. Aracı yoğun olarak yüklendiği bir göstergesi olduğu CPU kullanımı tutarlı bir şekilde yüksek nineties içinde ise. Sonraki yaygın sorun bellek kullanımı ' dir. Testleri yoğun için aşağıdaki kaynakları izleyerek, makineler kaynakları artırın veya Testlerinizi farklı dağıtırsanız, belirlemenize yardımcı olabilir.

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)