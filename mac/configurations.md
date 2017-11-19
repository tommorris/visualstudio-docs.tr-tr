---
title: "Derleme Yapılandırmalarını Anlama"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 78107CFA-9308-4293-A92A-9B552A259E15
ms.openlocfilehash: e435418c0c77f1577e9db8ab35d76d6bd54f8447
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="understanding-build-configurations"></a>Derleme yapılandırmalarını anlama

## <a name="project-build-configurations"></a>Proje derleme yapılandırmaları 

Projeleri birden çok yapılandırmaya sahip olabilir ve bunlar arasında geçiş yapma derleme zamanında farklı çıkış sağlar. Örneğin, bir hata ayıklama yapılandırmasını kullanırken, çıkış hata ayıklama simgeleri, işlev adları, parametreleri veya çöken bir uygulamanın yığın izlemesi değişkenlerinden gidermek hata ayıklayıcı sağlayan içerir. Hata ayıklama Yapılandırması'nı kullanarak, ancak müşteri adayları inflated dosya boyutu ve bunu dağıtım için tasarlanan bir uygulama için ideal olmayacaktır.

Her platform, derleme için belirli yapılandırmaları gerekir. Xamarin.Android geliştirme her zaman yalnızca bir sürümü ya da hata ayıklama yapılandırmasını olacaktır. Xamarin.iOS daha fazla yapılandırmaları vardır. Yeni iOS projeleri yalnızca sahip hatalarını ayıklama veya yayın yapılandırmaları, ancak bunlar bir aygıt veya yüklü bir simulator için ayarlanabilir.

## <a name="solution-configurations"></a>Çözüm yapılandırmaları

Proje yapılandırmaları benzer çözüm yapılandırmaları tüm proje için özel yapılandırmalar oluşturmak için kullanılır. Kullanarak **yapılandırma eşlemeleri** altında sekmesinde **Yapı > yapılandırmaları** öğesi atayabilirsiniz her çözüm öğesi için bir hedef yapılandırma aşağıda gösterildiği gibi:


 ![Yapılandırma eşleme seçenekleri](media/projects-and-solutions-image3.png)

Daha fazla bilgi için bkz [Configuration Manager](https://www.youtube.com/watch?v=tjSdkqYh5Vg) Ahmet Montemagno tarafından video.

## <a name="run-configuration"></a>Çalışma yapılandırması

Xamarin Studio önceki sürümlerde projesi olarak ayarla seçeneğine seçebilirsiniz bir **başlangıç projesi**, Çalıştır/genel Çalıştır/Hata Ayıkla komutunu kullanırken hata proje olduğu. Bu projenin adı proje panelinde için kalın yazı tarafından belirtilir.

Visual Studio başlangıç projesi ayarlama yerine Mac için ayarlayabileceğiniz bir _yapılandırmasını çalıştırmak_. Çalıştırma yapılandırmaları araç, aşağıda gösterildiği gibi yapı yapılandırma Seçici yanında aşağı açılan listesinde sunulur:

 ![Yapılandırma açılan çalıştırın](media/projects-and-solutions-image8.png)

Çalışma yapılandırması, bir ad ve farklı amaçlar için bir proje tanımlanan birkaç yapılandırmaları ile yürütme seçeneklerini kümesidir. Çalıştırma yapılandırmaları proje düzeyinde tanımlanır ve kadar gerekli eklemek mümkün olmakla varsayılan otomatik olarak çalıştırılabilir her proje için oluşturulur. Belirli proje türleri ek çalıştırma yapılandırmaları otomatik olarak oluşturur. Örneğin, watchOS projeler oluşturabilir _bakışta ve bildirim yapılandırmaları._ 
 
Yapılandırmaları (Bu durumda yapılandırmaları .csproj dosyanızda depolanır) diğer geliştiriciler paylaşılan veya (durumda .kullanıcı dosyasında depolanır yerel olarak) tutulur.

### <a name="android-run-configurations"></a>Android yapılandırmaları çalıştırma
 
Çalıştırma yapılandırmaları Android projeleri için hangi etkinlik, hizmet veya çalıştıran veya projenin hata ayıklamayı başlatmak için yayın alıcı belirtmenizi sağlar. Hedefi ek verileri geçirebilir ve bileşenlerinizin farklı başlatma koşullar altında test edebilmek için hedefi bayraklarını ayarlayın.

Etkinlikler dışında `MainLauncher` gerekecek `Exported=true` fiziksel cihaz üzerindeki hata ayıklama için etkinlik özniteliği eklenecek veya hedefi filtreleri tanımlı sahip.

## <a name="examples-of-data-that-might-be-included-in-run-configurations"></a>Çalıştırma yapılandırmalarında dahil veri örnekleri

Aşağıdaki liste çalıştırma yapılandırmalarında dahil veri bazı örnekleri sağlar:

* Normal .NET projesi
    * Farklı bir başlangıç uygulaması
    * Bağımsız değişkenler Başlat
    * Çalışma dizini
    * Ortam değişkenleri
    * (Yalnızca Mono üzerinde çalışırken kullanılmak üzere) mono çalışma zamanı seçenekleri
* Android projesi
    * Giriş noktası (etkinlik, hizmet, alıcı)
    * Hedefi bağımsız değişkenleri ve veri
* iOS projesi
    * Mod (Normal, arka planda getirmeye)
* iOS uzantı projesi
    * Başlangıç uygulaması: varsayılan veya özel
* WatchKit proje
    * Mod (tek bakışta, bildirim)
    * Bildirim yükü
