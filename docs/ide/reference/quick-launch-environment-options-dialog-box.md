---
title: Hızlı Başlatma, Ortam, Seçenekler İletişim Kutusu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.QuickLaunch
- vs.quicklaunch
helpviewer_keywords:
- searching IDE
- IDE, searching
ms.assetid: 4200f297-d065-4723-9a30-d91ff2e26c9d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad37856e8692d5182ddba4f80ec1c07aa095f674
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="quick-launch-environment-options-dialog-box"></a>Hızlı Başlatma, Ortam, Seçenekler İletişim Kutusu
Kullanabileceğiniz **hızlı başlatma** hızlı arama ve IDE varlıklar seçenekleri, şablonlar, menüler gibi eylemleri yürütün. Kullanamazsınız **hızlı başlatma** kod ve simgeleri aramak için. **Hızlı başlatma** arama kutusunu menü çubuğunu sağ üst köşesinde bulunan ve Ctrl + Q anahtarları seçerek erişilebilir olduğunu. Yalnızca arama dizenizle kutusuna girin. İçeren dizeleri aramak için @, Kullan ”@@”. 

 **Hızlı başlatma** Visual Studio yüklediğinizde varsayılan olarak etkindir. Menü çubuğunda, Göster Gizle veya **hızlı başlatma** seçerek **Araçları**, **seçenekleri**. Genişletme **ortamları** düğümünü ve ardından **Hızlı Başlat**. Seçin veya temizleyin **Hızlı Başlat'ı Etkinleştir** onay kutusu. Etkinleştirin veya bu sayfada arama kategorileri devre dışı bırakın.

## <a name="category-list"></a>Kategori Listesi
 Hızlı Başlatma arama sonuçları dört kategorilerde görüntülenir: **en son kullanılan**, **menüleri**, **seçenekleri**, ve **açık belgeleri**, ile birlikte kategorideki öğelerin sayısı. Kategoriye göre arama sonuçları arasında geçiş için sonraki kategorisinden tüm sonuçları görüntülemek için Ctrl + Q anahtarları'i seçin. Sonra en son kategori, Ctrl + Q her kategori birkaç sonuçlarını gösterir görüntülenir. Kategorilere ters sırada gitmek için Ctrl + Shift + Q kullanabilirsiniz. Bir kategori altında tüm arama sonuçları görüntülemek için kategori adı seçin.

 Aramanızı belirli kategorileri sınırlandırmak için aşağıdaki kısayollarını kullanabilirsiniz.

|Kategori|Kısayol|Kısayol açıklaması|
|--------------|--------------|--------------------------|
|Son Kullanılanlar|@mru<br /><br /> Örneğin, `@mru font`|Beş öğeleri kadar aldığınız görüntüler **en son kullanılan**.|
|Menüler|@menu<br /><br /> Örneğin, `@menu font`|Menü öğeleri arama sınırlanır.|
|Seçenekler|@opt<br /><br /> Örneğin, `@opt font`|Arama ayarları için sınırları **seçenekleri** iletişim kutusu.|
|Belgeler|@doc<br /><br /> Örneğin, `@doc font`|Dosya adlarını ve yollarını açık belgeleri aramak için arama ölçütlerini sınırlar, ancak dosyaları kendileri içindeki metni aramaz.|

> [!NOTE]
> Kısayol tuşları değiştirebileceğiniz **genel**, **klavye** sayfasındaki **seçenekleri** iletişim kutusu.


## <a name="show-previous-results"></a>Önceki sonuçları göster
 Varsayılan olarak, girdiğiniz arama terimiyle arama oturumları arasında kalıcı değildir. Arama dizesi, bir dönem için arama yaparsanız temizlendiğinde taşıma imleci dışında **hızlı başlatma** alan ve sonra Git yedekleyin. Arama sonuçlarını korumak için Git **seçenekleri** iletişim kutusunda, seçin **hızlı başlatma**ve ardından **Göster arama sonuçlarının önceki aramadan hızlı başlatma etkinleştirildiğinde.** onay kutusunu seçin. Bir arama yapın, hızlı başlat alanında bırakın ve geri gelen sonraki saat Hızlı Başlat son kullanılan arama terimi korumak ve ayrıca, arama sonuçlarını gösterir.

 En son ipuçları ve püf noktaları kullanmak için **hızlı başlatma**, bkz: [Visual Studio günlüğü](http://go.microsoft.com/fwlink/?LinkId=236054).

## <a name="see-also"></a>Ayrıca Bkz.

- [Genel kullanıcı arabirimi öğeleri (Visual Studio)](../../ide/reference/general-user-interface-elements-visual-studio.md)
- [Ortam Seçenekleri İletişim Kutusu](../../ide/reference/environment-options-dialog-box.md)