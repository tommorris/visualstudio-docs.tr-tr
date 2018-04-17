---
title: Belgeler, ortam, Seçenekler iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
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
ms.openlocfilehash: 49ac0d5aa5d621e7f6b833827057aeebba9a5181
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="documents-environment-options-dialog-box"></a>Belgeler, Ortam, Seçenekler İletişim Kutusu
Bu sayfanın kullanmak **seçenekleri** tümleşik geliştirme ortamı (IDE) belgelerde görüntülenmesini denetlemek ve dış değişiklikleri belgeleri ve dosyaları yönetmek için iletişim kutusu. Tıklatarak bu iletişim kutusuna erişebilirsiniz **seçenekleri** üzerinde **Araçları** menüsüne ve ardından seçerek **belgeleri** içinde **ortam** düğümü. Varsa **belgeleri** listesinde select görünmez **tüm ayarları göster** içinde **seçenekleri** iletişim kutusu.  
  
> [!NOTE]
>  İletişim kutuları, adları ve menü komutlarını, gördüğünüz konumlarını Seçenekleri Yardımı'nda etkin ayarlarınıza veya sürümünüze bağlı olarak açıklanan nedir alanından farklı olabilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  
  
 **Geçerli belge penceresine kaydettiyseniz yeniden**  
 Kaydedilmiş olan ve yeni bir belge aynı pencerede açar, seçili olduğunda, geçerli belgenizi kapatır. Geçerli belgenizi kaydedilmedi, açık kalır ve yeni belge ayrı bir pencerede açılır. Bu seçeneği temizlenirse, yeni belgeler her zaman ayrı pencerelerde açılır.  
  
 Çoklu Belge Kesme gerçekleştirmek ve yapıştırma işlemlerini seyrek ve açık belgeler ve windows çalışma alanınıza sayısını en aza indirmek istiyorsanız bu seçeneği deneyin.  
  
 **Dosya ortamı dışında değiştirildiğinde Algıla**  
 Bu seçenek belirlendiğinde, bir ileti hemen açık bir dosyayı IDE dışında bir düzenleyici tarafından yapılan değişiklikleri bildirir. İleti, depolama biriminden dosyayı yeniden olanak tanır.  
  
 **Otomatik değişiklikleri kaydettiyseniz yük**  
 Olduğunda **algılamak dosya ortamı dışında değiştirildiğinde** seçili ve IDE değiştiğinde bir uyarı iletisi IDE dışında açık bir dosyanın varsayılan olarak oluşturulur. Bu seçenek etkinleştirilirse, herhangi bir uyarı görünür ve dış değişiklikleri almak için IDE'yi belgeyi yeniden yüklendi.  
  
 **Salt okunur dosya düzenleme izni; ne zaman uyar kaydetmeyi deneyin**  
 Bu seçenek etkinleştirildiğinde açın ve salt okunur bir dosyayı düzenleyin. İşiniz bittiğinde, kullanmalısınız **Kaydet**kaydını yaptığınız değişiklikleri kaydetmek istiyorsanız, yeni bir ad tarafından dosyayı kaydetmek için komutu.  
  
 **Etkin belge dizini kullanarak dosya Aç**  
 Seçili olduğunda, bu seçenek belirtir **açık dosya** etkin belgeyi dizin iletişim kutusunu görüntüler. Bu seçenek temizlendiğinde **Dosya Aç** bir dosyayı açmak için en son kullanılan dizin iletişim kutusunu görüntüler.  
  
 **Tutarlı satır sonları yükü denetle**  
 Bir dosyada satır sonları tarama ve satır sonları nasıl biçimlendirileceğini içinde tutarsızlıklar algılanırsa, bir ileti kutusu görüntüleme Düzenleyicisi sağlamak için bu seçeneği belirleyin.  
  
 **Genel Geri Al değişiklik yaptığınızda görünen uyarı dosyalar düzenlenebilir**  
 Bir ileti görüntülemek için bu seçeneği belirleyin kutusunu **genel Geri Al** komutu geri alacaktır sonra yeniden düzenleme işlemi de değiştirilen dosyalarında yapılan düzenleme değişiklikleri. Bir dosya öncesi yeniden düzenleme durumuna döndürme sonradan dosyasında yapılan değişiklikleri atmak.  
  
 **Çeşitli dosyalar Çözüm Gezgini'nde Göster**  
 Görüntülemek için bu seçeneği belirleyin **çeşitli dosyalar** düğümünde **Çözüm Gezgini**. Çeşitli dosyalar dosyalardır proje ya da çözüm ile ilişkili değildir ancak görüntülenebilir **Çözüm Gezgini** size kolaylık sağlamak için.  
  
> [!NOTE]
>  Etkinleştirmek için bu seçeneği belirleyin **tarayıcıda görüntüle** komutunu **dosya** etkin Web uygulamasında dahil edilmeyen Web belgelerini menüsü.  
  
 **\<** *n* **> çeşitli dosyalar projede kaydedilen öğeleri**  
 Sızmak dosyası sayısını belirtir **MiscellaneousFiles** klasöründe **Çözüm Gezgini**. Artık bir düzenleyicide açık olsalar bile, bu dosyalar listelenir. Bir tam sayı 0'dan 256 belirtebilirsiniz. Varsayılan numarası 0'dır.  
  
 Bu seçenek 5 olarak ayarlayın ve tüm 10 dosyaları kapattığınızda 10 çeşitli dosyalar açık, varsa, örneğin, ilk 5 hala gösterilecek **çeşitli dosyalar** klasör.  
  
 **Veri kod sayfasında kaydedildiğinde Unicode olarak belgeleri kaydetme**  
 Varsayılan olarak Unicode olarak kaydedilecek seçili kod sayfası ile uyumsuz bilgilerini içeren dosyalar neden için bu seçeneği belirleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ortam Seçenekleri iletişim kutusu](../../ide/reference/environment-options-dialog-box.md)   
 [Çeşitli dosyalar](../../ide/reference/miscellaneous-files.md)   
 [Metin Bulma ve Değiştirme](../../ide/finding-and-replacing-text.md)