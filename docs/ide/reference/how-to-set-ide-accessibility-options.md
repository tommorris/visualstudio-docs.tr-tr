---
title: "Nasıl yapılır: IDE erişilebilirlik seçeneklerini ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 08/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: accessibility [Visual Studio]
ms.assetid: ddc96c4c-0600-46c1-8267-7dce4c44ad24
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e7b7623a60f5a6e06739596b02125806205c07b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-ide-accessibility-options"></a>Nasıl Yapılır: IDE Erişilebilirlik Seçeneklerini Ayarlama
> [!TIP]
> Son erişilebilirlik güncelleştirmeleri hakkında daha fazla bilgi için bkz: [Visual Studio 2017 sürüm 15.3 erişilebilirlik geliştirmeleri](https://blogs.msdn.microsoft.com/visualstudio/2017/08/14/accessibility-improvements-in-visual-studio-2017-version-15-3/) blog postası.

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]zorluğu yazılacak olan kişiler ve okumak için görme engelli kişiler için kolaylaştıran özellikler içerir. Bu özellikler, boyut ve birkaçıdır metin ve düğmeleri araç çubukları ve yöntemleri ve parametreleri için otomatik tamamlama boyutunu değiştirme düzenleyicileri içindeki metnin rengi değiştirme içerir.  

 Ayrıca, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] desteklediği en sık olun Dvorak klavye düzenleri, yazdığınız karakterler daha erişilebilir. İle kullanılabilen varsayılan kısayol tuşlarını özelleştirebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Daha fazla bilgi için bkz: [tanımlama ve özelleştirme klavye kısayolları](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  

> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  

## <a name="editors-dialogs-and-tool-windows"></a>Düzenleyiciler, iletişim kutuları ve araç pencereleri  
 Varsayılan olarak, iletişim kutuları ve aracı windows tarafından [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] renk ve yazı tipi boyutu ile aynı işletim sistemi olarak kullanın. IDE, iletişim kutuları, araç çubukları ve aracı windows çerçeve renk ayarlarını bağlı bir renk şeması: açık veya koyu. Geçerli renk temasını değiştirebileceğiniz [genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md).  

 Düzenleyicinin kod görünümünde açılır pencereleri de görüntüleyebilirsiniz. Bu windows bir işlevi veya deyimi tamamlamak için kullanılabilir üyeler geçerli nesne ve parametreleri isteyebilir. Bu windows yazmaya ilişkin zorluk varsa yararlı olabilir. Ancak, bazı kullanıcılar için sorunlu Kod düzenleyicisinde odak kesintiye uğratabilir. Seçenekler iletişim kutusu açılarak ve temizleme bu windows oturumunu kapatabilirsiniz **otomatik listesi üyeleri** ve **parametre bilgilerini** içinde **metin düzenleyici**, **tüm Dilleri**, **genel** sayfasındaki **seçenekleri** iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: Genel Düzenleyici seçeneklerini ayarlama](http://msdn.microsoft.com/en-us/704e4a7b-2162-4bed-8a47-f4f6ffec98c2).  

 Çalışma biçimini en iyi uyacak şekilde tümleşik geliştirme ortamı (IDE) windows düzenleyebilirsiniz. Yerleştirme, float Gizle veya otomatik olarak her araç penceresi gizle.  

 Pencere düzenlerini değiştirme hakkında daha fazla bilgi için bkz: [pencere düzenlerini özelleştirme](../../ide/customizing-window-layouts-in-visual-studio.md).  

### <a name="changing-the-size-of-text"></a>Metin boyutunu değiştirme  
 Gibi metin tabanlı aracı windows ayarlarını değiştirmek **komutu** penceresinde **hemen** penceresinde ve **çıkış** penceresi, **yazı tipleri ve Renkleri** bölmesinde **ortam** içinde seçenekleri **Araçları** iletişim kutusu. Zaman **[tüm metin Aracı Pencereleri]** seçildiyse **ayarlarını göster** aşağı açılan listesinde, varsayılan ayar olarak listeleniyor **varsayılan** içinde **öğesi ön plan**  ve **öğesi arka plan** aşağı açılır listeler. Ayrıca, metin düzenleyicide nasıl görüntüleneceğini için ayarları değiştirebilirsiniz.  

##### <a name="to-change-the-size-of-text-in-text-based-tool-windows-and-editors"></a>Metin tabanlı araç pencereleri ve düzenleyiciler metin boyutunu değiştirmek için  

1.  Gelen **Araçları** menüsünde seçin **seçenekleri**.  

2.  Seçin **yazı tiplerini ve renkleri** üzerinde **ortam** klasör.  

3.  Bir seçenek seçin **ayarlarını göster** açılır menü.  

     Bir düzenleyicideki metnin yazı tipi boyutunu değiştirmek için tercih **metin düzenleyici**.  

     Metin tabanlı aracı Windows metin yazı tipi boyutunu değiştirmek için tercih **[tüm metin Aracı Pencereleri]**.  

     Bir düzenleyici araç ipucu metni için yazı tipi boyutunu değiştirmek için tercih **Düzenleyici araç ipucu**.  

     Deyim tamamlama açılır pencereleri metin yazı tipi boyutunu değiştirmek için tercih **deyim tamamlama**.  

4.  Gelen **görüntülemek öğeleri**seçin **düz metin**.  

5.  İçinde **yazı tipi**, yeni bir yazı tipi seçin.  

6.  İçinde **boyutu**, yeni bir yazı tipi boyutu seçin.  

    > [!NOTE]
    >  Metin tabanlı araç pencereleri ve editörler için metin boyutu sıfırlamayı tercih **Varsayılanlar kullan**.  

7.  Seçin **Tamam**.  

### <a name="changing-the-colors-used-in-the-ide"></a>IDE içinde kullanılan renkleri değiştirme  
 Metin, kenar boşluğu göstergeleri, boşluk ve kod öğeleri Düzenleyicisi'nde için varsayılan renkleri değiştirmek seçebilirsiniz.  

> [!NOTE]
>  Tüm uygulama windows işletim sistemine yüksek karşıtlık renkleri kullanmak için sol basın **ALT +**sol **SHIFT + PRINT SCREEN**. Varsa [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] açın, kapatın ve yeniden [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yüksek karşıtlık renkleri tam olarak uygulamak için.  

##### <a name="to-change-the-color-of-items-in-the-editor"></a>Düzenleyicideki öğelerin rengini değiştirmek için  

1.  Gelen **Araçları** menüsünde seçin **seçenekleri**.  

2.  Seçin **yazı tiplerini ve renkleri** gelen **ortam** klasör.  

3.  İçinde **ayarlarını göster**, seçin **metin düzenleyici**.  

4.  Gelen **görüntülemek öğeleri**, görüntü gibi değiştirmek için gereken bir öğe seçin **düz metin**, **gösterge boşluğu**, **görünür boşluk**, **HTML öznitelik adı**, veya **XML özniteliği**.  

5.  Görüntü ayarlarını aşağıdaki seçeneklerden birini seçin: **öğesi ön plan**, **öğesi arka plan**, ve **kalın**.  

6.  Seçin **Tamam**.  

## <a name="toolbars"></a>Araç Çubukları  
 Araç çubuğu kullanılabilirlik ve erişilebilirlik artırmak için araç çubuğu düğmelerine metin ekleyebilirsiniz.  

#### <a name="to-assign-text-to-toolbar-buttons"></a>Araç çubuğu düğmelerine metin atamak için  

1.  Gelen **Araçları** menüsünde seçin **Özelleştir**.  

2.  İçinde **Özelleştir** iletişim kutusunda **komutları** sekmesi.  

3.  Seçin **araç** ve düşündüğünüz metnini görüntülemek için düğmeyi içeren araç çubuğu adı seçin.  

4.  Listede, değiştirmek istediğiniz komutu seçin.  

5.  Seçin **seçimi düzenlemek**.  

6.  Seçin **resim ve metin**.  

#### <a name="to-modify-the-buttons-displayed-text"></a>Düğme değiştirmek için görüntülenen metin  

1.  Yeniden seçin **seçimi düzenlemek**.  

2.  İçinde bitişik **adı**, Ekle, seçili düğme için yeni bir resim yazısı sağlar.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'nun erişilebilirlik özellikleri](../../ide/reference/accessibility-features-of-visual-studio.md)   
 [Erişilebilir Uygulamalar Tasarlama için Kaynaklar](../../ide/reference/resources-for-designing-accessible-applications.md)
