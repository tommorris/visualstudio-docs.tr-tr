---
title: "Erişilebilirlik | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 08/15/2017
ms.topic: article
ms.assetid: 2C4AAC2E-3B4A-4496-8BE0-1F5A7F81D1CA
ms.openlocfilehash: 13c69a1c13507a0f856bc652f7ffa0e5ab233081
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="accessibility"></a>Erişilebilirlik

Özellikleri ve macOS yardımcı programlara ek olarak, Visual Studio Mac için daha erişilebilir engelli kişiler için kolaylaştırarak aşağıdaki özelliklere sahiptir:

- Çözüm ve düzenleyici klavye takımı metin büyütme
- Düzenleyicilerde metin boyutu seçenekleri
- Düzenleyicilerde renk özelleştirme
- Klavye kısayolu özelleştirme
- Yöntem ve parametreler için kod tamamlama 

MacOS erişilebilirlik özellikleri hakkında daha fazla bilgi için bkz: [Apple'nın Web sitesi](https://www.apple.com/accessibility/mac/).

## <a name="using-accessibility-features-in-visual-studio-for-mac"></a>Mac için Visual Studio'da erişilebilirlik özelliklerini kullanma

Mac için Visual Studio'da erişilebilirlik özellikleri varsayılan olarak kapalıdır. Bunları etkinleştirmek için aşağıdaki adımları uygulayın:

1. Git **Visual Studio > Tercihler > Diğer > Erişilebilirlik**.

2. Seçin **etkinleştirmek erişilebilirlik** aşağıdaki çizimde gösterildiği gibi onay kutusunu:

    ![Erişilebilirlik onay kutusunu etkinleştir](media/accessibility-image1.png)

3. Tuşuna **Visual Studio'yu yeniden başlatın** erişilebilirlik özellikleri etkili şekilde düğmesi.


Alternatif olarak, erişilebilirlik özelliklerini etkinleştirmek için komut satırını kullanabilirsiniz. Bunu yapmak için terminal içinde aşağıdaki komutu girin: 

```bash
defaults write com.microsoft.visual-studio com.monodevelop.AccessibilityEnabled 1 
```

Erişilebilirliği etkinleştirdikten sonra Visual Studio yeniden başlatmanız gerekir.

## <a name="how-to-use-keyboard-navigation"></a>Nasıl yapılır: klavye gezinti kullanın

Klavye gezinme, tam Klavye erişimi seçeneğini ayarlayarak etkinleştirilebilir **sistem tercihleri > klavye > kısayolları** için **tüm denetimler**:

  ![Macos sistemleri Tercihler panelinde](media/accessibility-image2.png)

Tam klavye erişimini ayarını odak dikdörtgeni etkinleştirir. Daha sonra kullanarak denetimleri seçebilirsiniz:
- Denetimlerde İleri Git sekmesi
- Geriye dönük denetimlerde gitmek için Shift-sekmesi
- Oklar yönünü denetimlerinde arasında gezinmek için ok tuşları. 

Ara çubuğu tuşlarına odaklı denetimin etkinleştirir.

## <a name="how-to-enable-and-use-voice-over"></a>Nasıl yapılır: etkinleştirme ve ses üzerinden kullanma

VoiceOver tuşuna açılıp **Cmd CTRL + F5**

UI VoiceOver komutları gitmek için aşağıdaki komutları kullanın:

- VoiceOver imleç denetimler arasında taşıma: **Ctrl + Alt + Sol ok tuşunu / sağ ok tuşu**

Denetimleri, bazı ayrıntıları ve onunla yapabileceklerinizi adını çıkışı voiceOver okur. 

- Grupları ve denetimleri (örneğin, çözüm paneli, araç ve diğer klavye takımı) girin: **Ctrl + Alt + üst karakter + aşağı ok**

İçindeki bir denetim, kullandığınız sonra **Ctrl + Alt + okları** içinde hareket etmek için. 
 
MacOS içinde VoiceOver kullanma hakkında genel bilgi için aşağıdaki kılavuzlara bakın:

- [VoiceOver ile çalışmaya başlama](https://help.apple.com/voiceover/info/guide/10.12/)
- [MacOS voiceOver komutları](http://lab.dotjay.com/notes/voiceover-commands/)
