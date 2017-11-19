---
title: "Bildirimler ve Visual Studio için ilerleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0ef65e9-0f1f-45f4-9f25-6e2398691168
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0d16ed0f58929a6559812261c3443b3561375205
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="notifications-and-progress-for-visual-studio"></a>Bildirimler ve Visual Studio için ilerleme durumu
##  <a name="BKMK_NotificationSystems"></a>Bildirim sistemleri  
  
### <a name="overview"></a>Genel Bakış  
 Visual Studio yazılım geliştirme görevlerini ilgili olarak neler olduğunu kullanıcıya bildirmek için birkaç yolu vardır.  
  
 Her türlü bildirim uygularken:  
  
-   **En az bildirim sayısı tutmak** etkili numarası. Bildirim iletileri, Visual Studio kullanıcıların çoğunluğunun ya da bir özel özellik/özellik alanı kullanıcılarının uygulamalıdır. Bildirimler aşırı kullanım kullanıcı sidetrack veya sistem kullanımı algılanan kolaylığı düşmesine olabilir.  
  
-   **NET, işlem yapılabilir iletileri sunan olun** kullanıcının daha karmaşık seçimleri yapmak ve daha fazla eylemin gerçekleştirilmesi için uygun bağlamı çağırmak için kullanabilirsiniz.  
  
-   **Zaman uyumlu ve zaman uyumsuz ileti uygun şekilde sunar.** Zaman uyumlu bildirimleri hemen ilgilenilmesi gereken bir şey, ne zaman bir web hizmeti kilitlenmesine veya bir kod gibi özel durum gösterir. Hemen bir modal iletişim kutusunda gibi kendi girişi gerektiren bir şekilde bu durumlarda, kullanıcı bilgisi. Zaman uyumsuz bildirimleri, kullanıcı hakkında bilmeniz gereken ancak gibi bir derleme işlemi tamamlandığında veya bir web sitesi dağıtım tamamlandıktan hemen sonra yapması gereken değil ' dir. Bu iletiler, daha fazla ortam ve kullanıcının Görev akışı kesme değil.  
  
-   **Kalıcı iletişim kutuları kullanıcı daha fazla eylem engellemek için yalnızca gerekli olduğunda kullanın** ileti aktarımının ya da iletişim kutusunda sunulan bir kararı vermeden önce.  
  
-   **Artık geçerli olduklarında ortam bildirimleri kaldırın.** Kullanıcı hakkında bildirildi sorunu çözmek için eylemi zaten gerçekleştirmişsiniz varsa bir bildirim verilecek gerektirmez.  
  
-   **Bildirimler için false bağıntıları açabilir unutmayın.** Kullanıcılar, aslında nedensel hiçbir ilişki değiştirildiği bir veya daha fazla eylemlerini bir bildirim tetiklenen olduğunu düşünüyorsanız. Clear bağlamı, tetikleyici ve bildirim kaynağı hakkında bildirim iletisi olması.  
  
### <a name="choosing-the-right-method"></a>Doğru yöntemi seçme  
 İletinizi kullanıcıya bildirmek için doğru yöntemi seçme yardımcı olmak üzere bu tabloyu kullanın.  
  
|Yöntem|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|Kullanmayın|  
|------------|---------|----------------|  
|[Kalıcı hata iletisi iletişim kutuları](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ModalErrorMessageDialogs)|Devam etmeden önce kullanıcının yanıtı gerektiğinde kullanın.|Kullanıcı engelleme ve kendi akış kesme gerekli olduğunda kullanmayın. Kalıcı iletişim kutuları ileti başka bir, daha az müdahale şekilde göstermek mümkünse kullanmaktan kaçının.|  
|[IDE durum çubuğu](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_IDEStatusBar)|Bir işlem durumuyla ilgili ortam metin bilgileri olduğunda kullanın.|Tek başına kullanmayın. En iyi şekilde başka bir geri bildirim mekanizması ile birlikte kullanılır.|  
|[Katıştırılmış bilgi çubuğu](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_EmbeddedInfobar)|Araç penceresi veya belge penceresinde, devam ediyor, hata durumunda, sonuçları ve/veya işlem yapılabilir bilgi bildirmek için kullanın.|Bilgi bilgi çubuğu yerleştirildiği konum ilgili değilse kullanmayın.<br /><br /> Belge/araç penceresi dışında kullanmayın.|  
|[Fare imleci değişiklikleri](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_MouseCursorChanges)|Bir işlem geçiyor bildirmek için kullanılabilir. Sürükle ve bırak ilerleme durumunu veya fare imlecini çizim modu gibi belirli modunda olduğunda gibi fare bir durum değişikliği olduğunu bildirmek için de kullanılır.|Veya, fluttering, imleç (örneğin, uzun çalışan bir işlemi yerine tüm işlem bölümlerini bağlı olduğunda) büyük olasılıkla kısa Süren değişiklikler için kullanmayın.|  
|[İlerleme göstergesi](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_NotSysProgressIndicators)|Rapor ilerleme (belirli veya belirsiz) ihtiyacınız olduğunda kullanın. İlerleme göstergesi türleri ve belirli kullanım her biri için çeşitli vardır. Bkz: [İlerleme göstergesi](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ProgressIndicators).||  
|[Visual Studio bildirimler penceresi](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_VSNotificationsToolWindow)|Bildirimler penceresini herkese açık şekilde genişletilebilir değil. Ancak, bir dizi iletileri lisans ve bilgilendirici bildirimleri Visual Studio veya paketleri için güncelleştirmeleri, kritik sorunlar da dahil olmak üzere Visual Studio hakkında iletişim kurmak için kullanılır.|Diğer bildirim türleri için kullanmayın.|  
|[Hata listesi](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ErrorList)|Bir sorun (uyarı/hata/bilgisi) sahip doğrudan kullanıcının açık çözüm için sorun ilgilidir, kod eyleme geçmek gerekebilir.<br /><br /> Bu, örneğin aşağıdakileri içerir:<br /><br /> -Derleyici iletilerini (uyarı/hata/bilgisi)<br /><br /> -Kod Çözümleyicisi/tanılama iletileri kod hakkında<br /><br /> -İletileri derleme<br /><br /> Proje ya da çözüm dosyaları ile ilgili sorunlar için uygun olabilir, ancak bir Çözüm Gezgini göstergesi önce göz önünde bulundurun.|Kullanıcının açık çözüm kodu herhangi ilişkisine sahip olmayan öğeler için kullanmayın.|  
|Düzenleyici bildirimleri: ampul|Dosya Aç var olan bir sorunu gidermek için kullanılabilecek bir düzeltme sahip olduğunuzda kullanın.<br /><br /> Ampul ayrıca kullanıcının kodu yapan yeniden düzenlemeler gibi isteğe bağlı alınır ancak bu durumda "bildirim stili." görünmez hızlı Eylemler barındırmak için kullanılması gerektiğini unutmayın|Hiçbir ilişki açık dosyasına sahip olmayan öğeler için kullanmayın.|  
|Düzenleyici bildirimleri: dalgalı çizgiler|Belirli bir aralık kendi açık kod (örneğin, bir kırmızı dalgalı hatalar için) ile ilgili bir sorun için kullanıcıyı uyarmak için kullanın.|Kendi açık kodunun belirli bir aralığa ilişkili olmayan öğeler için kullanmayın.|  
|[Katıştırılmış durum çubukları](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_EmbeddedStatusBars)|İçerik veya işlemi belirli araç penceresi, belge penceresine ya da iletişim kutusu penceresinin bağlam içinde ilgili durum sağlamak için kullanın.|Genel Ürün bildirimleri, işlemler veya içeriğe hiçbir ilişkisi belirli penceresi içinde olmayan öğeler için kullanmayın.|  
|[Windows Tepsisi bildirimleri](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_WindowsTray)|İşlem dışı işlemler için bildirimler yüzey veya uygulamaları Yahoo! companion için kullanın.|IDE ilgili bildirimler için kullanmayın.|  
|[Bildirim balonları](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_NotificationBubbles)|Bir uzak işlemini bildir veya değiştirmek için kullanın **dışında** IDE.|Bir araç olarak işlemler kullanıcı bilgilendirmek için kullanmayın **içinde** IDE.|  
  
### <a name="notification-methods"></a>Bildirim yöntemleri  
  
####  <a name="BKMK_ModalErrorMessageDialogs"></a>Kalıcı hata iletisi iletişim kutuları  
 Kalıcı hata iletisi iletişim kutusu, kullanıcı onayı veya eylem gerektiren bir hata iletisi görüntülemek için kullanılır.  
  
 ![Kalıcı hata iletisi](../../extensibility/ux-guidelines/media/0901-01_modalerrormessage.png "0901 01_ModalErrorMessage")  
  
 **Geçersiz bağlantı dizesi veritabanına kullanıcı uyarı kalıcı hata iletisi iletişim kutusu**  
  
####  <a name="BKMK_IDEStatusBar"></a>IDE durum çubuğu  
 Kullanıcıları durum çubuğu metni fark olasılığını çepeçevre bilgisayar deneyimi ve Windows platform belirli deneyimiyle hatalarla ilintilidir. Visual Studio müşteri tabanı olsa bile bilgili Windows kullanıcıları durum çubuğundaki değişiklikleri kaçırmış iki alanda deneyimli olma eğilimindedir. Bu nedenle, bilgileri başka bir yerde sunulan için durum çubuğunu en iyi bilgilendirici amaçlarla veya yedek ipucu olarak kullanılır. Bir iletişim kutusu veya bildirimleri aracı penceresinde kullanıcı hemen çözülmelidir kritik bilgilerin herhangi bir tür sağlanmalıdır.  
  
 Visual Studio durum çubuğu görüntülenecek çeşitli bilgi türleri için izin verecek şekilde tasarlanmıştır. Geri bildirim, Tasarımcısı, ilerleme çubuğu, animasyon ve istemci için bölgeler ayrılmıştır.  
  
 Geri bildirim bölge ve tasarımcı bölge her zaman görüntülenebilir. İlerleme çubuğu ve animasyon bölgeler her zaman kullanıcı bağlamı dayalı ve dinamik. Tasarımcı bölge kısa mesaj eşlik eden bir kaynaktan çekilen dize uzunluğu tarafından belirlenen statik bir genişliği vardır. Bu kod değişikliğine gerek kalmadan genişliği yeniden boyutlandırmak yerelleştirme sağlar. İngilizce için bu dizeyi genişliğini kabaca 220 pikseldir. Tasarımcı bölge normal şekilde davranır ve geri bildirim bölge kalan alanı almak.  
  
 Durum çubuğu IDE hata ayıklama modunda olduğunda gibi çeşitli IDE durum değişiklikleri iletişim kurarak visual faiz ve işlevsel değer eklemek için de renklendirilen.  
  
 ![IDE durum çubuğu renk değişiklikleri](../../extensibility/ux-guidelines/media/0901-02_idestatusbar.png "0901 02_IDEStatusBar")  
  
 **IDE durum çubuğu renkleri**  
  
####  <a name="BKMK_EmbeddedInfobar"></a>Katıştırılmış bilgi çubuğu  
 Belge penceresine veya aracı penceresinin en üstünde bir bilgi çubuğu kullanıcı durumu ya da koşul bildirmek için kullanılır. Kullanıcı bir şekilde kolayca eylemde böylece komutları da sunabilir. Bilgi çubuğu standart Kabuk denetimdir. Kendi oluşturmamaya özen gösterin, hangi hareket ve IDE içinde başkalarıyla tutarsız görünür. Bkz: [Infobars](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars) uygulama ayrıntılarını ve kullanım kılavuzu için.  
  
 ![Bilgi çubuğu katıştırılmış](../../extensibility/ux-guidelines/media/0901-03_embeddedinfobar.png "0901 03_EmbeddedInfobar")  
  
 **Bir bilgi çubuğu IDE geçmiş hata ayıklama modunda ve standart hata ayıklama modunda yaptığı gibi Düzenleyicisi aynı şekilde yanıt vermez kullanıcı uyarı belge penceresinde katıştırılmış.**  
  
####  <a name="BKMK_MouseCursorChanges"></a>Fare imleci değişiklikleri  
 Fare imlecini değiştirirken VSColor hizmetine bağlanır ve zaten imleci ile ilişkili olan renkleri kullanın. İmleç devam eden bir işlem belirten için kullanılabilir, aynı zamanda kullanıcı sürüklenen, üzerine bırakılan veya bir nesneyi seçmek için kullanılan bir hedef nerede getirildiğinde bölgeleri isabet.  
  
 Kullanıcı başka bir giriş ifade önleme, bir işlem için tüm kullanılabilir CPU süresi yalnızca ayrılmalıdır meşgul bekleme fare imleci kullanın. Çoklu iş parçacığı kullanan iyi yazılmış uygulamalar ile çoğu durumda, diğer işlemlerin engel kullanıcıların ne zaman engellenir kez seyrek olmalıdır.  
  
 Bilgi için yedek bir işaret başka bir yerde sunulduğu şekilde imleç yararlıdır göz önünde bulundurun. Bir imleç değişiklik kullanıcı çözülmesi gereken önemli olan özellikle bir şey iletmek çalışırken kullanıcıyla iletişim tek yolu olarak kullanmayın.  
  
####  <a name="BKMK_NotSysProgressIndicators"></a>İlerleme göstergesi  
 İlerleme göstergesi, tamamlanması birkaç saniye sürebilir işlemleri sırasında kullanıcı geri bildirimde için önemlidir. İlerleme göstergesi gösterilmesi yerinde (yakın başlatma noktası işlem devam ediyor), katıştırılmış durum çubuğu, kalıcı bir iletişim kutusu veya Visual Studio durum çubuğu. Yönergeleri [İlerleme göstergesi](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_ProgressIndicators) kendi kullanın ve uygulama ile ilgili.  
  
####  <a name="BKMK_VSNotificationsToolWindow"></a>Visual Studio bildirimler penceresi  
 Visual Studio bildirimler penceresini geliştiriciler lisans, ortam (Visual Studio), uzantılar ve güncelleştirmeler hakkında uyarır. Kullanıcılar tek tek bildirimleri sayabilirsiniz veya belirli türdeki bildirimlerin göz ardı etmeyi seçebilir. Yoksayılan bildirimler listesi olarak yönetilen bir **Araçlar > Seçenekler** sayfası.  
  
 Bildirimler penceresini şu anda Genişletilebilir değil.  
  
 ![Visual Studio bildirimler penceresini](../../extensibility/ux-guidelines/media/0901-06_vsnotificationswindow.png "0901 06_VSNotificationsWindow")  
  
 **Visual Studio bildirimleri araç penceresi**  
  
####  <a name="BKMK_ErrorList"></a>Hata listesi  
 Hata listesi içindeki bir bildirim hataları ve derleme sırasında oluştu ve derleme işlemi ve kullanıcının belirli bir kod hata kodu gitmek sağlayan uyarıları gösterir.  
  
 ![Hata listesi](../../extensibility/ux-guidelines/media/0901-08_errorlist.png "0901 08_ErrorList")  
  
 **Visual Studio'da hata listesi**  
  
####  <a name="BKMK_EmbeddedStatusBars"></a>Katıştırılmış durum çubukları  
 Etkin belge penceresi ve kullanıcının bağlamında ve/veya sistem yanıtları üzerinde güncelleştirme bilgileri ayarlanan istemci bölgesi içerikli IDE durum çubuğu dinamik olduğu için bilgi sürekli bir görüntüsünü korumak ya da durum çubuğunda uzun vadeli vermek zor olabilir zaman uyumsuz işlemler. Örneğin, IDE durum çubuğu birden çok çalıştırır ve/veya hemen tıklatılabilir öğesi seçimleri testi sonuçlarını bildirimleri için uygun değil. Bağlamında, kullanıcı bir seçim yapar veya bir işlem başlatır belge veya aracı penceresi gibi durum bilgileri korumak önemlidir.  
  
 ![Katıştırılmış durum çubuğu](../../extensibility/ux-guidelines/media/0901-09_embeddedstatusbar.png "0901 09_EmbeddedStatusBar")  
  
 **Visual Studio'da katıştırılmış durum çubuğu**  
  
####  <a name="BKMK_WindowsTray"></a>Windows Tepsisi bildirimleri  
 Windows görev çubuğunda bildirim alanında Windows yanındaki sistem saati. Kullanıcının ekran çözünürlüğünü değiştirme veya yazılım güncelleştirmelerini alma gibi sistem genelinde görevler için bir bağlam menüsü alabilmesi adına, bu alandaki simgeler birçok yardımcı programları ve yazılım bileşenleri sağlar.  
  
 Visual Studio bildirim hub'ı, Windows bildirim alanındaki ortamı düzeyi bildirimleri ortaya.  
  
####  <a name="BKMK_NotificationBubbles"></a>Bildirim balonları  
 Bildirim balonları bilgilendirici bir düzenleyici/Tasarımcısı'nda veya Windows bildirim alanında bir parçası olarak görünebilir. Kullanıcı bu balonları kritik olmayan bildirimler için bir avantajı olduğu daha sonra çözebilirsiniz sorunları algılar. Balonları kullanıcı hemen çözmeniz gerekir önemli bilgiler için uygun. Visual Studio'da bildirim balonları kullanıyorsanız, izleyin [bildirim balonları için Windows Masaüstü Kılavuzu](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742472\(v=vs.85\).aspx).  
  
 ![Bildirim Kabarcık](../../extensibility/ux-guidelines/media/0901-07_notificationbubbles.png "0901 07_NotificationBubbles")  
  
 **Visual Studio için kullanılan Windows bildirim alanında bildirim Kabarcık**  
  
##  <a name="BKMK_ProgressIndicators"></a>İlerleme göstergesi  
  
### <a name="overview"></a>Genel Bakış  
 İlerleme göstergesi bildirim sistemi kullanıcı geri bildirimde için önemli bir parçasıdır. İşlemler ve işlemleri tamamladığınızda, bunlar kullanıcı söyleyin. İlerleme çubukları, dönen imleçler ve animasyonlu simgeleri tanıdık göstergesi türleri içerir. Bir İlerleme göstergesi yerleşimini ve türünü ne raporlanan dahil olmak üzere, bağlam ve ne kadar süre işlem veya işlem tamamlanması için gereken bağlıdır.  
  
#### <a name="factors"></a>Etkenler  
 Hangi göstergesi uygun olduğunu belirlemek için aşağıdaki etmenleri belirlemeniz gerekir.  
  
1.  **Zamanlama:** süre işlemi sürer  
  
2.  **Şekil:** işlemi (kilitler işlem tamamlanana kadar UI) ortamına kalıcı olup  
  
3.  **Kalıcı/geçici:** ilerleme nihai sonucu olup olmadığını daha sonraki bir zamanda bildirilen ve/veya görüntülenebilir olması gerekiyor  
  
4.  **Belirli/belirsiz:** işlemi bitiş saati ve ilerleme hesaplanabilir  
  
5.  **Grafik/Textual konumu:** ilerleme veya işlem bir ileti veya ağaç denetimi gibi belirli bir denetim gövdesinde yakalanan satır içi olup  
  
6.  **Yakınlık:** olup ilerleme ilgili olduğu UI yakın olması gerekir. (Örneğin, uzakta olabilir, durum çubuğunda olabilir veya bu işlemi başlatılan düğmesi olmak zorunda?)  
  
#### <a name="determinate-progress"></a>Belirli ilerleme durumu  
  
|İlerleme türü|Ne zaman ve nasıl kullanılacağını|Notlar|  
|-------------------|-------------------------|-----------|  
|İlerleme çubuğu (belirli)|Beklenen süresini > 5 saniye.<br /><br /> İşlem ayrıntıları metinsel açıklaması içerebilir.|**Verme** animasyonda metin ekleme.|  
|Bilgi Çubuğu|Bağlamsal kullanıcı Arabirimi ile ilişkili ileti. Bkz: [Infobars](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars).<br /><br /> İşlem ayrıntıları metinsel açıklaması içerebilir.|**Verme** birden çok işlemlerini göstermek gerektiğinde birden çok infobars kullanın. Yığılmış ilerleme çubukları kullanın.|  
|Çıktı Penceresi|Geçici bildirim: kullanıcı uygulama düzeyinde işlem istediğiniz **gözden** ayrıntılarını tamamlandıktan sonra.|**Verme** kullanıcı verilerini daha sonra başvurmak üzere gerekecekse kullanın.|  
|Günlük dosyası|Önemli olduğunda durumlarda intransient bildirim eşleştirilmiş **kaydetmek** tamamlandıktan sonra ayrıntıları.||  
|Durum çubuğu|Geçici bildirim: uygulama düzeyinde işlemi kullanıcının olacak **gerek** ayrıntılarını tamamlandıktan sonra.<br /><br /> Katıştırılmış ilerleme çubuğu içerir.<br /><br /> İşlem ayrıntıları metinsel açıklaması içerebilir.||  
  
#### <a name="indeterminate-progress"></a>Belirsiz ilerleme durumu  
  
|İlerleme türü|Ne zaman ve nasıl kullanılacağını|Notlar|  
|-------------------|-------------------------|-----------|  
|İlerleme çubuğu (belirsiz)|Beklenen süresini > 5 saniye.<br /><br /> İşlem ayrıntıları metinsel açıklaması içerebilir.|**Verme** animasyonda metin ekleme.|  
|Karıncaların (animasyonlu yatay nokta)|Sunucuya gidiş dönüş.<br /><br /> NEAR noktası bağlamının üst kapsayıcı üstte yerleştirilir.|**Verme** tüm kapsayıcı tarafından üst öğe değil kullanın.|  
|Değer değiştirici (ilerleme halka)|Bağlamsal kullanıcı Arabirimi ile veya alanı önemli bir unsur olduğu ilişkili işlemi.<br /><br /> İşlem ayrıntıları metinsel açıklaması içerebilir.||  
|Bilgi Çubuğu|Bağlamsal kullanıcı Arabirimi ile ilişkili ileti. Bkz: [Infobars](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars).|**Verme** birden çok işlemlerini göstermek gerektiğinde birden çok infobars kullanın. Yığılmış ilerleme çubukları kullanın.|  
|Çıktı Penceresi|Geçici bildirim:, kullanıcı uygulama düzeyinde işlem istediğiniz **gözden** ayrıntılarını tamamlandıktan sonra.|**Verme** oturumlarında kalıcı hale getirmek için gereken bilgileri belirtmek için kullanın.|  
|Günlük dosyası|Önemli olduğunda durumlarda intransient bildirim eşleştirilmiş **kaydetmek** tamamlandıktan sonra ayrıntıları.||  
|Durum çubuğu|Geçici bildirim: uygulama düzeyinde işlemi kullanıcının olacak **gerek** ayrıntılarını tamamlandıktan sonra.<br /><br /> Katıştırılmış ilerleme çubuğu içerir.<br /><br /> İşlem ayrıntıları metinsel açıklaması içerebilir.||  
  
### <a name="progress-indicator-types"></a>İlerleme göstergesi türleri  
  
#### <a name="progress-bars"></a>İlerleme çubukları  
  
##### <a name="indeterminate"></a>Belirsiz  
 ![Belirsiz ilerleme çubuğu](../../extensibility/ux-guidelines/media/0901-04_indeterminate.png "0901 04_Indeterminate")  
  
 **Belirsiz ilerleme çubuğu**  
  
 Bir işlem genel ilerlemesi "Belirsiz" anlamına gelir veya işlem belirlenemiyor. Belirsiz ilerleme çubukları sınırsız süreyi gerektiren veya bilinmeyen bir nesne sayısı erişim işlemleri için kullanın. Bir metinsel olanlar eşlik için kullanın. Zaman aşımları sınırları zamana dayalı işlemlerine izin vermek için kullanın. Belirsiz ilerleme çubukları animasyonları ilerleme yapılıyor, ancak başka hiçbir bilgi sağlamak göstermek için kullanın. Doğruluk tek başına yalnızca olası eksikliği dayalı bir belirsiz ilerleme çubuğu seçmeyin.  
  
##### <a name="determinate"></a>Belirli  
 ![Belirli bir ilerleme çubuğu](../../extensibility/ux-guidelines/media/0901-05_determinate.png "0901 05_Determinate")  
  
 **Belirli bir ilerleme çubuğu**  
  
 Bir işlem veya işlem bir sınırlanmış süreyi gerektirdiği bu süreyi doğru şekilde tahmin edilemez olsa bile "Belirli" anlamına gelir. Açıkça tamamlama gösterir. Bir ilerleme çubuğu işlem tamamlanmadan sürece yüzde 100'e gidin izin vermeyin. Belirli bir ilerleme çubuğu animasyon % 100'e 0'dan soldan sağa taşır.  
  
 Hiçbir zaman bir işlem sırasında geri İlerleme göstergesi taşıyın. Çubuğu işlemi başladığında, sürekli olarak ilerler ve sona erdiğinde % 100 ulaşması gerekir. İlerleme çubuğu kullanıcıya tüm işlemi, kaç tane adımları dahil bağımsız olarak gereken süreyi hakkında bir fikir vermek için noktasıdır.  
  
##### <a name="concurrent-reporting-stacked-progress-bars"></a>Eşzamanlı (Yığın ilerleme çubukları) raporlama  
 Bir işlem - uzun zaman alacaksa belki de birkaç dakika - sonra iki ilerleme çubukları kullanılabilir, biri bir işlem için genel ilerleme durumunu ve geçerli adımı ilerleyişini için başka bir gösterir. Kurulum programı çok sayıda dosya kopyalama, örneğin, ardından bir ilerleme çubuğu sürecinin tamamı ikinci bir yüzde geçerli dosyanın belirtebilir ya da dizin kopyalanan gereken süreyi belirtmek için kullanılabilir. Beşten fazla eşzamanlı işlem veya yığın ilerleme çubukları kullanarak işlemleri bildirmez. Beşten fazla eşzamanlı işlem veya rapor işlemler varsa, kalıcı bir iletişim kutusu bir iptal düğmesi ve rapor ilerleme ayrıntıları için çıkış penceresini kullanın.  
  
##### <a name="textual-descriptions"></a>Metinsel açıklamaları  
 Neler olduğunu eşlik metinsel ve tahmini tamamlanma süresi kullanın. Bir işlem ne kadar sürer belirlemek mümkün ise, geri bildirimde için daha iyi bir seçimdir bir ilerleme çubuğu yerine animasyonlu simge olabilir.  
  
 Visual Studio durum çubuğundaki Visual Studio'ya tümleşik herhangi bir ürün tarafından kullanılan bir standart ilerleme çubuğu sağlar. İlerleme çubuğu animasyonlu ederken neler olduğunu, metinsel açıklamaları için durum çubuğu metni güncelleştirilebilir.  
  
#### <a name="other-progress-indicators"></a>Diğer İlerleme göstergesi  
  
##### <a name="ants-animated-horizontal-dots"></a>Karıncaların (animasyonlu yatay nokta)  
 ![İlerleme karıncaların](../../extensibility/ux-guidelines/media/0903-01_ants.png "0903 01_Ants")  
  
 "Karıncaların," animasyonlu yatay noktalar, bir belirsiz gidiş dönüş sunucu işlemi için görsel bir başvuru sağlar.  
  
##### <a name="spinner-progress-ring"></a>Değer değiştirici (ilerleme halka)  
 ![Devam eden değer değiştirici](../../extensibility/ux-guidelines/media/0903-02_spinner.png "0903 02_Spinner")  
  
 Değer değiştirici (olarak da bilinen bir "ilerleme halka"), öncelikle bağlamsal UI ile ilgili olarak kullanılan bir belirsiz ilerleme göstergesidir. Bir metinsel kategori başlığını, ileti veya denetim gibi ilgili içeriğini yakın bir değer değiştiricinin görüntüler.  
  
##### <a name="cursor-feedback"></a>İmleç geri bildirimi  
 2-7 saniye arasında sürebilir işlemleri için imleci geri bildirim sağlayın. Genellikle, bu işletim sistemi tarafından sağlanan bekleme imleç kullanılması anlamına gelir. Yönergeler için MSDN makalesine bakın [Cursors.Wait özelliği](https://msdn.microsoft.com/en-us/library/system.windows.input.cursors.wait\(v=vs.110\).aspx).  
  
#### <a name="progress-indicator-locations"></a>İlerleme göstergesi konumları  
  
##### <a name="status-bar"></a>Durum çubuğu  
 Durum çubuğu, uygulama kullanıcının iş kesintiye uğratmadan kullanıcıya iletileri ve yararlı bilgileri görüntülemek için bir yer sağlar. Genellikle bir penceresinin alt kısmında görüntülenen, ilerleme durumunu ilerleme ölçü hakkında bir ileti bir ilerleme çubuğu göstergesi ile birlikte içeren bir araç ipucu bölmesini olacaktır.  
  
 ![İlerleme çubuğu ile durum çubuğu](../../extensibility/ux-guidelines/media/0903-03_statusbarprogressbar.png "0903 03_StatusBarProgressBar")  
  
 **İlerleme çubuğu ile durum çubuğu**  
  
 ![Mesajlaşma ile durum çubuğu](../../extensibility/ux-guidelines/media/0903-04_statusbarmessage.png "0903 04_StatusBarMessage")  
  
 **Metinsel ile durum çubuğu**  
  
##### <a name="infobar"></a>Bilgi Çubuğu  
 Durum çubuğu, Bilgi Çubuğu'nu benzer bağlamsal bildirim ve mesajlaşma, hangi da ilerleme çubuğu veya değer değiştirici gibi belirsiz İlerleme göstergesi ile eşleştirilmesi sağlar. Bilgi Çubuğu'nu ayrıntılı düzey ilerleme durumunu veya belirli İlerleme göstergesi sağlamalıdır değil. Bkz: [Infobars](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md#BKMK_Infobars).  
  
 ![İlerleme çubuğu ve mesajlaşma ile bilgi çubuğu](../../extensibility/ux-guidelines/media/0903-05_infobar.png "0903 05_InfoBar")  
  
 **İlerleme çubuğu ve metinsel bilgi çubuğu**  
  
 ![Bir pencere içinde bilgi çubuğu](../../extensibility/ux-guidelines/media/0903-06_infobarinwindow.png "0903 06_InfoBarInWindow")  
  
 **Kod Analizi penceresi içinde bilgi çubuğu**  
  
##### <a name="inline"></a>Satır içi  
 Satır içi İlerleme göstergesi ilerleme yükleyicisi türleri temsil edilebilir. İlerleme göstergesi iletiyle genellikle eşleştirilmiş, ancak bu zorunlu değildir.  
  
 ![Satır içi ilerleme değiştiricisi](../../extensibility/ux-guidelines/media/0903-07_inlinespinner.png "0903 07_InlineSpinner")  
  
 **Değer değiştirici metinsel ile birlikte**  
  
 ![Satır içi ilerleme çubukları Yığılmış](../../extensibility/ux-guidelines/media/0903-08_inlinestackedprogress.png "0903 08_InlineStackedProgress")  
  
 **Belirli Yığılmış ilerleme çubukları**  
  
 ![Satır içi ilerleme Mesajlaşma](../../extensibility/ux-guidelines/media/0903-09_inlinetext.png "0903 09_InlineText")  
  
 **Sunucu Gezgini satır içi metni: yenileniyor...**  
  
##### <a name="tool-windows"></a>Araç pencereleri  
 Genel İlerleme göstergesi doğrudan araç çubuğunun altında konumlandırılmış bir belirsiz ilerleme çubuğu olarak temsil edilir.  
  
 ![Genel belirsiz ilerleme çubuğu](../../extensibility/ux-guidelines/media/0903-23_globalindeterminate.png "0903 23_GlobalIndeterminate")  
  
 **Takım Gezgini genel belirsiz ilerleme çubuğu**  
  
##### <a name="dialogs"></a>İletişim kutuları  
 İletişim kutuları ilerleme yükleyici türlerinden herhangi birini içerebilir. İlerleme göstergesi Mesajlaşma ile eşleştirilmiş yanı sıra birden çok düzeyi ayrıntılı temsil eder ve alt işlemleri için İlerleme göstergesi ile birlikte.  
  
 ![Birden çok İlerleme göstergesi türleriyle iletişim](../../extensibility/ux-guidelines/media/0903-11_dialog.png "0903 11_Dialog")  
  
 **Visual Studio iletişim eşzamanlı işlemleri ve birden çok İlerleme göstergesi türü**  
  
 ![İlerleme Yükleyicisi ve mesajlaşma ile iletişim](../../extensibility/ux-guidelines/media/0903-12_dialog2.png "0903 12_Dialog2")  
  
 **İlerleme Yükleyicisi ve satır içi komut verme Mesajlaşma ile Visual Studio iletişim**  
  
##### <a name="document-well"></a>Belge iyi  
 Belge denetimleri ile birlikte birden çok ilerleme yükleyici türü de görüntüleyebilirsiniz.  
  
 ![Belgede iyi Mesajlaşma ilerleme](../../extensibility/ux-guidelines/media/0903-13_documentwell.png "0903 13_DocumentWell")  
  
 **Araç çubuğunun altında belirsiz ilerleme çubuğu**  
  
##### <a name="output-window"></a>Çıktı Penceresi  
 Çıktı penceresi, işlem ilerleme ve satır içi metinsel Mesajlaşma aracılığıyla devam eden ilerleme durumunu işlemek için uygundur. Durum çubuğu hiçbir çıktı penceresi ilerleme durumu raporlama ile birlikte kullanmanız gerekir.  
  
 ![Çıktı penceresinde Mesajlaşma ilerleme](../../extensibility/ux-guidelines/media/0903-14_outputwindow.png "0903 14_OutputWindow")  
  
 **Pencere çıkış ile devam eden işlem durumunu ve mesajlaşma bekleyin**  
  
##  <a name="BKMK_Infobars"></a>Infobars  
  
### <a name="overview"></a>Genel Bakış  
 Infobars dikkatini kendi noktası yakın bir göstergesi kullanıcıya vermek ve paylaşılan bir bilgi çubuğu denetimini kullanarak görsel görünümünü ve etkileşim tutarlılık sağlar.  
  
 ![Bilgi Çubuğu](../../extensibility/ux-guidelines/media/0904-01_infobar.png "0904 01_Infobar")  
  
 **Visual Studio'da Infobars**  
  
#### <a name="appropriate-uses-for-an-infobar"></a>Bir bilgi çubuğu uygun kullanımları  
  
-   Engelleyici olmayan ama önemli ileti geçerli bağlamla ilgili kullanıcıya vermek için  
  
-   Kullanıcı arabirimini belirli bir durumu veya geçmiş hata ayıklama gibi bazı etkileşim etkileri izleme koşulu olduğunu belirtmek için  
  
-   Sistem, bir uzantı performans sorunları olduğunda neden gibi sorunlar algıladı kullanıcıya bildirmek için  
  
-   Kullanıcı kolayca Düzenleyicisi'ni bir dosya sekmeleri ve boşlukları karma algıladığında gibi eyleme için bir yol sağlamak için  
  
##### <a name="do"></a>Yapın:  
  
-   Bilgi çubuğu ileti metni, kısa ve noktasına tutun.  
  
-   Bağlantılar ve düğmeler üzerindeki metin kısa tutun.  
  
-   Kullanıcılara sağlamak "eylem" seçenekleri yalnızca gerekli eylemleri gösteren az olduğundan emin olun.  
  
##### <a name="dont"></a>Yapma:  
  
-   Araç çubuğunda yerleştirilmelidir standart komutları sunmak için bir bilgi çubuğu kullanın.  
  
-   Kalıcı iletişim yerine bir bilgi çubuğu kullanın.  
  
-   Penceresi dışında kayan bir ileti oluşturun.  
  
-   Aynı penceresi içinde çeşitli konumlarda birden çok infobars kullanın.  
  
#### <a name="can-multiple-infobars-show-at-the-same-time"></a>Aynı anda birden çok infobars gösterebilir?  
 Evet, aynı anda birden çok infobars gösterebilir. Bunlar, ilk hizmet önce gelen sırayla gösterme üst ve ek infobars aşağıdaki gösteren ilk bilgi çubuğu ile görüntülenir.  
  
 Kullanıcı aynı anda en fazla üç infobars görür daha fazla infobars varsa, bilgi çubuğu bölge kaydırılabilir hale geleceği sonra.  
  
### <a name="creating-an-infobar"></a>Bir bilgi çubuğu oluşturma  
 Bilgi çubuğu soldan sağa dört bölümü vardır:  
  
-   **Simge:** burada herhangi bir simgesini eklemek budur bir uyarı simgesi gibi bilgi çubuğu için görüntülemek istediğiniz.  
  
-   **Metin:** , senaryo/durum kullanıcı açıklamak için metin, metin içindeki bağlantılarıyla birlikte gerekirse ekleyebilir. Metin kısa tutmayı unutmayın.  
  
-   **Eylemler:** bağlantılar ve düğmeler kullanıcı, Bilgi Çubuğu'nda gerçekleştirebileceğiniz eylemler için bu bölümü içermelidir.  
  
-   **Kapat düğmesi:** sağındaki son Kısım Kapat düğmesi olabilir.  
  
#### <a name="creating-a-standard-infobar-in-managed-code"></a>Yönetilen kodda standart bir bilgi çubuğu oluşturma  
 InfoBarModel sınıfı, bir bilgi çubuğu için bir veri kaynağı oluşturmak için kullanılabilir. Bu dört oluşturucular birini kullanın:  
  
```  
public InfoBarModel(IEnumerable<IVsInfoBarTextSpan> textSpans, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
  
```  
  
```  
public InfoBarModel(string text, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
  
```  
  
```  
public InfoBarModel(IEnumerable<IVsInfoBarTextSpan> textSpans, IEnumerable<IVsInfoBarActionItem> actionItems, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
  
```  
  
```  
public InfoBarModel(string text, IEnumerable<IVsInfoBarActionItem> actionItems, ImageMoniker image = default(ImageMoniker), bool isCloseButtonVisible = true);  
```  
  
 Aşağıda bir InfoBarModel bazı metni içeren bir köprü, eylem düğmesi ve bir simge oluşturur bir örnek verilmiştir.  
  
 ![Bilgi çubuğu köprü ile](../../extensibility/ux-guidelines/media/0904-02_infobarhyperlink.png "0904 02_InfobarHyperlink")  
  
```  
var infoBar = new InfoBarModel(  
    textSpans: new[]  
    {  
        new InfoBarTextSpan("This is a "),  
        new InfoBarHyperlink("hyperlink"),  
        new InfoBarTextSpan(" InfoBar.")  
    },  
    actionItems: new[]  
    {  
        new InfoBarButton("Click Me")  
    },  
    image: KnownMonikers.StatusInformation,  
    isCloseButtonVisible: true);  
  
```  
  
#### <a name="creating-a-standard-infobar-in-native-code"></a>Yerel kodda standart bir bilgi çubuğu oluşturma  
 Yerel koddan bir bilgi çubuğu sağlamak amacıyla IVsInfoBar arabirimini uygular.  
  
```  
public interface IVsInfoBar  
{  
    IVsInfoBarActionItemCollection ActionItems { get; }  
    ImageMoniker Image { get; }  
    bool IsCloseButtonVisible { get; }  
    IVsInfoBarTextSpanCollection TextSpans { get; }  
}  
  
```  
  
#### <a name="getting-an-infobar-uielement-from-an-infobar"></a>Bir bilgi çubuğu bir bilgi çubuğu UIElement alma  
 UIElement kullanıcı Arabiriminde gösterilecek için açık olmalıdır veri modelleri InfoBarModel veya IVsInfoBar uygulama var. UIElement SVsInfoBarUIFactory/IVsInfoBarUIFactory hizmetiyle alınabilir.  
  
```  
private bool TryCreateInfoBarUI(IVsInfoBar infoBar, out IVsInfoBarUIElement uiElement)  
{  
    IVsInfoBarUIFactory infoBarUIFactory = serviceProvider.GetService(typeof(SVsInfoBarUIFactory)) as IVsInfoBarUIFactory;  
    if (infoBarUIFactory == null)  
    {  
        uiElement = null;  
        return false;  
    }  
  
    uiElement = infoBarUIFactory.CreateInfoBar(infoBar);  
    return uiElement != null;  
}  
```  
  
### <a name="placement"></a>Yerleştirme  
 Bir veya daha fazla aşağıdaki konumlardan içinde Infobars gösterilebilir:  
  
-   Araç pencereleri  
  
-   İçinde bir belge sekmesi  
  
> [!IMPORTANT]
>  Genel bağlam hakkında bir ileti vermek için bir bilgi çubuğu konumlandırmak mümkündür. Bu araç çubukları ve belgenin iyi arasında görüntülenir. "Atlamak ve jerk" ile ilgili sorunlara neden olduğu için bu önerilmez IDE ve sürece kaçınılmalıdır kesinlikle gerekli ve uygun.  
  
#### <a name="placing-an-infobar-in-a-toolwindowpane"></a>Bir ToolWindowPane bir bilgi çubuğu yerleştirme  
 ToolWindowPane.AddInfoBar(IVsInfoBar) yöntemi, bir araç penceresi için bir bilgi çubuğu eklemek için kullanılabilir. Bu API (varsayılan uygulama hangi InfoBarModel'dir) bir IVsInfoBar ya da ekleyebilir veya bir IVsUIElement.  
  
#### <a name="placing-an-infobar-in-a-document-or-non-toolwindowpane"></a>Bir belge veya ToolWindowPane olmayan bir bilgi çubuğu yerleştirme  
 Bir bilgi çubuğu herhangi IVsWindowFrame yerleştirilecek VSFPROPID_InfoBarHost özelliğini kullanarak IVsInfoBarHost için çerçevesi Al ve UIElement bilgi çubuğu ekleyin.  
  
```  
private void AddInfoBar(IVsWindowFrame frame, IVsUIElement uiElement)  
{  
    IVsInfoBarHost infoBarHost;  
    if (TryGetInfoBarHost(frame, out infoBarHost))  
    {  
        infoBarHost.AddInfoBar(uiElement);  
    }  
}  
private bool TryGetInfoBarHost(IVsWindowFrame frame, out IVsInfoBarHost infoBarHost)  
{  
    object infoBarHostObj;  
    if (ErrorHandler.Failed(frame.GetProperty((int)__VSFPROPID7.VSFPROPID_InfoBarHost, out infoBarHostObj)))  
    {  
        infoBarHost = null;  
        return false;  
    }  
  
    infoBarHost = infoBarHostObj as IVsInfoBarHost;  
    return infoBarHost != null;  
}  
  
```  
  
#### <a name="placing-an-infobar-in-the-main-window"></a>Ana pencerede bir bilgi çubuğu yerleştirme  
 Ana pencerede bir bilgi çubuğu yerleştirmek için ana pencerenin IVsInfoBarHost almak için IVsShell hizmet VSSPROPID_MainWindowInfoBarHost kullanın ve UIElement bilgi çubuğu ekleyin.  
  
### <a name="will-i-know-when-the-user-takes-action-in-my-infobar"></a>Bilgi Çubuğu'nda kullanıcı eylemde bulunduğunda bilebilirim?  
 Evet, biz her olay eylem bilgi çubuğu yazarın döndürür. Bilgi Çubuğu'nda Kullanıcı Seçimi göre IDE'de eyleme geçmek için bilgi çubuğu Yazar kadar sonra olur. Infobars, Kapat düğmesini tıklandığını ana bilgisayardan otomatik olarak kaldırılacak, ancak diğer infobars sonra kaldırılması gerek kapatırsanız ek iş gereklidir. Telemetri de bağımsız olarak her bilgi çubuğu ile oturum açmış olmanız gerekir.  
  
#### <a name="receiving-infobar-events-in-a-toolwindowpane"></a>Bir ToolWindowPane bilgi çubuğu olayları alma  
 ToolWindowPane infobars için iki olay vardır. Bir Bilgi Çubuğu'nda ToolWindowPane kapatıldığında InfoBarClosed olay tetiklenir. Köprü ya da bilgi çubuğu içindeki düğmesine tıklandığında InfoBarActionItemClicked olay tetiklenir.  
  
#### <a name="receiving-infobar-events-directly-from-the-uielement"></a>UIElement doğrudan alıcı bilgi çubuğu olayları  
 IVsInfoBarUIElement.Advise doğrudan bir bilgi çubuğu 's UIElement olaylara abone olmak için kullanılabilir. IVsInfoBarUIEvents uygulama Kapat almak ve tıklama olayları yazar izin verir.  
  
```  
public interface IVsInfoBarUIEvents  
{  
    void OnActionItemClicked(IVsInfoBarUIElement infoBarUIElement, IVsInfoBarActionItem actionItem);  
    void OnClosed(IVsInfoBarUIElement infoBarUIElement);  
}  
  
```  
  
##  <a name="BKMK_ErrorValidation"></a>Hata doğrulama  
 Kullanıcı kabul edilebilir, gerekli bir alan zaman atlanır gibi veya yanlış biçimde veri girildiğinde değil bilgi girdiğinde, kullanım denetim doğrulama ya da geribildirim engelleme açılan hata iletişim kutusu kullanmak yerine denetimi yakın için iyidir.  
  
### <a name="field-validation"></a>Alan doğrulama  
 Form ve alan doğrulama üç bileşenlerden oluşur: bir denetim, simge ve araç ipucu. Denetimleri çeşitli türleri bu kullanabilirsiniz, ancak bir metin kutusu örnek olarak kullanılır.  
  
 ![Alan doğrulama &#40; boş &#41; ] (../../extensibility/ux-guidelines/media/0905-01_fieldvalidation.png "0905 01_FieldValidation")  
  
 Alan gerekiyorsa, olmamalıdır metin belirten Filigran  **\<gerekli >** ve alan arka plan açık olmalıdır sarı (VSColor: `Environment.ControlEditRequiredBackground`) ve ön gri olmalıdır (VSColor: `Environment.ControlEditRequiredHintText`):  
  
 ![Alan doğrulama "Gerekli" etiketi ile](../../extensibility/ux-guidelines/media/0905-02_fieldvalidationrequired.png "0905 02_FieldValidationRequired")  
  
 Program denetimi bir durumda olduğunu anlayabilirsiniz *girilen geçersiz içerik* odak başka bir denetime zaman taşınır veya kullanıcı bir [Tamam] yürütme düğmesine tıkladığında ya da kullanıcı belgeyi veya formu zaman kaydeder.  
  
 Geçersiz içerik durumu belirlendiğinde denetimi içinde ya da yalnızca yanında bir simge görüntülenir. Hatayı açıklayan bir araç ipucu simgesi veya denetim gidildiğinde görüntülenmesi gerekir. Ayrıca, 1 piksel kenarlık geçersiz duruma oluşturma denetim görünmelidir.  
  
 ![Alan doğrulama düzeni belirtimleri](../../extensibility/ux-guidelines/media/0905-03_layoutspecs.png "0905 03_LayoutSpecs")  
  
 **Alan doğrulama düzeni belirtimleri**  
  
#### <a name="acceptable-variations-for-icon-location"></a>Simge konumu için kabul edilebilir değişimler  
 Kullanıcıların doğrulama hataları hakkında bilgi sahibi olmak gerekir sayısız özel durumlar vardır. Denetim türü ve yapılandırması UI göz önünde bulundurularak, durumunuza uygun simgeyi yerleştirme seçin.  
  
 ![Simge konumu için kabul edilebilir konumlarını](../../extensibility/ux-guidelines/media/0905-04_iconlocation.png "0905 04_IconLocation")  
  
 **Alan doğrulama simge konumları için kabul edilebilir değişimler**  
  
#### <a name="validation-requiring-a-round-trip-to-a-server-or-network-connection"></a>Bir sunucu veya ağ bağlantısı için gidiş dönüş gerektiren doğrulama  
 Bazı durumlarda, sunucuya gidiş dönüş içeriği doğrulamak için gerekli olan ve doğrulandı, kullanıcı ilerleme ve hata durumları göstermek önemli. Bu durumda ve önerilen UI örneğini aşağıdaki şekilde gösterir.  
  
 ![Sunucuya gidiş dönüş içeren doğrulama](../../extensibility/ux-guidelines/media/0905-05_roundtrip.png "0905 05_RoundTrip")  
  
 **Sunucuya gidiş dönüş içeren doğrulama**  
  
 "Doğrulanıyor..." ve "Yeniden dene" metin karşılamak üzere yeterli kullanılabilir alan denetimi sağındaki sağlanmalıdır unutmayın.  
  
#### <a name="in-place-warning-text"></a>Yerinde uyarı metni  
 Oda hata durumunda denetimi yakın hata iletisini almaya kullanılabilir olduğunda, bu tek başına araç ipucunu kullanmayı tercih edilir.  
  
 ![İçinde &#45; Yerleştir uyarı](../../extensibility/ux-guidelines/media/0905-06_inplacewarning.png "0905 06_InPlaceWarning")  
  
 **Yerinde uyarı metni**  
  
#### <a name="watermarks"></a>Filigranlar  
 Bazen bir tüm denetim veya penceresi bir hata durumuna sahip. Bu durumda, filigran hata belirtmek için kullanın.  
  
 ![Filigran](../../extensibility/ux-guidelines/media/0905-07_watermark.png "0905 07_Watermark")  
  
 **Filigran alan doğrulama**