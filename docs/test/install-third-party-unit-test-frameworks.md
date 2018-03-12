---
title: "Üçüncü şahıs birim test çerçevelerini yükleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c0cd7853c65d5501213076cb7ccb533c5134c9f4
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="install-third-party-unit-test-frameworks"></a>Nasıl yapılır: Üçüncü taraf birim testi çerçevelerini yükleme
Visual Studio Test Gezgini herhangi bir birimi bir bağdaştırıcı arabirimi Explorer geliştirmiştir test çerçevesi çalıştırabilirsiniz. Framework'ün yükleme programı ikilileri yükler ve onu destekleyen diller için Visual Studio Proje şablonları ekler. Şablonu kullanarak bir proje oluşturduğunuzda, framework Test Gezgini ile kaydedilir. Visual Studio çözümü farklı çerçeveler kullanan ve farklı dil hedeflenen birim testi projelerini içerebilir. Test Gezgini tümünü çalışır.  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise, Visual Studio Professional  
  
## <a name="acquiring-third-party-frameworks"></a>Üçüncü taraf çerçeveleri alınıyor  
 İndirin ve Visual Studio Uzantı Yöneticisi'ni kullanarak ya da Visual Studio marketten çok sayıda üçüncü taraf birim test çerçevelerini yükleyin. Çerçeveler framework'ün Web sitesi gibi diğer sitelerdeki de indirilebilir.  
  
### <a name="installing-from-visual-studio"></a>Visual Studio'dan yükleme  
  
1.  Seçin **Araçları** standart menüsünde ve ardından **Uzantılar ve güncelleştirmeler**.  
  
2.  Genişletme **çevrimiçi**, **Visual Studio Marketi'ine**, **Araçları**. Seçin **sınama**.  
  
3.  Framework bulmak için listeyi göz atın.  
  
4.  Framework seçin ve **karşıdan**.  
  
 Daha fazla bilgi için bkz: [bulma ve Visual Studio uzantılarını kullanarak](../ide/finding-and-using-visual-studio-extensions.md).  
  
### <a name="installing-from-the-web"></a>Web üzerinden yükleme  
 İlgilendiğiniz framework biliyorsanız:  
  
1.  Açık [Visual Studio Market'te](https://marketplace.visualstudio.com/vs).  
  
2.  Framework'ün adı **Bul** kutusu.  
  
3.  Aracı için Visual Studio Market'te sayfasına gitmek için sonuçlar listesinde framework seçin.  
  
 Diğer test araçları ile birlikte çerçeveleri listesini göz atmak için:  
  
1.  Açık [Visual Studio Market'te](https://marketplace.visualstudio.com/vs).  
  
2.  İçinde **kategoriye göre filtre / koleksiyon**, seçin **tümünü görmek**.  
  
3.  İçinde **kategori** listesi (olarak etiketli **gösteren**), genişletin **Araçları** düğümünü ve ardından **test**.  
  
4.  Aracı için Visual Studio Market'te sayfaya gitmek için sonuçları listesinde bir çerçeve seçin. 

## <a name="update-to-the-latest-test-adapters"></a>Son test bağdaştırıcıları güncelleştir

Daha iyi deneyim için en son kararlı test bağdaştırıcısı güncelleştirmeye bulma ve yürütme sınayın. Mstest'i, NUnit ve xUnit test bağdaştırıcıları güncelleştirmeleri hakkında daha fazla bilgi için bkz: [Visual Studio blog](https://blogs.msdn.microsoft.com/visualstudio/2017/11/16/test-experience-improvements/).

### <a name="to-update-to-the-latest-stable-test-adapter-version"></a>En son kararlı test bağdaştırıcısı sürüme güncelleştirmek için

1. Giderek çözümünüz için Nuget Paket Yöneticisi'ni açmak **Araçlar > NuGet Paket Yöneticisi > çözüm için NuGet paketlerini Yönet...**

2. Tıklayın **güncelleştirmeleri** sekmesi ve NUnit veya xUnit aramak için test yüklü olan bağdaştırıcıları.

3. Her test bağdaştırıcısı seçin ve sonra da açılan menüden en yeni kararlı sürüm seçin.

4. Seçin **yükleme** düğmesi.

![Yükseltme testi bağdaştırıcısı](media/installadapter-upgrade.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuza Birim Testi Uygulama](../test/unit-test-your-code.md)
