---
title: İçin Mac araçları Unity için Visual Studio kullanarak
description: Bu kılavuz, Unity uzantısı için Mac araçları Visual Studio kullanmayı açıklar
author: dantogno
ms.author: v-davian
ms.date: 07/17/2017
ms.assetid: 83FDD7A3-5D16-4B4B-9080-078E3FB5C623
ms.openlocfilehash: 4044169508b177ff5524ee024479244595661eab
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="using-visual-studio-for-mac-tools-for-unity"></a>İçin Mac araçları Unity için Visual Studio kullanarak

Bu bölümde, Visual Studio için Mac araçları Unity'nın tümleştirme ve verimlilik özellikleri için nasıl kullanılacağı ve Mac hata ayıklayıcı Unity geliştirme için Visual Studio kullanmayı öğreneceksiniz.

## <a name="opening-unity-scripts-in-visual-studio-for-mac"></a>Mac için Visual Studio'da Unity komut dosyaları açma

Mac için Visual Studio olduğunda [Unity için dış betik düzenleyicisi olarak ayarlamak](/visualstudio/mac/setup-vsmac-tools-unity#configure-unity-for-use-with-visual-studio-for-mac), Unity Düzenleyicisi'nden herhangi komut dosyasının açılması otomatik olarak başlar veya seçilen komut dosyası, Mac için Visual Studio anahtarıyla açın.

Alternatif olarak, Mac için Visual Studio ile kaynak Düzenleyicisi'nde açık betik seçerek açılabilen **C# proje Aç** gelen **varlıklar** Unity menüde.

![C# proje Aç](media/using-vsmac-tools-unity-image1.png)

## <a name="unity-documentation-access"></a>Unity belgelerine erişim

Mac araçları Unity için Visual Studio Unity API belgelerine erişmek için bir kısayol içerir. Mac için Visual Studio'dan Unity API belgelerine erişmek için imleci Unity hakkında bilgi edinin ve basın API yerleştirin **⌘ komutu + '**.

## <a name="intellisense-for-unity-messages"></a>Unity iletileri için IntelliSense
Unity altyapısı MonoBehaviour komut dosyaları, iletilere OnMouseDown, vb. OnTriggerEnter tepki verdiğini kod yazmaya geliştiriciler izin vererek iletileri yayımlar. Bu sanal yöntemler temel MonoBehaviour sınıfta olmadığından, MonoDevelop gibi bazı IDE Unity iletileri için kod tamamlama işlevselliği yoksundur.

Ancak, Mac araçları Unity için Visual Studio Unity iletileri için IntelliSense işlevselliği genişletir. Bu Unity iletileri MonoBehaviour komut dosyalarında uygulamak kolaylaştırır ve Unity API öğrenmeye yardımcı olur. Unity iletiler için IntelliSense kullanmak için:

1.  İmleci MonoBehaviour türeyen bir sınıf gövdesi içinde yeni bir satıra getirin.

2.  Gibi bir Unity adını yazarak Başlangıç iletisi `OnTriggerEnter`.

3.  Bir kez harf "**yazı tipi**", IntelliSense öneriler listesi görüntülenir yazmış.

  ![IntelliSense Kullanma](media/using-vsmac-tools-unity-image2.png)

4.  Seçim listesindeki üç yolla değiştirilebilir:

    * İle **yukarı** ve **aşağı** ok tuşları.

    * İstenen öğe üzerinde fareyle tıklatarak.

    * İstenen öğe adını yazmaya devam ederek.

5.  IntelliSense, gerekli tüm parametreleri de dahil olmak üzere seçili Unity iletiyi ekleyebilirsiniz:

    * Basarak **sekmesini**.

    * Basarak **iade**.

    * Seçili öğeyi çift tıklatarak.

  ![IntelliSense Unity ileti Ekle](media/using-vsmac-tools-unity-image3.png)

## <a name="adding-new-unity-files-and-folders"></a>Yeni Unity dosyalar ve klasörler ekleme

Unity Düzenleyicisi'nde Unity projeye yeni dosyaları her zaman ekleyebilirsiniz, ancak yeni Unity komut dosyaları, gölgelendiriciler ve Visual Studio içinde klasörlerden kolayca oluşturmak için Visual Studio Mac için sağlar.

### <a name="add-a-new-c-monobehaviour-script"></a>Yeni bir C# MonoBehaviour komut dosyası Ekle

Yeni bir C# MonoBehaviour komut dosyası eklemek için **varlıklar klasörüne sağ** ya da çözüm paneli seçip dizinlerinden biri **Ekle > Yeni MonoBehaviour**.

![Yeni MonoBehaviour ekleme](media/using-vsmac-tools-unity-image4.png)

### <a name="add-a-new-unity-shader"></a>Yeni bir Unity gölgelendirici ekleme

Yeni bir Unity gölgelendirici eklemek için **varlıklar klasörüne sağ** ya da bir alt çözüm paneli seçip **Ekle -> Yeni gölgelendirici**.

### <a name="add-a-new-folder"></a>Yeni bir klasör ekleyin

Yeni bir klasör eklemek için **varlıklar klasörüne sağ** ya da bir alt çözüm paneli seçip **Ekle > Yeni bir klasör**.

Bu eklemeleri Unity Düzenleyicisi'ni proje penceresinde yansıtılır.

### <a name="to-rename-a-file-or-folder"></a>Bir dosya veya klasör yeniden adlandırmak için
**sağ** çözümde yeniden adlandırmak için öğeyi doldurur ve seçin **yeniden adlandır...** .

> [!NOTE]
> Komut dosyası yeni Unity projesi varsa ve varlıklar klasörü Visual Studio'da Çözüm panelinde Mac için gösterilmez, bir ilk C# betikten Unity Düzenleyicisi içinde ekleyin.

## <a name="unity-debugging"></a>Unity hata ayıklama

Unity projeleri Visual Studio ile Mac için hata ayıklaması yapılabilir

### <a name="start-debugging"></a>Hata ayıklama başlatılamıyor

Hata ayıklama başlatmak için:

1.  Tıklayarak Unity için Visual Studio bağlanmak **Yürüt** düğmesini veya türü **Command + dönmek**, veya **F5**.

  ![Visual Studio'da Kullan'ı tıklatın](media/using-vsmac-tools-unity-image5.png)

2.  Geçiş Unity'ye tıklayın **Yürüt** oyun Düzenleyicisi'nde çalıştırmak için düğmesi.

  ![Unity Kullan'ı tıklatın](media/using-vsmac-tools-unity-image6.png)

3.  Visual Studio'ya bağlıyken Unity Düzenleyicisi'nde oyun çalıştırırken, karşılaştı kesme oyun yürütülmesini Duraklat ve burada oyun Mac için Visual Studio'da kesme noktası isabet kod satırı Getir

### <a name="stop-debugging"></a>Hata ayıklamayı durdurun

Hata ayıklamayı durdurmak için:

1.  Tıklatın **durdurmak** Mac veya basın için Visual Studio düğmesini **Shift + Command + dönmek**.

  ![Visual Studio'da Durdur düğmesini tıklatın](media/using-vsmac-tools-unity-image7.png)

Mac için Visual Studio'da hata ayıklama hakkında daha fazla bilgi için bkz: [hata ayıklayıcıyı kullanma](https://docs.microsoft.com/visualstudio/mac/debugging).
