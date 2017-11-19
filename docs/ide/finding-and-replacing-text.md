---
title: "Metin bulma ve değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
- find, text
- Find in Files dialog box
- find
- text searches, finding and replacing text
- Replace dialog box
- text, finding and replacing
- find, symbol
- find and replace
- replace
- find text
- replacing text
ms.assetid: a62545c3-1570-4d12-99fb-a82607eb35a1
caps.latest.revision: "31"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a2b925e32711e1624a4dfbe74fb5614ee6e0b062
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="finding-and-replacing-text"></a>Metin Bulma ve Değiştirme
Bul ve Visual Studio kod düzenleyicisini ve bazı metin tabanlı çıkış penceresine metni gibi değiştirin **Bul sonuçları** kullanarak windows **bulma ve değiştirme** denetim veya **bulmak / Dosyalarda Değiştir**. Ayrıca arama ve bazı XAML Tasarımcısı ve Windows Forms Tasarımcısı gibi tasarımcı windows ve windows aracı değiştirme  
  
 Geçerli belge, geçerli çözüme veya özel bir klasör kümesi için arama kapsamını belirleyebilirsiniz. Birden çok dosya aramaları için dosya adı uzantılarını kümesi de belirtebilirsiniz. .NET normal ifadeler kullanarak arama söz dizimi özelleştirebilirsiniz.  
  
 Bul ve Değiştir normal ifadeler için bkz: [Visual Studio'da normal ifadeler kullanarak](../ide/using-regular-expressions-in-visual-studio.md).  
  
> [!TIP]
>  **Bul/komut** kutusu araç çubuğu denetimi olarak hala kullanılabilir, ancak artık varsayılan olarak görünür. Görüntüleyebileceğiniz **Bul/komut** seçerek kutusunu **Düğme Ekle veya Kaldır** üzerinde **standart** araç çubuğu ve ardından seçme **Bul**. Daha fazla bilgi için bkz: [Bul/komut kutusu](../ide/find-command-box.md).  
  
## <a name="find-and-replace-control"></a>Bul ve Değiştir denetimi  
 **Bulma ve değiştirme** denetim kodu Düzenleyicisi penceresinin sağ üst köşesinde görüntülenir. **Bulma ve değiştirme** denetim hemen geçerli belgede verilen arama dizesi her geçtiği vurgular. Seçerek başka bir örnekten gidebilirsiniz **Sonrakini Bul** düğmesini veya **Öncekini Bul** arama denetimini düğmesinde.  
  
 Düğmenin yanında seçerek değiştirme seçenekleri erişebilirsiniz **Bul** metin kutusu. Bir seferde bir tane değişiklik yapmaya karar **Değiştir sonraki** düğmesine **Değiştir** metin kutusu. Tüm eşleşmeleri değiştirmek için tercih **Tümünü Değiştir** düğmesi.  
  
 İçin eşleşen vurgulama rengini değiştirmek için tercih **Araçları** menüsünde, select **seçenekleri**ve ardından **ortam**seçip **yazı tiplerini ve renkleri** . İçinde **ayarlarını göster** listesinden, **metin düzenleyici**ve ardından **görüntülemek öğeleri** listesinden, **Bul vurgulayın (uzantısı)**.  
  
### <a name="searching-tool-windows"></a>Araç pencereleri arama  
 Kullanabilirsiniz **Bul** Windows'da, kod veya metin denetimini **çıkış** windows ve **Bul sonuçları** seçerek windows **bulma ve değiştirme**üzerinde **Düzenle** menüsü veya (CTRL + F).  
  
 Bulma Denetimi sürümü bazı aracı Windows'da da mevcuttur. Örneğin, şimdi denetimlerinde listesini filtreleyebilirsiniz **araç** arama kutusuna metin girerek penceresi. Şimdi içeriklerini arama yapmanıza izin diğer aracı windows dahil **Çözüm Gezgini**, **özellikleri** penceresinde ve **Takım Gezgini**, diğerlerinin yanı sıra.  
  
## <a name="findreplace-in-files"></a>Dosyalarda Bul ve Değiştir  
 **Bulma/değiştirme dosyalarında** gibi çalışır **bulma ve değiştirme** aramanız için bir kapsam tanımlayabilirsiniz dışında denetim. Yalnızca geçerli açık dosyayı düzenleyicide arayabilirsiniz, ancak aynı zamanda arayabilirsiniz tüm açık belgeleri, çözümün tamamı, geçerli projenin ve klasör kümeleri seçili. Ayrıca, dosya adı uzantısına göre arama yapabilirsiniz. Erişim için **bulun ve değiştirin dosyalarında** iletişim kutusunda, seçin **bulma ve değiştirme** üzerinde **Düzenle** menü (veya CTRL + SHIFT + F).  
  
 Seçtiğinizde **Tümünü Bul**, **Bul sonuçları** penceresi açılır ve arama için eşleşen listeler. Listedeki bir sonuç seçilmesi ilişkili dosya görüntüler ve eşleşme vurgular. Dosyayı düzenlemek için açık değilse, bunu sekmesini sağ tarafındaki bir önizleme sekmesinde de açılır. Kullanabileceğiniz **bulmak** arama yapmak denetim **Bul sonuçları** listesi.  
  
### <a name="creating-custom-search-folder-sets"></a>Özel bir arama klasörü kümeleri oluşturma  
 Arama kapsamı seçerek tanımlayabilirsiniz **Arama Klasörleri Seç** düğmesini (gibi görünüyor **...** ) yanındaki **konum** kutusu. İçinde **Arama Klasörleri Seç** iletişim kutusu, bir dizi içinde arama yapmak istediğiniz klasörleri belirtin ve böylece daha sonra yeniden belirtimi kaydedebilirsiniz. Yalnızca yerel makineye sürücüsünü eşledikten uzak makinede klasörleri belirtebilirsiniz.  
  
### <a name="creating-custom-component-sets"></a>Özel bileşen kümeleri oluşturma  
 Seçerek arama kapsamınızı bileşen kümeleri tanımlayabilirsiniz **özel bileşen kümesini Düzenle** düğmesine **konum** kutusu. Yüklü .NET veya COM bileşeni, çözümünüzü veya (.dll, .tlb, .olb, .exe veya .ocx) herhangi derleme veya Tür Kitaplığı'na Visual Studio projeleri belirtebilirsiniz. Başvuru arama yapmak için seçin **başvurularında Ara** kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da normal ifadeler kullanma](../ide/using-regular-expressions-in-visual-studio.md)