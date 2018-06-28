---
title: Mac araçları Unity için Visual Studio Kurulumu
description: Ayarlama ve Unity araçları kullanmak için Mac için Visual Studio yükleme
author: dantogno
ms.author: v-davian
ms.date: 05/25/2018
ms.assetid: 83FDD7A3-5D16-4B4B-9080-078E3FB5C623
ms.openlocfilehash: 6e5e6b90350aa16d4e0ffee04673a1aa1063cded
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057105"
---
# <a name="setup-visual-studio-for-mac-tools-for-unity"></a>Mac araçları Unity için Visual Studio Kurulumu

Bu bölümde, Mac araçları Unity için Visual Studio ile çalışmaya başlamak açıklanmaktadır.

## <a name="install-visual-studio-for-mac"></a>Mac için Visual Studio yükleme

### <a name="unity-bundled-installation"></a>Unity paket yükleme

Unity 2018.1 ile başlayarak, Mac için Visual Studio, C# IDE Unity için varsayılandır ve Unity karşıdan yükleme Yardımcısı, aynı zamanda Unity hub'ı yükleme aracı eklenir. Unity gelen indirme [store.unity.com](https://store.unity.com/).

Yükleme sırasında Mac için Visual Studio ile Unity yüklenecek bileşenleri listesinde işaretli olduğundan emin olun:

#### <a name="unity-hub"></a>Unity Hub

![Unity hub'ı yükleme](media/setup-vsmac-tools-unity-image7.png)

#### <a name="unity-download-assistant"></a>Unity Yükleme Yardımcısı

![Unity karşıdan yükleme Yardımcısı'nı yükleme](media/setup-vsmac-tools-unity-image8.png)

#### <a name="check-for-updates-to-visual-studio-for-mac"></a>Mac için Visual Studio Güncelleştirmeleri denetle

Unity yüklemeye dahil Mac için Visual Studio sürümü en son olmayabilir. En son araçları ve özellikleri erişiminiz olduğundan emin olmak güncelleştirmeleri denetlemek için önerilir.

* [Mac için Visual Studio güncelleştirme](update.md)

### <a name="manual-installation"></a>El ile yükleme

Unity 5.6.1 zaten varsa veya üstü, ancak Visual Studio için Mac yoksa, Mac için Visual Studio el ile yükleyebilirsiniz. Mac için Visual Studio'nin tüm sürümleri, Mac araçları ücretsiz Community sürümü de dahil olmak üzere Unity için Visual Studio ile paketlendi:

* Mac için Visual Studio indirme [visualstudio.microsoft.com](https://visualstudio.microsoft.com/).
* Mac araçları Unity için Visual Studio yükleme işlemi sırasında otomatik olarak yüklenir.
* Adımları [Yükleme Kılavuzu](installation.md) ek yükleme Yardım.

> [!NOTE]
> Mac araçları Unity için Visual Studio gerektirir Unity sürüm 5.6.1 veya üstü. Unity için Visual Studio Araçları Unity sürümünüzde etkinleştirildiğini doğrulamak için seçeneklerini **hakkında Unity** metni ara ve Unity menüden "Microsoft Visual Studio etkin Unity için iletişim kutusunun sol Araçları".
>
> ![Unity hakkında](media/setup-vsmac-tools-unity-image3.png)

## <a name="confirm-that-the-visual-studio-for-mac-tools-for-unity-extension-is-enabled"></a>Visual Studio Mac araçları Unity uzantısı için etkinleştirilmiş olduğunu doğrulayın

Visual Studio için Unity uzantısı Mac araçları varsayılan olarak etkinleştirilmiş olmalıdır, ancak bu onaylayın ve yüklü sürüm numarasını kontrol edin:

1. Visual Studio menüsünden seçin **uzantıları...** .

  ![Uzantıları seçin](media/setup-vsmac-tools-unity-image1.png)

1. Oyun Geliştirme bölümü genişletin ve Visual Studio için Mac araçları için Unity girişi onaylayın.

  ![Görünümü Unity girişi](media/setup-vsmac-tools-unity-image2.png)

## <a name="configure-unity-for-use-with-visual-studio-for-mac"></a>Unity Mac için Visual Studio ile kullanılacak şekilde yapılandırma

Unity 2018.1 ile başlayarak, Visual Studio Unity varsayılan dış betik düzenleyicisinde olmalıdır. Bunu doğrulamak veya Visual Studio için dış betik Düzenleyicisi'ni değiştirin:

1. Seçin **tercihleri...**  Unity menüsünde.

  ![Tercihler seçin](media/setup-vsmac-tools-unity-image4.png)

1. Tercihler iletişim kutusunda seçin **Harici Araçlar** sekmesi.

1. Dış komut dosyası düzenleyicisi açılır listeden seçin **Visual Studio** listeleniyorsa, aksi takdirde seçin **Gözat...** .

  ![Visual Studio seçin](media/setup-vsmac-tools-unity-image5.png)

1. Varsa **Gözat...**  olan seçili, uygulamaları dizine gidin ve Visual Studio seçin ve ardından **açık**.

  ![Aç'ı seçin](media/setup-vsmac-tools-unity-image6.png)

1. Visual Studio içinde seçildikten sonra **dış komut dosyası Düzenleyicisi** listesinde, yapılandırma işlemini tamamlamak için Tercihler iletişim kutusunu kapatın.
