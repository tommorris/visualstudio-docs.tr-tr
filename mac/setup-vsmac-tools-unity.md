---
title: Mac araçları Unity için Visual Studio Kurulumu
description: Ayarlama ve Unity araçları kullanmak için Mac için Visual Studio yükleme
author: dantogno
ms.author: v-davian
ms.date: 07/17/2017
ms.assetid: 83FDD7A3-5D16-4B4B-9080-078E3FB5C623
ms.openlocfilehash: 4ad938530131a725e353a38cd481c871cb53bc9b
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="setup-visual-studio-for-mac-tools-for-unity"></a>Mac araçları Unity için Visual Studio Kurulumu

Bu bölümde, Mac araçları Unity için Visual Studio ile çalışmaya başlamak açıklanmaktadır.

## <a name="install-visual-studio-for-mac"></a>Mac için Visual Studio yükleme

İndirme ve Mac için Visual Studio yükleme Mac için Visual Studio'nin tüm sürümleri, Mac araçları ücretsiz Community sürümü de dahil olmak üzere Unity için Visual Studio destekler:

* Mac için Visual Studio indirme [visualstudio.com](https://www.visualstudio.com/).
* Mac araçları Unity için Visual Studio yükleme işlemi sırasında otomatik olarak yüklenir.
* Adımları [Yükleme Kılavuzu](/visualstudio/mac/installation) ek yükleme Yardım.

## <a name="confirm-that-the-visual-studio-for-mac-tools-for-unity-extension-is-enabled"></a>Visual Studio Mac araçları Unity uzantısı için etkinleştirilmiş olduğunu doğrulayın

Visual Studio için Unity uzantısı Mac araçları varsayılan olarak etkinleştirilmiş olmalıdır, ancak bu onaylayın ve yüklü sürüm numarasını kontrol edin:

1.  Visual Studio menüsünden seçin **uzantıları...** .

  ![Uzantıları seçin](media/setup-vsmac-tools-unity-image1.png)

2.  Oyun Geliştirme bölümü genişletin ve Visual Studio için Mac araçları için Unity girişi onaylayın.

  ![Görünümü Unity girişi](media/setup-vsmac-tools-unity-image2.png)

## <a name="install-unity"></a>Unity yükleyin

Mac araçları Unity için Visual Studio gerektirir Unity sürüm 5.6.1 veya üstü. Tüm Unity planlar boş kişisel planı dahil olmak üzere Unity için Visual Studio Araçları ile çalışır. Unity gelen indirme [store.unity.com](https://store.unity.com/).

> [!NOTE]
> Unity için Visual Studio Araçları Unity sürümünüzde etkinleştirildiğini doğrulamak için seçeneklerini **hakkında Unity** metni ara ve Unity menüden "Microsoft Visual Studio etkin Unity için iletişim kutusunun sol Araçları".
>
>   ![Unity hakkında](media/setup-vsmac-tools-unity-image3.png)

## <a name="configure-unity-for-use-with-visual-studio-for-mac"></a>Unity Mac için Visual Studio ile kullanılacak şekilde yapılandırma

Visual Studio, Unity dış betik düzenleyicisinde olarak ayarlamanız gerekir:

1.  Seçin **tercihleri...**  Unity menüsünde.

  ![Tercihler seçin](media/setup-vsmac-tools-unity-image4.png)

2.  Tercihler iletişim kutusunda seçin **Harici Araçlar** sekmesi.

3.  Dış komut dosyası düzenleyicisi açılır listeden seçin **Visual Studio** listeleniyorsa, aksi takdirde seçin **Gözat...** .

  ![Visual Studio seçin](media/setup-vsmac-tools-unity-image5.png)

4.  Varsa **Gözat...**  olan seçili, uygulamaları dizine gidin ve Visual Studio seçin ve ardından **açık**.

  ![Aç'ı seçin](media/setup-vsmac-tools-unity-image6.png)

5.  Visual Studio içinde seçildikten sonra **dış komut dosyası Düzenleyicisi** listesinde, yapılandırma işlemini tamamlamak için Tercihler iletişim kutusunu kapatın.
