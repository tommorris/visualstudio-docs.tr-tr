---
title: Metin bulma ve değiştirme
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.find
- vs.findreplacecontrol
- vs.findreplace.findsymbol
- vs.findreplace.symbol
- findresultswindow
- vs.findreplace.quickreplace
- vs.findsymbol
- vs.findinfiles
- vs.findresults1
- vs,findsymbolwindow
- vs.findreplace.quickfind
- vs.lookin
- vs.replace
helpviewer_keywords:
- text searches
- Replace in Files dialog box
- Find in Files dialog box
- text searches, finding and replacing text
- text, finding and replacing
- find and replace
- find text
- replace text
ms.assetid: a62545c3-1570-4d12-99fb-a82607eb35a1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7051b90dde45965b76e8a9e08b33b5326ff2848c
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="find-and-replace-text"></a>Metin bulma ve değiştirme

Bul ve Visual Studio düzenleyicisinde metin kullanarak değiştirin [bulma ve değiştirme](#find-and-replace-control) veya [bulun ve değiştirin dosyalarında](#find-in-files-and-replace-in-files).

> [!TIP]
> Kod simgeleri değişkenleri ve yöntemleri gibi yeniden adlandırma, daha iyi *[düzenleme](../ide/reference/rename.md)* Bul ve Değiştir kullanımı çok bunları. Yeniden düzenleme Akıllı ve Bul ve Değiştir doğrudan tüm örneklerini değiştirir ancak kapsam anlar.

Bul ve değiştir işlevselliği belirli diğer metin tabanlı Windows Düzenleyicisi'nde gibi **Bul sonuçları** windows, XAML Tasarımcısı ve Windows Forms Tasarımcısı gibi tasarımcı windows ve windows aracı.

Geçerli belge, geçerli çözüme veya özel bir klasör kümesi için arama kapsamını belirleyebilirsiniz. Birden çok dosya aramaları için dosya adı uzantılarını kümesi de belirtebilirsiniz. .NET kullanarak arama söz dizimi özelleştirme [normal ifadeler](../ide/using-regular-expressions-in-visual-studio.md).

> [!TIP]
> [Bul/komut](../ide/find-command-box.md) kutusu araç çubuğu denetimi olarak kullanılabilir, ancak varsayılan olarak görünmez. Görüntülenecek **Bul/komut** kutusunda **Düğme Ekle veya Kaldır** üzerinde **standart** araç ve ardından **Bul**.

## <a name="find-and-replace-control"></a>Bul ve Değiştir denetimi

**Bulma ve değiştirme** denetim kodu Düzenleyicisi penceresinin sağ üst köşesinde görüntülenir. **Bulma ve değiştirme** denetim hemen geçerli belgede verilen arama dizesi her geçtiği vurgular. Seçerek başka bir örnekten gidebilirsiniz **Sonrakini Bul** düğmesini veya **Öncekini Bul** arama denetimini düğmesinde.

![Bul ve Değiştir denetimi](media/find-and-replace-box.png)

Düğmenin yanında seçerek değiştirme seçenekleri erişebilirsiniz **Bul** metin kutusu. Bir seferde bir tane değişiklik yapmaya karar **Değiştir sonraki** düğmesine **Değiştir** metin kutusu. Tüm eşleşmeleri değiştirmek için tercih **Tümünü Değiştir** düğmesi.

İçin eşleşen vurgulama rengini değiştirmek için tercih **Araçları** menüsünde, select **seçenekleri**ve ardından **ortam**seçip **yazı tiplerini ve renkleri** . İçinde **ayarlarını göster** listesinden, **metin düzenleyici**ve ardından **görüntülemek öğeleri** listesinden, **Bul vurgulayın (uzantısı)**.

### <a name="search-tool-windows"></a>Arama Araç pencereleri

Kullanabileceğiniz **Bul** Windows'da, kod veya metin denetimini **çıkış** windows ve **Bul sonuçları** seçerek windows **Düzenle**  >  **Bulma ve değiştirme** veya tuşuna basarak **Ctrl + F**.

Bir sürümünü **Bul** denetim kullanılabilir ayrıca bazı araç pencereleri. Örneğin, denetimlerinde listesini filtreleyebilirsiniz **araç** arama kutusuna metin girerek penceresi. İçerikleri arama yapmanıza izin diğer aracı windows dahil **Çözüm Gezgini**, **özellikleri** penceresinde ve **Takım Gezgini**.

## <a name="find-in-files-and-replace-in-files"></a>Dosyaları ve dosyaları Değiştir Bul

**Bulma/değiştirme dosyalarında** gibi çalışır **bulma ve değiştirme** aramanız için bir kapsam tanımlayabilirsiniz dışında denetim. Yalnızca geçerli açık dosyayı düzenleyicide arayabilirsiniz, ancak ayrıca tüm belgeleri, çözümün tamamı, geçerli projenin açın ve klasör kümeleri seçili. Ayrıca, dosya adı uzantısına göre arama yapabilirsiniz. Erişmek için **bulun ve değiştirin dosyalarında** iletişim kutusunda **bulma ve değiştirme** üzerinde **Düzenle** menüsü veya basın **Ctrl + Shift + F**.

![Dosyalarda Bul iletişim kutusu](media/find-in-files-box.png)

### <a name="find-results"></a>Sonuçları Bul

Seçtiğinizde **Tümünü Bul**, **Bul sonuçları** penceresi açılır ve arama için eşleşen listeler. Listedeki bir sonuç seçilmesi ilişkili dosya görüntüler ve eşleşme vurgular. Dosyayı düzenlemek için açık değilse, bunu sekmesini sağ tarafındaki bir önizleme sekmesinde de açılır. Kullanabileceğiniz **bulmak** arama yapmak denetim **Bul sonuçları** listesi.

### <a name="create-custom-search-folder-sets"></a>Özel bir arama klasörü kümeleri oluşturma

Arama kapsamı seçerek tanımlayabilirsiniz **Arama Klasörleri Seç** düğmesini (gibi görünüyor **...** ) yanındaki **konum** kutusu. İçinde **Arama Klasörleri Seç** iletişim kutusu, klasörleri aramak için bir dizi belirtebilirsiniz ve böylece daha sonra yeniden belirtimi kaydedebilirsiniz.

> [!TIP]
> Yerel makinenize bir uzak makinenin sürücü eşlenen uzak makinede arama klasörleri belirtebilirsiniz.

### <a name="create-custom-component-sets"></a>Özel bileşen kümeleri oluşturma

Seçerek arama kapsamınızı bileşen kümeleri tanımlayabilirsiniz **özel bileşen kümesini Düzenle** düğmesine **konum** kutusu. Yüklü .NET veya COM bileşeni, çözümünüzü veya herhangi bir derleme veya Tür Kitaplığı'na Visual Studio projeleri belirtebilirsiniz (*.dll*, *.tlb*, *.olb*, *.exe*, veya *.ocx*). Başvuru arama yapmak için seçin **başvurularında Ara** kutusu.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da normal ifadeleri kullanma](../ide/using-regular-expressions-in-visual-studio.md)
- [Visual Studio'da kodu yeniden Düzenle](../ide/refactoring-in-visual-studio.md)