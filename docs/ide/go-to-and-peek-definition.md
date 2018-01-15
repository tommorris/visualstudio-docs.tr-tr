---
title: "Visual Studio'da tür tanımları görüntüleme | Microsoft Docs"
ms.custom: 
ms.date: 01/10/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code editor, view definition
- go to definition
- peek definition
- type definition [Visual Studio]
- member definition [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 945eb6e905613d3d068321e2d5993f4506036963
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="view-type-and-member-definitions"></a>Tür ve üye tanımları görüntüle

Geliştiriciler genellikle kendi kodunda türleri veya kullandıkları sınıf üyeleri için kaynak kodu tanımları görüntülemeniz gerekir. Visual Studio'da Tanıma Git ve Peek tanımı özelliklerini kolayca bir tür veya üye tanımının görüntülemenizi sağlar. Meta veriler kaynak kodunu kullanılabilir durumda değilse, bunun yerine görüntülenir.

## <a name="go-to-definition"></a>Tanıma gitme

Tanıma Git özelliğini bir tür veya üye kaynağına gider ve sonucu yeni bir pencerede açılır. Klavye kullanıcısıysanız metin imlecinizi basın ve sembol adını içinde yere yerleştirin **F12**. Fare kullanıcısıysanız seçin **Tanıma Git** bağlam menüsünden veya kullanım **CTRL tuşuna basıp tıklayın** aşağıdaki bölümde açıklanan işlevselliği.

### <a name="ctrl-click-go-to-definition"></a>CTRL tuşuna basıp tıklayın Tanıma Git

Visual Studio 2017 içinde sürüm 15.4, fare kullanıcıların Tanıma Git hızlı bir şekilde erişmek kolay bir yolu yoktur. Simgeler hale tıklanabilir bastığınızda **Ctrl** ve tür veya üye üzerine getirin. Hızlı bir şekilde bir simge tanımına gezinmek için basın **Ctrl** anahtar ve ardından ona tıklayın. Kolay!

![Fare tıklatma tanımı animasyon Git](../ide/media/click_gotodef.gif)

Fare tıklatma değiştirici tuşa değiştirebileceğiniz **Tanıma Git** giderek **Araçları**, **seçenekleri**, **Metin Düzenleyicisi**, **Genel**, ya da seçerek **Alt** veya **Ctrl + Alt** gelen **kullanım değiştirici tuşa** açılır. Fare tıklatma de devre dışı bırakabilirsiniz **Tanıma Git** kaldırarak **Tanıma Git gerçekleştirmek için etkinleştir fare tıklatma** onay kutusu.

![Fare tıklatma etkinleştirme tanımına gidin](../ide/media/editor_options_mouse_click_gotodef.png)

## <a name="peek-definition"></a>Özet tanımı

Peek tanımı özellik geçerli konumunuz Düzenleyicisi'nde ayrılmadan bir tür tanımını Önizleme olanak sağlar. Klavye kullanıcısıysanız metin imlecinizi basın ve tür veya üye adı içinde bir yere yerleştirin **Alt + F12**. Fare kullanıcısıysanız seçebileceğiniz **Peek tanımı** ve bağlam menüsünden. Visual Studio 2017 içinde 15.4 ve sonraki sürümleri, yoktur gözlem görünüm tanımı için yeni bir yol fareyi kullanarak. İlk olarak, Git **Araçları**, **seçenekleri**, **metin düzenleyici**, **genel**. Seçeneğini **tanımı gözlem görünümünde açmak** tıklatıp **Tamam** kapatmak için **seçenekleri** iletişim kutusu.

![Fare tıklatma gözlem tanımı seçeneği ayarlama](../ide/media/editor_options_peek_view.png)

Daha sonra basın **Ctrl** (veya hangi değiştirici tuşa seçili **seçenekleri**) ve tür veya üye'ye tıklayın.

![Tanımı animasyon Gözat](../ide/media/peek_definition.gif)

Açılan pencerede başka bir tanımından peek varsa daire ve açılan görünür oklarını kullanarak gidebilirsiniz bir içerik haritası yolu başlar.

Daha fazla bilgi için bkz: [nasıl yapılır: görüntüleme ve düzenleme kod kullanarak Peek tanımını (Alt + F12) tarafından](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md).

## <a name="view-metadata-as-source-code-c"></a>Kaynak kodu (C#) olarak meta verilerini görüntüleme

C# türleri veya üyeleri tanımını görüntülediğinizde kimin sahip kaynak kod kullanılabilir değilse, bunların meta verilerini bunun yerine görüntülenir. Türleri ve üyeleri ancak kendi uygulamalarını bildirimlerini görebilirsiniz.

Çalıştırdığınızda **Tanıma Git** veya **Peek tanımı** kaynak kodu kullanılamıyor, bir öğenin bu öğeye ait meta verileri, kaynak kodu görüntülenen bir görünümünü içeren sekmeli belge komutu Kod Düzenleyicisi'nde görüntülenir. Türünün adını ve ardından **[from meta verileri]**, belgenin sekmesinde görünür.

Örneğin çalıştırırsanız **Tanıma Git** komutunu <xref:System.Console>, meta verileri <xref:System.Console> Kod düzenleyicisinde C# kaynak kodu olarak görünür. Kod bildiriminden benzer, ancak şimdi uygulaması göstermez.

![Kaynak olarak meta veriler](../ide/media/metadatasource.png "MetadataSource")

> [!NOTE]
> Çalıştırmak çalıştığınızda **Tanıma Git** veya **Peek tanımı** komut türleri veya dahili olarak işaretlenmiş üyeleri için Visual Studio görüntülemez bunların meta verilerini bağımsız olarak mı yoksa kaynak kodu başvuruda bulunan bir arkadaş veya derlemesidir.

### <a name="view-decompiled-source-definitions-instead-of-metadata-c"></a>Meta veriler (C#) yerine kaynak tanımları decompiled görüntüle

Yeni **Visual Studio 2017 sürüm 15,6 Önizleme 2**, C# tür veya üye tanımının görüntülediğinizde decompiled kaynak kodu görmek için bir seçenek belirleyebilirsiniz kimin sahip kaynak kodu kullanılamıyor. Bu özelliği etkinleştirmek için tercih **Araçları** > **seçenekleri** menü çubuğundan. Ardından, **metin düzenleyici** > **C#** > **Gelişmiş**seçip **etkinleştirmek decompiled kaynaklarınaGezinti**.

![Decompiled tanımı görüntüleme](media/go-to-definition-decompiled-sources.png)

> [!NOTE]
> Visual Studio yöntem gövdeleri ILSpy kaynak koda dönüştürme kullanarak yeniden oluşturur. Bu özelliğe erişmek ilk kez ticari marka yasaları ve yazılım lisans ve telif hakkı ilgili yasal Sorumluluklar kabul gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Kodda gezinme](../ide/navigating-code.md)  
[Nasıl yapılır: Özet Tanımı'nı Kullanarak Kodu Görüntüleme ve Düzenleme (Alt+F12)](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)
