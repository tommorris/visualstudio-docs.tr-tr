---
title: Visual Studio Yük testi senaryosu özellikleri
ms.date: 10/19/2016
ms.topic: reference
helpviewer_keywords:
- load tests, properties
- load tests, scenarios
ms.assetid: 4414a638-1fa2-40ad-b1f4-b99f90b62e62
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 2619ce42d80eb804929482ffc2c6fd431e238ca5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31977221"
---
# <a name="load-test-scenario-properties"></a>Yük Testi Senaryosu Özellikleri

Yük testi gereksinimlerini karşılamak için Visual Studio, yük test senaryosu özelliği ayarlarınızı değiştirin. Bu makalede kategoriye göre çeşitli yük testi senaryosu özellikleri listelenmektedir.

## <a name="general"></a>Genel

|Özellik|Tanım|
|--------------|----------------|
|**Ad**|Senaryo için ad.|

## <a name="mix"></a>Karışımı

|Özellik|Tanım|
|--------------|----------------|
|**Tarayıcı karışımı**|Yük testi için Web tarayıcısı karışımını belirtir. Farklı Web tarayıcısı türleri ve yük dağılımını belirtebilirsiniz.<br /><br />Tarayıcı Karışımını Düzenle iletişim kutusunu açın ve kullanmak için üç nokta (...) düğmesini seçin **Ekle** ve **kaldırmak** yük testinde Web tarayıcısı türlerini seçin.<br /><br />Daha fazla bilgi için bkz: [Web tarayıcısı türlerini belirtme](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).|
|**Ağ karışımı**|Yük testi için ağ karışımı belirtir. Eklenecek hangi ağ türlerini ve bunların yük dağıtımı belirtebilirsiniz.<br /><br />Açmak için üç nokta (...) düğmesini seçin **Ağ Karışımını Düzenle** iletişim kutusu ve kullanım **Ekle** ve **kaldırmak** yük testinde ağ türlerini seçin.<br /><br />Daha fazla bilgi için bkz: [sanal ağ türlerini belirtme](../test/specify-virtual-network-types-in-a-load-test-scenario.md).|
|**Test karışımı**|Web performans ve birim test karışımı yük testi için belirtir. Hangi testlerin ekleneceğini ve yük dağılımını belirtebilirsiniz.<br /><br />Açmak için üç nokta (...) düğmesini seçin **Test Karışımını düzenleme** iletişim kutusu ve kullanım **Ekle** ve **kaldırmak** yük testinde testleri seçmek için.<br /><br />Daha fazla bilgi için [bir yük testi senaryosu için Test Karışımını düzenleme](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).|
|**Test karışım türü**|Yük testi için test karışımı modeli belirtir.<br /><br />Açmak için üç nokta (...) düğmesini seçin **Test Karışımını düzenleme** iletişim kutusu ve kullanım açılan altında **Test karışımı modeli** yük testinde kullanmak için test karışımı modeli seçin.<br /><br />Daha fazla bilgi için bkz: [karışımı modellerini düzenleme](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).|

## <a name="options"></a>Seçenekler

|Özellik|Tanım|
|--------------|----------------|
|**Kullanılacak Aracılar**|Uzaktan test, senaryonuzun yükü çalıştırıyorsanız kullanmasını istediğiniz aracıları belirtir. Örneğin, performans eğilimlerini analiz ederken tutarlılığını korumak için belirli bir aracı kümesi belirtmek isteyebilirsiniz. Ayrıca, hangi betikler arasındaki çalıştıkları ve aracı bulunduğu benzeşim yani aracılar coğrafi olarak dağıtılabilir.<br /><br />Aracıları ayrılmalıdır virgüllerle, örneğin "**Aracı1, Aracı2, Aracı3**". Özelliği boş bırakmak senaryo tüm kullanılabilir aracıları'nı kullanması gerektiğini belirtir.<br /><br />Daha fazla bilgi için bkz: [nasıl yapılır: kullanılacak Test aracıları belirtme](../test/how-to-specify-test-agents-to-use-in-load-test-scenarios.md).|
|**Gecikmesine Dağıtım uygulama**|Test karışımı modeli Adımlama kullanıcı tipik dağıtım gecikmelerine isteyip istemediğinizi belirtmek için kullanılan Boole değeri. Bu özellik yalnızca geçerlidir **Test karışım türü** özelliği ayarlanmış **kullanıcı adına dayalı**.<br /><br />Daha fazla bilgi için bkz: [nasıl yapılır: dağıtım gecikmesine Uygula](../test/how-to-apply-distribution-to-pacing-delay-when-using-a-user-pace-test-mix-model.md)|
|**IP geçişi**|IP değiştirme kullanılıp kullanılmayacağını belirtmek için kullanılan Boole değeri.<br /><br />IP geçişi farklı IP adres aralığını kullanarak bir sunucuya istek göndermek bir test aracısı sağlar. Bu, farklı istemci bilgisayarlardan gelen çağrıların benzetimini yapar. Yük dengeli Web grubu karşı test ettiğinizde, IP geçişi önemlidir. Çoğu yük dengeleyicileri, istemcinin IP adresini kullanarak bir istemci belirli bir Web sunucusu arasında benzeşim kurar. Tek bir istemciden gelen tüm istekleri görünmesini, yük dengeleyici yükü dengelemez. Web grubunda iyi Yük Dengeleme elde etmek için istekleri bir dizi IP adreslerinden gelen önemlidir.<br /><br />IP değiştirme yalnızca test aracısı ile kullanılabilir.|
|**En yüksek Test Yinelemeleri**|Senaryoda Çalıştırılacak testleri en fazla sayısını belirtmek için kullanılan sayısal değer. 0 değeri hiçbir verilen belirtir.<br /><br />Daha fazla bilgi için bkz: [senaryolar için Test yinelemelerini yapılandırma](../test/configure-test-iterations-in-a-load-test-scenario.md).|
|**Yeni kullanıcı yüzdesi**|Yeni kullanıcılar veya ilk kez gelen ziyaretçilerin yüzdesini senaryoda belirtir sayısal değer.<br /><br />Daha fazla bilgi için bkz: [nasıl yapılır: sanal kullanıcı yüzdesi bu kullanım Web önbellek verilerini belirtin](../test/how-to-specify-the-percentage-of-virtual-users-that-use-web-cache-data.md).|
|**Düşünme profili**|Senaryo kullanıp kullanmayacağını belirtir **Normal dağıtım**, veya Düşünme profili ise **üzerinde** veya **devre dışı**.<br /><br />Daha fazla bilgi için bkz: [benzetimini Web sitesi insan etkileşimi gecikmelerini için düşünme sürelerini düzenleme](../test/edit-think-times-in-load-test-scenarios.md).|

## <a name="timing"></a>Zamanlama

|Özellik|Tanım|
|--------------|----------------|
|**Gecikme başlangıç zamanı**|Kaç saat, dakika ve saniye cinsinden gecikme yükleme sonrası senaryo başlatma başlatır test gösteren bir saat değeri. Varsa **Isınma sırasında devre dışı bırak** özelliği ayarlanmış **doğru**, Isınma süresi tamamlandıktan sonra beklenecek süreyi uygular.<br /><br />Daha fazla bilgi için bkz: [Senaryo Başlatma Gecikmelerini Yapılandırma](../test/configure-scenario-start-delays.md).|
|**Isınma sırasında devre dışı bırak**|Senaryo çalıştırırsanız veya sırasında değil belirtmek için kullanılan Boole değeri **Isınma Süresi** çalıştırma ayarı yük testinde belirtilen özelliği saat değeri.<br /><br />Yük testi özelliklerini ayarlama hakkında daha fazla bilgi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).<br /><br />Daha fazla bilgi için bkz: [Senaryo Başlatma Gecikmelerini Yapılandırma](../test/configure-scenario-start-delays.md).|
|**Düşünme süreleri Test Yinelemeleri arasındaki**|Test yinelemeleri arasındaki saniye cinsinden bekleme süresini belirtmek için kullanılan sayısal değer.<br /><br />Daha fazla bilgi için bkz: [benzetimini Web sitesi insan etkileşimi gecikmelerini için düşünme sürelerini düzenleme](../test/edit-think-times-in-load-test-scenarios.md).|

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi senaryolarını düzenleme](../test/edit-load-test-scenarios.md)