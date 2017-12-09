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
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 280df2197aa7ef9b5e533244831585cb72f7466e
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/07/2017
---
# <a name="identifying-and-customizing-keyboard-shortcuts-in-visual-studio"></a>Visual Studio'daki klavye kısayollarını tanımlama ve özelleştirme

Visual Studio komutları için kısayollar tanımlayabilir, bu kısayolları özelleştirebilir ve başkalarının kullanması için dışarı aktarabilirsiniz. Birçok kısayol her zaman aynı komutları çağırır, ancak kısayolun davranışı aşağıdaki koşullara göre değişebilir:

- Visual Studio'yu ilk kez çalıştırdığınızda seçtiğiniz varsayılan ortam ayarları (örneğin, Genel Geliştirme veya Visual C#).

- Kısayolun davranışını özelleştirip özelleştirmediğiniz.

- Kısayolu seçtiğiniz anda içinde bulunduğunuz bağlam. Örneğin F2 kısayolu, Ayarlar Tasarımcısı'nı kullanıyorsanız Edit.EditCell komutunu, Ekip Gezgini'ni kullanıyorsanız File.Rename komutunu çağırır.

Ayarları, özelleştirme ve bağlam bağımsız olarak her zaman bulabilir ve bir klavye kısayolu değiştirmek **seçenekleri** iletişim kutusu. Birkaç düzine komutlar için varsayılan klavye kısayolları de arayabilir [sık kullanılan komutlar için varsayılan klavye kısayolları](../ide/default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md), ve (genel geliştirmeye göre tüm varsayılan kısayolların tam bir listesini bulabilirsiniz Ayarları) içinde [varsayılan klavye kısayolları](../ide/default-keyboard-shortcuts-in-visual-studio.md).

Bir komuta Genel bağlamda kısayol atanmış ve diğer bağlamlarda atanmamışsa, ilgili kısayol her zaman bu komutu çağırır. Ancak bir kısayol, Genel bağlamda bir komuta ve özel bağlamda farklı bir komuta atanabilir. Böyle bir komutu özel bağlamda kullanırsanız, özel bağlama ilişkin komutu çağırır (Genel bağlama ilişkin komutu çağırmaz).

> [!NOTE]
> Ayarlarınıza ve Visual Studio sürümünüze göre, menü komutlarının adları ve konumları ve iletişim kutularında görünen seçenekler değişik olabilir. Bu konuda dayanır **genel geliştirme ayarları**.

## <a name="identifying-a-keyboard-shortcut"></a>Klavye kısayolu tanımlama

1. Menü çubuğunda seçin **Araçları**, **seçenekleri**.

2. Genişletme **ortam**ve ardından **klavye**.

   ![Klavye kısayolları Seçenekleri iletişim kutusunda görüntüleme](../ide/media/optionskeyboard.png "OptionsKeyboard")

3. İçinde **Göster komutlarını içeren** kutusuna, boşluk içermeyen komutun adını bölümünü veya tümünü girin.

   Örneğin, komutları için bulabilirsiniz `solutionexplorer`.

4. Listede doğru komutu seçin.

    Örneğin, seçebileceğiniz **View.SolutionExplorer**.

5. Komutun bir klavye kısayolu varsa görünür **seçili komut için kısayol** listesi.

   ![Belirtilen komut için kısayol görüntülemek](../ide/media/viewshortcut.png "ViewShortcut")

## <a name="customizing-a-keyboard-shortcut"></a>Klavye kısayolunu özelleştirme

1. Menü çubuğunda seçin **Araçları**, **seçenekleri**.

2. Genişletme **ortam** klasörünü ve ardından **klavye**.

3. İsteğe bağlı: boşluksuz komutun adı kısmını veya tamamını girerek komutların listesini filtrelemek **Göster komutlarını içeren** kutusu.

4. Listede, klavye kısayolu atamak istediğiniz komutu seçin.

İçinde **kullanım yeni kısayoluna** listesinde, kısayolu kullanmak istediğiniz özellik alanı seçin.

    For example, you can choose **Global** if you want the shortcut to work in all contexts. You can use any shortcut that isn't mapped (as Global) in another editor. Otherwise, the editor overrides the shortcut.

    > [!NOTE]
    > You can't assign the following keys as part of a keyboard shortcut in **Global**: Print Scrn/Sys Rq, Scroll Lock, Pause/Break, Tab, Caps Lock, Insert, Home, End, Page Up, Page Down, the Windows logo key, the Application key, any of the Arrow keys, or Enter; Num Lock, Delete, or Clear on the numeric keypad; the Ctrl+Alt+Delete key combination.

6. İçinde **basın kısayol tuşları** kutusunda, kullanmak istediğiniz kısayol girin.

    > [!NOTE]
    > Bir harfi; Alt tuşu, Ctrl tuşu veya her ikisiyle birden birleştiren bir kısayol oluşturabilirsiniz. Ayrıca Shift tuşu ve bir harfi; Alt tuşu, Ctrl tuşu veya her ikisiyle birden birleştiren bir kısayol da oluşturabilirsiniz.

     Bir kısayol zaten başka bir komuta atanmışsa görünür **şu anda kullandığı kısayol** kutusu. Bu durumda, farklı birini denemden önce kısayolu silmek için Geri Al tuşunu seçin.

    ![Bir komutu için başka bir kısayol belirtin](../ide/media/reassignshortcut.png "ReassignShortcut")

7. Seçin **atamak** düğmesi.

    > [!NOTE]
    > Bir komutu için başka bir kısayol belirtirseniz, seçin **atamak** düğmesine tıklayın ve ardından **iptal** düğmesi, iletişim kutusu kapanır, ancak değişikliğin geri değil.

## <a name="sharing-custom-keyboard-shortcuts"></a>Özel klavye kısayollarını paylaşma

Özel klavye kısayollarınızı bir dosyaya dışarı aktararak ve verileri içeri aktarabilmeleri için bu dosyayı başkalarına vererek, klavye kısayollarınızı paylaşabilirsiniz.

### <a name="to-export-only-keyboard-shortcuts"></a>Yalnızca klavye kısayollarını dışarı aktarmak için

1. Menü çubuğunda seçin **Araçları**, **içeri ve dışarı aktarma ayarları**.

2. Seçin **verme seçili ortam ayarları**ve ardından **sonraki** düğmesi.

3. Altında **hangi ayarların vermek istiyor musunuz?**, Temizle **tüm ayarları** onay kutusunu işaretleyin, genişletin **seçenekleri**, genişletin ve ardından **ortam**.

4. Seçin **klavye** onay kutusunu işaretleyin ve ardından **sonraki** düğmesi.

    ![Yalnızca özelleştirilmiş klavye kısayolları verme](../ide/media/exportshortcuts.png "ExportShortcuts")

5. İçinde **ne ayarları dosyanızın adı istiyor musunuz?** ve **my ayarları dosyası bu dizinde depola** kutularına ya da varsayılan değerleri bırakın veya farklı değerleri belirtin ve ardından  **Son** düğmesi.

    Varsayılan olarak, kısayollarınızı %USERPROFILE%\Documents\Visual Studio 2017\Settings klasöründeki dosyasına kaydedilir. Dosyanın adı ayarları dışarı aktardığınız tarihi yansıtır ve uzantısı .vssettings olur.

### <a name="to-import-only-keyboard-shortcuts"></a>Yalnızca klavye kısayollarını içeri aktarmak için

1. Menü çubuğunda seçin **Araçları**, **içeri ve dışarı aktarma ayarları**.

2. Seçin **seçili ortam ayarları** seçenek düğmesine ve ardından **sonraki** düğmesi.

3. Seçin **Hayır, yalnızca geçerli ayarlarımı üzerine yeni ayarlarını içeri aktarmak** seçenek düğmesine ve ardından **sonraki** düğmesi.

4. Altında **My ayarları**, almak veya seçmek istediğiniz kısayolları içeren dosyayı seçin **Gözat** düğmesi doğru dosyasını bulun.

5. Seçin **sonraki** düğmesi.

6.  Altında **hangi ayarları içeri aktarmak istiyor musunuz?**, Temizle **tüm ayarları** onay kutusunu işaretleyin, genişletin **seçenekleri**, genişletin ve ardından **ortam**.

7. Seçin **klavye** onay kutusunu işaretleyin ve ardından **son** düğmesi.

    ![İçeri aktarma yalnızca klavye kısayolları özelleştirilmiş](../ide/media/importshortcuts.png "ImportShortcuts")

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'nun Erişilebilirlik Özellikleri](../ide/reference/accessibility-features-of-visual-studio.md)