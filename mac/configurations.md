---
title: "Derleme Yapılandırmalarını Anlama"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 78107CFA-9308-4293-A92A-9B552A259E15
ms.openlocfilehash: bf27e89b6a1a606b2a7430fc7d4394b8c5ab22bc
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="understanding-build-configurations"></a>Derleme yapılandırmalarını anlama

## <a name="project-build-configurations"></a>Proje derleme yapılandırmaları 

Projeleri birden çok yapılandırmaya sahip olma eğilimi gösterir ve bunlar arasında geçiş yapma derleme zamanında farklı çıkış izin verir. Örneğin, bir hata ayıklama yapılandırmasını işlev adları, parametreleri veya çöken bir uygulamanın yığın izlemesi değişkenlerinden gidermek hata ayıklayıcı izin vererek, hata ayıklama simgeleri çıkarır. Bu ek bilgiler geliştirme sırasında kullanışlı olsa da, bir inflated dosya boyutuna yol açar ve dağıtım için uygun değil.

Her platformun, derleme için belirli yapılandırmaları vardır. 

## <a name="solution-configurations"></a>Çözüm yapılandırmaları

Proje yapılandırmaları benzer çözüm yapılandırmaları tüm proje için özel yapılandırmalar oluşturmak için kullanılır. Kullanarak **yapılandırma eşlemeleri** altında sekmesinde **Yapı > yapılandırmaları** öğesi atayabilirsiniz her çözüm öğesi için bir hedef yapılandırma aşağıdaki görüntüde gösterildiği gibi:


 ![Yapılandırma eşleme seçenekleri](media/projects-and-solutions-image3.png)

Yapılandırmaları hakkında daha fazla bilgi için bkz: [Configuration Manager](https://www.youtube.com/watch?v=tjSdkqYh5Vg) Ahmet Montemagno tarafından video.

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

Aşağıdaki listede çalıştırma yapılandırmalarında dahil veri bazı örnekler verilmiştir:

* Normal .NET projesi
    * Farklı bir başlangıç uygulaması
    * Bağımsız değişkenler Başlat
    * Çalışma dizini
    * Ortam değişkenleri
    * (Yalnızca Mono üzerinde çalışırken kullanılmak üzere) mono çalışma zamanı seçenekleri
* Android projesi
    * Giriş noktası (etkinlik, hizmet, alıcı)
    * Hedefi bağımsız değişkenleri ve veri
* iOS project
    * Mod (Normal, arka planda getirmeye)
* iOS uzantı projesi
    * Başlangıç uygulaması: varsayılan veya özel
* WatchKit proje
    * Mod (tek bakışta, bildirim)
    * Bildirim yükü
