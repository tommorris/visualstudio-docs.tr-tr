---
title: Visual Studio için ortak denetim düzenleri | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 3e893949-6398-42f1-9eab-a8d8c2b7f02d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8383537a7e9d49f79e98da4dd95a3474803315d8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31148408"
---
# <a name="common-control-patterns-for-visual-studio"></a>Visual Studio için ortak denetim desenleri
##  <a name="BKMK_CommonControls"></a> Ortak Denetimler  
  
### <a name="overview"></a>Genel Bakış  
Ortak Denetimler Visual Studio kullanıcı arabiriminde çoğunluğu oluşturur. Visual Studio arabiriminde kullanılan en yaygın denetimleri izlemelidir [Windows Masaüstü etkileşim kuralları](https://msdn.microsoft.com/library/windows/desktop/dn742399.aspx). Bu konu için Visual Studio özeldir ve özel durumlar veya bu Windows yönergeleri büyütmek ayrıntıları ele alınmaktadır.  
  
#### <a name="common-controls-in-this-topic"></a>Bu konudaki ortak denetimler  
  
-   [Kaydırma çubukları](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_Scrollbars)  
  
-   [Giriş alanları](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_InputFields)  
  
-   [Birleşik giriş kutusu ve aşağı açılır listeler](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ComboBoxesAndDropDowns)  
  
-   [Onay kutuları](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_CheckBoxes)  
  
-   [Radyo düğmeleri](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_RadioButtons)  
  
-   [Grup çerçeveler](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_GroupFrames)  
  
-   [Metin denetimleri](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TextControls)  
  
-   [Düğmeleri ve bağlar](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ButtonsAndHyperlinks)  
  
-   [Ağaç görünümleri](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TreeViews)  
  
#### <a name="visual-style"></a>Görsel stili  
Denetimlere stil ekleme yaparken dikkate alınması gereken ilk denetimleri konulu kullanıcı Arabiriminde kullanılacak olan şeydir. Standart kullanıcı arabiriminde denetimler konulu dışı kullanıcı Arabirimi ve izlemeniz gereken [normal Windows Masaüstü stili](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742399\(v=vs.85\).aspx), yeniden şablonlu değildir ve varsayılan denetim görünümlerini görüntülenip anlamına gelir.  
  
-   **Standart (yardımcı programı) iletişim kutuları:** değil tema uygulanabilir. RE şablonu yok. Temel denetim stili varsayılanları kullanın.  
  
-   **Aracı windows, belge düzenleyicileri, tasarım yüzeyleriyle ve tema uygulanabilir iletişim kutuları:** renk hizmetini kullanarak özel konulu görünümünü kullanın.  
  
###  <a name="BKMK_Scrollbars"></a> Kaydırma çubukları  
 Kaydırma çubukları izlemelidir [Windows için ortak etkileşim desenler kaydırma çubukları](https://msdn.microsoft.com/en-us/library/windows/desktop/bb787527\(v=vs.85\).aspx) içerik bilgilerle engagement'ta sürece, Kod düzenleyicisinde ister.  
  
###  <a name="BKMK_InputFields"></a> Giriş alanları  
 Tipik etkileşim davranışını izleyin [metin kutuları için Windows Masaüstü yönergeleri](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742442\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Görsel stili  
  
-   Giriş alanlarının yardımcı programı iletişim kutularında stilde döndürmemelidir. Denetime iç temel stil kullanın.  
  
-   Konulu giriş alanları, yalnızca konulu iletişim kutuları ve aracı windows kullanılmalıdır.  
  
#### <a name="specialized-interactions"></a>Özel etkileşimler  
  
-   Salt okunur alanları gri (devre dışı) arka plan varsayılan (etkin) ön plan ancak sahip olur.  
  
-   Alanların gerekli  **\<gerekli >** olarak Filigran belgeler bunların içinde. Nadir durumlarda dışında bir arka plan rengini değiştirmemeniz gerekir.  
  
-   Hata doğrulama: bkz [bildirimleri ve Visual Studio için ilerleme durumu](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md)  
  
-   Bunlar gösterilir penceresinin genişliğini uygun değildir veya rasgele bir yolu gibi uzun bir alanın uzunluğu eşleşecek şekilde içeriğin sığması için girdi alanlarının boyutlandırılmalıdır. Uzunluk alanında kaç karakterlere izin ilişkin sınırlamalar, kullanıcıya bir göstergesi olabilir.  
  
     ![Yanlış giriş alanı uzunluğu: ad bu uzun olacağını düşüktür. ] (../../extensibility/ux-guidelines/media/0707-01_incorrectinputfieldcontrol.png "0707 01_IncorrectInputFieldControl")<br />Yanlış giriş alanı uzunluğu: ad bu uzun olacağını düşüktür.
  
     ![Giriş alanı uzunluğu düzeltin: beklenen içerik için makul bir genişliği giriş alanıdır. ] (../../extensibility/ux-guidelines/media/0707-02_correctinputfieldcontrol.png "0707 02_CorrectInputFieldControl")<br />Giriş alanı uzunluğu düzeltin: beklenen içerik için makul bir genişliği giriş alanıdır.
  
###  <a name="BKMK_ComboBoxesAndDropDowns"></a> Birleşik giriş kutusu ve aşağı açılır listeler  
Tipik etkileşim davranışını izleyin [aşağı açılır listeler ve birleşik giriş kutuları için Windows Masaüstü yönergeleri](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742404\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Görsel stili  
  
-   Yardımcı programı iletişim kutularında, denetimi yeniden şablonu yok. Denetime iç temel stil kullanın.  
  
-   UI konulu birleşik giriş kutusu ve aşağı açılan listeler denetimler için standart tema izleyin.  
  
#### <a name="layout"></a>Düzen  
Birleşik giriş kutusu ve aşağı açılan listeler, bunlar gösterilir penceresinin genişliğini uygun değildir veya rasgele bir yolu gibi uzun bir alanın uzunluğu eşleşecek şekilde içeriğin sığması için boyutlandırılmalıdır.  
  
![Yanlış: açılan genişliği görüntülenecek içerik için çok uzun. ] (../../extensibility/ux-guidelines/media/0707-03_incorrectdropdownlayout.png "0707 03_IncorrectDropDownLayout")<br />Yanlış: açılan genişliği görüntülenecek içerik için çok uzun.
  
![Doğru: açılan çeviri artışa izin verme, ancak değil gereksiz yere uzun boyutlandırılır. ] (../../extensibility/ux-guidelines/media/0707-04_correctdropdownlayout.png "0707 04_CorrectDropDownLayout")<br />Doğru: açılan çeviri artışa izin verme, ancak değil gereksiz yere uzun boyutlandırılır. 
  
###  <a name="BKMK_CheckBoxes"></a> Onay kutuları  
Tipik etkileşim davranışını izleyin [onay kutuları için Windows Masaüstü yönergeleri](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742401\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Görsel stili  
  
-   Yardımcı programı iletişim kutularında, denetimi yeniden şablonu yok. Denetime iç temel stil kullanın.  
  
-   Konulu kullanıcı Arabiriminde, standart tema denetimler için onay kutularını izleyin.  
  
#### <a name="specialized-interactions"></a>Özel etkileşimler  
  
-   Bir onay kutusu ile etkileşimi hiçbir zaman bir iletişim kutusu açılır veya başka bir bölümüne gitmek gerekir.  
  
-   Onay kutuları metnin ilk satırını taban çizgisi ile hizalar.  
  
     ![Yanlış: onay kutusu metni ortalanır. ] (../../extensibility/ux-guidelines/media/0707-05_incorrectcheckboxalign.png "0707 05_IncorrectCheckBoxAlign")<br />Yanlış: onay kutusu metni ortalanır.
  
     ![Doğru: onay kutusunu metninin ilk satırı ile hizalanır. ] (../../extensibility/ux-guidelines/media/0707-06_correctcheckboxalign.png "0707 06_CorrectCheckBoxAlign")<br />Doğru: onay kutusunu metninin ilk satırı ile hizalanır.
  
###  <a name="BKMK_RadioButtons"></a> Radyo düğmeleri  
Tipik etkileşim davranışını izleyin [radyo düğmeleri için Windows Masaüstü yönergeleri](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742436\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Görsel stili  
Yardımcı programı iletişim kutularında, stil radyo düğmeleri yapın. Denetime iç temel stil kullanın.  
  
#### <a name="specialized-interactions"></a>Özel etkileşimler  
Grup ayrım sıkı bir düzende korumak gerekli olmadıkça radyo seçimler kapsamak için bir grup çerçevesini kullanmak gerekli değildir.  
  
###  <a name="BKMK_GroupFrames"></a> Grup çerçeveler  
Tipik etkileşim davranışını izleyin [Grup çerçeveler için Windows Masaüstü yönergeleri](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742405\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Görsel stili  
Yardımcı programı iletişim kutularında, grubu çerçeve stili yok. Denetime iç temel stil kullanın.  
  
#### <a name="layout"></a>Düzen  
  
-   Grup ayrım sıkı bir düzende korumak gerekli olmadıkça radyo seçimler kapsamak için bir grup çerçevesini kullanmak gerekli değildir.  
  
-   Hiçbir zaman tek bir denetim için bir grup çerçevesi kullanın.  
  
-   Bazen, bir grup çerçeve kapsayıcısını yerine yatay bir kural kullanmanız için kabul edilebilir.  
  
##  <a name="BKMK_TextControls"></a> Metin denetimleri

### <a name="static-text-fields"></a>Statik metin alanları

Bir statik metin alanı salt okunur bilgileri gösterir ve kullanıcı tarafından seçilemez. Panoya kopyalamak için kullanıcının isteyebileceği herhangi bir metin için kullanmaktan kaçının. Ancak, salt okunur statik metin durumundaki bir değişikliği yansıtacak şekilde değiştirebilirsiniz. Aşağıda, kök Namespace metin kutusunun üstüne yapılan değişiklikleri yansıtacak şekilde bilgi Grup değişikliklerini altındaki çıkış adı statik metin örnekte.

Statik metin bilgileri görüntülemek için iki yolu vardır.

Statik metin kendi herhangi kapsama olmadan bir iletişim kutusu açtığında hiçbir gruplandırma çakışması olduğunu olabilir. Ek satırları kutusunun gerçekten gerekli olup olmadığına karar. Bir örnek aşağıda gösterildiği gibi bir dizin yolu bir Grup satırı tarafından oluşturulan bir bölümünün altında görüntülenir:  

![Statik metin bilgisi metin denetimlerinde](../../extensibility/ux-guidelines/media/DisplayingStaticText.png "DisplayingStaticText.png")<br />Statik metin bilgisi metin denetimlerinde

Bir iletişim burada diğer gruplandırılmış alanlar var ve bilgilerin kapsama okunabilirliği yardımcı ve ne zaman bir bölüm bulunabilir gizli veya gösterilen (olarak **Özellikler penceresini** açıklama bölmesinde) veya benzer kullanıcı Arabirimi ile tutarlı olmasını istediğiniz statik metin kutusunun içine koyun. Bu grup kutusu tek bir kural olmalıdır ve ile renkli `ButtonShadow`:

![Statik metin özellikleri penceresinde](../../extensibility/ux-guidelines/media/PropertiesWindow.png "PropertiesWindow.png")<br />Özellikleri penceresinde statik metin

### <a name="read-only-text-box"></a>Salt okunur metin kutusu

Bu alanın içindeki metni seçin, ancak düzenlemek değil izin verir. Bu metin kutuları ile normal 3-b düz uç tarafından katýna bir `ButtonShadow` dolgu.

Bir metin kutusu etkin hale gelebilir (düzenlenebilir) bir kullanıcı denetimi/onay kutusunun işaretini kaldırdığınızda veya seçme/seçimini radyo düğmesi gibi ilişkili bir denetim olarak değiştiren olduğunda. Örneğin, **Araçları &gt; seçenekleri** aşağıda gösterilen sayfa **giriş sayfası** metin kutusu etkin hale geldiği zaman **Varsayılanı kullan** onay kutusunun işaretli olduğundan.

![Salt okunur metin kutusu, etkin ve etkin durumları gösteren](../../extensibility/ux-guidelines/media/ReadOnlyTextBox.png "ReadOnlyTextBox.png")<br />Etkin ve etkin durumları gösteren salt okunur metin kutusu

### <a name="using-text-in-dialogs"></a>İletişim kutularında metin kullanma

Anahtar yönergeleri iletişim kutuları metin:

-   Metin kutuları, liste kutuları ve çerçeveleri unthemed iletişim kutuları için etiketleri bir fiil ile başlatmak, yalnızca ilk sözcüğün ilk büyük olması ve noktayla bitmelidir.

    > Metin denetimlerinde konulu iletişim kutularını izleyin [Windows Masaüstü UX yönergeleri](https://msdn.microsoft.com/library/windows/desktop/dn742479.aspx) ve Yardım bağlantıları soru işaretleri dışında bitiş noktalama kazanmaz.

-   Onay kutuları ve seçenek düğmeleri için etiketleri yalnızca ilk sözcüğü bir ilk büyük bir fiil başlatmak ve bitiş noktalama işareti.

-   Düğmeler, menüler, menü öğeleri ve sekmeler için etiketleri ilk harfler büyük harf her sözcüğün (başlık harf) sahip.

-   Etiket terminolojisi diğer iletişim kutuları benzer etiketler ile tutarlı olmalıdır.

-   Mümkünse, bir yazıcı/yazma ya da uygulama geliştiriciye geçmeden önce metin düzenleyicisi vardır.

-   Tüm denetimler etiketleri dışında özel durumlarda olmalıdır hangi sekme yeterlidir.
Yardımcı metin uygun olduğunda kullanın.

### <a name="helper-text"></a>Yardımcı metin

İletişim kutusu amacını anlamasına yardımcı olmak için veya hangi eylemin yapılacağını göstermek için iletişim kutularında dahil. Yardımcı metin basit iletişim kutuları alanınızda karışıklık önlemek için yalnızca gerekli olduğunda kullanılmalıdır. İki çeşit Yardımcısı metnin iletişim ve filigran ' dir.

Yardımcı metin için ortak konumlarını izleyin ve yeni alanlara tanışın Seçici. Yardımcı metin için genel senaryolar şunlardır:

-   Karmaşık bir iletişim kutusu ile etkileşim konusunda ek yönü vermek için iletişim kutuları, metin Yardımcısı.

-   Filigran metni boş aracı windows ya da içerik neden görünür olduğunu açıklamak için iletişim kutuları.

-   Açıklama bölmesinde en altında ister **Özellikler penceresini**.

-   Metin kullanıcı başlamak için yapması gereken eylemi açıklamak için boş bir düzenleyicide Filigran.
  
### <a name="dialog-helper-text"></a>İletişim yardımcı metin

Bir kullanıcı deneyimi Tasarımcısı yardımcı metin uygun olduğunda belirlemenize yardımcı. Tasarımcı yardımcı metin yanı sıra genel içeriği göründüğü tanımlayabilirsiniz. Kullanıcı Yardımı yazma/gerçek metnini düzenle.

### <a name="watermarks"></a>Filigranlar

İletişim kutuları hazırladığı biraz farklı Filigran kılavuzları yararlanır. Bir iletişim kutusu özellikle çok sayıda kullanıcı Arabirimi öğeleri ile (etiketleri, ipucu metnini, düğmeler ve diğer kapsayıcı denetimleri metinle), meşgul görünebilir çünkü bunlar siyah ekranda göründüğünde, filigranları göze koyu gri daha iyi (VSColor: `ButtonShadow`). Genellikle bir denetimi beyaz bir arka plan içeren bir liste kutusu gibi içinde Filigran görüntülenir (VSColor: `Window`).

-   Metin koyu gri görünür (VSColor: `ButtonShadow`). Ancak, bir orta gri veya renkli diğer Filigran görünüyorsa, (VSColor: `ButtonFace`) arka plan ve ilgilendiren okunabilirlik hakkında siyah metinle Git yoktur (VSColor: `WindowText`).

-   Filigranlar ortalanmış veya sola. Standart tasarım kurallar hizalama kararları verirken uygulanır. Filigran arka planda seçilemez.

![Filigran metni örneği](../../extensibility/ux-guidelines/media/WatermarkTextExample.gif)<br />Filigran metni örneği

### <a name="context-specific-dynamic-text"></a>Bağlama özgü (dinamik) metin

Dinamik metin iletişim veya kalıcı olmayan UI iki yolla kullanılan biri olabilir: dinamik içerik olarak veya dinamik bir etiket.

-   Dinamik etiketi: bir ortak dinamik metin öğeleri ve sağa kılavuzda görüntülenen bu öğeler için özellikler listesini içeren bir iletişim kutusu gibi daha fazla bilgi için seçili öğeyi teklif açıklayıcı panelinde kullanılır. Böylece sol tarafta bir öğe seçildiğinde, sağ kılavuza belirli o öğeye ilişkin bilgileri gösterir ve özellik ızgarasının etiketi dinamik olabilir.

-   Dinamik metin: Burada bu şekilde belirli bilgileri ve genel bilgileri görüntülemek gerekir, ancak bakım değil aşırı için alınması gereken durumlarda yararlı olabilir.

Kullanıcıların bilgi kopyalama becerisini sahip olmasını istiyorsanız, salt okunur metin alanındaki dinamik metin olmalıdır.
  
##  <a name="BKMK_ButtonsAndHyperlinks"></a> Düğmeleri ve bağlar  
  
### <a name="overview"></a>Genel Bakış  
Düğme ve bağlantı denetimleri (köprü) izlemelidir [köprüleri temel Windows Masaüstü yönergeler](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742406\(v=vs.85\).aspx) ifadesi, boyutlandırma ve aralık kullanım için.  
  
### <a name="choosing-between-buttons-and-links"></a>Düğmeler ve bağlantıları arasında seçim yapma  
Geleneksel olarak, düğmeleri eylemler için kullanılmış ve köprüleri gezinti için ayrılmış. Düğmeleri tüm durumlarda kullanılabilir, ancak rolü bağlantılar, düğmeler ve bağlantıları bazı koşullarda daha değiştirilebilir; böylece Visual Studio'da genişletilmiştir.  
  
Ne zaman komut düğmeleri kullanın:  
  
-   Birincil komutları  
  
-   Giriş toplamak için kullanılan windows görüntüleme veya ikincil komutları olsa bile seçimleri, yapmak  
  
-   Yıkıcı veya geri alınamaz Eylemler  
  
-   Sihirbazlar ve sayfa akışları içinde taahhüt düğmeleri  
  
Aracı Windows komut düğmesi engellemek veya ikiden fazla sözcükler etiketi gerekiyorsa. Bağlantılar uzun etiket olabilir.  
  
 Ne zaman kullanılacağı bağlantılarını içerir:  
  
-   Başka bir pencere, belge veya web sayfasına gezinme  
  
-   Bir uzun etiket ya da eylemi amacı açıklamak için kısa cümle gerektiren durumlar  
  
-   Burada bir düğme UI doldurmaya sıkı alanları sağlanan eylem yıkıcı veya geri alınamaz değil  
  
-   İkincil komutları durumlarda devre dışı bırakma emphasizing komutların çoğu olduğu  
  
#### <a name="examples"></a>Örnekler  
![Komut bir durum iletisi aşağıdaki Bilgi Çubuğu'nda kullanılan bağlantıları](../../extensibility/ux-guidelines/media/070703-01_commandlinkinfobar.png "070703 01_CommandLinkInfobar")<br />Bir durum iletisi aşağıdaki Bilgi Çubuğu'nda kullanılan komutu bağlantıları
  
![CodeLens açılan penceresinde kullanılan bağlantıları](../../extensibility/ux-guidelines/media/070703-02_linksincodelens.png "070703 02_LinksInCodeLens")<br />CodeLens açılan penceresinde kullanılan bağlantıları
  
![Burada düğmeleri çok fazla dikkat çekmek ikincil komutları için kullanılan bağlantıları](../../extensibility/ux-guidelines/media/070703-03_linksassecondarycommands.png "070703 03_LinksAsSecondaryCommands")<br />Burada düğmeleri çok fazla dikkat çekmek ikincil komutları için kullanılan bağlantıları
  
### <a name="common-buttons"></a>Ortak düğmeleri  
  
#### <a name="text"></a>Metin  
Yazma yönergeleri izleyin [UI metin ve terminolojiyi](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology).  
  
#### <a name="visual-style"></a>Görsel stili  
  
##### <a name="standard-unthemed"></a>Standart (unthemed)  
Visual Studio'da çoğu düğmeleri yardımcı programı iletişim kutularında görünür ve değil stilde. Bunlar işletim sistemi tarafından gerektiği şekilde düğmelerin standart görünümünü yansıtmalıdır.  
  
##### <a name="themed"></a>Teması  
Bazı durumlarda, düğmeleri stilde UI içinde kullanılabilir ve bu düğmeleri uygun şekilde biçimlendirilmiş gerekir. Bkz: [iletişim kutularını](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Dialogs) konulu denetimleri hakkında bilgi için.  
  
### <a name="special-buttons"></a>Özel düğmeler  
  
#### <a name="browse-buttons"></a>Düğmeleri Gözat...  
**[Gözat...]**  düğmeleri kılavuzları, iletişim kutuları ve aracı windows ve diğer kalıcı olmayan bir kullanıcı Arabirimi öğeleri kullanılır. Bunlar, kullanıcı değeri denetime doldurma yardımcı olur. bir seçici görüntüler. Bu düğme, uzun ve kısa iki çeşidi vardır.  
  
![Uzun [Gözat...] düğmesi](../../extensibility/ux-guidelines/media/070703-04_browselong.gif "070703 04_BrowseLong")<br />Uzun [Gözat...] düğmesi
  
![Yalnızca üç nokta kısa [...] düğmesi](../../extensibility/ux-guidelines/media/070703-05_browseshort.gif "070703 05_BrowseShort")<br />Yalnızca üç nokta kısa [...] düğmesi
  
Ne zaman yalnızca üç nokta kısa düğmesini kullanın:  
  
-   Varsa birden fazla uzun **[Gözat...]**  zaman göz atmak için birkaç alanlar izin gibi bir iletişim kutusu düğmesini. Kısa kullanmak **[...]**  bu durum tarafından oluşturulan kafa karıştırıcı erişim tuşları önlemek her düğmesi (**& Gözat** ve **B & özatın** aynı iletişim).  
  
-   Sıkı bir iletişim kutusu veya uzun düğmesini koyma makul bir yer olduğunda.  
  
-   Düğme bir kılavuz denetiminde görüneceğini.  
  
Düğme kullanma için yönergeler:  
  
-   Erişim tuşu kullanmayın. Klavyeyi kullanarak erişmek için kullanıcının bitişik denetiminden sekme gerekir. Herhangi bir Gözat düğmesini hemen doldurur alan sonra kalan şekilde sekme sırası olduğundan emin olun. İlk dönemden altındaki bir alt çizgi hiçbir zaman kullanmayın.  
  
-   Microsoft Active Accessibility (MSAA) ayarlamak **adı** özelliğine **Gözat...**  , ekran şekilde (üç nokta dahil olmak üzere) okuyucular, "Gözat" ve "nokta nokta nokta" veya değil "Dönem-Dönem-Dönem." okur Yönetilen denetimler için bu ayarı anlamına gelir **AccessibleName** özelliği.  
  
-   Hiçbir zaman bir üç nokta kullanmayın **[...]**  Gözat eylem dışında her şey için düğmesi. Örneğin, gerekirse bir **[yeni...]**  düğmesi, ancak iletişim kutusunun tasarlanması gerekir metin için yeterli alan yok.  
  
##### <a name="sizing-and-spacing"></a>Boyutlandırma ve aralığı  
![Düğmeler [Gözat...] boyutlandırma: standart sürümünü 75 x 23 piksel, kısa sürüm 26 x 23 piksel](../../extensibility/ux-guidelines/media/070703-06_browsesizing.png "070703 06_BrowseSizing")<br />Düğmeler [Gözat...] boyutlandırma
  
![Aralık [Gözat...] düğmeleri: ilgili denetim ve standart Gözat düğmesi 7 piksel aralığı, arasındaki boşluğu ilgili denetim ve kısa Gözat düğmesini 5 piksel](../../extensibility/ux-guidelines/media/070703-07_browsespacing.png "070703 07_BrowseSpacing")<br />Aralık [Gözat...] düğmeleri
  
#### <a name="graphical-buttons"></a>Grafik düğmeleri  
Bazı düğmeleri her zaman bir grafik görüntüsünü kullanabilir ve hiçbir zaman alanından tasarruf etmek ve Yerelleştirme sorunları önlemek için metni içeren gerekir. Bunlar genellikle alan seçiciler ve diğer sıralanabilir listelerinde kullanılır.  
  
> **Not:** kullanıcınız (hiçbir erişim tuşları vardır) bu düğmeleri sekmesinde, bu nedenle bunları duyarlı bir sırada yerleştirin. Harita `name` sürer ve böylece ekran okuyucular doğru düğmesi eylemi yorumlama eyleme düğmesinin özelliği.  
  
| İşlev | Düğme |  
| --- | --- |  
| Ekle | ![Grafik "Ekle" düğmesi](../../extensibility/ux-guidelines/media/070703-08_buttonadd.png "070703 08_ButtonAdd") |
| Kaldır | ![Grafik "Kaldır" düğmesine](../../extensibility/ux-guidelines/media/070703-09_buttonremove.png "070703 09_ButtonRemove") |
| Tümünü Ekle | ![Grafik "Tümünü Ekle" düğmesi](../../extensibility/ux-guidelines/media/070703-10_buttonaddall.png "070703 10_ButtonAddAll") |
| Tümünü Kaldır | ![Grafik "Tümünü Kaldır" düğmesini](../../extensibility/ux-guidelines/media/070703-11_buttonremoveall.png "070703 11_ButtonRemoveAll") |
| Yukarı Taşı | ![Grafik "Yukarı Taşı" düğmesini](../../extensibility/ux-guidelines/media/070703-12_buttonmoveup.png "070703 12_ButtonMoveUp") |
| Aşağı Taşı | ![Grafik "Aşağı Taşı" düğmesini](../../extensibility/ux-guidelines/media/070703-13_buttonmovedown.png "070703 13_ButtonMoveDown") |
| Sil | ![Grafik "Sil" düğmesini](../../extensibility/ux-guidelines/media/070703-14_buttondelete.png "070703 14_ButtonDelete") |
  
##### <a name="sizing-and-spacing"></a>Boyutlandırma ve aralığı  
Grafik düğmeleri kısa aynıdır için boyutlandırma **[Gözat...]**  düğmesi (26 x 23 piksel cinsinden):  
  
![Grafik görüntüsünün düğmesine, ile ve saydam rengi gösteren olmadan görünümünü](../../extensibility/ux-guidelines/media/070703-15_graphicalbuttonspacing.png "070703 15_GraphicalButtonSpacing")<br />Grafik görüntüsünün düğmesine, olan ve olmayan saydam rengi gösteren görünüm
  
### <a name="hyperlinks"></a>Köprüler  
Köprüler Yardım konusu, kalıcı iletişim veya Sihirbazı'nı açma gibi Gezinti tabanlı eylemler için uygundur. Köprü komutu için kullanılırsa, her zaman için kullanıcı Arabirimi görünür ve belirgin bir değişiklik görüntülemelidir. Genel olarak, (kaydetme, iptal ve Sil gibi) bir eylem yürütme Eylemler daha iyi bir düğmesini kullanarak bildirilir.  
  
#### <a name="writing-style"></a>Yazı stili  
İzleyin [kullanıcı arabirimi metni için Windows Masaüstü Kılavuzu](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx). "Bilgi daha fazla hakkında" kullanmayın "Söyleyin bana daha fazla hakkında" veya "Bu Get help" ifade. Bunun yerine, Yardım içerik tarafından yanıtlanan birincil soru bakımından Yardım bağlantı metni ifade. Örneğin, "**için Sunucu Gezgini bir sunucuya nasıl ekleyebilirim?**"  
  
#### <a name="visual-style"></a>Görsel stili  
  
-   Köprüler her zaman kullanılması gereken [VSColor hizmet](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService). Köprü doğru biçimlendirilmiş değil, kırmızı etkin olduğunda yanıp sönen veya ziyaret sonra farklı bir renk gösterir.  
  
-   Bağlantı bir cümle parçası içinde tam bir cümle gibi Filigran olmadıkça durumu üzerine notlarını denetim en alt çizgiler dahil etmeyin.  
  
-   Alt çizgiler gidildiğinde görünür döndürmemelidir. Bunun yerine, geri bildirim bağlantısı etkin olduğunu kullanıcıya hafif renk değişikliği ve uygun bağlantıyı imleci ' dir.  
  
##  <a name="BKMK_TreeViews"></a> Ağaç görünümleri  
  
Üst-alt gruplar halinde karmaşık düzenlemek için bir yöntem listeler ağaç görünümleri sağlar. Bir kullanıcı genişletin veya ortaya veya temel alınan alt öğeleri gizlemek için üst gruplar daraltın. Ağaç görünümü içinde her öğe, daha fazla eylem sağlamak için seçilebilir.  
  
###  <a name="BKMK_TreeViewVisualStyle"></a> Ağaç görünümü görsel stili  
  
#### <a name="expanders"></a>Genişleticileri  
Ağaç görünümü denetimleri, Windows ve Visual Studio tarafından kullanılan genişletici tasarımı için uygun olmalıdır. Her düğüm genişletici denetimi ortaya temel alınan öğeleri veya gizlemek için kullanır. Genişletici denetimi kullanarak, Windows ve Visual Studio içinde farklı ağaç görünümleri karşılaşabileceğiniz kullanıcılar için tutarlılık sağlar.  
  
![Doğru: ağaç görünümü düğümünün genişletici denetimi kullanarak uygun stili](../../extensibility/ux-guidelines/media/070705-1_treeviewcorrect.png "070705 1_TreeViewCorrect")<br />Doğru: ağaç görünümü düğümünün genişletici denetimi kullanarak uygun stili
  
![Yanlış: ağaç görünümü düğümünün hatalı stili](../../extensibility/ux-guidelines/media/070705-2_treeviewincorrect1.png "070705 2_TreeViewIncorrect1")<br />Yanlış: ağaç görünümü düğümünün hatalı stili
  
#### <a name="selection"></a>Seçim  
Bir düğüm ağaç görünümü seçildiğinde Vurgu ağaç görünümü denetiminin tam genişlik için genişletmeniz gerekir. Bu, kullanıcıların seçmiş olduğunuz hangi öğesinin NET bir şekilde belirlemesine yardımcı olur. Seçim renkleri geçerli Visual Studio temasını yansıtmalıdır.  
  
![Doğru: Seçili düğümün Vurgu ağaç görünümü denetiminin tüm genişliği sığar. ] (../../extensibility/ux-guidelines/media/070705-1_treeviewcorrect.png "070705 1_TreeViewCorrect")<br />Doğru: Seçili düğümün Vurgu ağaç görünümü denetiminin tüm genişliği sığar.
  
![Yanlış: Vurgu Seçili düğümün ağaç görünümü denetiminin tüm genişliği uygun değil. ] (../../extensibility/ux-guidelines/media/070705-3_treeviewincorrect2.png "070705 3_TreeViewIncorrect2")<br />Yanlış: Vurgu Seçili düğümün ağaç görünümü denetiminin tüm genişliği uygun değil.
  
#### <a name="icons"></a>Simgeler  
Bunlar görsel öğeleri arasındaki farklar belirlemenize yardımcı simgeleri yalnızca ağaç görünümü denetimleri kullanılmalıdır. Genel olarak, simgeler yalnızca simgeler öğeleri türlerini ayırt etmek için bilgi taşımak heterojen listelerinde kullanılmalıdır. Türdeş listesinde simgelerle parazit olarak sık görülebilir ve kaçınılmalıdır. Bu durumda grubu simgesi (üst) içindeki öğe türü iletmek. Bu kural için özel simge dinamiktir ve durumu göstermek için kullanılan olacaktır.  
  
#### <a name="scroll-bars"></a>Kaydırma çubukları  
İçerik ağaç görünümü denetiminin içinde uyuyorsa kaydırma çubukları her zaman gizli. Bunu kaydırılabilir penceresinde gizli veya yarı saydam ve ağaç görünümü içeren pencere odağa sahip olduğunda görüntülenir veya ağaç vurgulu kendisini görüntülemek için kaydırma çubuklarını için kabul edilebilir.  
  
![Ağaç görünümü denetiminin sınırları içeriği aştığınızdan iki dikey ve yatay kaydırma çubukları görüntülenir. ] (../../extensibility/ux-guidelines/media/070705-4_scrollbars.png "070705 4_Scrollbars")<br />Ağaç görünümü denetiminin sınırları içeriği aştığınızdan iki dikey ve yatay kaydırma çubukları görüntülenir.
  
###  <a name="BKMK_TreeViewInteractions"></a> Ağaç görünümü etkileşimleri  
  
#### <a name="context-menus"></a>Bağlam menüleri  
Alt menü seçenekleri bir bağlam menüsündeki bir ağaç görünümü düğümü ortaya çıkarabilir. Bir kullanıcı bir öğeyi sağ veya menü öğesi seçili ile Windows klavyede tuşa genellikle, bu oluşur. Düğüm odağı kazanır ve seçili önemlidir. Bu alt ait hangi öğesinin tanımlamak kullanıcı yardımcı olur.  
  
![Kullanıcıya bildirmek için bağlam menüsünde kazançlar odak hangi öğesi oluşturmak sahip öğe seçilmedi. ] (../../extensibility/ux-guidelines/media/070705-5_contextmenu.png "070705 5_ContextMenu")<br />Kullanıcıya bildirmek için bağlam menüsünde kazançlar odak hangi öğesi oluşturmak sahip öğe seçilmedi.
  
#### <a name="keyboard"></a>Klavye  
Ağaç görünümü, öğeleri seçin ve klavyeyi kullanarak düğümleri Genişlet/Daralt özelliği sağlaması gerekir. Bu gezinti bizim erişilebilirlik gereksinimleri karşıladığını sağlar.  
  
##### <a name="tree-view-control"></a>Ağaç görünümü denetimi  
Visual Studio ağaç denetimleri ortak klavye gezinti izlemelisiniz:  
  
-   **Yukarı Ok:** ağacı taşıyarak öğeleri seçin  
  
-   **Aşağı ok:** ağaç taşıyarak öğeleri seçin  
  
-   **Sağ ok:** ağacında bir düğümü genişletin  
  
-   **Sol Ok:** ağacında bir düğümü Daralt  
  
-   **Anahtarı girin:** başlatmak, yük, seçili öğe yürütme  
  
##### <a name="trid-tree-view-and-grid-view"></a>Trid (ağaç görünümü ve ızgara görünümü)  
Kılavuz içinde bir ağaç görünümü içeren karmaşık bir denetimi trid denetimdir. Ağaç gezinme genişletme ve daraltma aynı klavye komutlarını aşağıdaki eklemelerle bir ağaç görünümü olarak dikkate:  
  
-   **Sağ ok:** bir düğümünü genişletin. Düğüm genişletildikten sonra sağdaki yakın sütuna gezinme devam etmelidir. Gezinti satırın sonunda durdurmanız gerekir.  
  
-   **Sekmesi:** yakın hücrenin sağdaki gitmenizi sağlar.  Satırın sonunda Gezinti sonraki satıra devam eder.  
  
-   **Üst karakter + sekme:** yakın hücrenin sol gitmenizi sağlar.  Satırın başındaki Gezinti önceki satırdaki en sağdaki hücreye devam eder.  
  
![Visual Studio trid denetiminde](../../extensibility/ux-guidelines/media/070705-6_trid.png "070705 6_Trid")<br />Visual Studio'da trid denetimi