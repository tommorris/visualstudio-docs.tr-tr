---
title: Visual studio tam ekran ve sanal alan modu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0f6535c656c512d5c849a8a5d8d2fb37319aa883
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-manage-editor-modes"></a>Nasıl yapılır: Düzenleyici modlarını yönetme
Visual Studio kod düzenleyicisini çeşitli görüntü modları görüntüleyebilirsiniz.  
  
> [!NOTE]
> İletişim kutuları ve menü komutlarını gördüğünüz etkin ayarlarınıza veya edition bağlı olarak bu makaledeki açıklanana farklı olabilir. Ayarlarınızı, örneğin değiştirmek için **genel** veya **Visual C++** ayarları seçebilirsiniz **Araçları**, **içeri ve dışarı aktarma ayarları**ve ardından seçin **tüm ayarlara**.
  
## <a name="enabling-full-screen-mode"></a>Tam ekran modunu etkinleştirme  
Tüm aracı windows gizlemek ve yalnızca belge pencereleri etkinleştirerek görüntülemek seçebileceğiniz **tam ekran** modu.  
  
#### <a name="to-enable-full-screen-mode"></a>Tam ekran modunu etkinleştirmek için  
  
-   Tuşuna **Alt**+**Shift**+**Enter** girin ya da çıkmak için **tam ekran** modu.  
  
     --ya da--  
  
-   Komutu Yürüt `View.Fullscreen` içinde **komutu** penceresi.  
  
## <a name="enabling-virtual-space-mode"></a>Sanal alan modu etkinleştirme  
İçinde **sanal adres alanı** modu, boşluk, her kod satırının sonuna eklenir. Kodunuzu yanındaki tutarlı bir noktada açıklamaları konumlandırmak için bu seçeneği belirleyin.  
  
#### <a name="to-enable-virtual-space-mode"></a>Sanal alan modu etkinleştirmek için  
  
1.  Seçin **seçenekleri** gelen **Araçları** menüsü.

2.  Genişletin **metin düzenleyici** klasörünü seçin **tüm diller** bu seçenek genel olarak ayarlamak veya belirli bir dil klasörü seçin. Örneğin, Visual Basic'te yalnızca satır numaraları etkinleştirmek için temel, metin düzenleyici düğümü seçin.
  
3.  Seçin **genel** seçenekleri ve altında **ayarları**seçin **etkinleştirmek sanal adres alanı**.  
  
    > [!NOTE]
    >  **Sanal alan** etkin **sütun seçimi** modu. Zaman **sanal adres alanı** modu etkin değil, ekleme noktasını bir satır sonundan sonraki ilk karakteri için doğrudan taşır.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Düzenleyiciyi özelleştirme](../ide/customizing-the-editor.md)   
[Visual Studio'da pencere düzenlerini özelleştirme](../ide/customizing-window-layouts-in-visual-studio.md)   
[Yazı tipleri ve renkler, ortam, Seçenekler iletişim kutusu](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)