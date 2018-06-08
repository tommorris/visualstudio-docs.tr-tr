---
title: 'Nasıl yapılır: Üçüncü taraf birim testi çerçevelerini yükleme'
ms.date: 06/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d0994b226a80385e381fa7b738c0194ec393d87a
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844701"
---
# <a name="install-third-party-unit-test-frameworks"></a>Nasıl yapılır: Üçüncü taraf birim testi çerçevelerini yükleme

Visual Studio Test Gezgini herhangi bir birimi bir bağdaştırıcı arabirimi Explorer geliştirmiştir test çerçevesi çalıştırabilirsiniz. Framework'ün yükleme programı ikilileri yükler ve onu destekleyen diller için Visual Studio Proje şablonları ekler. Şablonu kullanarak bir proje oluşturduğunuzda, framework Test Gezgini ile kaydedilir. Visual Studio çözümü farklı çerçeveler kullanan ve farklı dil hedeflenen birim testi projelerini içerebilir. Test Gezgini tümünü çalışır.

## <a name="acquire-third-party-frameworks"></a>Üçüncü taraf çerçeveleri Al

İndirin ve Visual Studio Uzantı Yöneticisi'ni kullanarak ya da Visual Studio marketten çok sayıda üçüncü taraf birim test çerçevelerini yükleyin. Çerçeveler framework'ün Web sitesi gibi diğer sitelerdeki de indirilebilir.

### <a name="install-from-visual-studio"></a>Visual Studio'dan yükleyin

1. Seçin **Araçları** standart menüsünde ve ardından **Uzantılar ve güncelleştirmeler**.

2. Genişletme **çevrimiçi** > **Visual Studio Marketi'ine** > **Araçları**. Seçin **sınama**.

3. Framework bulmak için listeyi göz atın.

4. Framework seçin ve **karşıdan**.

Daha fazla bilgi için bkz: [bulabilir ve Visual Studio uzantıları](../ide/finding-and-using-visual-studio-extensions.md).

### <a name="install-from-the-web"></a>Web'den yükleme

İlgilendiğiniz framework biliyorsanız:

1. Açık [Visual Studio Market'te](https://marketplace.visualstudio.com/vs).

2. Framework'ün adı **Bul** kutusu.

3. Aracı için Visual Studio Market'te sayfasına gitmek için sonuçlar listesinde framework seçin.

Diğer test araçları ile birlikte çerçeveleri listesini göz atmak için:

1. Açık [Visual Studio Market'te](https://marketplace.visualstudio.com/vs).

2. İçinde **kategoriye göre filtre / koleksiyon**, seçin **tümünü görmek**.

3. İçinde **kategori** listesi (olarak etiketli **gösteren**), genişletin **Araçları** düğümünü ve ardından **test**.

4. Aracı için Visual Studio Market'te sayfaya gitmek için sonuçları listesinde bir çerçeve seçin.

## <a name="update-to-the-latest-test-adapters"></a>Son test bağdaştırıcıları güncelleştir

Daha iyi deneyim için en son kararlı test bağdaştırıcısı güncelleştirmeye bulma ve yürütme sınayın. Mstest'i, NUnit ve xUnit test bağdaştırıcıları güncelleştirmeleri hakkında daha fazla bilgi için bkz: [Visual Studio blog](https://blogs.msdn.microsoft.com/visualstudio/2017/11/16/test-experience-improvements/).

### <a name="to-update-to-the-latest-stable-test-adapter-version"></a>En son kararlı test bağdaştırıcısı sürüme güncelleştirmek için

1. Giderek çözümünüz için Nuget Paket Yöneticisi'ni açmak **Araçları** > **NuGet Paket Yöneticisi** > **ÇözümiçinNuGetpaketleriniYönet**.

2. Tıklayın **güncelleştirmeleri** sekmesi ve NUnit veya xUnit aramak için test yüklü olan bağdaştırıcıları.

3. Her test bağdaştırıcısı seçin ve sonra da açılan menüden en yeni kararlı sürüm seçin.

4. Seçin **yükleme** düğmesi.

   ![Yükseltme testi bağdaştırıcısı](media/install-adapter-upgrade.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Birim testi kodunuz](../test/unit-test-your-code.md)
