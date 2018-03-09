---
title: "Visual Studio Mac tur için | Microsoft Docs"
description: "Mac için Visual Studio macOS ASP.NET Core Web siteleri ve Xamarin iOS, Android, Mac ve Xamarin.Forms projelerde dahil olmak üzere, .NET uygulamaları oluşturmak için bir tümleşik geliştirme ortamı sağlar."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 7DC64A52-AA41-4F3A-A8A1-8A20BCD81CC7
ms.openlocfilehash: 0dfd77c36c9880f1510f240f0a6c8f490a055fc4
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="visual-studio-for-mac-tour"></a>Visual Studio için Mac turu

Visual Studio Mac için Xamarin'ın mobil merkezli IDE, Xamarin Studio Mac üzerinde bir mobil ilk olarak, bulut ilk geliştirme ortamına dönüşmesi. Bu Geliştirici odaklı aracı, kullanıcılarınız tarafından gerekli tüm platformlar için uygulama oluşturmak için .NET gücünü kullanmanıza olanak sağlar.

Kullanıcı deneyimini (UX) Visual Studio Mac için Windows karşılığı, ancak yerel macOS kullanımında ile benzerdir. Visual Studio Windows üzerinde önceden kullanılmış herkes için tanıdık bir deneyim oluşturma, açma ve bir uygulama geliştiren olacaktır. Buna ek olarak, Mac için Visual Studio çok güçlü bir IDE Windows karşılığı olun güçlü aracını kullanır. Roslyn derleyici Platform yeniden düzenleme ve IntelliSense için kullanılır. MSBuild proje sistem ve yapı altyapısı kullanın ve TextMate paketleri kendi kaynak Düzenleyicisi'ni destekler. Aynı hata ayıklayıcı motorları Xamarin ve .NET Core uygulamaları ve aynı tasarımcıları Xamarin.iOS ve Xamarin.Android için kullanır.

Bu makalede, Mac, platformlar arası uygulamalar oluşturmak için güçlü bir araç olun özelliklerinden bazıları bakma sağlamak için Visual Studio çeşitli bölümlerini araştırır.

## <a name="ide-tour"></a>IDE turu

Mac için Visual Studio, uygulama dosyalarını ve ayarlarını yönetme, uygulama kodu oluşturma ve hata ayıklama için çeşitli bölümlere düzenlenmiştir.

## <a name="welcome-screen"></a>Hoş Geldiniz ekranı

Başlatıldığında, Mac için Visual Studio görüntüler bir *Hoş Geldiniz ekranı*:

![Hoş Geldiniz ekranı](media/ide-tour-image1.png)

Hoş Geldiniz ekranında aşağıdaki bölümleri içerir:

- **Araç çubuğu** -arama çubuğunu hızlı erişim sağlar. Bir çözüm yüklendiğinde, araç uygulama yapılandırmaları, hata ayıklama ve hataları görüntülemek için ayarlamak için kullanılır.
- **Başlarken** -Mac için Visual Studio ile çalışmaya başlama geliştiriciler için kullanışlı konuları hızlı erişim sağlar
- **Son çözümleri** -açmak veya projeleri oluşturmak için uygun düğmeler yanı sıra, en son açılan çözümleri hızlı erişim sağlar.
- **Geliştirici Haberleri** -güncel hakkında en son Microsoft Developer bilgileri tutan bir haber akışı.

## <a name="solutions-and-projects"></a>Projeler ve Çözümler

Aşağıdaki resimde, yüklenen uygulama ile Mac için Visual Studio gösterilmektedir:

![Yüklenen bir uygulamayla Mac için Visual Studio](media/ide-tour-image17.png)

Aşağıdaki bölümler, Mac için Visual Studio temel alanları genel bir bakış sağlar

## <a name="solution-pad"></a>Çözüm paneli

Çözüm paneli bir çözümde proje düzenler:

![Çözüm defterinde düzenlenmiş projeleri](media/ide-tour-image18.png)

Kaynak kodu, kaynaklar, kullanıcı arabirimi ve bağımlılıklar için dosyaları platforma özgü projelere burada düzenlenir budur.

Visual Studio'da projeler ve çözümler için Mac kullanma hakkında daha fazla bilgi için bkz: [projeler ve çözümler](~/projects-and-solutions.md) makalesi.

## <a name="assembly-references"></a>Derleme başvuruları
 
Derleme başvurularını her proje için başvurular klasörünün altında mevcuttur:

![Çözüm panelinde başvuruları klasörü](media/ide-tour-image19.png)

Ek başvurular kullanarak eklenir **Düzenle başvuruları** başvuruları klasörü çift veya seçerek görüntülenen iletişim **Düzenle başvuruları** bağlam menüsü eylemlerini üzerinde:
 
![Başvurular iletişim Düzenle](media/ide-tour-image20.png)

Başvuruları Visual Studio'daki Mac için kullanma hakkında daha fazla bilgi için bkz: [bir projedeki başvuruları yönetme](~/managing-references-in-a-project.md) makalesi.

## <a name="dependencies--packages"></a>Bağımlılıklar / paketleri

Uygulamanızda kullanılan tüm dış bağımlılıkları bir .net olmanıza bağlı olarak bağımlılıklar veya paketler klasöründe depolanan çekirdek veya Xamarin.iOS/Xamarin.Android projesi. Bu, genellikle bir NuGet veya bileşeni biçiminde sağlanır.

NuGet en popüler .NET geliştirme paket yöneticisidir. Visual Studio'nun NuGet desteğiyle kolayca aramak ve paketleri uygulaması projenize ekleyin.

Uygulamanıza bir bağımlılık eklemek için bağımlılıkları sağ / paketleri klasörü ve select **paketleri Ekle**:

![Bir NuGet paketi ekleme](media/ide-tour-image21.png)

Bir uygulamada bir NuGet paketi kullanma hakkında daha fazla bilgi bulunabilir [dahil olmak üzere bir NuGet proje projenizdeki](~/nuget-walkthrough.md) makalesi.

## <a name="refactoring"></a>Yeniden Düzenle

Mac için Visual Studio kodunuzu yeniden düzenlemeniz için iki yararlı yöntemleri sağlayan: bağlam eylemleri ve kaynak çözümleme. Daha fazla bilgiyi ilgili [Refactoring](~/refactoring.md) makalesi.

## <a name="debugging"></a>Hata Ayıklama

Mac için Visual Studio yerel hata ayıklayıcı bir izin verme hata ayıklama desteği Xamarin.iOS, Xamarin.Mac ve Xamarin.Android uygulamaları için vardır. Mac için Visual Studio Mono yumuşak Mono çalışma zamanına uygulanan tüm platformlarda yönetilen kodda hata ayıklama için IDE'yi izin vererek hata ayıklayıcı kullanır. Hata ayıklama ile ilgili ek bilgi için ziyaret [hata ayıklama](~/debugging.md) makalesi.

Hata ayıklayıcı dizeler, renkler, URL'ler, yanı sıra boyutları, ortak ordinates ve bézier eğrileri gibi özel türleri için zengin görselleştiriciler içerir.

Hata Ayıklayıcı'nın veri görselleştirmeleri ile ilgili daha fazla bilgi için ziyaret [veri görselleştirmeleri](~/data-visualizations.md) makalesi.

## <a name="version-control"></a>Sürüm Denetimi

Mac için Visual Studio Git ve alt sürüme kaynak denetimi sistemleriyle tümleştirilir. Kaynak denetimi altında projeleri çözüm adının yanındaki listelenen dal ile belirtilir: 

![Kaynak denetimi altında proje belirtmek için şube adı](media/ide-tour-image22.png)

Kaydedilmemiş dosyalarıyla değiştirilen açıklamanın simgelerine çözüm bölmesinde aşağıdaki görüntüde gösterildiği gibi vardır:

![Çözüm panelinde kaydedilmemiş dosyaları](media/ide-tour-image23.png)

Visual Studio'daki sürüm denetimi kullanma hakkında daha fazla bilgi için bkz: [sürüm denetimi](~/version-control.md) makalesi.