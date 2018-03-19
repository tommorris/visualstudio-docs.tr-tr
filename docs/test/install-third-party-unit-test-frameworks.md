---
title: "Visual Studio'da üçüncü şahıs birim test çerçevelerini yükleme | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: dcf255e68076ff0ffffb2e36d8e276f19b2b313a
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="install-third-party-unit-test-frameworks"></a>Nasıl yapılır: Üçüncü taraf birim testi çerçevelerini yükleme

Visual Studio Test Gezgini herhangi bir birimi bir bağdaştırıcı arabirimi Explorer geliştirmiştir test çerçevesi çalıştırabilirsiniz. Framework'ün yükleme programı ikilileri yükler ve onu destekleyen diller için Visual Studio Proje şablonları ekler. Şablonu kullanarak bir proje oluşturduğunuzda, framework Test Gezgini ile kaydedilir. Visual Studio çözümü farklı çerçeveler kullanan ve farklı dil hedeflenen birim testi projelerini içerebilir. Test Gezgini tümünü çalışır.

## <a name="acquiring-third-party-frameworks"></a>Üçüncü taraf çerçeveleri alınıyor

İndirin ve Visual Studio Uzantı Yöneticisi'ni kullanarak ya da Visual Studio marketten çok sayıda üçüncü taraf birim test çerçevelerini yükleyin. Çerçeveler framework'ün Web sitesi gibi diğer sitelerdeki de indirilebilir.

### <a name="installing-from-visual-studio"></a>Visual Studio'dan yükleme

1. Seçin **Araçları** standart menüsünde ve ardından **Uzantılar ve güncelleştirmeler**.

2. Genişletme **çevrimiçi** > **Visual Studio Marketi'ine** > **Araçları**. Seçin **sınama**.

3. Framework bulmak için listeyi göz atın.

4. Framework seçin ve **karşıdan**.

Daha fazla bilgi için bkz: [bulma ve Visual Studio uzantılarını kullanarak](../ide/finding-and-using-visual-studio-extensions.md).

### <a name="installing-from-the-web"></a>Web üzerinden yükleme

İlgilendiğiniz framework biliyorsanız:

1. Açık [Visual Studio Market'te](https://marketplace.visualstudio.com/vs).

2. Framework'ün adı **Bul** kutusu.

3. Aracı için Visual Studio Market'te sayfasına gitmek için sonuçlar listesinde framework seçin.

Diğer test araçları ile birlikte çerçeveleri listesini göz atmak için:

1. Açık [Visual Studio Market'te](https://marketplace.visualstudio.com/vs).

2. İçinde **kategoriye göre filtre / koleksiyon**, seçin **tümünü görmek**.

3. İçinde **kategori** listesi (olarak etiketli **gösteren**), genişletin **Araçları** düğümünü ve ardından **test**.

4. Aracı için Visual Studio Market'te sayfaya gitmek için sonuçları listesinde bir çerçeve seçin.

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)
