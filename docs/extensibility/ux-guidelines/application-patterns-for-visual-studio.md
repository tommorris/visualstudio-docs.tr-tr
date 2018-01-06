---
title: "Visual Studio için uygulama düzenleri | Microsoft Docs"
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ed68602-4e28-46fe-b39f-f41979b308a2
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 139b51fbf0ede7ea439d2308a0d03afe7ba617ec
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="application-patterns-for-visual-studio"></a>Visual Studio için uygulama düzenleri
##  <a name="BKMK_WindowInteractions"></a>Pencere etkileşimleri  
  
### <a name="overview"></a>Genel Bakış  
Visual Studio'da kullanılan iki ana penceresi belge düzenleyicileri ve aracı windows türleridir. Büyük kalıcı olmayan iletişim kutuları, Rare ancak mümkün değildir. Bunlar Kabuğu'nda tüm engelleyici olsa da, bunların şekillerine temelde farklı. Bu bölüm, belge windows, aracı windows ve kalıcı olmayan iletişim kutuları arasındaki farkı kapsar. Kalıcı iletişim düzenleri ele alınmıştır [iletişim kutularını](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Dialogs).  
  
### <a name="comparing-window-usage-patterns"></a>Pencere kullanım desenlerini karşılaştırma  
**Belge windows** belge içinde iyi neredeyse her zaman görüntülenir. Bu bir "merkezi aşama" Belge Düzenleyicisi verir geçici ek araç pencereleri düzenlemek için.  
  
A **araç penceresi** çoğunlukla IDE kenar karşı daraltılmış ayrı, daha küçük bir pencere görüntülenir. Bu görünür, gizli veya otomatik olarak gizli olabilir. Ancak, bazen aracı windows iyi, belge içinde kaldırarak sunulan **penceresi/Docking** penceresinde özelliği. Bu daha fazla Gayrimenkul olur, ancak aynı zamanda ortak bir tasarım kararı: Visual Studio'ya tümleştirmek çalışırken, özellik araç penceresi ya da bir belge penceresi görüntüleyip görüntülemeyeceğini karar vermelisiniz.  
  
**Kalıcı olmayan iletişim kutuları** Visual Studio'da önerilmez. En kalıcı olmayan iletişim kutuları tanım olarak, aracı windows kayan olan ve bu şekilde uygulanması gerekir. Kalıcı olmayan iletişim kutuları burada Kabuk tarafına yerleştirilmiş normal araç penceresi boyutunu çok sınırlama durumlarda izin verilir. Bunlar da kullanıcı iletişim kutusu için ikincil bir izleyici taşımak büyük olasılıkla olduğu durumlarda izin verilir.  
  
Dikkatle hangi kapsayıcı türü hakkında ihtiyacınız düşünün. Genel kullanım deseni UI tasarımı için aşağıdaki tabloda noktalardır.  
  
||Belge penceresi|Araç penceresi|Kalıcı olmayan iletişim|  
|-|---------------------|-----------------|---------------------|  
| **Konumu** | Her zaman bu belgenin içinde iyi konumlandırılmış ve IDE kenarları yerleştirme değil. "Ana Kabuğu'ndan ayrı olarak gezinen böylece bu çekebilir devre dışı". | Genel sekmesi-yerleşik IDE köşelerindeki ancak (Temizle) kayan için özelleştirilmiş, otomatik olarak gizli olabilir veya belge içinde iyi yerleştirildi.|IDE içinden ayrı büyük kayan pencere. |  
| **Model Yürüt** | *Gecikmeli yürütme*<br /><br /> Bir belgedeki verileri kaydetmek için kullanıcının dağıtmalı **dosya &gt; kaydetmek**, **Kaydet**, veya **Tümünü Kaydet** komutu. "Dirtied" içindeki veri kavramı kaydetme biri olarak kaydedilmiş bir belge penceresine sahip komutları. Bir belge penceresi kapatıldığında tüm içeriği diske kaydedilmiş ya da kayboldu. | *Hemen tamamlama*<br /><br /> Hiçbir Kaydet yoktur modeli. Bir dosya düzenlenmesine yardımcı olmak denetçisi aracı Windows, dosyayı active Düzenleyicisi'ni veya Tasarımcısı'nda açık olması gerekir ve Düzenleyicisi veya Tasarımcısı kaydetme sahip olduğu. | *Ertelenen veya Acil tamamlama*<br /><br /> Genellikle, büyük bir kalıcı olmayan iletişim değişiklikleri yürütmek için bir eylem gerektirir ve iletişim oturum içinde yapılan tüm değişiklikler geri alındığında bir "İptal" işlemi için izin verir.  Araç pencereleri her zaman bir hemen yürütme modeline sahiptir, bu aracı penceresinden kalıcı olmayan iletişim ayırır. |  
| **Görünürlüğü** | *Açık (dosya) / oluşturun ve Kapat*<br /><br /> Belge pencereleri açma var olan bir belgeyi açarak veya yeni bir belge oluşturmak için bir şablon kullanarak aracılığıyla gerçekleştirilir. Yok yok "açık \<belirli bir düzenleyici >" komutu. | *Gizle ve Göster*<br /><br /> Windows Tek Örnekli aracı gizli veya gösterilmektedir. İçeriği ve araç penceresi içinde durumları kalıcı görünümünde olup olmadığını veya gizli. Çok örnekli aracı windows kapalı gizli yanı sıra. Çok örnekli araç penceresi kapatıldığında, içerik ve araç penceresi içinde durum atılır. | *Bir komutu başlattı*<br /><br /> İletişim kutuları, bir görev tabanlı komut başlatılır. |  
| **Örnekler** | *Çok örnekli*<br /><br /> Bazı düzenleyiciler aynı zamanda birden fazla düzenleyicisinde açılması aynı dosyayı izin verirken, birkaç düzenleyicileri düzenleme farklı dosya ve aynı anda açık olabilir (kullanarak **penceresi &gt; yeni pencere** komutu).<br /><br /> Tek bir düzenleyici (Proje Tasarımcısı) aynı anda bir veya birden çok dosya düzenleme. | *Tek veya birden çok instance*<br /><br /> Bağlam (olduğu gibi özellik tarayıcısı) yansıtmak veya odak/bağlam diğer windows (görev listesi, Çözüm Gezgini) anında iletme için içeriği değiştirin.<br /><br /> Değil olmadıkça ilgi çekici bir nedenle için tek örnekli ve çok örnekli aracı windows etkin belge penceresi ile ilişkili olmalıdır. | *Tek örnek* |  
| **Örnekler** | **Metin düzenleyicileri**, ister Kod Düzenleyicisi<br /><br /> **Tasarım yüzeyleri**form tasarımcısı veya bir model yüzey gibi<br /><br /> **Denetim düzenleri iletişim kutuları için benzer**, ister bildirim Tasarımcısı | **Çözüm Gezgini** bir çözüm ve çözüm içinde yer alan projeleri sağlar<br /><br /> **Sunucu Gezgini** pencerede açmak için kullanıcının seçtiği sunucuları ve veri bağlantısı hiyerarşik bir görünümünü sağlar. Bir nesne gibi bir sorgu veritabanı hiyerarşisini açma bir belge penceresi açar ve sorgu düzenlemesine olanak tanır.<br /><br /> **Özellik tarayıcısı** belge penceresini veya başka bir araç penceresinde seçili nesnenin özelliklerini görüntüler. Özellikler hiyerarşik ızgara görünümünde veya karmaşık iletişim benzeri denetimler sunulur ve bu özelliklerin değerlerini ayarlamak izin verin. | |  
  
##  <a name="BKMK_ToolWindows"></a>Araç pencereleri  
  
### <a name="overview"></a>Genel Bakış  
Araç pencereleri belge Windows'da olur kullanıcının iş destekler. Visual Studio işleyebilir ve sağlayan bir temel kök nesneyi temsil eden bir hiyerarşi görüntülemek için kullanılabilir.  
  
IDE içinde yeni bir araç penceresi değerlendirirken yazarlar gerekir:  
  
-   Benzer işlevselliği olan yeni kampanya oluşturmak değil ve görev uygun varolan aracı windows kullanın. Yeni aracı windows yalnızca önemli ölçüde farklı "aracı" veya benzer penceresine veya özetleyerek hub'a var olan bir pencere açarak tümleştirilemez işlevselliği sağlamıyorsa oluşturulmalıdır.  
  
-   Standart komut çubuğunda, gerekirse, aracı penceresinin en üstünde kullanın.  
  
-   Denetim sunu ve klavye gezinti için diğer aracı windows zaten mevcut desenlerle tutarlı olması.  
  
-   Denetim sunu diğer aracı Windows ile tutarlı olmalıdır.  
  
-   Yalnızca üst belge etkinleştirildiğinde görünmesini sağlayacak şekilde belgeye özel araç pencereleri otomatik görünür mümkün olduğunda, olun.  
  
-   Pencere içeriklerini (Destek ok tuşları) klavye kullanılarak gezinilebilir olduğundan emin olun.  
  
#### <a name="tool-window-states"></a>Araç penceresi durumları  
Visual Studio aracı windows bazıları (otomatik olarak gizle özelliği gibi) kullanıcı etkinleştirilmiş olan farklı durumuna sahiptir. Diğer durumlarını otomatik görünür ister, doğru bağlamında görüntülenir ve gerekli olduğunda gizlemek araç pencereleri imkan tanır. Toplam beş araç penceresi durumlar vardır.  
  
-   **Yerleşik ve sabitlenmiş** araç pencereleri herhangi bir belge alanı dört tarafına ağa eklenebilir. Raptiye simgesinin aracı penceresinin başlık çubuğunda görünür. Araç penceresi yatay veya dikey kabuk ve diğer aracı windows kenarına yerleşik ve ayrıca sekmesinde bağlı olabilir.  
  
-   **Otomatik gizli** aracı windows sabitlenmemiş. Pencerenin sekmeyle (adını araç penceresi ve simgesini) belge alanının kenarına bırakarak görüş dışında kaydırabilirsiniz. Bir kullanıcı sekmenin üzerine geldiğinde çıkışı araç penceresi slayt.  
  
-   **Otomatik görünür** araç pencereleri otomatik olarak kullanıcı Arabirimi, başka bir parçasını bir düzenleyici gibi başlatılır veya kazanır odak yaptığınızda görünmez.  
  
-   **Kayan** aracı windows dışında IDE getirin. Bu, birden çok monitör yapılandırmaları için kullanışlıdır.  
  
-   **Sekmeli belge** aracı windows yerleşik belge içinde iyi. Bu, daha fazla çerçeve kenarlarına yerleştirme izin verdiğinden Gayrimenkul gereken nesne tarayıcısı gibi büyük aracı windows için kullanışlıdır.  
  
![Visual Studio'da pencere durumları aracı](../../extensibility/ux-guidelines/media/0702-01_toolwindowstates.png "0702 01_ToolWindowStates")<br />Visual Studio'da araç penceresi durumları
  
#### <a name="single-instance-and-multi-instance"></a>Tek Örnekli ve birden çok örneği  
Aracı windows Tek Örnekli ya da çok örnekli markalarıdır. Çok örnekli aracı windows görünmeyebilir ancak bazı tek örnek araç pencereleri etkin belge penceresi ile ilişkili olabilir. Çok örnekli aracı windows yanıt veren **penceresi &gt; yeni pencere** penceresini yeni bir örneğini oluşturarak komutu. Aşağıdaki resimde penceresi örneği etkin olduğunda yeni pencere komutu etkinleştirme bir araç penceresi gösterilmektedir:  
  
!['Yeni pencere' komut penceresi örneği olduğunda etkinleştirme araç penceresi etkin olduğu](../../extensibility/ux-guidelines/media/0702-02_toolwindowenablingcommand.png "0702 02_ToolWindowEnablingCommand")<br />Araç penceresi penceresi örneği etkin olduğunda 'Yeni pencere' komutunu etkinleştirme  
  
Windows Tek Örnekli aracı gizli veya gösterilen çok örnekli aracı windows kapalı gizli yanı sıra sırada. Tüm aracı windows, sekme bağlı, kayan veya birden çok belge arabirimi (MDI) alt pencere (bir belge penceresine benzer) olarak ayarlanmış yerleşik. Tüm aracı windows Pencere menüsünden uygun pencere yönetimi komutları yanıt:  
  
![Pencere Yönetimi komutları Visual Studio penceresinin menüde](../../extensibility/ux-guidelines/media/0702-03_windowmanagementcontrols.png "0702 03_WindowManagementControls")<br />Pencere Yönetimi komutları Visual Studio penceresinin menüde
  
#### <a name="document-specific-tool-windows"></a>Belgeye özel araç pencereleri  
Bazı araç pencereleri verilen belge türüne göre değiştirmek için tasarlanmıştır. Bu windows sürekli IDE etkin belgeyi penceresinde uygulanabilir işlevselliğini yansıtacak şekilde güncelleştirin.  
  
Araç ve Belge Anahattı seçili Düzenleyicisi yansıtacak şekilde içerikleri değiştirme aracı windows örnekleridir. Bir düzenleyici penceresini bağlamına sunmaz odağa sahip olduğunda bu windows Filigran gösterir.  
  
#### <a name="navigable-list-tool-windows"></a>Gezinebilir listesi araç pencereleri  
Bazı aracı windows kullanıcı etkileşim kurabildikleri gezinebilir öğelerinin bir listesini görüntüler. Bu tür penceresi, her zaman olmalıdır geri bildirim listesinde, geçerli öğenin pencere etkin olsa bile. Listenin yanıt vermesi gereken **GoToNextLocation** ve **GoToPrevLocation** penceresinde seçili öğenin de değiştirerek komutları  
  
Çözüm Gezgini ve Bul sonuçları penceresi gezinebilir listesi aracı windows örnekleridir.  
  
### <a name="tool-window-types"></a>Araç penceresi türleri  
  
#### <a name="common-tool-windows-and-their-functions"></a>Ortak aracı windows ve bunların işlevleri

**Hiyerarşik araç pencereleri**
| Araç penceresi | İşlev | 
| --- | --- | 
| Çözüm Gezgini | Belgelerin listesini görüntüleyen bir hiyerarşik ağaç projeleri, çeşitli dosyalar ve çözüm öğeleri içeriyordu. Proje öğeleri görüntüleme proje türü (örneğin, tabanlı başvurusu, dizin tabanlı ya da karma modda türleri) sahip paket tarafından tanımlanır. | 
| Sınıf Görünümü | Hiyerarşik bir sınıf ve belgelerin, dosyaların bağımsız çalışma kümesindeki çeşitli öğeleri. | 
| Server Explorer | Çözümdeki tüm sunucuları ve veri bağlantıları görüntüler hiyerarşik ağaç. | 
| Belge Anahattı | Etkin belge hiyerarşik yapısı. | 

**Kılavuz araç pencereleri**
| Araç penceresi | İşlev | 
| --- | --- | 
| Özellikler | Bu özelliklerini düzenlemek için değer seçiciler birlikte seçili nesne için özellikler listesini görüntüleyen bir kılavuz. | 
| Görev Listesi | Oluşturma/düzenleme/silme görevleri ve açıklamalar kullanıcıya izin veren bir kılavuz. | 

**İçerik araç pencereleri**
| Araç penceresi | İşlev | 
| --- | --- | 
| Yardım | Kullanıcılarının "Nasıl yedeklerim?" den Yardım alma çeşitli yöntemleri erişmesini sağlayan bir pencere MSDN Forumlarında videoları. | 
| Dinamik Yardım | Yardım konuları geçerli seçime uygun bağlantıları görüntüleyen bir araç penceresi. | 
| Nesne Tarayıcısı | İki sütun çerçeve hiyerarşik nesne bileşenlerinde sol bölmesinde ve nesnenin özellikleri ve yöntemleri sağ sütundaki listesini içeren. | 

**İletişim kutusu araç pencereleri**
| Araç penceresi | İşlev | 
| --- | --- | 
| Bul | Bir iletişim kutusu, kullanıcının bulmak veya bulma ve çözüm içindeki çeşitli dosyalarında değiştirme olanak sağlar. |
| Gelişmiş bulma | Bir iletişim kutusu, kullanıcının bulmak veya bulma ve çözüm içindeki çeşitli dosyalarında değiştirme olanak sağlar. | 

**Diğer araç pencereleri**
| Araç penceresi | İşlev | 
| --- | --- | 
| Araç Kutusu | Tüm tasarımcıları için tutarlı bir Sürükle-kaynak sağlayarak tasarım yüzeyleriyle üzerine bırakılacak öğe depolamak için kullanılan araç penceresi. |
| Başlangıç Sayfası | Geliştirici Haberleri, Visual Studio Yardım ve son projeler akışlarını erişimi olan kullanıcı portalı Visual Studio. Kullanıcılar da oluşturabilir özel başlangıç sayfalarını StartPage.xaml dosyasından kopyalayarak "Common7\IDE\StartPages\" Visual Studio program files dizini StartPages klasörüne Visual Studio'da belgeler dizin ve ardından her iki XAML düzenleme elle veya Visual Studio veya başka bir kod düzenleyicisini açma. | 

**Hata ayıklayıcı araç pencereleri**
| Araç penceresi | İşlev | 
| --- | --- |
| Otomatik değişkenler ||  
| Hemen ||  
| Çıkış | Çıktı penceresi metinsel olayları veya bildirmek için durum olduğunda kullanılabilir. |  
| Bellek ||  
| Kesme noktaları ||  
| Çalıştırılıyor ||  
| Belgeler ||  
| Çağrı yığını ||  
| Yerel öğeler ||  
| Gözcü ||  
| Ayrıştırılmış kodu ||  
| Kaydeder ||  
| İş Parçacıkları ||  
  
##  <a name="BKMK_DocumentEditorConventions"></a>Belge Düzenleyicisi kuralları  
  
### <a name="document-interactions"></a>Belge etkileşimleri  
"İyi belge" IDE içinden en geniş alanı ve burada kullanıcı genellikle dikkatini ek aracı windows tarafından destekli görevlerini tamamlamak için odaklı. Belge düzenleyicileri kullanıcı açar ve Visual Studio içinde kaydeden iş temel birimleri temsil eder. Çözüm Gezgini'nde veya diğer etkin olan hiyerarşi windows bağlı seçimi güçlü bir fikir korurlar. Kullanıcının bu hiyerarşi windows birini işaret ve çözüm, proje ya da Visual Studio paketi tarafından sağlanan başka bir kök nesnesi için belge bulunduğu ve ilişkisini biliyor olması gerekir.  
  
Belge düzenleme tutarlı bir kullanıcı deneyimi gerektirir. Elinizdeki yerine pencere yönetimi ve komutları bulma odaklanmak izin vermek için bu belge türü düzenlemek için kullanıcı görevleri için en uygun bir belge görünümü stratejisi seçin.  
  
#### <a name="common-interactions-for-the-document-well"></a>İyi belge için ortak etkileşimleri  
  
-   Ortak tutarlı etkileşim modelinde korumak **yeni dosya** ve **açık dosya** karşılaştığında.  
  
-   Belge penceresi açıldığında ilgili windows ve menüleri ilgili işlevleri güncelleştirin.  
  
-   Menü komutları gibi yaygın menüler içine uygun şekilde tümleştirilir **Düzenle**, **biçimi**, ve **Görünüm** menüleri. Özel komutlar önemli miktarda varsa, yeni bir menü oluşturulabilir. Yalnızca belge odağa sahip olduğunda bu yeni menü görünür olması gerekir.  
  
-   Katıştırılmış araç çubuğu Düzenleyicisi üstünde yerleştirilebilir. Bu Düzenleyicisi dışında görüntülenen ayrı bir araç çubuğu zorunda tercih edilir.  
  
-   Çözüm Gezgini'nde veya benzer etkin bir seçim her zaman korumak hiyerarşisi penceresi.  
  
-   Çözüm Gezgini'nde bir belgeyi çift aynı eylemi gerçekleştirmesi gerektiğini **açık**.  
  
-   Bir belge türünde birden fazla Düzenleyicisi kullanılabiliyorsa kullanıcı geçersiz kılma veya belirli belge türü kullanılarak üzerinde varsayılan eylem sıfırlamasına olmalıdır **birlikte Aç** dosyayı sağ tıklatıp seçerek iletişim kutusu **Aç İle** kısayol menüsünden.  
  
-   Bir belge sihirbazında iyi derleme yok.  
  
### <a name="user-expectations-for-specific-document-types"></a>Belirli bir belge türleri için kullanıcı beklentiler  
Belge düzenleyicileri birkaç farklı temel tür vardır ve her bir aynı türden başkalarıyla tutarlı etkileşimleri kümesi vardır.  
  
-   **Metin tabanlı Düzenleyicisi:** kod düzenleyicisini, günlük dosyaları  
  
-   **Tasarım yüzeyi:** WPF forms Tasarımcısı, Windows forms  
  
-   **İletişim-stil Düzenleyicisi:** bildirim Tasarımcısı, proje özellikleri  
  
-   **Model designer:** iş akışı Tasarımcısı, codemap, mimarisi diyagramı, ilerleme  
  
Belge kullanmaktadır birkaç Düzenleyicisi olmayan türü vardır. Belgeleri kendilerini düzenleme yapmadığınız durumdayken belge windows için standart etkileşimleri izlemek gerekir.  
  
-   **Raporları:** IntelliTrace raporunu kullanarak, Hyper-V rapor profil oluşturucusu raporu  
  
-   **Pano:** tanılama hub'ı  
  
#### <a name="text-based-editors"></a>Metin tabanlı düzenleyiciler  
  
-   Belgeyi açmaya gerek kalmadan önizlemek için izin verme Önizleme sekmesi modelindeki belge katılır.  
  
-   Belge Anahattı gibi bir yardımcı araç penceresi içinde belgenin yapısını temsil edilebilir.  
  
-   IntelliSense (uygunsa) diğer kod düzenleyicileri ile tutarlı bir şekilde davranır.  
  
-   Açılır pencereleri veya yardımcı UI izleyin benzer stilleri ve desenler CodeLens gibi varolan benzer UI.  
  
-   İletileri belge durumuyla ilgili bir bilgi çubuğu denetimi belgenin üst veya durum çubuğu sunulur.  
  
-   Kullanıcı yazı tipleri ve renkler kullanarak görünümünü özelleştirebilirsiniz bir **Araçlar > Seçenekler** sayfasında, paylaşılan yazı tiplerini ve renkleri sayfası veya bir özel düzenleyici için.  
  
#### <a name="design-surfaces"></a>Tasarım yüzeyleriyle  
  
-   Boş bir tasarımcı Filigran nasıl başlayacağınızı belirten yüzey üzerinde olmalıdır.  
  
-   Kod Düzenleyicisi ya da her iki bölmeleri etkileşime izin vererek belge penceresine sekmeleri açmak için çift gibi varolan düzenleri Görünüm değiştirme mekanizmaları izler.  
  
-   Yüksek oranda belirli araç penceresi gerekli olmadığı sürece tasarım yüzeyine öğe eklemek araç yapılmalıdır.  
  
-   Yüzey üzerinde öğeleri tutarlı seçimi modelini izler.  
  
-   Katıştırılmış araç çubukları içeren belge özgü komutları yalnızca, bilinen komutları gibi **kaydetmek**.  
  
#### <a name="dialog-style-editors"></a>İletişim-style düzenleyiciler  
  
-   Denetim düzenini normal iletişim düzeni kurallarına uygun.  
  
-   Sekmelerin Düzenleyicisi içinde belge sekmeleri görünümünü eşleşmemelidir, biri iki izin verilen iç sekmesini stili ile eşleşmelidir.  
  
-   Kullanıcılar yalnızca klavye kullanma denetimler ile etkileşim kurabilmesi gerekir; ya da Düzenleyicisi'ni etkinleştirme ve denetim aracılığıyla veya sekme standart anımsatıcıları kullanarak.  
  
-   Tasarımcı ortak Modeli Kaydet kullanmanız gerekir. Diğer düğmeleri uygun olabilir ancak hiçbir genel kaydetme veya yürütme düğmeleri yüzey üzerinde yerleştirilmelidir.  
  
#### <a name="model-designers"></a>Model tasarımcıları  
  
-   Boş bir tasarımcı Filigran nasıl başlayacağınızı belirten yüzey üzerinde olmalıdır.  
  
-   Tasarım yüzeyine öğe eklemek araç yapılmalıdır.  
  
-   Yüzey üzerinde öğeleri tutarlı seçimi modelini izler.  
  
-   Katıştırılmış araç çubukları içeren belge özgü komutları yalnızca, bilinen komutları gibi **kaydetmek**.  
  
-   Gösterge yüzeyinde hatırlanması veya filigran görünebilir.  
  
-   Kullanıcı kullanarak yazı tiplerini/renkleri görünümünü özelleştirebilirsiniz bir **Araçlar > Seçenekler** sayfasında, paylaşılan yazı tiplerini ve renkleri sayfası veya bir özel düzenleyici için.  
  
#### <a name="reports"></a>Raporlar  
  
-   Raporlar salt bilgileri genellikle ve kaydetme modelinde katılmak yok. Ancak, bunlar diğer ilgili bilgileri veya genişletme ve daraltma Bölümleri bağlantıları gibi etkileşim içerebilir.  
  
-   Yüzey üzerinde komutların çoğu köprüler, düğmeleri olmalıdır.  
  
-   Düzeni, bir başlığı dahil et ve standart rapor düzenini yönergeleri izleyin.  
  
#### <a name="dashboards"></a>Panolar  
  
-   Panoları bir etkileşim modeli kendilerini sunulmadı, ancak çeşitli diğer araçları sunmak için bir yol hizmet.  
  
-   Kaydet modelinde katılın değil.  
  
-   Kullanıcıların Düzenleyicisi'ni etkinleştirme ve denetimlerde sekme veya standart anımsatıcıları kullanarak yalnızca klavye kullanma denetimleri ile etkileşim kurabilmesi gerekir.  
  
##  <a name="BKMK_Dialogs"></a>İletişim kutuları  
  
### <a name="introduction"></a>Giriş  
Visual Studio'da iletişim kutuları, genellikle kullanıcının iş bir ayrık birimi desteklemelidir ve sonra kapatılır.  
  
Bir iletişim kutusu gereksinim karar verdiyseniz, tercih sırasına göre üç seçeneğiniz vardır:  
  
1.  Visual Studio'da paylaşılan iletişim kutuları birine özelliklerinizi tümleştirin.  
  
2.  Varolan bir benzer iletişim kutusunda bulunan bir desen kullanarak kendi iletişim oluşturun.  
  
3.  Yeni bir iletişim kutusu, aşağıdaki etkileşim ve Düzen kılavuzu oluşturun.  
  
Bu bölümde, Visual Studio iş akışı içinde doğru iletişim düzeni iletişim tasarımı için genel kurallar seçip açıklar.  
  
### <a name="themes"></a>Temalar  
Visual Studio'da iletişim kutularının iki temel stili birini izleyin:  
  
#### <a name="standard-unthemed"></a>Standart (unthemed)  
İletişim kutuları çoğunluğu standart yardımcı programı iletişim kutuları olan ve unthemed olması gerekir. Ortak Denetimler re şablon yapabilir veya stilize "modern" düğmeleri veya denetimleri oluşturma girişimi. Denetimleri ve izleyin chrome görünümünü [iletişim kutuları için standart Windows Masaüstü etkileşim kuralları](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx).  
  
#### <a name="themed"></a>Teması  
Özel "imza" iletişim kutuları konulu olabilir. Konulu iletişim kutuları stili ile ilişkili bazı özel etkileşim desenleri de olan ayrı bir görünümü vardır. Tema yalnızca bu gereksinimleri karşılıyorsa iletişim:  
  
-   İletişim kutusu görülen ve sık sık veya çok sayıda kullanıcı tarafından kullanılan ortak deneyimidir (örneğin, **yeni proje** iletişim.  
  
-   İletişim kutusu belirgin ürün marka öğeleri içerir (örneğin, **hesap ayarlarını** iletişim).  
  
-   Tema uygulanabilir diğer iletişim kutuları içeren daha büyük bir akış ayrılmaz bir parçası iletişim kutusu görüntülenir (örneğin, **bağlı hizmet Ekle** iletişim).  
  
-   İletişim kutusu, yükseltme veya ürün sürümü ayrım stratejik bir rol oynar bir deneyim önemli bir parçasıdır.  
  
Konulu bir iletişim kutusu oluşturulurken uygun ortam renkleri kullanın ve doğru düzeni ve etkileşim desenlerini izleyin. (Bkz [Visual Studio için Düzen](../../extensibility/ux-guidelines/layout-for-visual-studio.md).)  
  
### <a name="dialog-design"></a>İletişim tasarım  
İyi tasarlanmış iletişim kutuları aşağıdaki öğeleri dikkate alın:  
  
-   Desteklenen kullanıcı görevi  
  
-   İletişim metin stili, dil ve terminolojisi  
  
-   Denetim seçim ve UI kuralları  
  
-   Görsel düzen belirtimi ve denetimi hizalama  
  
-   Klavye erişimi  
  
#### <a name="content-organization"></a>İçerik kuruluş  
İletişim kutularının temel türleri arasındaki farklar göz önünde bulundurun:  
  
-   [Basit iletişim kutuları](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_SimpleDialogs) tek kalıcı pencere denetimlerinde sunar. Sunu alan Seçici veya bir simge çubuğu gibi karmaşık denetim düzenleri varyasyonları içerebilir.  
  
-   [İletişim kutuları katmanlı](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_LayeredDialogs) en ekran Gayrimenkul tek bir UI denetimlerinin birden çok grubu içerdiğinde yapmak için kullanılır. "Kullanıcı belirli bir anda görmek için hangi gruplandırma seçebilmeniz iletişim kutusu gruplandırmaları sekme denetimleri, gezinti liste denetimleri veya düğmeleri katmanlı".  
  
-   [Sihirbazlar](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Wizards) bir görevin tamamlanma yönelik adımlar mantıksal bir dizi kullanıcı yönlendirerek için kullanışlıdır. Bir dizi seçenek, farklı iş akışları ("dalları") önceki panelinde yapılan bir seçime bağlı bazen Tanıtımı sıralı paneller sunulur.  
  
####  <a name="BKMK_SimpleDialogs"></a>Basit iletişim kutuları  
Basit bir iletişim kutusu denetimleri tek bir kalıcı penceresinde sunumu ' dir. Bu sunu alan Seçici gibi karmaşık denetim düzenleri varyasyonları içerebilir. Basit iletişim kutuları için standart genel düzeni gibi karmaşık denetim gruplandırmaları için gerekli herhangi bir belirli düzeni izleyin.
  
![> oluşturma güçlü ad anahtarı Visual Studio'da basit bir iletişim kutusu bir örnektir. ] (../../extensibility/ux-guidelines/media/0704-01_createstrongnamekey.png "0704 01_CreateStrongNameKey")<br />Oluşturma güçlü ad anahtarı Visual Studio'da basit bir iletişim kutusu bir örnektir.
  
####  <a name="BKMK_LayeredDialogs"></a>Katmanlı iletişim kutuları  
Katmanlı iletişim kutuları sekmeler, panolar ve katıştırılmış ağaçları içerir. Tek bir kullanıcı Arabirimi içinde sunulan denetimlerin birden çok grubu olduğunda Gayrimenkul en üst düzeye çıkarmak için kullanılır. Böylece kullanıcı herhangi bir zamanda görmek için hangi gruplandırma gruplandırmaları katmanlı.  
  
En basit durumda gruplandırmaları arasında geçiş yapmak için bir sekme denetimi mekanizmadır. Birkaç alternatifleri kullanılabilir. Önceliklendirme ve katmanlama en uygun stili seçme için bkz.  
  
**Araçları &gt; seçenekleri** iletişim katıştırılmış bir ağaç kullanarak katmanlı bir iletişim kutusu örneği verilmiştir:  
  
![Araçlar > Seçenekler Visual Studio'da katmanlı bir iletişim kutusu bir örnektir. ] (../../extensibility/ux-guidelines/media/0704-02_toolsoptions.png "0704 02_ToolsOptions")<br />Araçlar > Seçenekler Visual Studio'da katmanlı bir iletişim kutusu bir örnektir.
  
####  <a name="BKMK_Wizards"></a>Sihirbazlar  
Sihirbazlar, bir görev tamamlandığında mantıksal bir dizi adımdan kullanıcı yönlendirerek için faydalıdır. Bir dizi seçenek içinde sıralı paneller sunulur ve kullanıcı sonraki geçmeden önce her adımın üzerinden devam etmeniz gerekir. Yeterli Varsayılanları kullanılabilir sonra **son** düğmesi etkindir.  
  
 Kalıcı sihirbazları görevler için kullanılan:  
  
-   Dal oluşturma, farklı yollar bağlı olarak kullanıcı seçimlerini Burada sunulan içerir  
  
-   Adımlar, sonraki adımlar önceki but kullanıcı girişi burada bağlıdır arasındaki bağımlılıkları içerir  
  
-   Kullanıcı arabirimini sunulan seçimleri ve her adımda olası sonuçları açıklamak için kullanılması gereken yeterince karmaşık  
  
-   Değişiklikler kaydedilmeden önce tamamının tamamlanması gereken adımları kümesini gerektiren işlem olan  
  
### <a name="common-conventions"></a>Genel kurallar  
En uygun tasarımı ve işlevselliği, iletişim kutuları ile elde etmek için bu kuralları iletişim kutusu boyutu, konum, standartları, Denetim yapılandırma ve hizalama, UI metin, başlık çubukları, denetim düğmeleri ve erişim tuşları izleyin.  
  
Düzen özgü yönergeler için bkz: [Visual Studio için Düzen](../../extensibility/ux-guidelines/layout-for-visual-studio.md).  
  
#### <a name="size"></a>Boyut  
İletişim kutuları içinde en az 1024 x 768 ekran çözünürlüğü sığacak ve ilk iletişim kutusu boyutu 900 x 700 piksel aşamaz. İletişim kutuları yeniden boyutlandırılabilir olabilir, ancak zorunlu değildir.  
  
Yeniden boyutlandırılabilir iletişim kutuları için iki öneriler şunlardır:  
  
1.  En küçük boyut tanımlanmış bir denetim için en iyi duruma getirir iletişim olduğunu kırpma olmadan ayarlamak ve makul yerelleştirme büyüme uyum sağlayacak şekilde ayarlayın.  
  
2.  Kullanıcı ölçeklendirilmiş boyutu oturumdan oturuma devam ettiğini. Örneğin, kullanıcı bir iletişim kutusu %150 ölçekler, bir sonraki başlatma iletişim kutusunun % 150 görüntülenir.  
  
#### <a name="position"></a>Konum  
İletişim kutuları, ilk başlatılırken IDE içinde ortalanmış görünmesi gerekir. Sonraki başlatır üzerinde ortalanmış göründükleri şekilde yeniden boyutlandırılabilir olmayan iletişim kutuları son konumunu kalıcı gerek yoktur. 

Yeniden boyutlandırılabilir iletişim kutuları için boyutu üzerinde sonraki başlatır kalıcı. Yeniden boyutlandırılabilir kalıcı iletişim kutuları için konumu kalıcı gerekmez. IDE içinde ortalanmış görüntüledikten kullanıcının görüntüleme yapılandırması değişti öngörülemeyen veya kullanılamaz konumda atarken iletişim olasılığını engeller. 

İletişim kutusunu daha büyük bir iş akışı'nın ayrılmaz bir parçası sık kullanılan, konumlandırılmasına engelleyici olmayan iletişim kutuları için kullanıcının konumunu sonraki başlatır üzerinde korunması gerekir.  
  
İletişim kutuları diğer iletişim kutuları oluşturma gerekir, üstteki iletişim sağa basamaklı ve aşağı olan yeni bir konuma gittiğinizde kullanıcı belirgin şekilde üst öğeden.  
  
#### <a name="modality"></a>Şekil  
Kalıcı olan kullanıcıların devam etmeden önce iletişim kutusunu iptal edin veya tamamlamak için gerekli olmadığı anlamına gelir. Kalıcı iletişim kutuları ortamdaki diğer bölümleriyle etkileşim kullanıcının engellemek bu yana, özelliğin Görev akışı bunları mümkün olduğunca az sayıda kullanmanız gerekir. Kalıcı bir işlem gerekli olduğunda, Visual Studio özelliklerinizi içine tümleştirebilir paylaşılan iletişim kutuları sayısına sahip. Yeni bir iletişim kutusu oluşturmanız gerekiyorsa, benzer işlevlere sahip varolan bir iletişim kutusu etkileşim desenini izler.  
  
Kullanıcılar, aynı anda iki etkinlik gerçekleştirmek gerektiğinde, ister **Bul** ve **Değiştir** kullanıcı kolayca aralarında geçiş yapabilirsiniz yeni kod yazarken, iletişim kutusu engelleyici olmayan olmalıdır. Visual Studio windows aracı Düzenleyicisi'ni destekleyen bağlantılı görev bu tür için genellikle kullanır.  
  
#### <a name="control-configuration"></a>Denetimi yapılandırma  
Visual Studio'da aynı şeyi başarmak varolan denetim yapılandırmalar tutarlı olmalıdır.  
  
#### <a name="title-bars"></a>Başlık çubukları  
  
-   Başlık çubuğu metni, başlatılan komutun adını yansıtması gerekir.  
  
-   Hiçbir simge iletişim başlık çubuklarında kullanılmalıdır. Burada sistem gerektiren durumlarda, Visual Studio logosu kullanın.  
  
-   İletişim kutuları olmamalıdır en aza indirmeniz veya düğmeleri en üst düzeye çıkarın.  
  
-   Başlık çubuğu Yardım düğmeleri kullanım dışı bırakıldı. Bunları yeni iletişim kutuları için eklemeyin. Mevcut olduğunda, bunlar bir görevle ilgili kavramsal bir Yardım konusu belirmelidir.  
  
 ![Visual Studio iletişim kutuları başlık çubuklarında için kılavuz belirtimleri](../../extensibility/ux-guidelines/media/0704-03_titlebarspecs.png "0704 03_TitleBarSpecs")<br />Visual Studio iletişim kutuları başlık çubuklarında için kılavuz belirtimleri
  
#### <a name="control-buttons"></a>Denetim düğmeleri  
Genel olarak, **Tamam**, **iptal**, ve **yardımcı** düğmeleri düzenlenmiş yatay iletişim kutusunun sağ alt köşesindeki. Bir iletişim kutusu denetim düğmelerle visual karışıklığı sunmak iletişim kutusunun altındaki çeşitli diğer düğmeleri varsa alternatif dikey yığın izin verilir.  
  
![Visual Studio iletişim kutuları denetim düğmeleri için kabul edilebilir yapılandırmaları](../../extensibility/ux-guidelines/media/0704-04_controlbuttonconfig.png "0704 04_ControlButtonConfig")<br />Visual Studio iletişim kutuları denetim düğmeleri için kabul edilebilir yapılandırmaları
  
İletişim kutusu, varsayılan denetim düğmesi bulunmalıdır. Varsayılan olarak kullanmak için en iyi komutu belirlemek için (öncelik sırasına göre listelenmiş) aşağıdaki seçenekler arasından seçim yapın:  
  
-   Varsayılan olarak güvenli ve en güvenli komutunu seçin. Bu, veri kaybını önlemek ve istenmeyen sistem erişimi önlemek büyük olasılıkla komutu seçme anlamına gelir.  
  
-   Veri kaybı ve güvenlik faktörleri değilseniz, kolaylık üzerinde göre varsayılan komut seçin. Sık sık ve yinelenen görevleri iletişim desteklediğinde, büyük olasılıkla komut varsayılan olarak dahil olmak üzere kullanıcının iş akışı artırır.  
  
Varsayılan komutu için kalıcı olarak zararlı bir eylemi seçme kaçının. Böyle bir komuta varsa, daha güvenli bir komut varsayılan olarak bunun yerine seçin.  
  
#### <a name="access-keys"></a>Erişim tuşları  
Erişim tuşları kullanmayın **Tamam**, **iptal**, veya **yardımcı** düğmeler. Bu düğmelerin kısayol tuşları için varsayılan olarak eşlenir:  
  
| Düğme adı | Klavye kısayolu |  
| --- | --- |  
| Tamam | Enter |  
| İptal | Esc |  
| Yardım | F1 |  
  
#### <a name="imagery"></a>Görüntüler  
Görüntüleri tutumlu iletişim kutularında kullanın. Büyük simgeler iletişim kutularında yalnızca alanını kullanmak için kullanmayın. Yalnızca uyarı simgeleri veya durum animasyonları gibi kullanıcı iletiye saymayı önemli bir bölümü varsa görüntüleri kullanın.  
  
###  <a name="BKMK_PrioritizingAndLayering"></a>Öncelik ve katmanlama  
  
#### <a name="prioritizing-your-ui"></a>UI önceliğini belirleme  
Belirli kullanıcı Arabirimi öğeleri için forefront getirmek ve daha gelişmiş davranışı ve iletişim kutuları (belirsiz komutları dahil) seçeneklere yerleştirmek gerekli olabilir. Yaygın olarak kullanılan işlevselliği, onu yer yaparak ve iletişim kutusu görüntülendiğinde yaparak onu görünen varsayılan olarak kullanıcı arabiriminde bir metin etiketi ile forefront duruma getirin.  
  
#### <a name="layering-your-ui"></a>UI katmanlama  
Bir iletişim kutusu gereklidir, ancak basit bir iletişim kutusunda ne görüntülenebilir ötesinde kullanıcıya sunmak istediğiniz ilgili işlevselliği gider karar verdiyseniz, UI katman gerekir. Visual Studio kullanan en yaygın katmanlama sekmeler ve hallways veya panolar yöntemleridir. Bazı durumlarda, genişletme ve daraltma bölgeleri uygun olabilir. Visual Studio'da Uyarlamalı UI genellikle önerilmez.  
  
Olumlu ve olumsuz yönleri için kullanıcı Arabirimi aracılığıyla sekmesini benzeri denetimlere katmanlama farklı yöntemleri vardır. Durumunuza uygun bir katmanlama teknik seçme emin olmak için aşağıdaki listeyi gözden geçirin.  
  
##### <a name="tabbing"></a>Sekme  
  
| Geçiş mekanizması | Avantajları ve uygun kullanın | Olumsuz yönleri ve uygunsuz kullanım |  
| --- | --- | --- |  
| Sekme denetimi | İlgili ayarlar iletişim kutusu sayfaları mantıksal Grup<br /><br />Daha az beş (veya tek bir satırda arasında iletişim uygun sekme sayısı) için yararlı iletişim ilgili denetimlerin sayfaları<br /><br />Sekme etiketleri kısa olmalıdır: içeriği kolayca tanıyacak bir veya iki sözcükler<br /><br />Bir ortak sistem iletişim stili<br /><br />Örnek: **dosya Gezgini &gt; öğe özellikleri** | Tanımlayıcı kısa etiketler yapmak zor olabilir<br /><br />Genellikle bir iletişim kutusunda beş sekme geçmiş ölçeklendirilmediğini<br /><br />Bir satır (kullanın bir alternatif katmanlama teknik) için çok fazla sekme varsa uygunsuz<br /><br />Değil Genişletilebilir |  
| Kenar gezinme | Sekmeleri'den daha fazla kategori uyum basit geçiş aygıtı<br /><br />Düz listesini kategorileri (hiyerarşi yok)<br /><br />Genişletilebilir<br /><br />Örnek: **Özelleştir... &gt;Komut ekleme** | İyi kullanılmıyor üçten grupları varsa yatay alanı<br /><br />Görev daha iyi bir açılan için uygun olabilir |  
| Ağaç denetimi | Sınırsız kategorileri sağlar<br /><br />Gruplandırma ve/veya kategori hiyerarşisi sağlar<br /><br />Genişletilebilir<br /><br />Örnek: **Araçları &gt; seçenekleri** | Yoğun bir şekilde iç içe geçmiş hiyerarşileri aşırı yatay kaydırma neden olabilir<br /><br />Visual Studio bir overabundance ağaç görünümlerinin olan |  
| Sihirbazı | Kullanıcı görev tabanlı, sıralı adımlarda size kılavuzluk ederek görev tamamlama yardımcı olur: sihirbazın üst düzey bir görevi temsil eder ve ayrı ayrı paneller genel görevi gerçekleştirmek için gereken görevleri temsil eder<br /><br />Yararlı görev zaman kullanıcı Aksi durumda birden çok düzenleyicilerini kullanın görevi tamamlamak için windows aracı gerekirdi olarak UI sınırları kestiği<br /><br />Görev dallanma gerektirdiğinde yararlı<br /><br />Görev bağımlılıkları adımlar arasındaki içerdiğinde yararlı<br /><br />Yararlı bir karar çatalı ile birkaç benzer görevleri farklı benzer iletişim kutuları sayısını azaltmak için bir iletişim kutusunda sunulabilir | Sıralı iş akışı gerektirmez herhangi bir görev için uygun olmayan<br /><br />Kullanıcıların kısası ve çok fazla adım sihirbaz tarafından kafası hale gelebilir<br /><br />Sihirbazlar kendiliğinden ekran Gayrimenkul sınırlı |  
  
##### <a name="hallways-or-dashboards"></a>Hallways veya panoları  
Hallways ve panolar iletişim kutuları veya diğer iletişim kutuları ve windows noktalarına başlatma olarak hizmet paneller markalarıdır. İyi tasarlanmış "koridor" hemen yalnızca en yaygın seçenekler, komutları ve kullanıcının taşımalarına genel görevleri gerçekleştirmenize izin ayarları, ortaya çıkarır. Burada gerçek koridor arkasına odaları erişmek için açılan kapılar sağlar gibi daha az yaygın UI ayrı "odaları" (genellikle diğer iletişim kutuları) ana koridor erişilebilir ilgili işlevlerinin içine toplanır.  
  
Alternatif olarak, daha az ortak işlevsellik ayrı konumlar yeniden düzenleme yalnızca bir Pano yerine, tek bir koleksiyon içindeki tüm kullanılabilir işlevler sunan UI.  
  
![Outlook'ta ek kullanıcı Arabirimi gösterme için koridor kavram](../../extensibility/ux-guidelines/media/0704-08_hallway.png "0704 08_Hallway")<br />Outlook'ta ek kullanıcı Arabirimi gösterme için koridor kavramı
  
##### <a name="adaptive-ui"></a>Uyarlamalı kullanıcı Arabirimi  
Gösterme veya gizleme UI kullanımı dikkate alarak veya bir kullanıcının kendi kendine bildirilen deneyimini diğer bölümleri gizleme çalışırken gerekli UI sunan başka bir yoludur. Bu Visual Studio'da göstermek veya gizlemek UI karar verme algoritmaları zor olabilir ve kuralların her zaman bazı durumlarda kümesi için yanlış olur önerilmez.  
  
##  <a name="BKMK_Projects"></a>Projeleri  
  
### <a name="projects-in-the-solution-explorer"></a>Çözüm Gezgini'nde projeleri  
Çoğu projeleri olarak tabanlı başvurusu, dizin tabanlı veya karma sınıflandırılır. Üç tür projeleri Çözüm Gezgini'nde eşzamanlı olarak desteklenir. Projeleri ile çalışırken kullanıcı deneyiminin kök bu penceresinin içinde gerçekleşir. Farklı proje düğümleri başvurusu, dizin veya karma mod türü projelerini olsa da, bir başlangıç noktası olarak projeye özgü kullanıcı desenleri uzaklaşan önce uygulanması gereken bir ortak etkileşim düzeni yoktur.  
  
Projeleri her zaman gerekir:  
  
-   Proje içeriği düzenlemek için proje klasörler ekleme yeteneği desteği  
  
-   Proje kalıcılığı için tutarlı bir modeli koru  
  
Projeleri için tutarlı etkileşim modelleri de korumanız gerekir:  
  
-   Proje öğeleri kaldırma  
  
-   Belgeleri kaydetme  
  
-   Proje özellik düzenleme  
  
-   Alternatif bir görünümü'nde projeye düzenleme  
  
-   Sürükleme ve bırakma işlemleri  
  
### <a name="drag-and-drop-interaction-model"></a>Sürükle ve Bırak etkileşimi modeli  
Projeleri genellikle sınıflandırmak kendilerinin tabanlı başvurusu (proje öğeleri depolama için yalnızca başvuruları kalıcı hale getirmek kullanabilir) dizin tabanlı (fiziksel olarak yalnızca proje öğeleri kalıcı hale getirmek için saklanan bir projenin hiyerarşisi içinde), ya da (başvuruları kalıcı mümkün karma veya fiziksel öğeleri). IDE içinde aynı anda üç tür projeleri düzenler **Çözüm Gezgini**.  
  
Sürükle ve bırak açısından bakıldığında, aşağıdaki özelliklere projesi içinde her tür uygulanması gereken **Çözüm Gezgini**:  
  
-   **Proje başvurusu tabanlı:** anahtar proje'nın geçici depolama alanındaki bir öğeyi başvuru sürükleyerek noktasıdır. Bir başvuru tabanlı proje bir taşıma işlemi için bir kaynak olarak davranırken, yalnızca öğesine başvuruda projeden kaldırmanız gerekir. Öğe sabit sürücüden gerçekte silinmemelidir. Bir başvuru tabanlı projesi (kopyalama veya taşıma) işlemi için hedef olarak davranırken, özgün kaynak öğesine başvuruda öğesi özel bir kopyasını yapmadan eklemelisiniz.  
  
-   **Dizin tabanlı proje:** bir Sürükle ve bırak açısından bakıldığında, projeyi bir başvuru yerine fiziksel öğesi sürükleyerek. Dizin tabanlı bir proje bir taşıma işlemi için bir kaynak olarak davranırken sabit sürücüden fiziksel öğeyi silmek yanı sıra projeden kaldırma yukarı bitmelidir. Dizin tabanlı bir proje (kopyalama veya taşıma) işlemi için hedef olarak davranırken, hedef konumunda kaynak öğenin bir kopyasını olmanız gerekir.  
  
-   **Karma hedef projesi:** bir Sürükle ve bırak açısından bakıldığında, bu proje türünü davranışını (depolama alanındaki bir öğeyi referansı) ya da öğenin kendisini sürüklenen öğenin niteliğine temel alır. References ve fiziksel öğeleri için doğru davranış yukarıda açıklanmıştır.  
  
Projede yalnızca bir tür ise **Çözüm Gezgini**, sonra da sürükle ve bırak işlemleri kolay olacaktır. Her proje sistemi kendi sürükle ve bırak davranışını tanımlama yeteneği olduğundan, tahmin edilebilir kullanıcı deneyimi sağlamak için belirli yönergeleri (Windows Explorer sürükle ve bırak davranışı temelinde) gelmelidir:  
  
-   Değiştirilmemiş bir sürükleme işlemi **Çözüm Gezgini** (zaman Ctrl ya da SHIFT tuşlarını tutulur) bir taşıma işlemi neden olur.  
  
-   Shift sürükleme işlemi aynı zamanda bir taşıma işlemi neden olur.  
  
-   CTRL-sürükleme işlemi, bir kopyalama işleminde neden olur.  
  
-   Proje başvurusu tabanlı ve karma sistemleri kaynak öğesine bir bağlantı (veya başvuru) ekleme kavram destekler. Bu proje bir Sürükle ve bırak işlemi hedefinin olduğunda (zaman **Ctrl + Shift** tutulan), projeye eklenen öğesine başvuruda neden  
  
Tüm sürükle ve bırak işlemleri tabanlı başvurusu, dizin tabanlı ve karma projeler arasında duyarlı birleşimleridir. Özellikle, kaynak directory tabanlı proje taşınma tamamlandıktan sonra kaynak öğesini silmek olacağı için dizin tabanlı bir kaynak proje ve referans tabanlı hedef projesi arasında taşıma işlemi izin vermek görünen sorunlu oluşturur. Hedef tabanlı başvurusu proje sonra silinmiş bir öğeyi başvuru yapmış olursunuz.  
  
Hedef tabanlı başvurusu projenin kaynak öğesini bağımsız bir kopyasını yapmamanız gerekir çünkü bu proje türleri arasında kopyalama işlemi izin vermek görünen yanıltıcı. Dizin tabanlı bir proje başvuruları kalıcı hale getirmek edemediği benzer şekilde, Ctrl + Shift directory tabanlı hedef projeye sürükleme izin verilmemelidir. Burada sürükle ve bırak işlemi desteklenmiyor durumlarda IDE açılır izin verme ve kullanıcı (işaretçi aşağıdaki tabloda gösterilen) Hayır bırak imleç Göster gerekir.  
  
Sürükle ve bırak davranışı düzgün bir şekilde uygulamak için sürükle kaynak projenin hedef projeye doğası iletişim kurması gerekiyor. (Örneğin, bu başvuru veya dizin tabanlı mi?) Bu bilgiler, kaynak tarafından sunulan Pano biçimi ile belirtilir. Sürükleme (veya Pano kopyalama işlemi) kaynağı olarak bir proje ya da sunması gereken `CF_VSREFPROJECTITEMS` veya `CF_VSSTGPROJECTITEMS` sırasıyla proje başvurusu veya dizin tabanlı olup olmamasına bağlı olarak. Bu biçimler her ikisi de Windows benzer aynı veri içeriğe sahip `CF_HDROP` dosya adları, olmak yerine dizeleri listelerinde çift - ancak bu biçim`NULL` listesi sonlandırıldı `Projref` dizeleri ( döndürülen`IVsSolution::GetProjrefOfItem`veya `::GetProjrefOfProject` uygun şekilde).  
  
Bırakma (veya Pano Yapıştırma işlemi) hedefi olarak bir proje her ikisini de kabul etmelidir `CF_VSREFPROJECTITEMS` ve `CF_VSSTGPROJECTITEMS`sürükle ve bırak işlemi tam işlenmesini hedef proje ve kaynak projesini yapısına bağlı olarak farklılık gösterir ancak. Kaynak projesini olup sunar tarafından doğası bildirir `CF_VSREFPROJECTITEMS` veya `CF_VSSTGPROJECTITEMS`. Bırakma hedefi kendi yapısı anlar ve bu nedenle bir move, copy olup olmadığını olarak kararları için yeterli bilgiye sahip ya da bağlantı gerçekleştirilmelidir. Kullanıcı ayrıca Ctrl, Shift, veya hem Ctrl ve Shift tuşlarını tuşlarına basarak hangi sürükle ve bırak işlemi gerçekleştirilmelidir değiştirir. Bırakma hedefi düzgün hangi işlemi önceden içinde gerçekleştirilir belirtmek önemlidir, `DragEnter` ve `DragOver` yöntemleri. **Çözüm Gezgini** otomatik olarak kaynak projesini ve hedef projesi aynı proje olup olmadığını bilir.  
  
Proje öğeleri (örneğin, örneğinden diğerine devenv.exe) Visual Studio örneklerinde sürükleme özellikle olmayan desteklenmiyor. **Çözüm Gezgini** doğrudan da bu devre dışı bırakır.  
  
Kullanıcının her zaman bir öğeyi seçerek, hedef konuma sürükleyerek ve öğe kesilmeden önce aşağıdaki fare işaretçileri görünür Gözlemleme sürükle ve bırak işlemi etkisini belirlemek mümkün olması gerekir:  
  
| Fare işaretçisi | Komut | Açıklama |  
| :---: | --- | --- |  
| !["Açılan yok" simgesini fare](../../extensibility/ux-guidelines/media/0706-01_mousenodrop.png "0706 01_MouseNoDrop") | Hiçbir bırakma | Öğe belirtilen konuma bırakılamıyor. |  
| ![Fare "Kopyala" simgesi](../../extensibility/ux-guidelines/media/0706-02_mousecopy.png "0706 02_MouseCopy") | Kopyala | Öğesi, hedef konuma kopyalanacak. |  
| ![Fare "Taşı" simgesi](../../extensibility/ux-guidelines/media/0706-03_mousemove.png "0706 03_MouseMove") | Taşıma | Öğesi, hedef konuma taşınır. |  
| ![Fare simgesini "Başvuru Ekle"](../../extensibility/ux-guidelines/media/0706-04_mouseaddref.png "0706 04_MouseAddRef") | Başvuru ekleme | Hedef konuma seçili öğe için bir başvuru eklenir. |

#### <a name="reference-based-projects"></a>başvuru tabanlı projeler  
 Aşağıdaki tabloda hedef başvurulan tabanlı projelerde basılı kaynak öğesi ve değiştirici anahtarları doğasına bağlı gerçekleştirilmelidir sürükle ve bırak (yanı sıra Kes/kopyala/yapıştır) işlemleri özetlenmektedir:  
  
| Değiştirici | Kategori | Kaynak öğe: başvuru/bağlantısı | Kaynak öğe: fiziksel öğe veya dosya sistemi (`CF_HDROP`) |  
| --- | --- | --- | --- |  
| Hiçbir değiştiricisi | Eylem | Taşıma | Bağlantı |  
| Hiçbir değiştiricisi | Hedef | Özgün öğe başvuru ekler | Özgün öğe başvuru ekler |  
| Hiçbir değiştiricisi | Kaynak | Özgün öğe siler referansı | Özgün öğe korur |  
| Hiçbir değiştiricisi | Sonuç | `DROPEFFECT_MOVE`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | `DROPEFFECT_LINK`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama |  
| Shift + sürükleyin | Eylem | Taşıma | Hiçbir bırakma |  
| Shift + sürükleyin | Hedef | Özgün öğe başvuru ekler | Hiçbir bırakma |  
| Shift + sürükleyin | Kaynak | Özgün öğe siler referansı | Hiçbir bırakma |  
| Shift + sürükleyin | Sonuç | `DROPEFFECT_MOVE`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | Hiçbir bırakma |  
| CTRL + sürükle | Eylem | Kopyala | Hiçbir bırakma |  
| CTRL + sürükle | Hedef | Özgün öğe başvuru ekler | Hiçbir bırakma |  
| CTRL + sürükle | Kaynak | Özgün öğesine başvuruda korur | Hiçbir bırakma |  
| CTRL + sürükle | Sonuç | `DROPEFFECT_COPY`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | Hiçbir bırakma |  
| Ctrl + Shift + sürükleyin | Eylem | Bağlantı | Bağlantı |  
| Ctrl + Shift + sürükleyin | Hedef | Özgün öğe başvuru ekler | Özgün öğe başvuru ekler |  
| Ctrl + Shift + sürükleyin | Kaynak | Özgün öğesine başvuruda korur | Özgün öğe korur |  
| Ctrl + Shift + sürükleyin | Sonuç | `DROPEFFECT_LINK`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | `DROPEFFECT_LINK`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama |  
| Ctrl + Shift + sürükleyin | Not | Windows Gezgini'nde kısayolları için sürükle ve bırak davranışı ile aynıdır. ||  
| Kes/Yapıştır | Eylem | Taşıma | Bağlantı |  
| Kes/Yapıştır | Hedef | Özgün öğe başvuru ekler | Özgün öğe başvuru ekler |  
| Kes/Yapıştır | Kaynak | Özgün öğesine başvuruda korur|Özgün öğe korur |  
| Kes/Yapıştır | Sonuç | Madde depolama özgün konumda kalır | Madde depolama özgün konumda kalır |  
| Kopyala/Yapıştır | Eylem | Kopyala | Bağlantı |  
| Kopyala/Yapıştır | Kaynak | Özgün öğe başvuru ekler | Özgün öğe başvuru ekler |  
| Kopyala/Yapıştır | Sonuç | Özgün öğesine başvuruda korur | Özgün öğe korur |  
| Kopyala/Yapıştır | Eylem | Madde depolama özgün konumda kalır | Madde depolama özgün konumda kalır |  
  
#### <a name="directory-based-projects"></a>Dizin tabanlı projeler  
Aşağıdaki tabloda, hedef dizin tabanlı projelerde basılı kaynak öğesi ve değiştirici anahtarları doğasına bağlı gerçekleştirilmelidir sürükle ve bırak (yanı sıra Kes/kopyala/yapıştır) işlemleri özetlenmektedir:  
  
| Değiştirici | Kategori | Kaynak öğe: başvuru/bağlantısı | Kaynak öğe: fiziksel öğe veya dosya sistemi (`CF_HDROP`) |  
| --- | --- | --- | --- |  
| Hiçbir değiştiricisi | Eylem | Taşıma | Taşıma |  
| Hiçbir değiştiricisi | Hedef | Hedef konuma kopyalar öğesi | Hedef konuma kopyalar öğesi |  
| Hiçbir değiştiricisi | Kaynak | Özgün öğe siler referansı | Özgün öğe siler referansı | | Hiçbir değiştiricisi | Sonuç | `DROPEFFECT_MOVE`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | `DROPEFFECT_MOVE`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama |  
| Shift + sürükleyin | Eylem | Taşıma | Taşıma |  
| Shift + sürükleyin | Hedef | Hedef konuma kopyalar öğesi | Hedef konuma kopyalar öğesi |  
| Shift + sürükleyin | Kaynak | Özgün öğe siler referansı | Öğeyi özgün konumundan siler |
| Shift + sürükleyin | Sonuç | `DROPEFFECT_MOVE`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | `DROPEFFECT_MOVE`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama |  
| CTRL + sürükle | Eylem | Kopyala | Kopyala |  
| CTRL + sürükle | Hedef | Hedef konuma kopyalar öğesi | Hedef konuma kopyalar öğesi |  
| CTRL + sürükle | Kaynak | Özgün öğesine başvuruda korur | Özgün öğesine başvuruda korur |  
| CTRL + sürükle | Sonuç | `DROPEFFECT_COPY`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | `DROPEFFECT_COPY`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama |  
| Ctrl + Shift + sürükleyin | | Hiçbir bırakma | Hiçbir bırakma |  
| Kes/Yapıştır | Eylem | Taşıma | Taşıma |  
| Kes/Yapıştır | Hedef | Hedef konuma kopyalar öğesi | Hedef konuma kopyalar öğesi |  
| Kes/Yapıştır | Kaynak | Özgün öğe siler referansı | Öğeyi özgün konumundan siler |  
| Kes/Yapıştır | Sonuç | Madde depolama özgün konumda kalır | Depolama özgün konumundan öğe silindi |  
| Kopyala/Yapıştır | Eylem | Kopyala | Kopyala |  
| Kopyala/Yapıştır | Hedef | Özgün öğe başvuru ekler | Hedef konuma kopyalar öğesi |  
| Kopyala/Yapıştır | Kaynak | Özgün öğe korur | Özgün öğe korur |  
| Kopyala/Yapıştır | Sonuç | Madde depolama özgün konumda kalır | Öğe özgün konuma bileşenler deposunda kalır |
  
#### <a name="mixed-target-projects"></a>Karma hedef projeleri  
Aşağıdaki tablo karışık hedef projelerde basılı kaynak öğesi ve değiştirici anahtarları doğasına bağlı gerçekleştirilmelidir sürükle ve bırak (yanı sıra Kes/kopyala/yapıştır) işlemleri özetlenmektedir:  
  
| Değiştirici | Kategori | Kaynak öğe: başvuru/bağlantısı | Kaynak öğe: fiziksel öğe veya dosya sistemi (`CF_HDROP`) |  
| --- | --- | --- | --- |
| Hiçbir değiştiricisi | Eylem | Taşıma | Taşıma |
| Hiçbir değiştiricisi | Hedef | Özgün öğe başvuru ekler | Hedef konuma kopyalar öğesi |
| Hiçbir değiştiricisi | Kaynak | Özgün öğe siler referansı | Özgün öğe siler referansı |
| Hiçbir değiştiricisi | Sonuç | `DROPEFFECT_ MOVE`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | `DROPEFFECT_ MOVE`eylem olarak döndürülen `::Drop` ve depolama özgün konumundan öğe silindi |
| Shift + sürükleyin | Eylem | Taşıma | Taşıma |
| Shift + sürükleyin | Hedef | Özgün öğe başvuru ekler | Hedef konuma kopyalar öğesi |
| Shift + sürükleyin | Kaynak | Özgün öğe siler referansı | Öğeyi özgün konumundan siler | 
| Shift + sürükleyin | Sonuç | `DROPEFFECT_ MOVE`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | `DROPEFFECT_ MOVE`eylem olarak döndürülen `::Drop` ve depolama özgün konumundan öğe silindi |
| CTRL + sürükle | Eylem | Kopyala | Kopyala |
| CTRL + sürükle | Hedef | Özgün öğe başvuru ekler | Hedef konuma kopyalar öğesi |
| CTRL + sürükle | Kaynak | Özgün öğesine başvuruda korur | Özgün öğe korur |
| CTRL + sürükle | Sonuç | `DROPEFFECT_ COPY`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | `DROPEFFECT_ COPY`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama |
| Ctrl + Shift + sürükleyin | Eylem | Bağlantı | Bağlantı |
| Ctrl + Shift + sürükleyin | Hedef | Özgün öğe başvuru ekler | Özgün kaynak öğe başvuru ekler |
| Ctrl + Shift + sürükleyin | Kaynak | Özgün öğesine başvuruda korur | Özgün öğe korur |
| Ctrl + Shift + sürükleyin | Sonuç | `DROPEFFECT_ LINK`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama | `DROPEFFECT_ LINK`eylem olarak döndürülen `::Drop` ve madde kalır özgün konumda depolama |
| Kes/Yapıştır | Eylem | Taşıma | Taşıma |
| Kes/Yapıştır | Hedef | Hedef konuma kopyalar öğesi | Hedef konuma kopyalar öğesi |
| Kes/Yapıştır | Kaynak | Özgün öğe siler referansı | Öğeyi özgün konumundan siler |
| Kes/Yapıştır | Sonuç | Madde depolama özgün konumda kalır | Depolama özgün konumundan öğe silindi |
| Kopyala/Yapıştır | Eylem | Kopyala | Kopyala |
| Kopyala/Yapıştır | Hedef | Özgün öğe başvuru ekler | Hedef konuma kopyalar öğesi |
| Kopyala/Yapıştır | Kaynak | Özgün öğe korur | Özgün öğe korur |
| Kopyala/Yapıştır | Sonuç | Madde depolama özgün konumda kalır | Madde depolama özgün konumda kalır |
  
Bu ayrıntılar dikkate sürükleyerek uygularken alınıp alınmayacağını **Çözüm Gezgini**:  
  
-   Birden çok seçim senaryolar için tasarlayın.  
  
-   Dosya adları (tam yolu) hedef projede benzersiz olmalıdır veya bırakma izin.  
  
-   Klasör adları benzersiz olmalıdır (büyük küçük harf duyarsız) bunlar bırakılır düzeyinde.  
  
-   Sürükleme (yukarıdaki senaryolarda geçmeyen) zaman açık veya kapalı olan dosyaları arasındaki davranış farklılıkları vardır.  
  
-   Üst düzey dosyalar klasörler biraz farklı bir şekilde davranır.  
  
Dikkat edilmesi gereken başka bir taşıma işlemleri açık tasarımcıları veya düzenleyicileri olan öğeler için nasıl ele alınacağını bir sorundur. Beklenen bir davranış (tüm proje türleri için geçerlidir) aşağıdaki gibidir:  
  
1.  Açık Düzenleyicisi/designer kaydedilmeyen tüm değişiklikler yoksa Düzenleyicisi/Tasarımcısı penceresinin sessizce kapatılmalıdır.  
  
2.  Açık Düzenleyicisi/designer kaydedilmemiş değişiklikler varsa, bu ardından Sürükle kaynağı oluşur ve kullanıcının aşağıdakine benzer bir istem penceresiyle kapatmadan önce açık belgede kaydedilmemiş değişiklikler kaydetmesini isteyin bırakma beklemesi gereken :  
  
    ```  
    ==========================================================   
         One or more open documents have unsaved changes.  
    Do you want to save uncommitted changes before proceeding?   
                      [Yes]  [No]  [Cancel]   
    ==========================================================  
    ```  
  
Bu kullanıcının kendi kopyaları hedef yapar önce çalışmalarınızı kaydedin fırsatı verir. Yeni bir yöntem `IVsHierarchyDropDataSource2::OnBeforeDropNotify` bu işleme etkinleştirmek için eklendi.  
  
Depolama alanında olduğu gibi hedef sonra öğesinin durumunu kopyalayın (kullanıcı seçerseniz kaydedilmemiş değişiklikler Düzenleyicisi'nde hariç **Hayır**). Hedef, kopyalama tamamlandıktan sonra (içinde `IVsHierarchyDropDataSource::Drop`), kaynak taşıma işlemini Sil bölümünü tamamlamak için Fırsat verilir (içinde `IVsHierarchyDropDataSource::OnDropNotify`).  
  
Kaydedilmemiş değişiklikler ile tüm düzenleyicileri açık bırakılmalıdır. Kaydedilmeyen tüm değişiklikler bu belgeler için bu taşıma işlemi kopyalama kısmı gerçekleştirilir, ancak delete bölümü durdurulacak anlamına gelir. Kullanıcı seçtiğinde birden çok seçim senaryosunda **Hayır**, kaydedilmemiş değişiklikler bu belgelerle kapalı kaldırıldı veya değiştirilmemesi gereken ancak kaydedilmemiş değişiklikler olmayanlar kapalı ve kaldırılmış.