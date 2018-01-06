---
title: "Nasıl yapılır: Visual Studio IDE'de gezinme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- environments [Visual Studio], navigation
- documents [Visual Studio], navigating
- IDE, navigation
- navigation [Visual Studio]
- files [Visual Studio], navigating between
- windows [Visual Studio], navigating
- Window.NextDocumentWindowNav
- IDE navigator
ms.assetid: 6c36b6eb-c93f-496b-af08-4199f7afd8bd
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 175a22ecb56f8c41d76512309df2b0443a7481b6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-move-around-in-the-visual-studio-ide"></a>Nasıl Yapılır: Visual Studio IDE’de Gezinme
Tümleşik geliştirme ortamı (IDE) pencereden diğerine taşımanızı izin vermek için tasarlanmış ve dosyaya tercih ya da proje gereksinimlerinize bağlı olarak birkaç farklı şekillerde olmuştur. Düzenleyicideki açık dosyalar arasında geçiş yapma veya IDE içindeki tüm etkin araç pencereleri dolaşma seçebilirsiniz. Herhangi Dosya Aç bağımsız olarak, en son erişildiği sırası düzenleyicisinde için doğrudan geçiş yapabilirsiniz. Bu özellikler, IDE içinde çalışırken üretkenliğinizi artırmaya yardımcı olabilir.  
  
> [!NOTE]
> İletişim kutularındaki seçenekleri adlar ve menü komutlarını, gördüğünüz konumlarını ne etkin ayarlarınıza veya edition bağlı olarak bu makalede açıklanan alanından farklı olabilir. Bu makale ile yazılmıştır **genel** ayarları unutmayın. Ayarlarınızı, örneğin değiştirmek için **genel** veya **Visual C++** ayarları seçebilirsiniz **Araçları**, **içeri ve dışarı aktarma ayarları**ve ardından seçin **tüm ayarlara**.

## <a name="keyboard-shortcuts"></a>Klavye Kısayolları  
Neredeyse her menüsü komutu Visual Studio'daki klavye kısayolu vardır. Özel kısayollarınızı de oluşturabilirsiniz. Daha fazla bilgi için bkz: [tanımlama ve özelleştirme klavye kısayolları](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
## <a name="navigating-among-files-in-the-editor"></a>Düzenleyicideki dosyalar arasında gezinme  
Düzenleyicide açık dosyalar arasında gezinmek için çeşitli yöntemler kullanabilirsiniz. Burada erişmesine, şu anda açık olan herhangi bir dosya veya sekmeye sık kullanılan dosyaları da bunlar her zaman görünür; böylece hızla bulmak için IDE Gezgini kullanma sırasına göre dosyalar arasında taşıyabilirsiniz.  
  
Geriye git ve ileriye, bunlar erişilen, sipariş çok geri ve İleri görüntüleme geçmişiniz Microsoft Internet Explorer için yaptığınız gibi temel düzenleyicide açık dosyalar arasında geçiş yapın.  
  
#### <a name="to-move-through-open-files-in-order-of-use"></a>Kullanım sırasına göre açık dosyalar arasında taşımak için  
  
-   Açık belgeleri kullanıcılar en son işlemdeki sırada etkinleştirmek için basın **Ctrl**+**-**.  
  
-   Ters sırada açık belgeler etkinleştirmek için basın **Ctrl**+**Shift**+**-**.  
  
    > [!NOTE]
    > **Geriye doğru gidin** ve **ileriye** de bulunabilir **Görünüm** menüsü.  
  
Belirli bir dosyayı dosya son erişilen zaman bağımsız olarak düzenleyicide açık geçiş yapabilirsiniz kullanarak **IDE Gezgini**, **etkin dosyalar** düzenleyicisinde, liste veya **Windows** iletişim kutusu.  
  
**IDE Gezgini** çok pencerelerin uygulama gibi çalışır. Menülerden kullanılamaz ve yalnızca kısayol tuşları kullanılarak erişilebilir. İki komutlardan herhangi birini erişmek için kullanabileceğiniz **IDE Gezgini** (arasında geçiş yapmak istediğiniz sipariş bağlı olarak dosyalar arasında geçiş yapmak için aşağıda).  
  
![Visual Studio IDE Gezgini](../ide/media/vs2015_ide_navigator.png "VS2015_IDE_Navigator")  
  
`Window.PreviousDocumentWindowNav`en son erişilen dosya taşımanızı sağlar ve `Window.NextDocumentWindowNav` ters sırada taşımanızı sağlar. Genel Geliştirme Ayarları atar **Shift**+**Alt**+**F7** için `Window.PreviousDocumentWindowNav` ve **Alt** + **F7** için `Window.NextDocumentWindowNav`.
  
> [!NOTE]
> Kullanmakta olduğunuz ayarları bileşimi bu komuta atanan bir kısayol tuş bileşimini zaten yoksa, kendi özel komutunu kullanarak atayabilirsiniz **klavye** sayfasında **seçenekleri** iletişim bir kutu. Daha fazla bilgi için bkz: [tanımlama ve özelleştirme klavye kısayolları](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
#### <a name="to-switch-to-specific-files-in-the-editor"></a>Belirli dosyaları Düzenleyicisi'nde geçmek için  
  
-   Tuşuna **Ctrl**+**sekmesini** görüntülemek için **IDE Gezgini**. CTRL tuşunu basılı tutun ve sürekli olarak geçiş yapmak istediğiniz dosyayı seçene kadar SEKME tuşuna basın.  
  
    > [!TIP]
    >  İçinde gitmenizi sırasını tersine çevirmek için **etkin dosyalar** listesinde, basılı **Ctrl**+**Shift** anahtarları ve tuşuna **sekmesini**.  
  
    \-veya -  
  
-   Düzenleyici sağ üst köşesinde seçin **etkin dosyalar** düğmesine tıklayın ve ardından geçmek için listeden bir dosya seçin.  
  
    \-veya -  
  
-   Menü çubuğunda seçin **penceresi**, **Windows**.  
  
-   Listesinde, görüntülemek ve ardından istediğiniz dosyayı seçin **etkinleştirme**.  
  
## <a name="navigating-among-tool-windows-in-the-ide"></a>Araç Pencereleri IDE içinde arasında gezinme  
**IDE Gezgini** de sahip olduğunuz aracı Windows'un döngüsü sağlar IDE içinde açın. İki komutlardan herhangi birini erişmek için kullanabileceğiniz **IDE Gezgini** arasında geçiş yapmak istediğiniz sipariş bağlı olarak, aracı windows dolaşmak için. `Window.PreviousToolWindowNav`en son erişilen dosya taşımanızı sağlar ve `Window.NextToolWindowNav` ters sırada taşımanızı sağlar. Genel Geliştirme Ayarları atar **Shift**+**Alt**+**F7** için `Window.PreviousDocumentWindowNav` ve **Alt** + **F7** için `Window.NextDocumentWindowNav`.
  
> [!NOTE]
> Kullanmakta olduğunuz ayarları bileşimi bu komuta atanan bir kısayol tuş bileşimini zaten yoksa, kendi özel komutunu kullanarak atayabilirsiniz **klavye** sayfasında **seçenekleri** iletişim bir kutu. Daha fazla bilgi için bkz: [tanımlama ve özelleştirme klavye kısayolları](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md).  
  
#### <a name="to-switch-to-a-specific-tool-window-in-the-ide"></a>IDE belirli araç penceresinde geçmek için  
  
-   Tuşuna **Alt**+**F7** görüntülemek için **IDE Gezgini**. Basılı **Alt** anahtar ve tuşuna **F7** art arda düşündüğünüz geçmek için pencereyi seçene kadar.  
  
    > [!TIP]
    > İçinde gitmenizi sırasını tersine çevirmek için **etkin araç pencereleri** listesinde, üst karakter + ALT tuşlarını basılı tutun ve F7 tuşuna basın.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Pencere düzenlerini özelleştirme](../ide/customizing-window-layouts-in-visual-studio.md)   
[Klavye kısayolları](../ide/default-keyboard-shortcuts-in-visual-studio.md)