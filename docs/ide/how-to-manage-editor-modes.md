---
title: Visual Studio tam ekran ve sanal alan modu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- word wrap
- views, virtual space
- line numbers, displaying
- virtual space mode
- line numbers
- Code Editor, view and display options
- full screen mode
- Code Editor, modes
- views, splitting
- views, word wrapping
- fonts and size
- views, creating new windows
- views, line numbers
- views, changing mode
- views, outlining
ms.assetid: 1fb48027-d870-439f-8b72-4a0321390748
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 94bc99bf70340ef76639d0ae0f05e1f7737173a2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-manage-editor-modes"></a>Nasıl yapılır: Düzenleyici modlarını yönetme

Visual Studio kod düzenleyicisini çeşitli görüntü modları görüntüleyebilirsiniz.

> [!NOTE]
> İletişim kutuları ve menü komutlarını gördüğünüz etkin ayarlarınıza veya edition bağlı olarak bu makaledeki açıklanana farklı olabilir. Ayarlarınızı, örneğin değiştirmek için **genel** veya **Visual C++** ayarları seçebilirsiniz **Araçları** > **içeri ve dışarı aktarma ayarları**ve ardından **tüm ayarlara**.

## <a name="enable-full-screen-mode"></a>Tam ekran modunu etkinleştir

Tüm aracı windows gizlemek ve yalnızca belge pencereleri etkinleştirerek görüntülemek seçebileceğiniz **tam ekran** modu.

-   Tuşuna **Alt**+**Shift**+**Enter** girin ya da çıkmak için **tam ekran** modu.

     --ya da--

-   Komutu Yürüt `View.Fullscreen` içinde **komutu** penceresi.

## <a name="enable-virtual-space-mode"></a>Sanal alan modu etkinleştir

İçinde **sanal adres alanı** modu, boşluk, her kod satırının sonuna eklenir. Kodunuzu yanındaki tutarlı bir noktada açıklamaları konumlandırmak için bu seçeneği belirleyin.

1.  Seçin **seçenekleri** gelen **Araçları** menüsü.

2.  Genişletin **metin düzenleyici** klasörünü seçin **tüm diller** bu seçenek genel olarak ayarlamak veya belirli bir dil klasörü seçin. Örneğin, Visual Basic'te yalnızca satır numaraları etkinleştirmek için tercih **temel** > **metin düzenleyici** düğümü.

3.  Seçin **genel** seçenekleri ve altında **ayarları**seçin **etkinleştirmek sanal adres alanı**.

    > [!NOTE]
    > **Sanal alan** etkin **sütun seçimi** modu. Zaman **sanal adres alanı** modu etkin değil, ekleme noktasını bir satır sonundan sonraki ilk karakteri için doğrudan taşır.

## <a name="see-also"></a>Ayrıca bkz.

- [Düzenleyiciyi özelleştirme](../ide/customizing-the-editor.md)
- [Visual Studio'da pencere düzenlerini özelleştirme](../ide/customizing-window-layouts-in-visual-studio.md)
- [Yazı tipleri ve renkler, ortam, Seçenekler iletişim kutusu](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)