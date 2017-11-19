---
title: "Visual Studio'daki klavye kısayollarını tanımlama ve özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ToolsOptionsPages.Environment.Keyboard
helpviewer_keywords:
- keyboard shortcuts [Visual Studio], customizing
- importing shortcut keys [Visual Studio]
- shortcut key combinations [Visual Studio]
- commands [Visual Studio], shortcut keys
- custom shortcut keys [Visual Studio]
- customizing keyboard shortcuts [Visual Studio]
- exporting shortcut keys [Visual Studio]
ms.assetid: d2774be2-60a4-4d6f-95f1-79d0d9e55b56
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 13093fd63df094df624f0007ed593cbbf6014fef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="identifying-and-customizing-keyboard-shortcuts-in-visual-studio"></a>Visual Studio'daki Klavye Kısayollarını Tanımlama ve Özelleştirme
Visual Studio komutları için kısayollar tanımlayabilir, bu kısayolları özelleştirebilir ve başkalarının kullanması için dışarı aktarabilirsiniz. Birçok kısayol her zaman aynı komutları çağırır, ancak kısayolun davranışı aşağıdaki koşullara göre değişebilir:  
  
-   Visual Studio'yu ilk kez çalıştırdığınızda seçtiğiniz varsayılan ortam ayarları (örneğin, Genel Geliştirme veya Visual C#).  
  
-   Kısayolun davranışını özelleştirip özelleştirmediğiniz.  
  
-   Kısayolu seçtiğiniz anda içinde bulunduğunuz bağlam. Örneğin F2 kısayolu, Ayarlar Tasarımcısı'nı kullanıyorsanız Edit.EditCell komutunu, Ekip Gezgini'ni kullanıyorsanız File.Rename komutunu çağırır.  
  
 Ayarları, özelleştirme ve bağlam bağımsız olarak her zaman bulabilir ve bir klavye kısayolu değiştirmek **seçenekleri** iletişim kutusu. Birkaç düzine komutlar için varsayılan klavye kısayolları de arayabilir [sık kullanılan komutlar için varsayılan klavye kısayolları](../ide/default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md), ve (genel geliştirmeye göre tüm varsayılan kısayolların tam bir listesini bulabilirsiniz Ayarları) içinde [varsayılan klavye kısayolları](../ide/default-keyboard-shortcuts-in-visual-studio.md).  
  
 **Bu konudaki**  
  
-   [Klavye kısayolu tanımlama](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md#bkmk_identify)  
  
-   [Klavye kısayolu özelleştirme](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md#bkmk_assign)  
  
-   [Özel klavye kısayolları paylaşımı](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md#bkmk_transfer)  
  
 Bir komuta Genel bağlamda kısayol atanmış ve diğer bağlamlarda atanmamışsa, ilgili kısayol her zaman bu komutu çağırır. Ancak bir kısayol, Genel bağlamda bir komuta ve özel bağlamda farklı bir komuta atanabilir. Böyle bir komutu özel bağlamda kullanırsanız, özel bağlama ilişkin komutu çağırır (Genel bağlama ilişkin komutu çağırmaz).  
  
> [!NOTE]
>  Ayarlarınıza ve Visual Studio sürümünüze göre, menü komutlarının adları ve konumları ve iletişim kutularında görünen seçenekler değişik olabilir. Bu konuda dayanır **genel geliştirme ayarları**.  
  
##  <a name="bkmk_identify"></a>Klavye kısayolu tanımlama  
  
1.  Menü çubuğunda seçin **Araçları**, **seçenekleri**.  
  
2.  Genişletme **ortam**ve ardından **klavye**.  
  
     ![Klavye kısayolları Seçenekleri iletişim kutusunda görüntüleme](../ide/media/optionskeyboard.png "OptionsKeyboard")  
  
3.  İçinde **Göster komutlarını içeren** kutusuna, boşluk içermeyen komutun adını bölümünü veya tümünü girin.  
  
     Örneğin, komutları için bulabilirsiniz **Solution Explorer'da**.  
  
4.  Listede doğru komutu seçin.  
  
     Örneğin, seçebileceğiniz **View.SolutionExplorer**.  
  
5.  Komutun bir klavye kısayolu varsa görünür **seçili komut için kısayol** listesi.  
  
     ![Belirtilen komut için kısayol görüntülemek](../ide/media/viewshortcut.png "ViewShortcut")  
  
##  <a name="bkmk_assign"></a>Klavye kısayolu özelleştirme  
  
1.  Menü çubuğunda seçin **Araçları**, **seçenekleri**.  
  
2.  Genişletme **ortam** klasörünü ve ardından **klavye**.  
  
     ![Klavye kısayolları Seçenekleri iletişim kutusunda görüntüleme](../ide/media/optionskeyboard.png "OptionsKeyboard")  
  
3.  İçinde **Göster komutlarını içeren** kutusuna, boşluk içermeyen komutun adını bölümünü veya tümünü girin.  
  
     Örneğin, komutları için bulabilirsiniz **Solution Explorer'da**.  
  
4.  Listede, klavye kısayolu atamak istediğiniz komutu seçin.  
  
5.  İçinde **kullanım yeni kısayoluna** listesinde, kısayolu kullanmak istediğiniz özellik alanı seçin.  
  
     Örneğin, seçebileceğiniz **genel** tüm içerikleri ile çalışmak için kısayol istiyorsanız. Başka bir düzenleyicide Genel olarak eşlenmemiş herhangi bir kısayolu kullanabilirsiniz. Aksi takdirde düzenleyici kısayolu geçersiz kılar.  
  
    > [!NOTE]
    >  Bir klavye kısayolu bir parçası olarak aşağıdaki anahtarları atayamazsınız **genel**: yazdırma ekran/Sys Rq, kilitleme, Pause/Break sekmeye Caps Lock, Ekle, giriş, son, Page Up, Page Down, Windows logo tuşu, uygulama anahtarı, herhangi bir ok anahtarların veya Enter; Num Lock, silmek veya sayısal tuş takımında; temizleyin veya Ctrl + Alt + Delete.  
  
6.  İçinde **basın kısayol tuşları** kutusunda, kullanmak istediğiniz kısayol girin.  
  
    > [!NOTE]
    >  Bir harfi; Alt tuşu, Ctrl tuşu veya her ikisiyle birden birleştiren bir kısayol oluşturabilirsiniz. Ayrıca Shift tuşu ve bir harfi; Alt tuşu, Ctrl tuşu veya her ikisiyle birden birleştiren bir kısayol da oluşturabilirsiniz.  
  
     Bir kısayol zaten başka bir komuta atanmışsa görünür **şu anda kullandığı kısayol** kutusu. Bu durumda, farklı birini denemden önce kısayolu silmek için Geri Al tuşunu seçin.  
  
     ![Bir komutu için başka bir kısayol belirtin](../ide/media/reassignshortcut.png "ReassignShortcut")  
  
7.  Seçin **atamak** düğmesi.  
  
    > [!NOTE]
    >  Bir komutu için başka bir kısayol belirtirseniz, seçin **atamak** düğmesine tıklayın ve ardından **iptal** düğmesi, iletişim kutusu kapanır, ancak değişikliğin geri değil.  
  
##  <a name="bkmk_transfer"></a>Özel klavye kısayolları paylaşımı  
 Özel klavye kısayollarınızı bir dosyaya dışarı aktararak ve verileri içeri aktarabilmeleri için bu dosyayı başkalarına vererek, klavye kısayollarınızı paylaşabilirsiniz.  
  
#### <a name="to-export-only-keyboard-shortcuts"></a>Yalnızca klavye kısayollarını dışarı aktarmak için  
  
1.  Menü çubuğunda seçin **Araçları**, **içeri ve dışarı aktarma ayarları**.  
  
2.  Seçin **verme seçili ortam ayarları**ve ardından **sonraki** düğmesi.  
  
3.  Altında **hangi ayarların vermek istiyor musunuz?**, Temizle **tüm ayarları** onay kutusunu işaretleyin, genişletin **seçenekleri**, genişletin ve ardından **ortam**.  
  
4.  Seçin **klavye** onay kutusunu işaretleyin ve ardından **sonraki** düğmesi.  
  
     ![Yalnızca özelleştirilmiş klavye kısayolları verme](../ide/media/exportshortcuts.png "ExportShortcuts")  
  
5.  İçinde **ne ayarları dosyanızın adı istiyor musunuz?** ve **my ayarları dosyası bu dizinde depola** kutularına ya da varsayılan değerleri bırakın veya farklı değerleri belirtin ve ardından  **Son** düğmesi.  
  
     Varsayılan olarak kısayollarınız %USERPROFILE%\Documents\Visual Studio 2013\Settings klasöründe bulunan bir dosyaya kaydedilir. Dosyanın adı ayarları dışarı aktardığınız tarihi yansıtır ve uzantısı .vssettings olur.  
  
#### <a name="to-import-only-keyboard-shortcuts"></a>Yalnızca klavye kısayollarını içeri aktarmak için  
  
1.  Menü çubuğunda seçin **Araçları**, **içeri ve dışarı aktarma ayarları**.  
  
2.  Seçin **seçili ortam ayarları** seçenek düğmesine ve ardından **sonraki** düğmesi.  
  
3.  Seçin **Hayır, yalnızca geçerli ayarlarımı üzerine yeni ayarlarını içeri aktarmak** seçenek düğmesine ve ardından **sonraki** düğmesi.  
  
4.  Altında **My ayarları**, almak veya seçmek istediğiniz kısayolları içeren dosyayı seçin **Gözat** düğmesi doğru dosyasını bulun.  
  
5.  Seçin **sonraki** düğmesi.  
  
6.  Altında **hangi ayarları içeri aktarmak istiyor musunuz?**, Temizle **tüm ayarları** onay kutusunu işaretleyin, genişletin **seçenekleri**, genişletin ve ardından **ortam**.  
  
7.  Seçin **klavye** onay kutusunu işaretleyin ve ardından **son** düğmesi.  
  
     ![İçeri aktarma yalnızca klavye kısayolları özelleştirilmiş](../ide/media/importshortcuts.png "ImportShortcuts")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'nun erişilebilirlik özellikleri](../ide/reference/accessibility-features-of-visual-studio.md)