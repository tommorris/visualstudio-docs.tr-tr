---
title: Visual Studio'da görüntüleme tür tanımları
ms.date: 01/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- code editor, view definition
- go to definition
- peek definition
- type definition [Visual Studio]
- member definition [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 529486e39db57228feb703817eea44fab9399c85
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745769"
---
# <a name="view-type-and-member-definitions"></a>Görünüm türü ve üye tanımları

Geliştiriciler genellikle kendi kodunda türleri veya kullandıkları sınıf üyeleri için kaynak kodu tanımları görüntülemeniz gerekir. Visual Studio'da **Tanıma Git** ve **Peek tanımı** özelliklerini kolayca bir tür veya üye tanımını görüntüleme olanak tanır. Meta veriler kaynak kodunu kullanılabilir durumda değilse, bunun yerine görüntülenir.

## <a name="go-to-definition"></a>Tanıma gitme

**Tanıma Git** özelliği bir tür veya üye kaynağına gider ve sonucu yeni bir pencerede açılır. Klavye kullanıcısıysanız metin imlecinizi basın ve sembol adını içinde yere yerleştirin **F12**. Fare kullanıcısıysanız seçin **Tanıma Git** bağlam menüsünden veya kullanım **CTRL tuşuna basıp tıklayın** aşağıdaki bölümde açıklanan işlevselliği.

### <a name="ctrl-click-go-to-definition"></a>CTRL tuşuna basıp tıklayın Tanıma Git

Visual Studio 2017 içinde sürüm 15.4, hızlı bir şekilde erişmek için fare kullanıcılar için daha kolay bir yolu yoktur **Tanıma Git**. Simgeler hale tıklanabilir bastığınızda **Ctrl** ve tür veya üye üzerine getirin. Hızlı bir şekilde bir simge tanımına gezinmek için basın **Ctrl** anahtar ve ardından ona tıklayın. Kolay!

![Fare tıklatma tanımı animasyon Git](../ide/media/click_gotodef.gif)

Fare tıklatma değiştirici tuşa değiştirebileceğiniz **Tanıma Git** giderek **Araçları** > **seçenekleri** > **metin düzenleyicisi**   >  **Genel**, ya da seçerek **Alt** veya **Ctrl + Alt** gelen **kullanım değiştirici tuşa**açılır. Fare tıklatma de devre dışı bırakabilirsiniz **Tanıma Git** kaldırarak **Tanıma Git gerçekleştirmek için etkinleştir fare tıklatma** onay kutusu.

![Fare tıklatma etkinleştirme tanımına gidin](../ide/media/editor_options_mouse_click_gotodef.png)

## <a name="peek-definition"></a>Özet tanımı

**Peek tanımı** özellik geçerli konumunuz Düzenleyicisi'nde ayrılmadan bir tür tanımını Önizleme olanak sağlar. Klavye kullanıcısıysanız metin imlecinizi basın ve tür veya üye adı içinde bir yere yerleştirin **Alt + F12**. Fare kullanıcısıysanız seçebileceğiniz **Peek tanımı** ve bağlam menüsünden. Visual Studio 2017 içinde 15.4 ve sonraki sürümleri, yoktur gözlem görünüm tanımı için yeni bir yol fareyi kullanarak. İlk olarak, Git **Araçları** > **seçenekleri** > **metin düzenleyici** > **genel**. Seçeneğini **tanımı gözlem görünümünde açmak** tıklatıp **Tamam** kapatmak için **seçenekleri** iletişim kutusu.

![Fare tıklatma gözlem tanımı seçeneği ayarlama](../ide/media/editor_options_peek_view.png)

Daha sonra basın **Ctrl** (veya hangi değiştirici tuşa seçili **seçenekleri**) ve tür veya üye'ye tıklayın.

![Tanımı animasyon Gözat](../ide/media/peek_definition.gif)

Açılan pencerede başka bir tanımından peek varsa daire ve açılan görünür oklarını kullanarak gidebilirsiniz bir içerik haritası yolu başlar.

Daha fazla bilgi için bkz: [nasıl yapılır: Gözat tanımı (Alt + F12) kullanarak görüntüleme ve düzenleme kod](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md).

## <a name="view-metadata-as-source-code-c"></a>Kaynak kodu (C#) olarak meta verilerini görüntüleme

C# türleri veya kaynak kodu kullanılamıyor üyeleri tanımını görüntülediğinizde, bunların meta verilerini bunun yerine görüntülenir. Türleri ve üyeleri ancak kendi uygulamalarını bildirimlerini görebilirsiniz.

Çalıştırdığınızda **Tanıma Git** veya **Peek tanımı** kaynak kodu kullanılamıyor, bir öğenin bu öğeye ait meta verileri, kaynak kodu görüntülenen bir görünümünü içeren sekmeli belge komutu Kod Düzenleyicisi'nde görüntülenir. Türünün adını ve ardından **[from meta verileri]**, belgenin sekmesinde görünür.

Örneğin çalıştırırsanız **Tanıma Git** komutunu <xref:System.Console>, meta verileri <xref:System.Console> Kod düzenleyicisinde C# kaynak kodu olarak görünür. Kod bildiriminden benzer, ancak uygulama göstermez.

![Kaynak olarak Meta Veriler](../ide/media/metadatasource.png)

> [!NOTE]
> Çalıştırmak çalıştığınızda **Tanıma Git** veya **Peek tanımı** komut türleri veya dahili olarak işaretlenmiş üyeleri için Visual Studio görüntülemez bunların meta verilerini bağımsız olarak mı yoksa kaynak kodu başvuruda bulunan bir arkadaş veya derlemesidir.

### <a name="view-decompiled-source-definitions-instead-of-metadata-c"></a>Meta veriler (C#) yerine kaynak tanımları decompiled görüntüle

Yeni Visual Studio 2017 içinde sürüm 15,6, C# türü veya kaynak kodu kullanılamıyor üye tanımının görüntülediğinizde decompiled kaynak kodu görmek için bir seçenek belirleyebilirsiniz. Bu özelliği etkinleştirmek için tercih **Araçları** > **seçenekleri** menü çubuğundan. Ardından, **metin düzenleyici** > **C#** > **Gelişmiş**seçip **etkinleştirmek decompiled kaynaklarınaGezinti**.

![Decompiled tanımı görüntüleme](media/go-to-definition-decompiled-sources.png)

> [!NOTE]
> Visual Studio yöntem gövdeleri ILSpy kaynak koda dönüştürme kullanarak yeniden oluşturur. Bu özelliğe erişmek ilk kez ticari marka yasaları ve yazılım lisans ve telif hakkı ilgili yasal Sorumluluklar kabul gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [Kod gidin](../ide/navigating-code.md)
- [Nasıl yapılır: Gözat tanımı (Alt + F12) kullanarak görüntüleme ve düzenleme kod](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)