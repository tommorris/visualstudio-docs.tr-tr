---
title: Daraltma ve Visual Studio'da kodu bölgelerinin genişletin
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- outlining
- Visual Studio, expand/collapse code
- Visual Studio, outlining
- expand/collapse code
- code [Visual Studio], outlining
- code [Visual Studio], hiding
- outlining code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 62e6d5c7667bf697eeb190d69a996886fbee643f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="outlining"></a>Anahat Oluşturma

Artı işareti altında görünmesi bir bölge kodu daraltarak biraz kod görünümünden gizlemek seçebilirsiniz (**+**). Daraltılmış bölge artı işaretine tıklayarak genişletin. Klavye kullanıcısıysanız seçebileceğiniz **Ctrl**+**M**+**M** daraltın ve genişletin. Anahat bölge satırıyla kodunun sol yalnızca görünür anahat Kenar çubuğunda bölgede çift tıklayarak da daraltabilirsiniz. Daraltılmış bölgesini üzerine geldiğinizde, araç ipucu olarak daraltılmış bir bölge içeriğini görebilirsiniz.

Kenar boşluğu fareyle üzerine geldiğinizde anahat kenar boşluğu bölgelerde da vurgulanmıştır. Renk vurgulama varsayılan bazı renk yapılandırmalarda yerine soluk görünebilir. İçinde değiştirebileceğiniz **Araçları** > **seçenekleri** > **ortam** > **yazı tiplerini ve renkleri**  >  **Daraltılabilir bölge**.

Anahatları belirlenmiş kodda çalışırken, istediğiniz çalışma yapılır ve diğer bölümleri taşıma bunları Daralt bölümleri genişletebilirsiniz. Sahip olmasını istiyor musunuz anahat oluşturma görüntülenen, kullanabileceğiniz **durdurmak anahat oluşturma** temel kodunuzu etkilemeden anahat bilgileri kaldırmak için komutu.

**Geri** ve **Yinele** komutlarını **Düzenle** menü bu eylemleri etkiler. **Kopya**, **Kes**, **Yapıştır**, ve sürükle ve bırak işlemleri anahat bilgi ancak durumunda daraltılabilir bölgenin korur. Örneğin, daraltılıp, bölge kopyaladığınızda **Yapıştır** işlemi genişletilmiş bir bölge olarak kopyalanan metni yapıştırmak.

> [!CAUTION]
> Anahatları belirlenmiş bir bölgeyi değiştirdiğinizde, anahat oluşturma kaybolmuş olabilir. Örneğin, silme veya bulma ve değiştirme işlemleri bölge sonuna silebilir.

Aşağıdaki komutları bulunabilir **Düzenle** > **anahat** alt.

|||
|-|-|
|Seçimi Gizle|(**Ctrl**+**M**, **Ctrl**+**H**)-seçili değil normalde olacak kod bloğu daraltır Anahat oluşturma, örneğin için kullanılabilir bir `if` bloğu. Özel bölge kaldırmak için kullanın **gizleme geçerli Durdur** (veya **Ctrl**+**M**, **Ctrl** + **U**). Visual Basic'te kullanılamaz.|
|İki durumlu genişletme anahat oluşturma|-İç içe geçmiş bir daraltılmış bölümü imleci gerektiği zaman bölüm anahat oluşturma en içteki geçerli gizli veya genişletilmiş durumunu tersine çevirir.|
|Tüm anahat oluşturma Değiştir|(**Ctrl**+**M**, **Ctrl**+**L**)-aynı tüm bölgelere daraltılmış veya genişletilmiş durumuna ayarlar. Bazı bölgelerde genişletilir ve bazı daraltılmış, ardından daraltılmış bölgeler genişletilmiş.|
|Anahat oluşturma Durdur|(**Ctrl**+**M**, **Ctrl**+**P**)-tüm belgeyi tüm anahat bilgilerini kaldırır.|
|Geçerli gizleme Durdur|(**Ctrl**+**M**, **Ctrl**+**U**)-şu anda seçili anahat bilgilerini kaldırır Kullanıcı tanımlı bölgede. Visual Basic'te kullanılamaz.|
|Tanımları Daralt|(**Ctrl**+**M**, **Ctrl**+**O**)-tüm türleri üyeleri daraltır.|
|Daraltma engelle:\<mantıksal sınır >|(Visual C++) Ekleme noktasını içeren işlevi bir bölgede daraltır. Örneğin, ekleme noktasını bir döngü içinde yer alıyorsa, döngü gizlenir.|
|Tümünü Daralt: \<mantıksal yapıları >|(Visual C++) İşlevin içindeki tüm yapıları daraltır.|

Visual Studio SDK'sı, genişletmek veya daraltmak için istediğiniz metin bölgeleri tanımlamak için de kullanabilirsiniz. Bkz: [izlenecek yol: anahat oluşturma](../extensibility/walkthrough-outlining.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Düzenleyici'de kod yazma](../ide/writing-code-in-the-code-and-text-editor.md)
