---
title: Visual Studio için UX Essentials | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: a793cf7a-f230-43ce-88d0-fa5d6f1aa9c7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 52081c5a7f88a39ab25cf868164bd0258dd37885
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ux-essentials-for-visual-studio"></a>Visual Studio için UX temelleri
## <a name="best-practices"></a>Önerilen uygulamalar  
  
### <a name="1-be-consistent-within-the-visual-studio-environment"></a>1. Visual Studio ortamında tutarlı olması.  
  
-   Varolan izleyin [etkileşim desenleri](interaction-patterns-for-visual-studio.md) kabuktan.  
  
-   Özellikleri kabuğun visual dili ile tutarlı olacak şekilde tasarlayın ve [craftsmanship gereksinimleri](evaluation-tools-for-visual-studio.md).  
  
-   Bunlar varken paylaşılan komutları ve denetimleri kullanın.  
  
-   Visual Studio hiyerarşi ve nasıl bağlam oluşturur ve kullanıcı arabirimini sürücüleri anlayın.  
  
### <a name="2-use-the-environment-service-for-fonts-and-colors"></a>2. Yazı tipleri ve renkler için ortam hizmeti kullanın.  
  
-   UI geçerli saygı [ortam yazı tipi](fonts-and-formatting-for-visual-studio.md) özelleştirme seçenekleri iletişim kutusu yazı tipleri ve renkler sayfasında için sunulan sürece ayarlama.  
  
-   Kullanıcı Arabirimi öğeleri kullanmalıdır [VSColor hizmet](colors-and-styling-for-visual-studio.md), ortam belirteçleri veya özelliğe özgü belirteçleri paylaşılan kullanma.  
  
### <a name="3-make-all-imagery-consistent-with-the-new-vs-style"></a>3. Tüm görüntülerin yeni VS stili tutarlı olmasını sağla.  
  
-   Simgeler, karakterlerin ve diğer grafik için Visual Studio tasarım ilkeleri izleyin.  
  
-   Metin grafik öğeleri yerleştirmeyin.  
  
### <a name="4-design-from-a-user-centric-perspective"></a>4. Kullanıcı merkezli bir açısından tasarlayın.  
  
-   Görev akışı içindeki tek tek özellikleri önce oluşturun.  
  
-   Kullanıcılarınız ile ilgili bilgi sahibi olmanız ve bu bilgi, spec açık olun.  
  
-   Kullanıcı arabirimini gözden geçirirken ayrıntıları yanı sıra eksiksiz deneyimi değerlendirin.  
  
-   UI işlevsel ve yerel ayar veya dil bağımsız olarak çekici kalmayacak şekilde tasarlayın.  
  
## <a name="screen-resolution"></a>Ekran çözünürlüğü  
  
### <a name="minimum-resolution"></a>En düşük çözünürlük  
 - Visual Studio Dev14 için en düşük çözünürlük **1280 x 720**. Bu, anlamına gelir *olası* bir en iyi kullanıcı deneyimini olmayabilir ancak Visual Studio'nun bu çözünürlükte kullanmak için. Tüm yönleriyle 1280 x 720 düşük çözünürlüklerde kullanılabilir olacağını garanti yoktur.  
  
 - Visual Studio için hedef çözünürlüğü **1366 x 768**. Hangi etmeyeceğiz en düşük çözünürlüğü budur bir *iyi* kullanıcı deneyimi.

 - İlk iletişim yükseklik olmalıdır **700 pikselden küçük**, en düşük çözünürlük 96 dpi IDE çerçevenin içinde sığmasını sağlayın.
  
### <a name="high-density-displays"></a>Yüksek yoğunlukta görüntüler  
 Visual Studio kullanıcı Arabiriminde iyi kutudan çıktığında Windows destekler Etkenler ölçeklendirme tüm DPI iş gerekir: % 150, %200 ve % 250.  
  
## <a name="anti-patterns"></a>Koruma desenleri  
 Visual Studio kullanıcı Arabirimi bizim kılavuzları ve en iyi uygulamaları izleyin birçok örnekleri içerir. Tutarlı olacak şekilde bir çaba içinde ürün UI tasarım desenleri ne bunlar oluşturmakta olduğunuz için benzer geliştiriciler genellikle alın. Bu kullanıcı etkileşimi ve görsel tasarım tutarlılık sürücü bize yardımcı olur, bazen bizim yönergeleri Zamanlama kısıtlamaları nedeniyle karşılamıyor veya önceliği kusurlu birkaç ayrıntıları özelliklerle gönderdiğimiz, iyi bir yaklaşım olsa da. Visual Studio ortamında bozuk ya da tutarsız UI yayılmaya çünkü bu durumda, bu "koruma desenleri" birini kopyalayıp takıma istiyoruz değil.  
  
### <a name="required-fieldssettings-shown-in-error-state-by-default"></a>Hata durumunda varsayılan olarak gösterilen gerekli alanları/ayarları  
  
#### <a name="feature-team-goals"></a>Özellik takım hedefleri  
  
-   Yapılandırılması gereken bir öğe eklediğiniz kullanıcıları uyarın.  
  
-   Giriş gereksinim alanlarına kullanıcının dikkat çekmek.  
  
#### <a name="anti-pattern-solution"></a>Koruma düzeni çözümü  
 Hemen kullanıcı bir işlemi başlattığı hemen sonra ve görev tamamlanmadan önce kritik dur simgeleri yapılandırmaya ihtiyaç alanları yanındaki yerleştirin.  
  
#### <a name="example-manifest-designer-declarations"></a>Örnek: Bildirim tasarımcısını bildirimleri  
 Bir bildirim listesine hemen ekleme kullanıcı gerekli özelliklerini ayarlar kadar devam eden bir hata durumunda yerleştirir.  
  
 Bu durumda, yoktur ek bir sorun için uyarı kullanılan simge içerdiğinden bir "&times;" simgesini ortak Kaldır simgesi kullanılamaz. Sonuç olarak, kullanıcı arabirimini Kaldır düğmesi, bir daha clunky denetimi kullanır.  
  
 ![Kullanıcı Arabirimi, varsayılan olarak bir hata durumunda yerleştirme Visual Studio koruma Düzen yöneliktir. ] (../../extensibility/ux-guidelines/media/manifestdesignererrordeclarationsanti-pattern.png "ManifestDesignererrordeclarationsanti düzeni")<br />Kullanıcı Arabirimi, varsayılan olarak bir hata durumunda yerleştirme Visual Studio koruma Düzen yöneliktir.
  
#### <a name="alternatives"></a>Alternatifleri  
 Çok daha iyi bir çözüm bu sorunu olacaktır:  
  
-   Kullanıcı bildirimi uyarmadan ekleyin ve üzerinde öğenin özelliklerini ayarlamak hemen taşıyın.  
  
-   Uyarı simgesi (altın üçgen) eklemek zaman odağı taşır öğesinden gibi başka bir bildirimi listeye ekleyin veya sekmeler Tasarımcısı'nda değiştirmeye.  
  
-   Kullanıcı özellikleri herhangi bildirimlerinde ayarlamadan önce sekmeleri erişmeye çalışırsa, uygulamayı değil oluşturacaksınız açıklayan bir iletişim kutusu açılır (veya ne olursa olsun etkileri) uyarıları çözülene kadar. Yine de kullanıcı iletişim kutusunu kapatır ve sekmeler değiştirirse simge (kritik veya uyarı, uygun şekilde) bildirimleri sekmesine eklenir.  
  
### <a name="multiple-clicks-to-dismiss-ui"></a>UI kapatmak için birden çok tıklama  
  
#### <a name="feature-team-goals"></a>Özellik takım hedefleri  
 Açıklama metin görmeden UI kapatmak kullanıcı izin vermez.  
  
#### <a name="anti-pattern"></a>Koruma düzeni  
 VS UI içinde çeşitli yerlerde içine video bağlantı ekleme takım karşı ortak desenini karar "&times;" olarak Kapat düğmesi ve araç ipucu açıklama UX tarafından belirtilen, bunun yerine bir açılan uygulanan ve "bir daha gösterme" bağlayabilirsiniz.  

#### <a name="example-video-links-in-team-explorer"></a>Örnek: video bağlantıları Takım Gezgini
UI kutusunu kapatmadan önce açıklayıcı metin okuma kullanıcıya zorlama Visual Studio'dan karşı bir desen olur. Doğru bir şekilde tasarlanmış, video bağlantıları vurgulu ve tıklayarak ek bilgileri içeren bir araç ipucunu görüntülemesi gereken "&times;" daha fazla etkileşim için gerek kalmadan iletiyi yok sayın.


 ![Anti açıklayıcı metin&#45;düzeni &#45; yanlış](../../extensibility/ux-guidelines/media/incorrectuseofmultipleclicks.png "Incorrectuseofmultipleclicks")<br />Video bağlantısı yanlış düzeni
  
#### <a name="result"></a>Sonuç  
 Bir basit Kapat düğmesini yerine (tek bir tıklatmayla), yalnızca kullanıcı Arabiriminde, video bağlantıları görünür her yerde kapatmak için iki tıklatma kullanmak için kullanıcı zorlanır.  
  
#### <a name="alternatives"></a>Alternatifleri  
 Bu durum için doğru tasarım Internet Explorer, Office ve Visual Studio için ortak desenler izleyen olacaktır: gidildiğinde, araç ipucu açıklaması kullanıcı görebilir ve tek bir tıklatmayla kullanıcı arabirimini gizler.  
  
 ![Anti açıklayıcı metin&#45;düzeni &#45; doğru](../../extensibility/ux-guidelines/media/explanatorytextanti-pattern-correct.png "Explanatorytextanti desenini düzeltin")<br />Doğru video bağlantı düzeni
  
### <a name="using-command-bars-for-settings"></a>Komut çubukları ayarlarını kullanma  
 **Şekil A** koruma bu deseni temsil eder: ayarı daha fazlasını komutu için geçerli bir komut düğmesi altında koyma. Bu taslak içinde hata ayıklamayı Başlat yanı sıra komut vardır — ister tarayıcı, hata ayıklama olmadan başlat ve Step Into görünümünde — seçilen ayarı saygı.  

  ![Şekil A: komut koruma düzeni](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurea.png "Commandbaranti düzeni FigureA")<br />Şekil A: komut çubuğu koruma düzeni
  
 Biraz daha iyi ancak hala istenmeyen koyma ayarları bu tür araç çubuklarını, gösterildiği gibi **şekil B**. Bölünmüş düğme daha az alan alın ve bu nedenle bir geliştirme aşağı açılan listeler yaparken, her iki tasarımın gerçekten bir komutu yok bir şey yükseltmek için bir araç çubuğu hala kullanıyor.  
 
 ![Şekil B: daha iyi, ancak hala bir komut çubuğu koruma desen](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figureb.png "Commandbaranti düzeni FigureB")<br />Şekil B: daha iyi, ancak hala bir komut çubuğu koruma düzeni
 
  Gösterilen doğru yaklaşımda **şekil C**, bir dizi komut ayarı bağlıdır. Biz yalnızca dört komut arasında geçiş yapıyorsanız ve ayarlanan genel bir ayar yoktur. Bu araç komutları kabul edilebilir yalnızca durumdur. 

 ![Şekil C: düzeltmek Visual Studio komut çubuğu desen kullanılması,](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurec.png "Commandbaranti düzeni FigureC")<br />Visual Studio komut çubuğu desenini şekil C: doğru kullanın
   
### <a name="control-anti-patterns"></a>Denetim koruma desenleri  
 Bazı koruma desenleri yalnızca yanlış kullanım veya bir denetim veya denetimlerin Grup sunumu alır.  
  
#### <a name="underlining-used-as-a-group-label-not-a-hyperlink"></a>Bir köprü bir Grup etiketi kullanılan altını çizme  
 Altı çizili metni yalnızca köprüler için kullanılmalıdır.  
  
 **Hatalı:**    
 ![Köprü olmayan altı çizili bir Visual Studio koruma desen metindir. ] (../../extensibility/ux-guidelines/media/0102-g_grouplabelincorrect.png "0102 g_GroupLabelIncorrect")<br />Köprü olmayan altı çizili bir Visual Studio koruma desen metindir.
  
 **İyi:**   
 ![Doğru biçimlendirilmiş olmayan köprü metni ortamı yazı tipini asıl görüntülenir. ] (../../extensibility/ux-guidelines/media/0102-h_grouplabelcorrect.png "0102 h_GroupLabelCorrect")<br />Doğru biçimlendirilmiş olmayan köprü metni ortamı yazı tipini asıl görüntülenir.
  
#### <a name="clicking-on-a-check-box-results-in-a-pop-up-dialog"></a>Bir açılır iletişim kutusu bir onay kutusu sonuçlarında tıklayarak  
 "Microsoft Azure uygulamasını Yayımla" Sihirbazı'ndaki "Tüm rolleri için Uzak Masaüstü'nü etkinleştir" onay kutusunu hemen tıklamak, açılan iletişim, bir Visual Studio koruma desen getirir. Buna ek olarak, onay kutusu alanı bir onay kutusu seçildikten sonra dolgu değil başka bir etkileşim koruma düzeni.  
  
 ![Bir onay kutusunu tıklatarak bir Visual Studio koruma desen sonra iletişim kutusunu hale getirme. ] (../../extensibility/ux-guidelines/media/0102-i_checkboxpopup.png "0102 i_CheckboxPopup")<br />Bir onay kutusunu tıklatarak bir Visual Studio koruma desen sonra iletişim kutusunu hale getirme.
  
### <a name="hyperlink-anti-patterns"></a>Köprü koruma desenleri  
 Aşağıdaki örnek, iki koruma modeli içerir.  
  
1.  Gidildiğinde kırmızı kapatma ön yazı tipi hizmetinden doğru paylaşılan renk kullanılmadığı anlamına gelir.  
  
2.  "Daha fazla bilgi edinin" değil kavramsal konuya bağlantısı için uygun metni. Kullanıcının hedef daha, kendi seçtikleri ayrımlar anlamaktır değil öğrenmektir.  
  
 ![Renk hizmet yoksayılıyor ve "daha fazla bilgi edinmek için köprü" kullanarak Visual Studio koruma desenleri alır. ] (../../extensibility/ux-guidelines/media/0102-j_hyperlinkincorrect.png "0102 j_HyperlinkIncorrect")<br />Renk hizmet yoksayılıyor ve "daha fazla bilgi edinmek için köprü" kullanarak Visual Studio koruma desenleri alır.  
  
 **Daha iyi çözüm:** kullanıcı isteyen bağlantıya tıklayarak soru teşkil.  
  
-   Windows Azure hizmetleri nasıl çalışır?  
  
-   Bir Windows Azure Mobile Services projesi zaman gerekiyor mu?  
  
#### <a name="using-click-here-for-links"></a>"Bağlantıları için burayı tıklatın" kullanma  
 Köprüler self-descriptive olmalıdır. "Buraya tıklayın" kullanmak için bir koruma desen veya benzer bir değişim değil.  
  
 **Hatalı:** "yeni bir proje oluşturma hakkında yönergeler için burayı."
  
 **İyi:** "Nasıl oluşturabilirim yeni bir proje?"