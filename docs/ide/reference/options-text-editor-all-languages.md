---
title: "Seçenekler, metin düzenleyici, tüm diller | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.JavaScript.General
- VS.ToolsOptionsPages.Text_Editor.ResJSON.General
- vs.toolsoptionspages.text_editor.all_languages.scrollbars
helpviewer_keywords:
- Text Editor Options dialog box
- statement completion
- word wrap
- General dialog box
- line numbers
- virtual space
ms.assetid: 49ee7306-9d46-4170-850f-a1716171752d
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3ef5133f1d92d9f18a62117e40a0788766dfe439
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="options-text-editor-all-languages"></a>Seçenekler, Metin Düzenleyici, Tüm Diller
Bu iletişim kutusu, Kod Düzenleyicisi'nin varsayılan davranışı değiştirmenizi sağlar. Bu ayarlar üzerinde kod düzenleyicisinde, HTML Tasarımcısı kaynağı görünümü gibi temel diğer düzenleyiciler için de geçerlidir. Bu iletişim kutusunu açmak için seçin **seçenekleri** gelen **Araçları** menüsü. İçinde **metin düzenleyici** klasörünü genişletin **tüm diller** alt ve ardından **genel**.  
  
> [!CAUTION]
>  Bu sayfayı tüm geliştirme diller için varsayılan seçeneklerini ayarlar. Bu iletişim kutusunda bir seçenek sıfırlama tüm dillerde genel seçenekler ne olursa olsun seçenekler burada seçilen için sıfırlar olduğunu unutmayın. Metin Düzenleyici seçenekleri yalnızca bir dil için değiştirmek için o dil için alt klasörü genişletin ve seçenek sayfaları seçin.  
  
 Genel Seçenekler sayfalarında bazı programlama dilleri, ancak için diğer bir seçenek seçili gri bir onay işareti görüntülenir.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="statement-completion"></a>Deyim Tamamlama  
 Otomatik liste üyeleri  
 Düzenleyicide yazarken seçili olduğunda, kullanılabilir üyeler, özellikler, değerler veya yöntemleri açılır listeleri IntelliSense tarafından görüntülenir. Kodunuza öğesi eklemek için açılır listeden herhangi bir öğeyi seçin. Bu seçenek belirlendiğinde **üyeleri Gelişmiş Gizle** seçeneği.  
  
 Gelişmiş üyeler Gizle  
 Seçili olduğunda, yalnızca en sık kullanılan öğelerini görüntüleyerek açılır deyimi tamamlanma listeleri kısaltır. Diğer öğeler listeden filtrelenir.  
  
 Parametre bilgileri  
 Seçili olduğunda, tam sözdizimi geçerli bildirimi veya yordamı için tüm kullanılabilir parametrelerle düzenleyicisinde ekleme noktasını altında görüntülenir. Atayabilirsiniz sonraki parametrenin kalın olarak görüntülenir.  
  
## <a name="settings"></a>Ayarlar  
 Sanal alan etkinleştir  
 Bu seçenek seçildiğinde ve **sözcük kaydırma** olan temizlenmiş, herhangi bir yere kod düzenleyicisini ve türü bir satır sonundan tıklayabilirsiniz. Bu özellik, tutarlı bir noktada kodunuzun yanındaki açıklamaları konumlandırmak için kullanılabilir.  
  
 Sözcük kaydırma  
 Seçili olduğunda, herhangi bir kısmının görüntülenebilir Düzenleyicisi alanı yatay genişleten bir satır sonraki satırında otomatik olarak görüntülenir. Bu seçenek belirlendiğinde **Göster sözcük kaydırma için görsel karakterlerinin** seçeneği.  
  
> [!NOTE]
>  **Sanal adres alanı** özelliğin açık kapalı while **Kaydır** açıktır.  
  
 Sözcük kaydırma için görsel karakterlerinin Göster  
 Seçili olduğunda, bir return ok göstergesi burada uzun bir satır ikinci bir satır sarmalar görüntülenir.  
  
 ![LineBreakSymbol ekran görüntüsü](../../ide/reference/media/linebreak.gif "linebreak")  
  
 Bu göstergeler görüntülememek tercih ediyorsanız bu seçeneği temizleyin.  
  
> [!NOTE]
>  Bu anımsatıcı okları kodunuzu eklenmez ve yazdırma. Bunlar yalnızca başvuru amaçlıdır.  
  
 Herhangi bir seçim olduğunda kesme veya kopyalama komutları boş satırlar uygulayın.  
 Ekleme noktasını boş bir satıra getirin, nothing, seçin ve ardından kopyaladığınızda veya kesin bu seçenek Düzenleyicisi davranışını ayarlar.  
  
-   Bu seçenek belirlendiğinde, boş satır kopyaladığınız veya kesin. Ardından yapıştırırsanız, yeni, boş bir satır eklenir.  
  
-   Bu seçenek temizlendiğinde kesme komutu boş satırları kaldırır. Ancak, Panodaki veriler korunur. Bu nedenle, ardından Yapıştır komutunu kullanırsanız, en son Pano'ya kopyalanan içerik yapıştırılan. Hiçbir şey daha önce kopyalandı, hiçbir şey yapıştırılan.  
  
Bir satır boş değilse bu ayarın kopyalama veya kesme üzerinde hiçbir etkisi yoktur. Hiçbir şey seçili ise, tüm satırı kopyaladığınız veya kesin. Ardından yapıştırırsanız tüm satır ve kendi endline karakter metnin yapıştırılan.  
  
> [!TIP]
>  Boşluk, sekme ve uçları için göstergeleri görüntülemek ve bu nedenle tamamen boş satırlarından girintili satırları ayırt etmek için seçin **Gelişmiş** gelen **Düzenle** menü ve **görünüm beyaz Alanı**.  
  
## <a name="display"></a>Ekran  
 Satır numaraları  
 Seçili olduğunda, bir satır sayısı her kod satırının yanında görüntülenir.  
  
> [!NOTE]
>  Bu satır numaralarını kodunuzu eklenmez ve yazdırma. Bunlar yalnızca başvuru amaçlıdır.  
  
 Tek tıklamayla URL Gezinti etkinleştir  
 Bir URL Düzenleyicisi'nde üzerinden geçerken seçili olduğunda, fare imlecini işaret eden bir ele değiştirir. Web tarayıcınızda belirtilen sayfasını görüntülemek için URL tıklatabilirsiniz.  
  
 Gezinti çubuğu  
 Seçili olduğunda, görüntüler **gezinti çubuğu** Kod düzenleyicisinde üstünde. Kendi açılır **nesneleri** ve **üyeleri** listeleri kodunuzda, kendi üyelerini seçin belirli bir nesnenin seçmenizi sağlar ve Kod Düzenleyicisi'nde Seçili üyeyi bildirimi gider.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçenekler, metin düzenleyici, tüm diller, sekmeler](../../ide/reference/options-text-editor-all-languages-tabs.md)   
 [Genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md)   
 [IntelliSense Kullanma](../../ide/using-intellisense.md)