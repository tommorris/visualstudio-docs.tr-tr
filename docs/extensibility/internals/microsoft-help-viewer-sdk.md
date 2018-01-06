---
title: "Microsoft Yardım Görüntüleyicisi SDK | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 620d7dcd-d462-475e-a449-fbfa06ff12c5
caps.latest.revision: "33"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7c15956bc861f9eb20267dc97446cf5ea49cae31
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="microsoft-help-viewer-sdk"></a>Microsoft Yardım Görüntüleyicisi SDK
Bu makalede, Visual Studio Yardım Görüntüleyicisi tümleştiricileri için aşağıdaki görevleri içerir:  
  
-   Bir konu (F1 desteği) oluşturma  
  
-   Yardım Görüntüleyici içerik markalama paket oluşturma  
  
-   Makaleler kümesi dağıtma  
  
-   Visual Studio Kabuğu (tümleşik veya yalıtılmış) ekleme Yardım  
  
-   Ek Kaynaklar  
  
### <a name="creating-a-topic-f1-support"></a>Bir konu (F1 desteği) oluşturma  
Bu bölümde sunulan bir konu, konunun gereksinimleri, (F1 destek gereksinimleri dahil) konu ve son olarak, bir örnek konu ile işlenen sonucu oluşturmak için kısa bir açıklama bileşenlerinin genel bir bakış sağlar.  
  
**Yardım Görüntüleyicisi konusuna genel bakış**  
  
İşleme için bir konu çağrıldığında, Yardım Görüntüleyicisi'ni yükleme veya XHTML, konu ile birlikte son güncelleştirme zamanında konu ile ilişkili marka paketi öğelerini alır ve sunulan içeriği görünümle sonuçlanmasını iki birleştirir (veri markalama + Konu veri).  Marka paket logolar, içerik davranışları ve marka metni (telif hakkı, vs.) için destek içerir.  "Marka paketi oluşturma" marka paket öğeleri hakkında daha fazla bilgi için aşağıya bakın.  Var olması durumunda konuyla ilgili hiçbir markalama paketinin, Yardım Görüntüleyicisi'ni (Branding_en-US.mshc) Yardım Görüntüleyici uygulama kök dizininde bulunan geri dönüş markalama paketi kullanır.  
  
**Yardım Görüntüleyicisi konu gereksinimleri**  
  
Yardım Görüntüleyici içinde doğru işlenmek üzere ham konu içeriği W3C temel 1.1 XHTML olması gerekir.  
  
Bir konu genellikle iki bölüm içerir:  
  
-   Meta veriler (içerik meta verileri başvuru bakın): Örneğin, konu benzersiz kimliği, anahtar sözcüğü değeri, konu TOC kimliği, konuyla ilgili verileri üst düğüm kimliği, vb.  
  
-   Gövde içeriği: W3C temel 1.1 XHTML ile uyumlu içeren içerik davranışları (daraltılabilir alanı, kod parçacığında, vb. desteklenen Tam bir listesi aşağıda gösterilmiştir).  
  
Visual Studio markalama paketi denetimleri desteklenir:  
  
-   Bağlantılar  
  
-   CodeSnippet  
  
-   CollapsibleArea  
  
-   Devralınan üye  
  
-   LanguageSpecificText  
  
Desteklenen dil dizeleri (büyük/küçük harfe duyarlı değildir):  
  
-   JavaScript  
  
-   CSharp veya c#  
  
-   cplusplus veya visualc ++ veya c ++  
  
-   JScript  
  
-   visualbasic'tir veya vb  
  
-   f # veya fsharp veya fs  
  
-   diğer - bir dil adı temsil eden bir dize  
  
**Yardım Görüntüleyici konu oluşturma**  
  
ContosoTopic4.htm adlı yeni bir XHTML belge oluşturun ve başlık etiketi (aşağıda) içerir.  
  
```html  
<html>  
<head>  
<title>Contoso Topic 4</title>  
</head>  
  
<body>  
  
</body>  
</html>  
  
```  
  
Ardından, nasıl konu (kendi kendini veya markalı), sunulacak nasıl tanımlamak için veri eklemek için bu konuda bulunduğu TOC Kimliğini (için diğer konular başvuruyla bağlantı) içinde F1, bu konuda başvurmak için vb.  Desteklenen meta verileri tam bir listesi için aşağıdaki "İçerik meta verileri" tabloya bakın.  
  
-   Bu durumda, kendi markalama paketi, Visual Studio Yardım Görüntüleyicisi markalama paketinin bir değişken kullanacağız.  
  
-   F1 meta ad ve değer ekleme ("Microsoft.Help.F1" içerik "ContosoTopic4" =) IDE özellik paketi sağlanan F1 değerinde eşleşir.  (Daha fazla bilgi için F1 destek bölümüne bakın.)   Bu F1 eşleşen değerdir çağrı gelen F1 IDE'de seçildiğinde bu konuyu görüntülemek için IDE içinden.  
  
-   Konu kimliği Ekle Bu diğer konular tarafından bu konuya bağlanmak için kullanılan dizedir.  Bu konuda Yardım Görüntüleyicisi kimliği değil.  
  
-   İçindekiler için bu konuda İçindekiler düğümü nerede görüneceğini tanımlamak için bu konunun üst düğümü ekleyin.  
  
-   İçindekiler için bu konunun düğüm sırası ekleyin. Üst düğüm n sayıda alt düğüme sahip olduğunda, bu konunun konumu alt düğümleri sırasına göre tanımlayın. For example, bu konuda 4 4 alt konuları sayısıdır.)  
  
Örnek meta veri bölümü:  
  
```html  
<html>  
<head>  
<title>Contoso Topic 4</title>  
  
<meta name="SelfBranded" content="false" />     
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />  
    <meta name="Microsoft.Help.Id" content="ContosoTopic4" />  
<meta name="Microsoft.Help.F1" content=" ContosoTopic4" />  
    <meta name="Language" content="en-us" />  
<meta name="Microsoft.Help.TocParent" content="ContosoTopic0" />  
<meta name="Microsoft.Help.TocOrder" content="4" />   
  
</head>  
  
<body>  
  
</body>  
</html>  
  
```  
  
**Konu gövdesi**  
  
Konu gövdesi (üstbilgi ve altbilgi dahil değil) sayfası bağlantıları, bir not bölümü, daraltılabilir bir alanla, bir kod parçacığı ve dil belirli metnin bir bölümünü içerir.  Sunulan konunun bu alanları hakkında bilgi için markalama bölümüne bakın.  
  
1.  Bir konu başlığı etiketi ekleyin:`<div class="title">Contoso Topic 4</div>`  
  
2.  Not bölümüne ekleyin:`<div class="alert"> add your table tag and text </div>`  
  
3.  Daraltılabilir bir alanla ekleyin:`<CollapsibleArea Expanded="1" Title="Collapsible Area Test Heading"> add text  </CollapsibleArea>`  
  
4.  Kod parçacığını ekleyin:`<CodeSnippet EnableCopyCode="true" Language="CSharp" ContainsMarkup="false" DisplayLanguage="C#" > a block of code </CodeSnippet>`  
  
5.  Kod dili belirli bir metni ekleyin: `<LanguageSpecificText devLangcs="CS" devLangvb="VB" devLangcpp="C++" devLangnu="F#" />` bu devLangnu Not = diğer diller girmenize olanak sağlar. Örneğin, devLangnu = "Fortran" Fortran görüntüler, kod parçacığında DisplayLanguage Fortran =  
  
6.  Sayfa bağlantılarının ekleyin:`<a href="ms-xhelp://?Id=ContosoTopic1">Main Topic</a>`  
  
> [!NOTE]
>  Not: Desteklenmeyen yeni "için görüntüleme dilini" (örneğin, F #, Cobol, Fortran) kod renklendirme kod parçacığında bulunan tek renkli olacaktır.  
  
**Örnek Yardım Görüntüleyicisi konu** kodu meta verileri, bir kod parçacığı, daraltılabilir alan ve dil belirli bir metni nasıl tanımlanacağı gösterilmektedir.  
  
```html
<?xml version="1.0" encoding="utf-8"?>  
<html>  
<head>  
<title>Contoso Topic 4</title>  
  
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />  
    <meta name="Microsoft.Help.Id" content="ContosoTopic4" />  
<meta name="Microsoft.Help.F1" content=" ContosoTopic4" />  
    <meta name="Language" content="en-us" />  
<meta name="Microsoft.Help.TocParent" content="ContosoTopic0" />  
<meta name="Microsoft.Help.TocOrder" content="4" />   
<meta name="SelfBranded" content="false" />     
</head>  
  
<body>  
<div class="title">Contoso Topic 4</div>  
  
  <div id="header">  
<table id="bottomTable" cellpadding="0" cellspacing="0"  width="100%">  
        <tr id="headerTableRow2"><td align="left">  
            <span id="nsrTitle">Contoso Topic 1</span>  
          </td>  
<td align="right">  
</td></tr>  
<tr id="headerTableRow1"><td align="left">  
            <span id="runningHeaderText">Contoso Widgets & Sprockets</span>  
          </td></tr>  
      </table>  
</div>  
  
<h2>Table of Contents</h2>  
  
<ul class="toc">  
<li class="tocline1"><a href="#introduction" target="_self">1.0 Introduction</a></li>  
<li class="tocline1"><a href="#seealso" target="_self">See Also</a></li>  
</ul>  
  
<div class="topic">  
  
<div id="mainSection">  
<div id="mainBody">  
  
<a name="introduction"></a>  
<h2>1.0 Introduction</h2>  
<p>[This documentation is for sample purposes only.]</p>  
  
<p>Contoso Topic 1 contains examples of:  
<ul>  
<li>Collapsible Area</li>  
<li>Bookmark ("See also")</li>  
<li>Code Snippets from Branding Package</li>  
</ul>  
 </p>  
<div class="alert"><table><tr><th>  
<strong>Note </strong></th></tr>  
<tr><td>  
<p>This is an example of a <span class="label">Note </span>section.    
Call out important items for your reader in this <span class="label">Note </span>box.  
</p></td></tr>  
</table>  
</div>  
</div>  
  
<CollapsibleArea Expanded="1" Title="Collapsible Area Test Heading">  
  
            <a id="sectionToggle0"><!----></a>  
  
<div>  
Example of Collapsible Area  
<br/>  
Lorem ipsum dolor sit amet...  
</div>  
</CollapsibleArea>  
  
<div id="snippetGroup" >  
<CodeSnippet EnableCopyCode="true" Language="VisualBasic" ContainsMarkup="false" DisplayLanguage="Visual Basic" >  
Private Sub ToolStripRenderer1_RenderGrip(sender as Object, e as ToolStripGripRenderEventArgs) _ Handles ToolStripRenderer1.RenderGrip  
Dim messageBoxVB as New System.Text.StringBuilder()  
    messageBoxVB.AppendFormat("{0} = {1}", "GripBounds", e.GripBounds)  
    messageBoxVB.AppendLine()  
 ...  
    MessageBox.Show(messageBoxVB.ToString(),"RenderGrip Event")  
End Sub  
</CodeSnippet>  
  
<CodeSnippet EnableCopyCode="true" Language="CSharp" ContainsMarkup="false" DisplayLanguage="C#" >  
private void ToolStripRenderer1_RenderGrip(Object sender, ToolStripGripRenderEventArgs e)   
{   
System.Text.StringBuilder messageBoxCS = new System.Text.StringBuilder();  
messageBoxCS.AppendFormat("{0} = {1}", "GripBounds", e.GripBounds );  
messageBoxCS.AppendLine();  
...  
MessageBox.Show(messageBoxCS.ToString(), "RenderGrip Event" );  
}  
</CodeSnippet>  
  
<CodeSnippet EnableCopyCode="true" Language="fsharp" ContainsMarkup="false" DisplayLanguage="F#" >  
some F# code  
</CodeSnippet>  
</div>  
  
<h4 class="subHeading">Example of code specific text</h4>Language = <LanguageSpecificText devLangcs="CS" devLangvb="VB" devLangcpp="C++" devLangnu="F#" />  
  
<a name="seealso"></a>  
<h1 class="heading">See Also</h1>  
  
    <div id="seeAlsoSection" class="section">   
    <div class="seeAlsoStyle">  
        <a href="ms-xhelp://?Id=ContosoTopic1">Main Topic</a>  
    </div>  
 </div>  
</div>  
</div>  
</body>  
</html>  
  
```  
  
**F1 desteği**  
  
Visual Studio'da F1 seçerek imleci IDE içinden yerleşimini gelen sağlanan değerleri oluşturur ve "(İmleç konumuna dayalı. bir özellik paketi" sağlanan değerlerle doldurur İmleç x özelliği olduğunda, özellik x etkin/odak ve özellik paketi değerlerle doldurur.  F1 seçildiğinde özellik paketi doldurulur ve Visual Studio F1 kod görünür müşteriler varsayılan Yardım kaynak yerel ya da çevrimiçi olup olmadığını görmek için (çevrimiçi varsayılandır), ayarı kullanıcıları temel alan uygun dize oluşturur (varsayılan çevrimiçiyse) - Kabuk yürütme (Yardım yönetici parametreleri başlatma Kılavuzu exe bölümüne bakın) yerel Yardım Görüntüleyicisi + yerel Yardım varsayılan veya parametre listesi anahtar sözcüğüyle MSDN URL'si ise özellik paketi gelen anahtar sözcükleri parametrelere sahip.  
  
Birden çok değerli dize olarak, ilk terim arama vuruş için almak için üç dizeleri için F1'e döndürülürse, başvurulan ve bulundu, biz yapılır, Aksi halde, sonraki dizeye taşıyın.  Sırası önemlidir. Çoklu değer anahtar sözcükleri sunumu kısa dize için en uzun bir dize olmalıdır.  Bu durumda birden çok değerli anahtar kelimeleri doğrulamak için seçilen anahtar sözcüğünü içeren çevrimiçi F1 URL dizesi arayın.  
  
Böylece kullanıcı ayarı için çevrimiçi olduğunda, ardından biz yalnızca F1 isteği doğrudan çevrimiçi sorgu hizmetimizi Yardım Kitaplığı Aracısı yönlendirme yerine MSDN Geçiren Visual Studio 2012'de, biz kasıtlı olarak daha güçlü bir bölme çevrimiçi ve çevrimdışı arasında yapılan Biz Visual Studio 2010'da olduğunu. Biz sonra bir durumuna bağlı "yüklü satıcı içeriği = true" Bu bağlamda farklı bir şeyler verilmeyeceğini belirlemek için. TRUE ise, biz sonra müşterileriniz için desteklemek istediğinizi düşünmenizdir bağlı olarak bu ayrıştırma ve yönlendirme mantığı gerçekleştirin. False ise, ardından biz yalnızca MSDN'ye gidin. Kullanıcının ayar için yerel ise, tüm çağrıları yalnızca yerel Yardım motoruna gidin.  
  
F1 Akış Diyagramı:  
  
![F1 akış](../../extensibility/internals/media/f1flow.png "F1flow")  
  
Yardım Görüntüleyici varsayılan Yardım içerik kaynağı çevrimiçi (tarayıcıda başlatmak) için ayarlandığında:  
  
-   Visual Studio iş ortağı (VSP) özellikleri yayma F1 özellik paketi (özellik paketi prefix.keyword ve kayıt defterinde bulundu önek çevrimiçi URL'sini) değerine: F1'e gönderir bir VSP URL + parametreleri tarayıcıya.  
  
-   Visual Studio özellikleri (dil Düzenleyicisi, Visual Studio belirli menü öğeleri, vb.): F1 tarayıcıya bir Visual Studio URL gönderir.  
  
Yardım Görüntüleyici varsayılan Yardım içerik kaynağını yerel Yardım'a (Yardım Görüntüleyici'de başlatma) ayarlandığında:  
  
-   F1 özellik paketi ve yerel depo dizin arasında anahtar sözcüğü eşleştiği VSP özellikleri (diğer bir deyişle, özellik paketi prefix.keyword = yerel deposu dizininde bulunan değer): F1 Yardım Görüntüleyici konusunda işler.  
  
-   Visual Studio özellikleri (Visual Studio özelliklerinden yayılan özellik paketi geçersiz kılmak VSP seçeneği): F1 Yardım Görüntüleyici'de Visual Studio konu oluşturur.  
  
F1'e geri dönüş için satıcı Yardım içeriği etkinleştirmek için aşağıdaki kayıt defteri değerlerini ayarlayın. F1'e geri dönüş Yardım Görüntüleyici F1 Yardımı içerik aramak için çevrimiçi ayarlanır ve satıcı içeriği yerel olarak kullanıcıların sabit diske yüklenecek anlamına gelir. Varsayılan ayar için çevrimiçi yardıma olsa bile Yardım Görüntüleyici içerik için yerel Yardım bakmak.  
  
1.  Ayarlama **VendorContent** Yardım 2.3 kayıt defteri anahtarı altındaki:  
  
    -   32-bit işletim sistemleri için:  
  
         HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\v2.3\Catalogs\VisualStudio15  
  
         "VendorContent" = dword: 00000001  
  
    -   64-bit işletim sistemleri için:  
  
         HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15  
  
         "VendorContent" = dword: 00000001  
  
2.  Ortak ad alanı Yardım 2.3 kayıt defteri anahtarı altında kaydedin:  
  
    -   32-bit işletim sistemleri için:  
  
         HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\v2.3\Partner*\\< ad alanı\>*  
  
         "Konum"Çevrimdışı =""  
  
    -   64-bit işletim sistemleri için:  
  
         HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Partner*\\< ad alanı\>*  
  
         "Konum"Çevrimdışı =""  
  
**Ayrıştırma temel yerel Namespace**  
  
Kayıt defterinde temel yerel ad alanını ayrıştırma açmak için adını yazarak yeni bir DWORD değeri ekleyin: BaseNativeNamespaces ve 1 (altında desteklemek için istedikleri katalog anahtar) değerini ayarlayın.  Örneğin, Visual Studio katalog kullanmak istiyorsanız, anahtar yoluna ekleyebilirsiniz:  
  
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15
  
F1 anahtar sözcüğü zaman üstbilgi/yöntemi karşılaştı Biçim '/' karakterini çıkışı, aşağıdaki yapı kaynaklanan ayrıştırılır:  
  
-   Başlık: kayıt defterinde kaydetmek için kullanılan ad olacaktır  
  
-   YÖNTEM: Bu geçtiğini anahtar sözcüğü olur.  
  
Örneğin, verilen CustomLibrary adlı özel bir kitaplığı ve isteği içinde geliyorsa F1 olarak biçimlendirilmiş MyTestMethod, adında bir yöntem `CustomLibrary/MyTestMethod`.  
  
Bir kullanıcı daha sonra CustomLibrary namespace ortakları hive altında olarak kaydettirmek ve istenen ne olursa olsun konumu anahtarı sağlayın ve sorguya geçirilen anahtar sözcüğü MyTestMethod olacaktır.  
  
**Hata ayıklama aracı IDE'de Yardım etkinleştir**  
  
Aşağıdaki kayıt defteri anahtarı ve değeri ekleyin:  
  
HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\15.0\Dynamic Yardım anahtarı: görüntü hata ayıklama çıktı perakende değerindeki: Evet  
  
Yardım menü öğesi altında IDE içinde "Yardım bağlamını Debug" seçin  
  
**İçerik meta verileri**  
  
Aşağıdaki tabloda, köşeli ayraç görünen herhangi bir dize tarafından tanınan bir değer değiştirilmesi gereken bir yer tutucudur. Örneğin, \<meta name="Microsoft.Help.Locale" içerik = "[dil kodu]" / >, "[dil kodu]" gerekir yerine bir değerle gibi "en-us".  
  
|Özellik (HTML gösterim)|Açıklama|  
|--------------------------------------|-----------------|  
|\<Meta name="Microsoft.Help.Locale" içerik = "[kodu dili]" / >|Bu konu için bir yerel ayarlar. Bu etiket bir konuda kullandıysanız, yalnızca bir kez kullanılmalıdır ve diğer Microsoft Help etiketleri eklenmesi gerekir. Bu etiket kullanılmazsa konunun gövde metni belirtilmişse, ürün yerel ayar ile ilişkili bir sözcük ayırıcı kullanarak dizinlenir; Aksi takdirde, en-us sözcük ayırıcı kullanılır. Bu etiket ISOC RFC 4646 için uygundur. Microsoft Help düzgün çalıştığından emin olmak için genel Language özniteliği yerine bu özelliği kullanın.|  
|\<Meta name="Microsoft.Help.TopicLocale" içerik = "[kodu dili]" / >|Başka yerel ayarlara de kullanıldığında bu konu için bir yerel ayarlar. Bu etiket bir konuda kullanılırsa, yalnızca bir kez kullanılmalıdır. Katalog içeriği birden fazla dilde içerdiğinde bu etiketi kullanın. Birden çok konu katalogdaki aynı Kimliğe sahip olabilir, ancak her bir benzersiz TopicLocale belirtmeniz gerekir. Yerel katalog eşleşen bir TopicLocale belirtir konu içeriği tablosunda görüntülenen konu. Bununla birlikte, konu tüm dil sürümlerini arama sonuçlarında görüntülenir.|  
|\<başlık > [başlık] \< /title >|Bu konu başlığı belirtir. Bu etiketi gereklidir ve yalnızca bir kez bir konuda kullanılması gerekir. Konu gövdesi bir başlık içermiyorsa \<div > bölümü, bu başlık, konu ve içindekiler görüntülenir.|  
|\<Meta name = "Microsoft.Help.Keywords" içerik = "[aKeywordPhrase]" / >|Yardım Görüntüleyicisi'ni dizin bölmesinde görüntülenen bir bağlantı metnini belirtir. Bağlantı tıklatıldığında konu görüntülenir. Bir konu için birden çok dizin anahtar sözcükleri belirtebilir veya bağlantıları bu konuya dizinde görünmesini istemiyorsanız bu etiketi atlayabilirsiniz. Bu özellik için Yardım'ın önceki sürümlerinden "K" anahtar sözcükleri dönüştürülebilir.|  
|\<Meta name="Microsoft.Help.Id" içerik = "[TopicID]" / >|Bu konuda tanımlayıcısını ayarlar. Bu etiketi gereklidir ve yalnızca bir kez bir konuda kullanılması gerekir. Kimliği kataloğunda aynı yerel ayara sahip konuları arasında benzersiz olması gerekir. Başka bir konuda, bu kimliği kullanarak bu konuda bir bağlantı oluşturabilirsiniz|  
|\<Meta name="Microsoft.Help.F1" content="[System.Windows.Controls.Primitives.IRecyclingItemContainerGenerator]"/ >|Bu konu için F1 anahtar sözcüğü belirtir. Bir konu için birden çok F1 anahtar sözcükleri belirtebilir veya bir uygulamanın kullanıcı F1 tuşuna bastığında görüntülenmesi için bu konunun istemiyorsanız bu etiketi atlayabilirsiniz. Genellikle, yalnızca bir F1 anahtar sözcüğü bir konu için belirtilir. Bu özellik için Yardım'ın önceki sürümlerinden "F" anahtar sözcükleri dönüştürülebilir.|  
|\<Meta adı "Açıklama" Content = "[konu açıklama]" / >|Bu konudaki içeriğin kısa bir özetini sağlar. Bu etiket bir konuda kullanılırsa, yalnızca bir kez kullanılmalıdır. Bu özellik, doğrudan sorgu kitaplığı tarafından erişilir; Dizin dosyasında depolanmaz.|  
 Meta name="Microsoft.Help.TocParent" içerik = "[parent_Id]" / >|Bu konunun üst konu içindekilerde belirtir. Bu etiketi gereklidir ve yalnızca bir kez bir konuda kullanılması gerekir. Üst Microsoft.Help.Id değerdir. Bir konu tablo yalnızca tek bir konumda İçindekiler olabilir. "-1" İçindekiler kökü konu kimliği olarak kabul edilir. İçinde [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)], o sayfası Yardım Görüntüleyici giriş sayfasıdır. Bu, özellikle TocParent = 1, en üstte düzeyi gösterilmediğini emin olmak için bazı konular eklediğimiz aynı nedenidir. Yardım Görüntüleyici giriş sayfası bir sistem sayfasıdır ve bu nedenle olmayan tarafından değiştirilebilir. -1 Kimliğine sahip bir sayfa eklemek bir VSP çalışırsa, içerik kümesine eklenir, ancak Yardım Görüntüleyici her zaman sistem sayfası - Yardım Görüntüleyicisi giriş kullanır|  
|\<Meta name="Microsoft.Help.TocOrder" içerik = "[pozitif tamsayı]" / >|İçindekiler tablosuna göre kendi eş konular bu konuda göründüğü belirtir. Bu etiketi gereklidir ve yalnızca bir kez bir konuda kullanılması gerekir. Bir tamsayı değerdir. Bir alt değeri tamsayı belirten bir konu daha yüksek değer tamsayı belirten bir konu görünür.|  
|\<Meta name="Microsoft.Help.Product" içerik = "[ürün kodu]" / >|Bu konuda açıklanan ürün belirtir. Bu etiket bir konuda kullanılırsa, yalnızca bir kez kullanılmalıdır. Bu bilgiler ayrıca Yardım dizin oluşturucu geçirilen parametre olarak sağlanabilir.|  
|\<Meta name="Microsoft.Help.ProductVersion" içerik = "[sürüm numarası]" / >|Bu konuda açıklanan ürün sürümünü belirtir. Bu etiket bir konuda kullanılırsa, yalnızca bir kez kullanılmalıdır. Bu bilgiler ayrıca Yardım dizin oluşturucu geçirilen parametre olarak sağlanabilir.|  
|\<Meta name="Microsoft.Help.Category" içerik = "[dize]" / >|Ürünü tarafından içerik alt bölümleri tanımlamak için kullanılır. Bir konu için birden çok alt bölümleri tanımlamak veya tüm alt bölümleri tanımlamak için bağlantıları istemiyorsanız bu etiketi atlayabilirsiniz. Bu etiket bir konuda Yardım'ın önceki bir sürümden dönüştürüldüğünde TargetOS ve TargetFrameworkMoniker öznitelikleri depolamak için kullanılır. İçerik AttributeName:AttributeValue biçimidir.|  
|\<Meta name="Microsoft.Help.TopicVersion içerik ="[konu sürüm numarası]"/ >|Birden çok sürümü katalogdaki varken bu konuyu sürümünü belirtir. Microsoft.Help.Id benzersiz olması garanti edilmemiştir, bir konu birden fazla sürümünü katalogdaki, örneğin, bir katalog bir konu .NET Framework 3.5 ve bir konu için .NET Framework 4 için içerir ve her ikisi de aynı mikro sahip olduğunda mevcut olduğunda bu etiketi gereklidir çünkü yazılım. Help.Id.|  
|\<Meta adı "SelfBranded" content = "[TRUE veya false değerini]" = / >|Bu konuda Yardım Kitaplığı Yöneticisi başlatma markalama paketinin veya konuya belirli bir marka paket kullanıp kullanmadığını belirtir. Bu etiket ya da TRUE olmalıdır ya da yanlış. Konu diğer içerik işleme farklıysa bile tasarlandığı gibi işlenir böylece Yardım Kitaplığı Yöneticisi başlatıldığında ayarlanır markalama paketi ilişkili konu için markalama paketinin geçersiz kılmaları sonra TRUE ise. FALSE ise, geçerli konuda Yardım Kitaplığı Yöneticisi başlatıldığında ayarlanır markalama paketi göre işlenir. Varsayılan olarak, Yardım Kitaplığı Yöneticisi SelfBranded değişkeni TRUE olarak bildirilir sürece false olarak kendi kendine marka varsayar; Bu nedenle, bildirmeniz gerekmez \<meta adı "SelfBranded" Content = "FALSE" / >.|  
  
### <a name="creating-a-branding-package"></a>Marka paket oluşturma  
Visual Studio sürümünü Isolated ve tümleşik Kabuk Visual Studio iş ortakları için de dahil olmak üzere farklı Visual Studio ürün sayısı kapsar.  Bu ürünlerinin her biri bazı konu tabanlı Yardım içeriği desteği, ürüne özgü markalama derecesini gerektirir.  ISO Kabuk sarmalar, SQL Studio'yu kendi benzersiz Yardım içerik için her konuda markalama gerekirken Örneğin, Visual Studio konuları tutarlı marka sunuyu olması gerekir.  Tümleşik Kabuk iş ortağı kendi konu markalama korurken Visual Studio ürün Yardım içeriği üst öğe içinde olması için Yardım konuları isteyebilirsiniz.  
  
Marka paketleri Yardım Görüntüleyicisi'ni içeren ürün tarafından yüklenir.  Visual Studio ürünler için:  
  
-   Bir geri dönüş markalama paketi (Branding_\<yerel ayar > .mshc) Yardım Görüntüleyicisi 2.3 uygulama kök dizininde yüklü (örnek: C:\Program Files (x86) \Microsoft Help Viewer\v2.3) Yardım Görüntüleyici dil paketi tarafından.  Bu, paket markalama ürünü yüklü olmayan durumlar için kullanılır (içerik yüklendi) veya burada yüklü markalama paketi bozuk.  Paket marka uygulama kök geri dönüş kullanıldığında (logo ve geri bildirim) Visual Studio öğeleri yoksayılır unutmayın.  
  
-   Visual Studio içeriği içerik paket hizmetinden yüklendiğinde markalama paketinin (ilk zaman içerik yükleme senaryosu) da yüklenir.  Marka paket için bir güncelleştirme varsa, sonraki içerik güncelleştirme veya ek paket yükleme eylemi gerçekleştiğinde güncelleştirme yüklenir.  
  
Microsoft Yardım Görüntüleyici, konu meta verileri temel alarak konuları markalama destekler.  
  
-   Burada konu meta veri self markalı tanımlar = true, olduğu gibi konu işlemek, (durum marka) hiçbir şey yapma.  
  
-   Burada konu meta veri self markalı tanımlar = false, TopicVendor meta veri değeriyle ilişkili markalama paketinin kullanın.  
  
-   Burada konu meta veri name="Microsoft.Help.TopicVendor tanımlar" içerik =\< satıcı MSHA marka paket adı >, içerik değeri tanımlanan markalama paketinin kullanın.  
  
-   Visual Studio katalog içinde öncelik uygulama markalama paketlerin yoktur.  İlk Visual Studio varsayılan markalama uygulanır ve daha sonra konu meta verilerde tanımlanan ve desteklenen ilişkili markalama paketini (yükleme msha tanımlandığı gibi), satıcı tanımlı markalama bir geçersiz kılma uygulanır.  
  
Marka öğeleri genellikle üç ana kategoriye ayrılır:  
  
-   Üstbilgi öğeleri (örnekler geri bildirim bağlantısı, koşullu vazgeçme, logosu)  
  
-   (Örnekler Genişlet/Daralt denetim metin öğeler içerir ve kod parçacığını öğeleri) davranışlarını içerik  
  
-   Alt öğeleri (örneğin telif hakkı)  
  
Markalı öğeleri dahil olarak kabul öğeleri (Bu spec ayrıntılı):  
  
-   Katalog/ürün logo (örneğin, Visual Studio)  
  
-   Geri bildirim bağlantısı ve e-posta öğeleri  
  
-   Vazgeçme  
  
-   Telif Hakkı metin  
  
Visual Studio Yardım Görüntüleyicisi marka paketindeki destekleyici dosyaları şunları içerir:  
  
-   Grafik (logolar, simgeler, vb.)  
  
-   Branding.js - destekleyici içerik davranışları komut dosyaları  
  
-   Branding.xml - içerik genelinde tutarlı bir şekilde kullanılan dizeleri katalog.  Not: Visual Studio yerelleştirme metin branding.xml öğelerinde eklemek için _locID = "\<benzersiz değer >"  
  
-   Branding.css - sunu tutarlılık için Stil tanımları  
  
-   Printing.css - tutarlı yazdırılan sunum için Stil tanımları  
  
Yukarıda belirtildiği gibi markalama paketleri konu ile ilişkilidir:  
  
-   Zaman SelfBranded = false meta verilerde tanımlanan, konu paket markalama katalog devralır  
  
-   Veya ne zaman SelfBranded = false ve var. benzersiz bir marka paketi MSHA ve kullanılabilir içeriği yüklendiğinde tanımlanmıştır  
  
VSPs özel marka paketleri uygulamak için (VSP içerik, SelfBranded = True), devam etmek için bir yoldur (Yardım Görüntüleyicisi ile yüklenen) geri dönüş marka paket başlatmak ve uygun olarak dosyanın adını değiştirmek için.  Branding_\<yerel ayar > .mshc dosyadır .mshc için değiştirilen dosya uzantısına sahip bir zip dosyası, bu nedenle yalnızca uzantısı .mshc .zip olarak değiştirin ve içeriğini çıkarın.  Paket öğeleri markalama için aşağıya bakın ve uygun şekilde değiştirin (örneğin, VSP logo ve Branding.xml dosya logo referansı logosunu değiştirmek, Branding.xml güncelleştirme VSP özellikleri, vb.).  
  
Tüm değişiklikleri tamamladığınızda, istenen marka öğeleri içeren bir zip dosyası oluşturun ve uzantısını .mshc için değiştirin.  
  
Özel marka paketi ilişkilendirmek için (konularını içeren) içerik mshc birlikte marka mshc dosyaya başvuru içeren MSHA oluşturun.  "MSHA" temel MSHA oluşturmak için aşağıya bakın.  
  
Branding.xml dosyayı konu içerdiğinde tutarlı bir konuda belirli öğeleri çizmek için kullanılan bir liste öğelerini içeren \<meta name="Microsoft.Help.SelfBranded" içerik = "false" / >.  Branding.xml dosyasındaki öğeleri Visual Studio listesi aşağıda listelenmiştir.  Bu liste bir şablon olarak burada bunlar gereksinimlerini markalama kendi ürün karşılamak için bu öğeleri (örneğin logosu, geri bildirim ve telif hakkı) değiştirmek ISO Kabuk üyeler için kullanılması amaçlanmıştır unutmayın.  
  
Not: "{n}" tarafından belirtildiği kodu bağımlılıklarını değişkenleriniz - kaldırma veya bu değerleri değiştirme hataları ve büyük olasılıkla uygulama kilitlenme neden olur. Yerelleştirme tanımlayıcıları (örnek _locID="codesnippet.n"), Visual Studio markalama paketinde dahil edilir.  
  
**Branding.XML**  
  
|||  
|-|-|  
|Özellik:|**CollapsibleArea**|  
|Kullanım:|Daraltır içerik denetimi metni genişletme|  
|**Öğesi**|**Değer**|  
|ExpandText|Genişletme|  
|CollapseText|Daralt|  
|Özellik:|**CodeSnippet**|  
|Kullanım:|Kod parçacığı denetimi metin.  Not: Kod parçacığı "Sonu olmayan" alanı içerikle alanına değiştirilir.|  
|**Öğesi**|**Değer**|  
|CopyToClipboard|Panoya kopyala|  
|ViewColorizedText|Renklendirilen görünümü|  
|CombinedVBTabDisplayLanguage|Visual Basic (örnek)|  
|VBDeclaration|Bildirim|  
|VBUsage|Kullanım|  
|Özellik:|**Geri bildirim, altbilgi ve logosu**|  
|Kullanım:|E-posta yoluyla geçerli konu hakkında geri bildirim sağlamak müşteri için bir geri bildirim denetimi sağlar.  Telif Hakkı metin içeriği.  Logo tanımı.|  
|**Öğesi**|**Değer (Bu dizeler içerik katılım gereksinimini karşılamak üzere değiştirilebilir.)**|  
|Telif Hakkı|© 2013 Microsoft Corporation. Tüm hakları saklıdır.|  
|SendFeedback|\<bir href = "{0}" {1} > geri bildirim gönder\</a > Bu konuda Microsoft.|  
|FeedbackLink||  
|LogoTitle|[!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)]|  
|LogoFileName|vs_logo_bk.gif|  
|LogoFileNameHC|vs_logo_wh.gif|  
|Özellik:|**Sorumluluk reddi**|  
|Kullanım:|Makine için büyük/küçük harfe belirli bildirimler kümesi içerik çevrilir.|  
|**Öğesi**|**Değer**|  
|MT_Editable|Bu makale makine çevirisiyle. Internet bağlantınız varsa, "aynı anda özgün İngilizce içeriğe sahip düzenlenemez modunda bu sayfayı görüntülemek için bu konuyu çevrimiçi görüntülemek" seçin.|  
|MT_NonEditable|Bu makale makine çevirisiyle. Internet bağlantınız varsa, "aynı anda özgün İngilizce içeriğe sahip düzenlenemez modunda bu sayfayı görüntülemek için bu konuyu çevrimiçi görüntülemek" seçin.|  
|MT_QualityEditable|Bu makalede el ile çevrilmiştir. Internet bağlantınız varsa, "aynı anda özgün İngilizce içeriğe sahip düzenlenemez modunda bu sayfayı görüntülemek için bu konuyu çevrimiçi görüntülemek" seçin.|  
|MT_QualityNonEditable|Bu makalede el ile çevrilmiştir. Internet bağlantınız varsa, "aynı anda özgün İngilizce içeriğe sahip düzenlenemez modunda bu sayfayı görüntülemek için bu konuyu çevrimiçi görüntülemek" seçin.|  
|MT_BetaContents|Bu makalede bir ön sürüm için makine çevirisi. Internet bağlantınız varsa, "aynı anda özgün İngilizce içeriğe sahip düzenlenemez modunda bu sayfayı görüntülemek için bu konuyu çevrimiçi görüntülemek" seçin.|  
|MT_BetaRecycledContents|Bu makalede, bir ön sürüm için el ile çevrilmiştir. Internet bağlantınız varsa, "aynı anda özgün İngilizce içeriğe sahip düzenlenemez modunda bu sayfayı görüntülemek için bu konuyu çevrimiçi görüntülemek" seçin.|  
|Özellik:|**LinkTable**|  
|Kullanım:|Çevrimiçi konusuna bağlantılar için destek|  
|**Öğesi**|**Değer**|  
|LinkTableTitle|Bağlantı tablosu|  
|TopicEnuLinkText|İngilizce sürümü görüntülemek\</a > konunun bilgisayarınızda kullanılabilir.|  
|TopicOnlineLinkText|Bu konuyu görüntülemek \<bir href = "{0}" {1} > Çevrimiçi\</a >|  
|OnlineText|Çevrimiçi|  
|Özellik:|**Video ses denetimi**|  
|Kullanım:|Öğeleri ve video içeriği için metin görüntüleme|  
|**Öğesi**|**Değer**|  
|MultiMediaNotSupported|Internet Explorer 9 veya üstü {0} içeriği destekleyecek şekilde yüklenmesi gerekir.|  
|VideoText|video görüntüleme|  
|AudioText|ses akışı|  
|OnlineVideoLinkText|\<p > Bu konu ile ilgili video görüntülemek için {0} tıklatın\<bir href = "\ {1\}" > {2}here\</a >.\< /p >|  
|OnlineAudioLinkText|\<p > Bu konu ile ilgili ses dinlemek için {0} tıklatın\<bir href = "\ {1\}" > {2}here\</a >.\< /p >|  
|Özellik:|**İçerik denetimi yüklü değil**|  
|Kullanım:|Contentnotinstalled.htm işleme için kullanılan metin öğeleri (dize)|  
|**Öğesi**|**Değer**|  
|ContentNotInstalledTitle|İçerik bilgisayarınızda bulundu.|  
|ContentNotInstalledDownloadContentText|\<p > Bilgisayarınızı için içerik indirmek için \<bir href = "{0}" {1} > Yönet sekmesini\</a >.\< /p >|  
|ContentNotInstalledText|\<p > İçerik bilgisayarınızda yüklü. Lütfen yerel Yardım içerik yükleme için yöneticinize başvurun. \</p >|  
|Özellik:|**Konu denetim bulunamıyor**|  
|Kullanım:|Topicnotfound.htm işleme için kullanılan metin öğeleri (dize)|  
|**Öğesi**|**Değer**|  
|TopicNotFoundTitle|İstenen konu bilgisayarınızda bulunamıyor.|  
|TopicNotFoundViewOnlineText|\<p > istediğiniz konu bilgisayarınızda bulunamadı, ancak yapabilecekleriniz \<bir href = "{0}" {1} > konuyu çevrimiçi görüntüleyin\</a >.\< /p >|  
|TopicNotFoundDownloadContentText|\<p > Gezinti Bölmesi benzer konulara bağlantılar için bkz: veya \<bir href = "{0}" {1} > Yönet sekmesini\</a > bilgisayarınıza içerik indirmek için.\< /p >|  
|TopicNotFoundText|\<p > istediğiniz konu bilgisayarınızda bulunamadı. \</p >|  
|Özellik:|**Konu bozuk denetimi**|  
|Kullanım:|Topiccorrupted.htm işleme için kullanılan metin öğeleri (dize)|  
|**Öğesi**|**Değer**|  
|TopicCorruptedTitle|İstenen konu görüntülenemiyor.|  
|TopicCorruptedViewOnlineText|\<p > Yardım Görüntüleyici istenen konusu görüntüleyemiyor. Konunun içerik veya temel alınan bir sistem bağımlılığı bir hata olabilir. \</p >|  
|Özellik:|**Giriş sayfası denetimi**|  
|Kullanım:|Yardım Görüntüleyici üst düzey düğüm içeriği görüntülemeyi destekleme metin.|  
|**Öğesi**|**Değer**|  
|HomePageTitle|Yardım Görüntüleyicisi giriş|  
|HomePageIntroduction|\<p > Microsoft Yardım Görüntüleyici bir önemli bilgi kaynağı olarak Microsoft araçları, ürünleri, teknolojileri ve hizmetleri kullanan herkes için hoşgeldiniz. Yardım Görüntüleyicisi'ni nasıl yapılır ve başvuru bilgileri, örnek kod, teknik makaleler ve daha fazla bilgi için erişmenizi sağlar. İçindekiler göz gereken içeriği bulmak için tam metin araması kullanın ya da anahtar sözcük dizini kullanarak içerikte gezinin. \</p >|  
|HomePageContentInstallText|\<p >\<br / > kullanım \<bir href = "{0}" {1} > içeriği yönetmek\</a > sekmesinde aşağıdakileri yapın:\<ul >\<li > içeriği bilgisayarınıza eklemek.\< /li >\<li > yerel içeriğinize Güncelleştirmeleri denetle.\< /li >\<li > içeriği bilgisayarınızdan kaldırın.\< /li >\</ul >\</p >|  
|HomePageInstalledBooks|Yüklü defterleri|  
|HomePageNoBooksInstalled|İçerik bilgisayarınızda bulundu.|  
|HomePageHelpSettings|Yardım içerik ayarları|  
|HomePageHelpSettingsText|\<p > geçerli ayarınız yerel yardım eder. Yardım Görüntüleyicisi'ni, bilgisayarınızda yüklü içeriği görüntüler. \<br / > kaynağınız Visual Studio menü çubuğunda, Yardım içeriğinin değiştirmeyi tercih \<span style = "{0}" > Yardım, Yardım tercih kümesini\</span >.\< br / >\</p >|  
|Megabayt|MB|  
  
**Branding.js**  
  
Visual Studio Yardım Görüntüleyicisi marka öğeleri tarafından kullanılan JavaScript branding.js dosyası içerir.  Marka öğeleri ve destekleyici JavaScript işlevi listesi aşağıdadır.  Bu dosya için yerelleştirilmesi tüm dizeler, bu dosyanın üst "Yerelleştirilebilir dizeler" bölümünde tanımlanır.  ICL dosya branding.js dosya içinde loc dizeleri için oluşturulan unutmayın.  
  
||||  
|-|-|-|  
|**Marka özelliği**|**JavaScript işlevi**|**Açıklama**|  
|Var...||Değişkenleri tanımlayın|  
|Kullanıcı kod dili Al|setUserPreferenceLang|bir dizin eşlemeleri # kod dili için|  
|Ayarlama ve tanımlama bilgisi değerleri alma|getCookie, setCookie||  
|Devralınan üye|changeMembersLabel|Devralınan üye Genişlet/Daralt|  
|Zaman SelfBranded = False|Yüklendiğinde|Yazdırma isteği olup olmadığını denetlemek için sorgu dizesi okuyun.  Kullanıcı tercih edilen sekmesi odaklanmak codesnippets ayarlayın.  Bir yazdırma ise, istek sonra isPrinterFriendly true olarak ayarlayın. Yüksek karşıtlıklı modu için denetleyin.|  
|Kod parçacığı|addSpecificTextLanguageTagSet||  
||getIndexFromDevLang||  
||ChangeTab||  
||setCodesnippetLang||  
||setCurrentLang||  
||CopyToClipboard||  
|CollapsibleArea|addToCollapsibleControlSet|Tüm daraltılabilir denetim nesnesi listeye yazın.|  
||CA_Click|Daraltılabilir alanının durumuna göre hangi resim ve metin sunmak için tanımlar|  
|Logo Karşıtlık desteği|isBlackBackground()|Arka plan siyah olup olmadığını belirlemek için çağrılır.  Yalnızca doğru olduğunda yüksek karşıtlık modunda.|  
||isHighContrast()|yüksek karşıtlıklı modu algılamak için renkli span kullanın|  
||onHighContrast(black)|Yüksek Karşıtlık algılandığında çağrılır|  
|LST işlevi|||  
||addToLanSpecTextIdSet(id)||  
||updateLST(currentLang)||  
||getDevLangFromCodeSnippet(lang)||  
|Multimedya işlevi|Resim yazısı (başlar, son, metin stili)||  
||findAllMediaControls(normalizedId)||  
||getActivePlayer(normalizedId)||  
||captionsOnOff(id)||  
||toSeconds(t)||  
||getAllComments(node)||  
||styleRectify (stil adı, styleValue)||  
||showCC(id)||  
||subtitle(id)||  
  
**HTM DOSYALARI**  
  
Marka paket anahtar bilgileri örneğin hangi içerik kümeleri yüklü açıklayan bir bölüm ve konuları yapamadığında kullanıcıya söyleyen sayfaları içeren bir giriş sayfası Yardım içerik kullanıcılara iletişim kurmak için senaryoları desteklemek HTM dosyaları kümesini içerir konuları yerel kümesinde bulunamadı. Bu HTM dosyaları ürün değiştirilebilir unutmayın.  ISO Kabuk satıcılar varsayılan markalama paketi alıp davranışını ve bu sayfaların içerik paketine onların değiştirme imkanınız olur.  Bu dosyalar kendi ilgili markalama paketinin branding.xml dosyasından karşılık gelen içerik almak marka etiketleri için sırayla bakın.  
  
||||  
|-|-|-|  
|**Dosya**|**Kullanın**|**Görüntülenen içerik kaynağı**|  
|homepage.htm|Bu, şu anda yüklü olan içeriğin ve herhangi bir iletiyi içeriklerini hakkında kullanıcıya sunmak uygun görüntüleyen bir sayfasıdır.  Bu dosyanın ek meta veri özniteliği "Microsoft.Help.Id" içerik yok = yerel içerik TOC üstünde bu içerik koyan "-" 1.||  
||< META_HOME_PAGE_TITLE_ADD / >|Branding.XML, etiket \<HomePageTitle >|  
||< HOME_PAGE_INTRODUCTION_SECTION_ADD / >|Branding.XML, etiket \<HomePageIntroduction >|  
||< HOME_PAGE_CONTENT_INSTALL_SECTION_ADD / >|Branding.XML, etiket \<HomePageContentInstallText >|  
||< HOME_PAGE_BOOKS_INSTALLED_SECTION_ADD / >|Bölüm Branding.xml etiketi başlık\<HomePageInstalledBooks >, uygulamasından, oluşturulan veri \<HomePageNoBooksInstalled > hiçbir books yüklü olduğunda.|  
||< HOME_PAGE_SETTINGS_SECTION_ADD / >|Bölüm Branding.xml etiketi başlık \<HomePageHelpSettings >, bölüm metin \<HomePageHelpSettingsText >.|  
|topiccorrupted.htm|Bir konu yerel kümesindeki mevcut olduğunda, ancak herhangi bir nedenle görüntülenemiyor (bozuk içeriği).||  
||< META_TOPIC_CORRUPTED_TITLE_ADD / >|Branding.XML, etiket \<TopicCorruptedTitle >|  
||< TOPIC_CORRUPTED_SECTION_ADD / >|Branding.XML, etiket \<TopicCorruptedViewOnlineText >|  
|topicnotfound.htm|Ne zaman bir konu yerel içeriği çevrimiçi ayarlayın ya da kullanılabilir bulunamadı||  
||< META_TOPIC_NOT_FOUND_TITLE_ADD / >|Branding.XML, etiket \<TopicNotFoundTitle >|  
||< META_TOPIC_NOT_FOUND_ID_ADD / >|Branding.XML, etiket \<TopicNotFoundViewOnlineText > + \<TopicNotFoundDownloadContentText >|  
||< TOPIC_NOT_FOUND_SECTION_ADD / >|Branding.XML, etiket \<TopicNotFoundText >|  
|contentnotinstalled.htm|Ürün için yüklü yerel içerik olmadığında.||  
||< META_CONTENT_NOT_INSTALLED_TITLE_ADD / >|Branding.XML, etiket \<ContentNotInstalledTitle >|  
||< META_CONTENT_NOT_INSTALLED_ID_ADD / >|Branding.XML, etiket \<ContentNotInstalledDownloadContentText >|  
||< CONTENT_NOT_INSTALLED_SECTION_ADD / >|Branding.XML, etiket \<ContentNotInstalledText >|  
  
**CSS dosyaları**  
  
Visual Studio Yardım Görüntüleyicisi markalama paketi, Visual Studio Yardım tutarlı içerik sunum desteklemek için iki css dosyaları içerir:  
  
-   Branding.css - nerede işleme için css öğeleri içeren SelfBranded = false  
  
-   Printer.css - nerede işleme için css öğeleri içeren SelfBranded = false  
  
Branding.css dosyaları Visual Studio konu sunu için tanımları içerir (uyarı olduğu branding.css Branding_ bulunan\<yerel ayar > paket hizmetinden .mshc değişebilir).  
  
**Grafik dosyaları**  
  
Visual Studio içeriği diğer grafik yanı sıra, Visual Studio logosu görüntüler.  Visual Studio Yardım Görüntüleyicisi marka paketindeki grafik dosyaların tam listesini aşağıda gösterilmiştir.  
  
||||  
|-|-|-|  
|**Dosya**|**Kullanın**|**Örnekler**|  
|Clear.gif|Daraltılabilir alanı oluşturmak için kullanılan||  
|footer_slice.gif|Altbilgi sunu||  
|info_icon.gif|Bilgileri görüntülerken kullanılacak|Sorumluluk reddi|  
|online_icon.gif|Bu simge çevrimiçi bağlantılarıyla ilişkili olacak||  
|tabLeftBD.gif|Kod parçacığı kapsayıcısı oluşturmak için kullanılan||  
|tabRightBD.gif|Kod parçacığı kapsayıcısı oluşturmak için kullanılan||  
|vs_logo_bk.gif|Branding.xml etiketinde tanımlanan normal Karşıtlık logosu başvurular için kullanılan \<LogoFileName >.  Visual Studio ürünleri için logo vs_logo_bk.gif adıdır.||  
|vs_logo_wh.gif|Branding.xml etiketinde tanımlanan normal yüksek logosu başvurular için kullanılan \<LogoFileNameHC >.  Visual Studio ürünleri için logo vs_logo_wh.gif adıdır.||  
|ccOff.png|Açıklamalı alt yazı grafiği||  
|ccOn.png|Açıklamalı alt yazı grafiği||  
|ImageSprite.png|Daraltılabilir alanı oluşturmak için kullanılan|Genişletilmiş veya grafiği Daralt|  
  
### <a name="deploying-a-set-of-topics"></a>Konular kümesi dağıtma  
Bu bir MSHA dosyası ve kabinler kümesinden comprised ayarlamak Yardım Görüntüleyici içerik dağıtımı oluşturmak için çok basit ve hızlı bir öğretici veya MSHC konular içeren. MSHA cab dosyaları kümesini tanımlayan bir XML dosyası veya MSHC dosyaları değil. Yardım Görüntüleyicisi'ni (. içerik bir listesini almak için MSHA okuyabilir CAB veya. MSHC dosyaları) yerel yükleme için kullanılabilir.  
  
Yalnızca çok temel XML şeması için Yardım Görüntüleyicisi MSHA açıklayan öncü budur.  Bu kısa genel bakış Aşağıda örnek uygulama olduğuna dikkat edin ve HelpContentSetup.msha örnek.  
  
Bu primer amaçları için MSHA adı HelpContentSetup.msha'dır (dosya adı uzantısına sahip hiçbir şey olabilir. MSHA). HelpContentSetup.msha (Aşağıdaki örnek) kabinler veya MSHCs kullanılabilir listesini içermelidir.  Dosya türü (MSHA ve CAB dosya türlerini bileşimini desteklemez) MSHA içinde tutarlı olması gerektiğini unutmayın. Her CAB veya MSHC için olması gerektiğini bir \<div class = "paketini" >...  \< /div > (aşağıdaki örneğe bakın).  
  
Not: uygulama aşağıdaki örnekte, biz markalama paketinin eklediniz. Bu gerekli Visual Studio İçerik işleme öğeleri ve içerik davranışları alabilmek için dahil etmek için önemlidir.  
  
Örnek HelpContentSetup.msha dosyası: ("İçerik kümesi adı 1" değiştirin ve "İçerik kümesi adı 2" vb. dosya adlarıyla.)  
  
```html
<html>  
<head />  
<body class="vendor-book">  
<div class="details">  
<span class="vendor">Your Company</span>  
<span class="locale">en-us</span>  
<span class="product">Your Company Help Content</span>  
<span class="name">Your Company Help Content</span>  
</div>  
<div class="package-list">  
<div class="package">  
<span class="name">Your_Company _Content_Set_1</span>  
<span class="deployed">True</span>  
<a class="current-link" href="Your_Company _Content_Set_1.mshc">Your_Company _Content_Set_1.mshc </a>  
</div>  
<div class="package">  
<span class="name">Your_Company _Content_Set_2</span>  
<span class="deployed">True</span>  
<a class="current-link"href=" Your_Company _Content_Set_2.mshc "> Your_Company _Content_Set_2.mshc </a>  
</div>.  
  
```  
  
1.  "C:\SampleContent" gibi yerel bir klasör oluşturun  
  
2.  Bu örnekte, konular içerecek şekilde MSHC dosyaları kullanacağız.  Bir MSHC zip .zip olarak değiştirildi dosya uzantısına sahip olur. MSHC.  
  
3.  Oluşturma bir metin dosyası olarak HelpContentSetup.msha aşağıda (Not Defteri dosyası oluşturmak için kullanılan) ve yukarıda belirtilen klasöre kaydedin (1. adım bakın).  
  
Unutmayın sınıfı "Markalama" var ve benzersizdir. Markalama mshc yüklü içerik markalama sahip olur ve MSHCs bulunan içerik davranışları marka pakette yer alan ilgili destek öğeleri gerekir böylece bu primer dahil edilir. Sistem kopyalanan (yüklü) parçası olmayan destek öğeleri için içerik ararken olmadan hataları neden olur.  
  
Visual Studio Paketi markalama elde etmek için çalışma klasörünüzde C:\Program Files (x86) \Microsoft Help Viewer\v2.3\ Branding_en US.mshc dosyasını kopyalayın.  
  
```html  
<html>  
<head />  
<body class="vendor-book">  
<div class="details">  
<span class="vendor">Your Company</span>  
<span class="locale">en-us</span>  
<span class="product">Your Company Help Content</span>  
<span class="name">Your Company Help Content</span>  
</div>  
<div class="package-list">  
<div class="package">  
<span class="name">Your_Company _Content_Set_1</span>  
<span class="deployed">True</span>  
<a class="current-link" href="Your_Company _Content_Set_1.mshc">Your_Company _Content_Set_1.mshc </a>  
</div>  
<div class="package">  
<span class="name">Your_Company _Content_Set_2</span>  
<span class="deployed">True</span>  
<a class="current-link"href=" Your_Company _Content_Set_2.mshc "> Your_Company _Content_Set_2.mshc </a>  
</div>  
<div class="package">  
<span class="packageType">branding</span>  
<span class="name">Branding_en-US</span>  
<span class="deployed">True</span>  
<a class="current-link" href="Branding_en-US.mshc">Branding_en-US.mshc</a>  
</div>  
</div>  
</body>  
</html>  
  
```  
  
**Özet**  
  
Visual Studio Yardım Görüntüleyicisi için kendi içerik kümeleri dağıtmak VSPs kullanarak ve yukarıdaki adımları genişletme etkinleştirir.  
  
### <a name="adding-help-to-the-visual-studio-shell-integrated-and-isolated"></a>Visual Studio Kabuğu (tümleşik ve Isolated) Yardım ekleme  
**Giriş**  
  
Bu kılavuz, bir Visual Studio Kabuğu uygulamasına Yardım içeriğine dahil ve ardından dağıtmak gösterilmiştir.  
  
**Gereksinimler**  
  
1.  [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)]  
  
2.  [Visual Studio 2013 yalıtılmış Kabuk yeniden Dağıt](http://www.microsoft.com/visualstudio/11/downloads#vs-shell)  
  
**Genel bakış**  
  
[!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] Kabuğu olan bir sürümünü [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] IDE üzerinde sizin temel bir uygulama. Bu tür uygulamalar, oluşturduğunuz uzantıları birlikte yalıtılmış Kabuk içerir. Dahil edilen yalıtılmış Kabuk proje şablonlarını kullanın [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] uzantıları oluşturmak için SDK.  
  
Yalıtılmış kabuk tabanlı bir uygulama ve onun Yardım oluşturmak için temel adımlar:  
  
1.  Elde [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] ISO Kabuk yeniden dağıtılabilir (Microsoft İndirme).  
  
2.  Visual Studio'da yalıtılmış Kabuk örneğin dayanan bir Yardım uzantısı, daha sonra bu kılavuzda açıklanan Contoso Yardım uzantısı oluşturun.  
  
3.  Uzantı ve dağıtım MSI (Uygulama Kurulumu) yeniden dağıtılabilir ISO Kabuk sarılır. Bu kılavuzda, bir kurulum adımı içermez.  
  
Visual Studio İçerik depolama alanı oluşturun. Tümleşik Kabuk senaryo için Visual Studio12 ürün kataloğu adına aşağıdaki gibi değiştirin:  
  
-   C:\ProgramData\Microsoft\HelpLibrary2\Catalogs\VisualStudio15 bir klasör oluşturun.  
  
-   CatalogType.xml adlı bir dosya oluşturun ve klasöre ekleyin. Dosya, aşağıdaki kod satırlarını içermesi gerekir:  
  
    ```xml
    <?xml version="1.0" encoding="UTF-8"?>  
    <catalogType>UserManaged</catalogType>  
    ```  
  
İçerik deposu kayıt defterinde tanımlayın. Tümleşik Kabuk için VisualStudio15 ürün kataloğu ada değiştirin:  
  
-   HKLM\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15  
  
     Anahtar: LocationPath dize değeri: C:\ProgramData\Microsoft\HelpLibrary2\Catalogs\VisualStudio15\  
  
-   HKLM\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15\en-us  
  
     Anahtar: Katalogadı dize değeri: [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] belgeleri  
  
**Projeyi Oluşturma**  
  
Yalıtılmış kabuk uzantısı oluşturmak için:  
  
1.  Visual Studio'da altında **dosya**, seçin **yeni proje**altında **diğer proje türleri** seçin **genişletilebilirlik**ve ardından seçin **Visual Studio Kabuğu yalıtılmış**. Proje adı `ContosoHelpShell`) Visual Studio yalıtılmış Kabuk şablonunu temel alan bir genişletilebilirlik projesi oluşturmak için.  
  
2.  Çözüm Gezgini'nde ApplicationCommands.vsct ContosoHelpShellUI projede kaynak dosyaları klasörü açın. Bu satırı ("No_Help" Ara) kılınmıştır emin olun:`<!-- <define name="No_HelpMenuCommands"/> -->`  
  
3.  Derlemek ve çalıştırmak için F5 tuşuna seçin **hata ayıklama**. Yalıtılmış Kabuk IDE Deneysel örneğini seçin **yardımcı** menüsü. Olduğundan emin olun **Yardımı Görüntüle**, **ekleme ve kaldırma Yardım içeriğini**, ve **Yardım tercih kümesini** komutlar görüntülenir.  
  
4.  Çözüm Gezgini'nde ContosoHelpShell.pkgdef ContosHelpShell projede Kabuk özelleştirmesi klasörünü açın. Contoso Yardım katalog tanımlamak için aşağıdaki satırları ekleyin:  
  
    ```  
     [$RootKey$\Help]  
    "Product"="Contoso"  
    "Catalog"="Contoso"  
    "Version"="100"  
    "BrandingPackage"="ContosoBrandingPackage.mshc"  
    ```  
  
5.  Çözüm Gezgini'nde ContosoHelpShell.Application.pkgdef ContosHelpShell projede Kabuk özelleştirmesi klasörünü açın. F1 Yardımı etkinleştirmek için aşağıdaki satırları ekleyin:  
  
    ```  
    // F1 Help Provider  
  
    [$RootKey$\HelpProviders\{C99BDC23-FF29-46bf-9658-ADD634CCAED8}]  
    "Name"="13407"  
    "Package"="{DA9FB551-C724-11d0-AE1F-00A0C90FFFC3}"  
    @="Help3 Provider"  
    [$RootKey$\HelpProviders]  
    @="{C99BDC23-FF29-46bf-9658-ADD634CCAED8}"  
    [$RootKey$\Services\{C99BDC23-FF29-46bf-9658-ADD634CCAED8}]  
    "Name"="Help3 Provider"  
    @="{4A791146-19E4-11D3-B86B-00C04F79F802}"  
    ```  
  
6.  Çözüm Gezgini'nde ContosoHelpShell çözüm bağlam menüsünde seçin **özellikleri** menü öğesi. Altında **yapılandırma özellikleri**seçin **Configuration Manager**. İçinde **yapılandırma** sütun, her "Hata ayıklama" değeri "Yayın" olarak değiştirin.  
  
7.  Çözümü oluşturun. Bu sonraki bölümde kullanılacak bir yayın klasördeki dosyaları kümesini oluşturur.  
  
Bu gibi dağıttıysanız test etmek için:  
  
1.  Makinede indirilen (yukarıdaki) ISO Kabuğu yüklemek için Contoso dağıtıyorsanız.  
  
2.  Bir klasör oluşturun \\\Program Files (x86)\\ve adlandırın `Contoso`.  
  
3.  ContosoHelpShell yayın klasörünün içeriğini kopyalayın \\\Program Files (x86) \Contoso\ klasörü.  
  
4.  Kayıt Defteri Düzenleyicisi'ni seçerek başlatın **çalıştırmak** içinde **Başlat** menü ve girerek `Regedit`. Kayıt Defteri Düzenleyicisi'nde seçin **dosya**ve ardından **alma**. ContosoHelpShell proje klasörüne göz atın. ContosoHelpShell alt klasöründeki ContosoHelpShell.reg seçin.  
  
5.  İçerik deposu oluşturun:  
  
     Contoso içerik deposu C:\ProgramData\Microsoft\HelpLibrary2\Catalogs\ContosoDev12 ISO kabuğunda - oluşturun  
  
     İçin [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] tümleşik Kabuk C:\ProgramData\Microsoft\HelpLibrary2\Catalogs\VisualStudio15 bir klasör oluşturun  
  
6.  CatalogType.xml oluşturun ve içerik deposu (önceki adımda) içeren ekleyin:  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?>  
    <catalogType>UserManaged</catalogType>  
    ```  
  
7.  Aşağıdaki kayıt defteri anahtarlarını ekleyin:  
  
     HKLM\SOFTWARE\Wow6432Node\Microsoft\Help\v2.3\Catalogs\VisualStudio15Key: LocationPath dize değeri:  
  
     ISO kabuğu için:  
  
     C:ProgramDataMicrosoftHelpLibrary2CatalogsVisualStudio15  
  
     [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)]Tümleşik Kabuk:  
  
     C:ProgramDataMicrosoftHelpLibrary2CatalogsVisualStudio15en-ABD  
  
     Anahtar: Katalogadı dize değeri: [!INCLUDE[vs_dev12](../../extensibility/includes/vs_dev12_md.md)] belgeleri. ISO kabuğu için bu kataloğunuzu adıdır.  
  
8.  İçeriğinizi (cab veya MSHC ve MSHA) yerel bir klasöre kopyalayın.  
  
9. Örnek tümleşik Kabuk komut içerik deposu test satırı. ISO kabuğu için katalog ve launchingApp değerleri ürün eşleştirmek uygun şekilde değiştirin.  
  
     "C:\Program dosyaları (x86) \Microsoft Help Viewer\v2.3\HlpViewer.exe" /catalogName VisualStudio15 /helpQuery yöntemi = "& Sayfa kimliği ContosoTopic0 =" /launchingApp Microsoft, Visual Studio, 12.0  
  
10. Contoso uygulamadan (Contoso uygulama kökü) başlatın. ISO Kabuk içinde seçin **yardımcı** menü öğesi ve değişiklik **Yardım tercih kümesini** için **kullanılması yerel yardımcı**.  
  
11. Kabuk içinde seçin **yardımcı** menü öğesi, ardından **Yardımı Görüntüle**. Yerel Yardım Görüntüleyici başlatma. Seçin **içeriği Yönet** sekmesi. Altında **yükleme kaynağı**, seçin **Disk** seçenek düğmesi. Seçin **...**  düğmesine tıklayın ve Contoso içeriği (yukarıdaki adım yerel klasöre kopyalanır) içeren yerel klasöre gidin. HelpContentSetup.msha seçin. Contoso şimdi kitap seçimleri kitaptaki olarak gösterilmesi gerekir. Seçin **Ekle**ve ardından **güncelleştirme** düğmesini (sayfanın sağ alt köşesinde).  
  
12. Contoso IDE içinde F1 işlevselliğini sınamak için F1 tuşuna seçin.  
  
### <a name="additional-resources"></a>Ek Kaynaklar  
Çalışma zamanı API için bkz: [Windows Yardımı API](http://msdn.microsoft.com/library/windows/desktop/hh447318\(v=vs.85\).aspx).  
  
Yardım API'den yararlanabilirsiniz hakkında ek bilgi için bkz: [Yardım Görüntüleyicisi kod örnekleri](http://visualstudiogallery.msdn.microsoft.com/f08f296f-7076-4aec-8da3-8f0fbe04461e)  
  
Bu bileşenler hakkında geri bildirim sağlamak için kullanmak [Microsoft Connect](http://connect.microsoft.com/).  
  
Lütfen özellik önerileri gönderin [Microsoft kullanıcı sesi](http://visualstudio.uservoice.com/forums/121579-visual-studio)  
  
Ek Yardım almak için deneyin [MSDN Geliştirici belgeleri ve Yardım sistemi forumları](http://social.msdn.microsoft.com/Forums/devdocs/threads)  
  
Sorun, bölme üzerinde güncelleştirmeleri lütfen bkz. [Yardım Görüntüleyicisi Benioku dosyası](http://go.microsoft.com/fwlink/?LinkID=231397&clcid=0x409)  
  
Yardım Görüntüleyicisi PM takım doğrudan başvurmak için e-posta Gönderhlpfdbk@microsoft.com