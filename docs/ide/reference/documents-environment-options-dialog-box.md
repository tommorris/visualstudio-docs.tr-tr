---
title: Belgeler, Ortam, Seçenekler İletişim Kutusu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.Environment.Documents
- VS.ToolsOptionsPages.Environment.Documents
- VS.ToolsOptionsPag.Environment.Documents
helpviewer_keywords:
- Documents Environment Options dialog box
- defaults, directories
- error messages, customizing
- files [Visual Studio], default options
- files [Visual Basic], auto-loading modified
- windows, customizing environment
- in-memory editing
- folders [Visual Studio], specifying where Open File goes
- Open File dialog box
- windows, enabling re-use of current
- notifications, files changed
- files [Visual Studio], displaying in Solution Explorer
- default directories
- read-only files, editing
- Options dialog box, showing Miscellaneous Files
- directories [Visual Studio], IDE environment options
- Options dialog box, Documents page
- warnings, files changed
- Solution Explorer, displaying files in
ms.assetid: 4e3ccf1b-cd68-4db6-9470-710c911b47fc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ceccf3c051e3c85fa4b8e64ecbc33c388e9a884f
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178188"
---
# <a name="documents-environment-options-dialog-box"></a>Belgeler, Ortam, Seçenekler İletişim Kutusu
Bu sayfanın kullanın **seçenekleri** tümleşik geliştirme ortamında (IDE) belgeler görüntülenmesini denetlemek ve dış değişiklikler belgelerinizi ve dosyalarınızı yönetmek için iletişim kutusu. Bu iletişim kutusuna tıklayarak erişebilirsiniz **seçenekleri** üzerinde **Araçları** menüsüne ve ardından seçerek **belgeleri** içinde **ortam** düğümü. Varsa **belgeleri** listesinde seçin görünmüyor **tüm ayarları göster** içinde **seçenekleri** iletişim kutusu.

> [!NOTE]
> İletişim kutuları, adları ve konumları gördüğünüz gibi menü komutlarının Seçenekleri Yardımı'nda, etkin ayarlarınıza ve sürüm bağlı olarak açıklanan nedir öğesinden farklı olabilir. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).


 **Kaydedilmiş ise mevcut belge penceresini yeniden** kaydedildi ve yeni bir belge aynı pencerede açılır seçildiğinde, geçerli belge kapatır. Geçerli belgeyi kaydedilmemiş açık kalır ve yeni belge ayrı bir pencerede açılır. Bu seçenek işaretli değilse, yeni belgeler, her zaman ayrı bir pencerede açabilirsiniz.

 Çok Belgeli Kes'i gerçekleştirme ve işlemleri nadiren yapıştırın ve açık belgeler veya çalışma alanınızı windows sayısını en aza indirmek istiyorsanız bu seçeneği deneyin.

 **Dosya ortamı dışında değiştirildiğinde Algıla** bu seçenek belirlendiğinde, bir ileti hemen açık bir dosyayı IDE dışında bir düzenleyici tarafından yapılan değişiklikleri bildirir. İleti depolama biriminden dosyayı yeniden olanak sağlar.

 **Otomatik değişiklik kaydettiyseniz Yükle** olduğunda **dosya ortamı dışında değiştirildiğinde Algıla** seçili ve açık bir dosyayı bir uyarı iletisi IDE dışında IDE değişiklikleri varsayılan olarak oluşturulur. Bu seçenek etkinleştirilirse, herhangi bir uyarı görünür ve belge dış değişiklikleri almak için IDE'de yüklenir.

 **Salt okunur dosyaları düzenlemeye izin ver; uyar kaydetme girişiminde** bu seçenek etkinleştirildiğinde açın ve bir salt okunur dosyasını düzenleyin. İşlemi tamamladığınızda, kullanmalısınız **Kaydet**kaydını yaptığınız değişiklikleri kaydetmek istiyorsanız, dosyayı yeni bir adla kaydetmek için komutu.

 **Etkin belge dizini kullanarak dosya Aç** seçildiğinde bu seçenek, belirtir **Dosya Aç** etkin belgeyi dizinden iletişim kutusu görüntüler. Bu seçenek temizlendiğinde **Dosya Aç** bir dosyayı açmak için en son kullanılan dizin iletişim kutusunu görüntüler.

 **Tutarlı satır sonlarını denetle** Düzenleyici bir dosyada satır sonları tarama ve satır sonlarını nasıl biçimlendirileceğini içinde tutarsızlıklar algılanırsa bir ileti kutusu görüntülemek için bu seçeneği belirleyin.

 **Genel geri al işlemi görünen uyarı düzenlenmiş dosyaları** bir ileti görüntülemek için bu seçeneği kutusunu **genel Geri Al** komut geri sonra değiştirilen dosyalarda yapılan düzenleme değişiklikleri yeniden düzenleme işlemi. Bir dosya öncesi yeniden düzenleme durumuna geri döndürme dosyasında yapılan sonraki değişikliklerin at.

 **Çözüm Gezgini'nde diğer dosyaları göster** görüntülemek için bu seçeneği belirleyin **çeşitli dosyalar** düğümünde **Çözüm Gezgini**. Çeşitli dosyalar bir proje veya çözüm ile ilişkili olmayan ancak görünebilen dosyalarıdır **Çözüm Gezgini** size kolaylık sağlamak için.

> [!NOTE]
> Etkinleştirmek için bu seçeneği belirleyin **tarayıcıda görüntüle** komutunu **dosya** etkin web uygulamasında yer almayan web belgeler için menü.

 **\<** *n* **> diğer dosyalar projesinde kaydedilmiş öğeler** sızmak için dosya sayısını belirtir **MiscellaneousFiles** klasörü **Çözüm Gezgini**. Artık bir düzenleyicide açık olsalar bile bu dosyalar listelenir. Bir tam sayı 0'dan 256 belirtebilirsiniz. Varsayılan sayı 0'dır.

 Bu seçenek 5 ayarlanmış ve 10 dosyanın tamamı kapattığınızda, 10 çeşitli dosyalar açık, varsa, örneğin, ilk 5 hala gösterilecek **çeşitli dosyalar** klasör.

 **Veri kod sayfasına kaydedildiğinde belgeleri Unicode olarak Kaydet** neden Unicode olarak varsayılan olarak kaydedilmesi için seçilen kod sayfasıyla uyumsuz bilgi içeren dosyaları için bu seçeneği belirleyin.

## <a name="see-also"></a>Ayrıca Bkz.

- [Ortam Seçenekleri İletişim Kutusu](../../ide/reference/environment-options-dialog-box.md)
- [Çeşitli Dosyalar](../../ide/reference/miscellaneous-files.md)
- [Metin Bulma ve Değiştirme](../../ide/finding-and-replacing-text.md)