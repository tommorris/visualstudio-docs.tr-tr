---
title: Visual Studio'da pencere düzenlerini özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 01/23/2017
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.windows
- vs.environment
helpviewer_keywords:
- windows [Visual Studio], managing
- custom window configurations
- layout [Visual Studio], window management
- document windows [Visual Studio]
- interface modes
- AutoHide windows
- MDI, window interface modes
- multiple monitors
- Tabbed Document mode
- debug mode
- custom layouts
ms.assetid: 7517ff13-76de-4ecf-9c1b-eb9b7ff4d718
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02ed6d0801d5e4bbece37eb60f2e113fb690d5d9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="customize-window-layouts-in-visual-studio"></a>Visual Studio'da pencere düzenlerini özelleştirme
Visual Studio'da, konum, boyutu ve çeşitli geliştirme iş akışları için en iyi çalışır pencere düzenlerini oluşturmak için windows davranışını özelleştirebilirsiniz. Düzen özelleştirdiğinizde, IDE, hatırlıyor. Örneğin, yerleştirme konumunu değiştirirseniz **Çözüm Gezgini** ve başka bir bilgisayarda çalışıyorsanız bile Visual Studio, sonraki başlattığınızda Kapat **Çözüm Gezgini** olacaktır aynı konuma yerleştirildi. Ayrıca özel bir düzen bir ad verin ve dosyayı kaydedin ve tek bir komutla düzeni arasında geçiş yapın. Örneğin, düzenlemek için bir düzen ve hata ayıklama için başka bir oluşturun ve bunları kullanarak arasında geçiş **penceresi** > **pencere düzenini Uygula** menü komutu.  

## <a name="kinds-of-windows"></a>Pencere cinsleri  

### <a name="tool-and-document-windows"></a>Araç ve belge pencereleri  
 IDE iki temel pencere türleri var. *aracı windows* ve *belge windows*. Araç pencereleri dahil **Çözüm Gezgini**, **Sunucu Gezgini**, **çıktı penceresi**, **hata listesi**, tasarımcıları, hata ayıklayıcı windows , ve benzeri. Belge pencereleri kaynak kodu dosyaları, rastgele metin dosyaları, yapılandırma dosyaları vb. içerir. Araç pencereleri yeniden boyutlandırılabilir ve bunların başlık çubuğu tarafından sürüklenebilir. Belge pencereleri kendi sekmesiyle sürüklenebilir. Penceresinde diğer seçenekleri ayarlamak için sekme veya başlık çubuğunu sağ tıklayın.  

 **Penceresi** kayan ve IDE içinde windows gizleme takma seçenekleri menüsü gösterir. Bu belirli bir pencere için ek seçenekleri görmek için bir pencere sekmesini veya başlık çubuğunu sağ tıklayın. Aynı anda birden fazla örneğini belirli aracı windows görüntüleyebilirsiniz. Örneğin, birden fazla web tarayıcı penceresini görüntülemek ve bazı araç pencereleri ek örneklerini seçerek oluşturabilirsiniz **yeni pencere** üzerinde **penceresi** menüsü.  

### <a name="preview-tab-document-windows"></a>Önizleme sekmesi (belge windows)  
 İçinde **Önizleme** sekmesinde görüntüleyebilirsiniz dosyaları Düzenleyicisi'nde açmadan. Bunları seçerek dosyaları önizleyebilirsiniz **Çözüm Gezgini**, ne zaman hata ayıklama sırasında dosyalara ile adım **Tanıma Git**, ve arama sonuçlarını gözatarken. Dosyaları Önizleme iyi belge sekmesini sağ tarafındaki sekmesinde görünür. Dosya değiştirin ya da seçin düzenleme için açılır **açık**.  

### <a name="tab-groups"></a>Sekme grupları  
 Sekme grupları IDE içindeki iki veya daha fazla açık belgeleri ile çalışırken sınırlı çalışma alanını yönetme yeteneğinizi genişletir. Birden çok belge pencereleri ve aracı windows ya da dikey veya yatay sekme gruplar halinde düzenlemek ve belgeleri bir sekme grubundan karışık.  

### <a name="split-windows"></a>Bölünmüş Pencereler  
 Görüntülemek veya iki konumda aynı anda bir belgeyi düzenlemek varsa, windows bölebilirsiniz. Belgenizi iki bağımsız olarak kaydırma bölümlere ayırmak için tıklatın **bölünmüş** üzerinde **penceresi** menüsü. Tıklatın **Bölmeyi Kaldır** üzerinde **penceresi** tek bir görünüm geri yüklemek için menü.  

### <a name="toolbars"></a>Araç Çubukları  
 Araç çubukları düzenlenmiş sürükleyerek veya kullanarak **Özelleştir** iletişim kutusu. Konum ve araç çubuklarını özelleştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: menüleri ve araç çubuklarını özelleştirme](../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md).  

## <a name="arrange-and-dock-windows"></a>Pencereleri düzenleme ve windows yerleştirme  
 Bir belge penceresine veya araç penceresi olabilir *yerleşik*, konumunu ve boyutunu IDE pencere çerçevesi veya ayrı bir pencere IDE bağımsız değişken içinde sahip olması. Araç pencereleri herhangi bir yere IDE çerçevesinin içinde yerleşik; Bazı araç pencereleri Düzenleyicisi çerçevesinde sekmeli windows olarak yerleştirilmiş. Belge pencereleri Düzenleyicisi çerçevesinde yerleştirilmiş ve bunlar geçerli konumlarına sekme sırasında sabitlenmiş. Float bir araya için birden çok windows sabitleyebilirsiniz bir *raft* üzerinden veya IDE dışında. Araç pencereleri da simge durumuna küçültülmüş veya gizlenebilir.  

 Windows aşağıdaki yollarla düzenleyebilirsiniz:  

-   Belge pencereleri sekmesinde solundaki iyi sabitleyin.  

-   Sekme windows düzenleme çerçevesi için stok.  

-   IDE çerçevede köşesine araç pencereleri yerleştirme.  

-   Belge veya aracı windows üzerinden veya IDE dışında kaydırın.  

-   Araç Pencereleri IDE kenarında gizleyin.  

-   Windows farklı monitörlerde görüntüleme.  

-   Pencere yerleşimini varsayılan düzen veya kaydedilmiş bir özel yerleşim sıfırlayın.  

Araç ve belge pencereleri düzenlenmiş, komutları kullanarak sürükleyerek **penceresi** menüsünde ve düzenlenmesini penceresinin başlık çubuğunu sağ tıklanarak.  

> [!NOTE]
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  

### <a name="dock-windows"></a>Windows yerleştirme  
 ' I tıklatın ve aracı penceresinin başlık çubuğunu ya da belge penceresinin sekmesine sürükleyin kılavuz elmas görünür. Fare imlecini elmas okları birini üzerinden olduğunda sürükleme işlemi sırasında fare düğmesini şimdi yayımlarsanız penceresi nereye yerleştirilir gösteren gölgeli alana görünür.  

 Yerine tutturma olmadan yuvalanabilir pencere Taşı'yı seçin **Ctrl** pencereyi sürükleyin sırada anahtar.  

 En son sabitlenmiş konumuna araç penceresi ya da belge penceresine dönmek için basın **Ctrl** karşın başlık çubuğu veya penceresinin sekmesine çift tıklatın.  

 Aşağıdaki çizimde, yalnızca düzenleme çerçevesinde yerleşik belge pencereleri kılavuz elmas gösterir:  

 ![Belge penceresi kılavuz elmas](../ide/media/documentwindowguidediamonds.png "Documentwindowguidediamonds")  

 Araç Pencereleri IDE veya düzenleme çerçevesinde çerçevesinin bir tarafa tutturulabilir. Araç penceresi kolayca penceresini yeniden yerleştirme yardımcı olmak üzere başka bir konuma sürüklediğinizde kılavuz elmas görünür.  

 Araç pencereleri için kılavuz elmas  

 ![Araç penceresi Kılavuzu Karo](../ide/media/vs10guidediamond.png "VS10GuideDiamond")  

 Aşağıdaki çizimde gösterildiği **Çözüm Gezgini** mavi gölgeli alana göre gösterilen yeni bir konumda yerleştirildi:  

 ![Çözüm Gezgini'nde yeni bir konuma yerleştirme](../ide/media/vs2015_dock_diamond.png "VS2017_Dock_diamond")  

### <a name="close-and-auto-hide-tool-windows"></a>Kapatın ve araç pencereleri otomatik gizleme  
 Araç penceresi tıklayarak kapatabilirsiniz **X** pencere yeniden açmak için sağ başlık çubuğunda; üst içinde kendi klavye kısayol veya menü komutunu kullanın. Araç pencereleri destek adlı bir özellik *Otomatik Gizle*, farklı bir pencere kullandığınızda göz önünden kaydırarak açmak bir pencere neden olur. Bir pencere otomatik gizli olduğunda adını IDE kenarında sekmesinde görüntülenir. Pencereyi yeniden kullanmak için böylece penceresi slayt görünüme geri sekmesine gelin.  

 ![Otomatik Gizle](../ide/media/vs2015_auto_hide.png "vs2017_auto_hide")  

> [!NOTE]
>  Aracını kullanarak Otomatik Gizle çalışan ayarlanacağını windows ayrı ayrı veya sabitlenmiş gruplar halinde seçin veya temizleyin **otomatik gizle düğmesi, yalnızca active aracı windows etkiler** içinde **seçenekleri** iletişim kutusu. Daha fazla bilgi için bkz: [genel, ortam, Seçenekler iletişim kutusu](../ide/reference/general-environment-options-dialog-box.md).  

> [!NOTE]
>  Pencerenin odağa sahip olduğunda Otomatik Gizle Etkinleştirildi sahip araç pencereleri geçici olarak görünüme slayt. Pencereyi yeniden gizlemek için geçerli penceresinin dışında bir öğe seçin. Pencere odağı kaybettiğinde görünümü dışında geri döner.  

### <a name="specifying-a-second-monitor"></a>İkinci İzleyici belirtme  
 İkinci bir monitör varsa ve işletim sisteminizin destekliyorsa, hangi izleyicinin bir pencere görüntüler seçebilirsiniz. Hatta birden çok windows birlikte gruplandırma yapabilirsiniz *rafts* diğer monitörlerde.  

> [!TIP]
>  Birden çok örneğini oluşturabilirsiniz **Çözüm Gezgini** ve başka bir izleme taşıyın. Pencerenin sağ tıklatın ve seçin **yeni Solution Explorer görünümü**. Seçerken çift tıklayarak tüm windows özgün İzleyicisi'ne geri dönebilirsiniz **Ctrl** anahtarı.  

### <a name="reset-name-and-switch-between-window-layouts"></a>Sıfırlama, adı ve pencere düzenlerini arasında geçiş yapma  
 Kullanarak ayarlar koleksiyonunuz için özgün pencere düzenini IDE döndürebilir **pencere düzenini Sıfırla** komutu. Bu komutu çalıştırdığınızda, aşağıdaki eylemler gerçekleşir:  

-   Tüm windows varsayılan konumlarına taşınır.  

-   Varsayılan pencere düzeninde kapalı windows kapatılır.  

-   Varsayılan pencere düzeninde açılan pencereler açılır.  

### <a name="create-and-save-custom-layouts"></a>Oluşturun ve özel düzenler kaydedin  
 Visual Studio, en fazla 10 özel pencere düzenlerini kaydetmek ve kolayca aralarında geçiş sağlar. Aşağıdaki adımlar oluşturmak, kaydetme, çağırma ve her iki yerleşik ve kayan araç pencereleri ile birden çok monitör yararlanmak özel düzenler yönetmek nasıl gösterir.  

 İlk olarak, iki proje içeren bir test çözümü her biri farklı bir en iyi düzen oluşturun.  

##### <a name="create-a-ui-project-and-customize-the-layout"></a>Bir kullanıcı Arabirimi projesi oluşturun ve düzenini özelleştirin  

1.  İçinde **yeni proje** iletişim kutusunda, oluşturmak bir **C# WPF masaüstü uygulaması** ve istediğiniz gibi çağırın. Bu projenin biz alanı Tasarımcı penceresinin en üst düzeye çıkarmak ve diğer aracı windows dışına taşımak istediğiniz şekilde burada kullanıcı arabiriminde çalışmalarımız olduğunu içeriğini.  

2.  Birden çok monitörü varsa, çekme **Çözüm Gezgini** penceresi ve **özellikleri** pencere üzerinde ikinci İzleyicisi. Bir tek monitör sistemde Tasarımcı dışında tüm pencereleri kapatmayı deneyin.  

3.  Tuşuna **Ctrl + Alt + X** görüntülemek için **araç**. Pencerenin yerleştirilmişse sıralandığından, her iki monitörde konumlandırmak için burada istediğiniz gezinen şekilde sürükleyin.  

4.  Tuşuna **F5** Visual Studio hata ayıklama modu içine yerleştirilecek. Konumunu ayarlamak **otomobiller**, **çağrı yığını** ve **çıkış** windows bunları istediğiniz gibi hata ayıklama. Oluşturmakta olduğunuz düzeni düzenleme modunda hem hata ayıklama modu için geçerli olur.  

5.  Hem hata ayıklama modu, hem de düzenleme modunda, düzenleri olduğunda istediğiniz nasıl, ana menüden **penceresi** > **Kaydet pencere düzenini**. Bu düzen "Designer" çağırın  

     Yeni düzeninizi ayrılmış listesinden sonraki klavye kısayolu atanan Not **Ctrl** + **Alt** + **1... 0**.  

##### <a name="create-a-database-project-and-layout"></a>Bir veritabanı projesi oluşturup düzeni  

1.  Yeni bir ekleme **SQL Server veritabanı** çözüme proje.  

2.  Yeni projeye sağ tıklayın **Çözüm Gezgini** ve **Nesne Gezgini görünümünde**. Bu görüntüler **SQL Server Nesne Gezgini** penceresinde access tabloları, görünümleri ve diğer nesneleri veritabanınızdaki olanak sağlar. Bu pencere float veya yerleşik bırakın. Bir aracı windows bunları istediğiniz şekilde ayarlayın. Eklenen daha iyi bir asıl veritabanını ekleyebilirsiniz, ancak bu örnek için gerekli değildir.  

3.  Düzeninizi istediğiniz nasıl olduğunda, ana menüden **penceresi** > **Kaydet pencere düzenini**. Bu düzen "DB proje." çağırın (Biz bu proje için bir hata ayıklama modu düzen ile çıkarmaz.)  

##### <a name="switch-between-the-layouts"></a>Düzenleri arasında geçiş  

Düzenleri arasında geçiş yapmak için klavye kısayollarını kullanın veya ana menüden **penceresi** > **pencere düzenini Uygula**.  

![Uygula penceresi Düzen menüsü](../ide/media/vs2015_applywindowlayout.png "VS2017_ApplyWindowLayout")  

UI düzeni uyguladıktan sonra düzenleme modunda hem hata ayıklama modunda düzenini nasıl korunur unutmayın.  

Çoklu İzleyici Kurulum ve tek monitör dizüstü evde varsa, her makine için en iyi duruma getirilir düzenleri oluşturabilirsiniz.  

>[!NOTE]
>Bir tek İzleyici sistemde çok İzleyici düzeni uygularsanız, ikinci monitörde yerleştirilen kayan windows artık Visual Studio penceresinin arkasında gizlenir. Bu windows tuşuna basarak öne getirmek **Alt + Sekme**. Daha sonra Visual Studio ile birden çok monitör açarsanız, düzenini yeniden uygulayarak windows belirtilen konumlarına geri yükleyebilirsiniz.  

##### <a name="manage-and-roam-your-layouts"></a>Yönetmek ve, düzenleri dolaşan  

Kaldırabilir, yeniden adlandırmak veya seçerek özel düzeninizi yeniden sıralamak **penceresi** > **yönetmek pencere düzenlerini**. Bir düzen taşırsanız, anahtar bağlama listenin yeni konumda yansıtacak şekilde otomatik olarak düzeltilir. Değişiklik bağlamaları aksi olamaz ve bu nedenle aynı anda en fazla 10 düzenleri depolayabilirsiniz.  

![Pencere düzenlerini yönetmek](../ide/media/managewindowlayouts.png "ManageWindowLayouts")  

Kendinize anımsatmak hangi klavye kısayol hangi düzenin atandığı, seçin **penceresi** > **pencere düzenini Uygula**.  

Bu düzenleri otomatik olarak Visual Studio sürümleri arasında ve farklı makinelerde ve herhangi diğer bir Express kuruluş için Express sürümünden karışım örnekleri arasında dolaşıma girer. Ancak, düzenleri Visual Studio, harmanlama ve hızlı arasında dolaştırmamayı.  

## <a name="see-also"></a>Ayrıca bkz.  

[Nasıl yapılır: IDE'de gezinme](../ide/how-to-move-around-in-the-visual-studio-ide.md)
