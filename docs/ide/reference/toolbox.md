---
title: Visual Studio'daki araç kutusu
ms.date: 01/18/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.toolbox.general
- vs.toolbox
helpviewer_keywords:
- Toolbox [Visual Studio]
- custom controls [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3f296349a6dfda80ff402b1ede0f1da591f6caa9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947095"
---
# <a name="toolbox"></a>Araç Kutusu

**Araç** penceresi, Visual Studio projelerine ekleme denetimlerini görüntüler. Araç kutusu açmak için **araç** üzerinde **Görünüm** menüsü.

![Araç penceresi](media/toolbox.png)

Farklı denetim kullanıyorsanız ve yeniden boyutlandırma ve denetimleri konumlandırmak Tasarımcı yüzeyine sürükleyip bırakabilirsiniz.

Araç kutusu gibi XAML dosyasının designer Görünüm Tasarımcısı görünümleri ile birlikte görüntülenir. Araç kutusu geçerli Tasarımcısı'nda kullanılabilen denetimleri görüntüler. Daha fazla filtre uygulamak için araç kutusu içinde görünen öğeleri arama yapabilirsiniz.

> [!NOTE]
> Bazı proje türleri için araç kutusu öğeleri gösterme.

.NET Framework sürümünü projenizi araç kutusunda görünür denetimleri kümesini de etkiler hedefler. Farklı bir .NET Framework sürümünü projenin özellik sayfalarından hedeflemek için projenizi ayarlayabilirsiniz. Proje düğümünde seçin **Çözüm Gezgini**ve ardından menü çubuğunda, **proje** > **\<proje\> özellikleri**. Üzerinde **uygulama** sekmesinde, kullanmak **hedef framework** açılır.

## <a name="managing-the-toolbox-window-and-its-controls"></a>Araç penceresi ve kendi denetimlerini yönetme

Varsayılan araç kutusunu Visual Studio IDE sol tarafında daraltılmış ve imleci üzerine taşındığında görüntülenir. Araç kutusu sabitleyebilirsiniz (tıklayarak **PIN** , araç çubuğundaki simgesini) açık kalmayacak şekilde taşıdığınızda imleci. Ayrıca, araç penceresi çıkar ve ekranınızda herhangi bir yere sürükleyin. Yerleştirme, çıkar ve araç, araç çubuğunu sağ tıklatıp seçeneklerden birini seçerek gizle.

Araç kutusu sekmesinde öğeleri yeniden düzenleyin veya bağlam menüsünde aşağıdaki komutları kullanarak özel sekmeler ve öğeleri ekleyin:

- **Öğeyi yeniden adlandırmak** -seçili öğeyi yeniden adlandırır.

- **Tümünü Göster** -tüm olası denetimleri (yalnızca geçerli Designer'a geçerli olanları) gösterir.

- **Liste görünümü** -denetimleri dikey listesini gösterir. Seçilmezse, denetimleri yatay olarak görünür.

- **Öğeleri seçin** -açar **araç kutusu öğelerini Seç** iletişim kutusu görünür öğeleri belirtebilirsiniz **araç**. Gösterebilir veya öğeyi seçerek veya onay kutusunu temizleyerek gizleyebilirsiniz.

- **Sıralama öğelerini alfabetik olarak** -öğeleri adına göre sıralar.

- **Araç çubuğunu sıfırlama** - varsayılan araç kutusunu ayarlarını geri yükler ve öğeleri.

- **Sekme ekleme** -yeni bir araç kutusu sekmesi ekler.

- **Yukarı Taşı** -seçili öğeyi yukarı taşır.

- **Aşağı Taşı** -seçilen öğeyi aşağı taşır.

## <a name="creating-and-distributing-custom-toolbox-controls"></a>Oluşturma ve dağıtma özel araç çubuğu denetimleri

Özel araç çubuğu denetimleri, temel alan bir proje şablonu biriyle başlangıç oluşturabileceğiniz [Windows Presentation Foundation](../../extensibility/creating-a-wpf-toolbox-control.md) veya [Windows Forms](../../extensibility/creating-a-windows-forms-toolbox-control.md). Ardından, özel denetim için kodunuza dağıtmak veya kullanarak Web'de Yayımlama [araç kutusu denetimleri yükleyici](http://download.microsoft.com/download/8/3/6/836657BD-9CCB-4ED4-B9D2-FB769473B284/TCI_whitepaper.docx).

## <a name="help-on-toolbox-tabs"></a>Araç kutusu sekmelerinde Yardım

Kullanılabilir bazıları hakkında daha fazla bilgi aşağıdaki konularda **araç** sekmeleri.

- [Araç Kutusu, Veri Sekmesi](../../ide/reference/toolbox-data-tab.md)

- [Araç Kutusu, Bileşenler Sekmesi](../../ide/reference/toolbox-components-tab.md)

- [Araç Kutusu, HTML Sekmesi](../../ide/reference/toolbox-html-tab.md)
