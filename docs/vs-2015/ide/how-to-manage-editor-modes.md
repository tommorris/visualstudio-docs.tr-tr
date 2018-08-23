---
title: 'Nasıl yapılır: Düzenleyici modlarını yönetme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
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
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7e679c751f5d4e8aa23bb843f812476f2f9e9f5b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690450"
---
# <a name="how-to-manage-editor-modes"></a>Nasıl Yapılır: Düzenleyici Modlarını Yönetme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: Düzenleyici modlarını yönetme](https://docs.microsoft.com/visualstudio/ide/how-to-manage-editor-modes).  
  
Visual Studio Kod Düzenleyicisi çeşitli görüntüleme modlarında görüntüleyebilirsiniz.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="enabling-full-screen-mode"></a>Tam ekran modunu etkinleştirme  
 Tüm araç pencerelerini Gizle ve belge pencereleri etkinleştirerek görüntülemek seçebileceğiniz **tam ekran** modu.  
  
#### <a name="to-enable-full-screen-mode"></a>Tam ekran modunu etkinleştirmek için  
  
-   Girin ya da çıkmak için ALT + SHIFT + ENTER tuşlarına basın **tam ekran** modu.  
  
     --veya--  
  
-   Komutu Yürüt `View.Fullscreen` içinde **komut** penceresi.  
  
## <a name="enabling-virtual-space-mode"></a>Sanal alan modu etkinleştirme  
 İçinde **sanal adres alanı** modu, her kod satırının sonunda boşluklar eklenir. Kodunuzu yanındaki tutarlı bir noktada açıklamaları yerleştirmek için bu seçeneği belirleyin.  
  
#### <a name="to-enable-virtual-space-mode"></a>Sanal alan modu etkinleştirmek için  
  
1.  Seçin **seçenekleri** gelen **Araçları** menüsü.  
  
2.  Genişletin **metin düzenleyici** klasöründe ve **tüm diller** bu seçeneği genel olarak ayarlayın ya da belirli bir dil klasörü seçin. (Örneğin, yalnızca Visual Basic'te satır numaralarını etkinleştirmek için temel, metin düzenleyici seçenekleri seçin.)  
  
3.  Seçin **genel** seçenekleri altında **ayarları**seçin **sanal boşluğu etkinleştir**.  
  
    > [!NOTE]
    >  **Sanal adres alanı** etkin **sütun seçimi** modu. Zaman **sanal adres alanı** modu etkin değil, ekleme noktasını bir satır sonundan sonraki ilk karakteri için doğrudan taşır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düzenleyiciyi özelleştirme](../ide/customizing-the-editor.md)   
 [Nasıl yapılır: pencereleri düzenleme ve yerleştirme Windows](../misc/how-to-arrange-and-dock-windows.md)   
 [Yazı tipleri ve renkler, ortam, Seçenekler iletişim kutusu](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)



