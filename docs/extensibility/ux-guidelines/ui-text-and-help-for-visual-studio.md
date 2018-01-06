---
title: "UI metin ve Visual Studio için Yardım | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8747d07-6c90-46cc-b425-55b589f7e9e4
caps.latest.revision: "2"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 555fd622f5655a69ba77f3905a39635e01831c76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ui-text-and-help-for-visual-studio"></a>UI metin ve Visual Studio için Yardım
##  <a name="BKMK_UITextAndTerminology"></a>UI metin ve terminolojisi  
 Anlaşılabilir metin etkili kullanıcı Arabirimi için önemlidir. Yazılım kullanıcılar eğilimindedirler okumak için ilk olarak, yani bu elinizdeki tamamlamak için en uygun etiketler. Statik metin daha az sıklıkta okuyun. Bir hızlı tarama yaklaşık bu sırada UI okuma ve ardından tüm penceresinin iş oturumlarını başlatmak kullanıcılar için planlama:  
  
1.  Merkezi'ndeki etkileşimli denetimleri  
  
2.  Düğmeleri Yürüt  
  
3.  Başka bir yerde bulunan etkileşimli denetimleri  
  
4.  Ana yönergeleri  
  
5.  Ek Açıklamalar  
  
6.  Pencere Başlığı  
  
7.  Ana gövdesinde diğer statik metin  
  
### <a name="usage-patterns-for-ui-text"></a>UI metin için kullanım desenlerini  
  
#### <a name="title-bar-text"></a>Başlık çubuğu metni  
 Başlık çubuğu metni UI kökenli komutu eşleşmesi gerekir.  
  
#### <a name="instructional-text-helper-text"></a>Açıklayıcı metin (yardımcı metin)  
 Bazı iletişim kutularında penceresinde veya sayfanın yapmanız gerekenler açıklamak için belirgin ana yönergeler sağlamak yararlıdır. Bu bazen "Yardımcısı metin olarak." adlandırılır  
  
##### <a name="writing-style-rules-for-helper-text"></a>Stil kurallarını yardımcı metin yazma  
  
-   Belirgin açıklanmaz. Kesinlikle gerekli olmadıkça açıklayıcı metin dahil etmeyin.  
  
-   Açıklayıcı metin her zaman iletişim kutusunun üstündeki yerleştirilir ve gerçekleştirilen görev başvurmalıdır.  
  
-   Tam olarak kullanıcılara bunlar için yapmanız gerekenler açıklanmaktadır. Aşırı iletişim ve artıklık kaçının.  
  
-   Her penceresini gözden geçirin ve yinelenen sözcükleri ve ifadeleri ortadan kaldırmak.  
  
-   Açıklayıcı metin kısa tutun. Daha fazla bilgi gereken belirli kullanıcılar ya da senaryoları ise, ayrıntılı kavramsal çevrimiçi konuya bir bağlantı sağlayın.  
  
-   Metninizi yazın, böylece her word ağırlık tutar ve gereklidir.  
  
-   Varolan Microsoft kılavuzunu izleyin [kullanıcı arabirimi metni](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx) ve [stil ve üslup](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742477\(v=vs.85\).aspx).  
  
#### <a name="supplemental-instructions"></a>Ek yönergeler  
 Ek yönergeler denetimleri anlamak veya gruplandırmaları denetim kullanıcı yardımcı olacak ek bilgiler sağlar. Bu, ipucu metnini giriş denetiminin bekleniyor biçimi anlamak gerekli de içerebilir. Gerektiğinde ek yönergeleri kullanın. Bunları kullanıcı yapmakta olan tercih ayrımlar tam olarak anlamak olmaz büyük olasılıkla olduğu durumlar için yedek.  
  
 ![Visual Studio'da ek metin](../../extensibility/ux-guidelines/media/0601-b_supplementaltext1.png "0601 b_SupplementalText1")  
  
 **Visual Studio'da ek metin**  
  
 ![Visual Studio'da ek metin](../../extensibility/ux-guidelines/media/0601-c_supplementaltext2.png "0601 c_SupplementalText2")  
  
 **Visual Studio'da ek metin**  
  
#### <a name="infotips"></a>InfoTips  
 Genellikle, açıklayıcı metin kullanıcı Arabiriminde yerinde konumlandırmak için çok uzun olabilir veya dağınıklığı deneyimli kullanıcılar gibi HİSSEDİYORSUNUZ yalnızca yeni kullanıcılar için yararlı olabilir. Bu durumda, bir bilgi ipucu altında bir araç ipucu olarak yönerge ve bilgi amaçlı metin yerleştirilmelidir.  
  
 InfoTips için ilişkili olan ve henüz örtük belirli bilgi ipucu simgesi kullanması gereken denetimleri belirgin yerleştirilmelidir.  
  
 ![Visual Studio'da Bilgi İpucu](../../extensibility/ux-guidelines/media/0601-d_infotip.png "0601 d_InfoTip")  
  
 **Visual Studio'da bir bilgi ipucu örneği**  
  
##### <a name="writing-style-rules-for-infotips"></a>InfoTips için yazı stili kuralları  
  
-   InfoTips tam bir cümle yazın. Bunlar, belirli fiillere, cümle ve noktalama bitiş gerektirir.  
  
-   Ana yönergesi veya bilgi desteklemek için InfoTips kullanın. Ana fikir yazmayı farklı sözcükler yalnızca kullanıyorsanız, bir bilgi ipucu gerekmez.  
  
-   InfoTips ve tatlı kısa tutun. Küçük sözcükler ve düz, kullanın destekler ve kullanıcı teşvik eden gündelik dili.  
  
-   Varolan Microsoft kılavuzunu izleyin [kullanıcı arabirimi metni](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx) ve [stil ve üslup](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742477\(v=vs.85\).aspx).  
  
#### <a name="control-labels"></a>Denetim etiketleri  
 Denetim etiketleri kısa ve NET ve gerekir izleyin [denetimleri için Windows Masaüstü Kılavuzu](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742399\(v=vs.85\).aspx).  
  
 Denetimin etiket biçimi ve kullanıcı arabirimini içinde yerleştirme hakkında daha fazla bilgi için başvurmak [Visual Studio için Düzen](../../extensibility/ux-guidelines/layout-for-visual-studio.md).  
  
#### <a name="help-links"></a>Yardım bağlantıları  
 Yardım bağlantıları ya da açıklayıcı metin içinde veya UI gövdesine eklenebilir. Yardım bağlantıları olması veya iç iletişim kutuları başlatın.  
  
##### <a name="visual-style-rules-for-help-links"></a>Yardım bağlantıları için görsel stil kuralları  
  
-   Doğru ortamı renkleri köprüleri için kullanın. Düzgün stilde köprü kısaca tıklatıldığında kırmızı yanar değil. Bu görürseniz, sonra bu ortam renkleri kullanılmayan göstergesidir.  
  
-   Alt çizgiler, vurgulu veya bağlantı bir paragraf içinde ne zaman katıştırılmış yalnızca kullanılmalıdır.  
  
-   Köprüler visual ve etkileşim stilleri hakkında daha ayrıntılı bilgi için bkz: düğmeleri ve bağlar.  
  
##### <a name="writing-style-rules-for-help-links"></a>Yardım bağlantıları için stil kuralları yazma  
  
-   İletişim kutuları başlatılırken elipsler standartları korumak: hiçbir üç nokta gezinme, ek UI görev gerektiriyorsa, üç nokta.  
  
     ![Visual Studio Yardım bağlantısına](../../extensibility/ux-guidelines/media/0601-e_helplink.png "0601 e_HelpLink")  
  
     **Üç nokta (...) bir Yardım bağlantısını bulunan ek kullanıcı Arabirimi görev gerektirir gösterir.**  
  
-   Kullanıcının amacı olmayan gibi bağlantılar "Öğrenin," ile başlamamalıdır. Kullanıcının belirli bir soruya yanıt, genel bir eğitim almamayı istemektedir.  
  
-   Böylece bunlar konu yanıtlayacak soru tümcecik Yardım bağlar.  
  
     Yanlış:  
     "Windows Azure Mobile Services fiyatlandırma hakkında daha fazla bilgi edinin"  
  
     Düzeltin:  
     "Ne fiyatlandırma seçenekleri için Windows Azure Mobile Services kullanılabilir?"  
  
-   Hiçbir zaman kullanmayın *tıklatın...*  bağlantı metni.  
  
-   Hiç bağlantı yalnızca word "Buraya". Bu yalnızca köprülü word sesli bazı ekran okuyucular için sorunlu oluşturur.  
  
     Yanlış:  
     "Windows Azure mobil hizmetler hakkında bilgi bulmak **burada**"  
  
     Düzeltin:  
     "Ne fiyatlandırma seçenekleri için Windows Azure Mobile Services kullanılabilir?"  
  
-   Yardım bağlantıları için doğru yazı stili hakkında daha fazla bilgi için bkz: [Yardım için Windows Masaüstü Kılavuzu](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742494\(v=vs.85\).aspx).  
  
#### <a name="hint-text"></a>İpucu metni  
 İpucu metnini denetimdeki veya denetimi altında filigran olarak görünür. Doğru biçimlendirilmiş uygulanacak uygun VSColors belirteci kullanarak `Environment.GrayText`.  
  
 Çok sayıda formu görünebilir.  
  
-   Denetim etiketi yerine:  
  
     ![Visual Studio'da metin İpucu](../../extensibility/ux-guidelines/media/0601-f_hinttext1.png "0601 f_HintText1")  
  
-   Bir fiil ile yönergeler verir:  
  
     ![Visual Studio'da metin İpucu](../../extensibility/ux-guidelines/media/0601-g_hinttext2.png "0601 g_HintText2")  
  
-   Gerekli bir girdi belirten metinle:  
  
     ![Visual Studio'da metin İpucu](../../extensibility/ux-guidelines/media/0601-h_hinttext3.png "0601 h_HintText3")  
  
#### <a name="watermark-text"></a>Filigran metni  
 Bir boş tasarım yüzeyine metni ne yapmak yanı sıra diğer ilgili windows uygunsa açmak için bağlantılar sağlar belirtmeniz gerekir:  
  
 ![Filigran metni Visual Studio'da](../../extensibility/ux-guidelines/media/0601-i_watermarktext.png "0601 i_WatermarkText")  
  
 **Visual Studio'da filigran metni örneği**  
  
### <a name="common-terminology"></a>Ortak terminolojisi  
  
|Terim|Açıklama|Yorum|  
|----------|-----------------|-------------|  
|Oturum Aç / Oturumu Kapat|Fiiller maliyetle aynı anlamda web ile kimlik doğrulaması web özelliği içine temsil etmek için kullanılır. İstemcileri, bu kez üst düzey bir kavram IDE kullanıcı bağlantısı, lisans ve dolaşım gibi daha üst düzey özellikleri ile tüm diğer bağlantılar kullanılabilir değil sağlar üst düzey bir kimliğini temsil eder ve imzalama için kullanırız.|IDE kullanıcı temsil eden bir oturum açma / fiili oturum yalnızca özellik aynıdır en üst düzey bir IDE kullanıcıyı temsil eder.|  
|Bağlan / bağlantıyı kes|Burada bir özelliği bir çevrimiçi hizmet için tek bir bağlantı tutar yerlerde kullanın.|Sunucu Gezgini, burada yalnızca belirli bir anda bir etkin Azure bağlantısı olabilir, Bağlan/bağlantıyı kes örneğidir.|  
|Ekle / Kaldır|Olmayan bozucu. Ekleme veya listeden bir şey kaldırırken kullanın.|TFS Bağlantı Yöneticisi'ni sunucu listesi iletişim kutusu, Ekle/Kaldır örneğidir.|  
|Sil|Bozucu. Yalnızca kaldırılmakta öğesini kalıcı olarak atılacak veya diskten silindikçe kullanın.|Sonuç diskten bir dosyayı silmek, "Delete" bir istem genellikle gerektirir.|  
  
## <a name="error-messages"></a>Hata iletileri  
  
### <a name="overview"></a>Genel Bakış  
 Hataları gerçekleşir. Sınırlamalar kullanıcının ne kaçınılabilir hata iletileri engelleyen bir duyarlı ilk adımı ayardır. Ancak, bir hata ortaya çıktığında iyi yazılmış hata iletisi sorun Azaltıcı doğru uzun bir yol gidebilirsiniz. Hata iletileri tartışmaya açık bir şekilde çünkü bunlar zaman uyumlu ve çözülmesi gereken bir sorun olduğunu gösteriyor, kullanıcının, gördüğü bildirim en önemli türlerinden biridir. Kötü yazılmış hata iletileri kullanıcılar hataları nedenini karar vermek için kendi ve tüm olası çözümleri bırakın.  
  
 Kullanıcıları için aşırı kullanılmasına dikkat veya hata iletileri, kullanıcı değeri eklemek yalnızca gerekli iletileri yazma deneyimi için kafa karıştırıcı durabilir. Yalnızca bir bildirim iletisiyse alternatif bir sunumu kullanın.  
  
### <a name="rules-for-creating-an-error-message"></a>Bir hata iletisi oluşturmak için kurallar  
  
-   Hata iletileri oluşturulurken ilgili hata düzeyi hedef kitlesi seçin. Kullanıcı alabilir, bir eylem varsa sağlayan basit özetlerini hedefleyin. Durum kullanıcı bilmeniz gerekmez herhangi bir şey yok.  
  
-   Yapıcı Yardımı sağlarız. Okuma ve yönerge içeren bir hata iletisi hareket kolaydır.  
  
-   Çift negatif kullanmayın.  
  
-   Her iki otomatikleştirilmiş bir gerçekleştirmek ve el ile dilbilgisi ve yazım yazdığınız herhangi bir hata iletisi denetleyin.  
  
-   Karmaşık hata iletileri için sıralı iletişimleri kaçının. Hiçbir zaman bir F1 bağlantı için hata iletisini kullanın. İleti yeterli olacaktır.  
  
-   Doğru simgesini kullanın.  
  
-   Sorular anlamak ve "Delete" ve "İptal" gibi açık seçeneklerin düğmelerini kullanarak daha kolay hale getirin  
  
-   Uyarılar için ne devam etmeden sonucu olacağı hakkında Temizle olabilir. Düğmeleri sonucu gösterebilir.  
  
-   Hatalar için kullanıcı sorunu gidermek için neler yapabileceğinizi açıklar. Düğmeler eylemler olabilir veya "Kapat" söyleyin "Tamam" düğmesini bir hata iletisi için kullanmayın.  
  
-   Kendinize oluşturulurken bir hata iletisi, sorun bazı sorular:  
  
    -   Kullanıcı, bu hata tek başına sorunu çözmeyi hesaplayabilir?  
  
    -   Kullanıcı, bu hata olarak aynı sözlük kullanıyor mu?  
  
    -   Bu hata ambigious mu, yoksa birden çok durumlarda paylaşılan? Nasıl gerekiyorsa, kullanıcıların ihtiyaç duydukları çözüm için yol?  
  
#### <a name="build-errors"></a>Derleme hataları  
 Visual Studio yazılım geliştirme aracı olduğundan, çoğu bileşenlerinden biri dönüştürme ya da Geliştirici çalışma ikili biçime dönüştürmek için adım kodlama bir derleme vardır. Bu dönüşümleri derleyici yanlış yazılan dosyaları işleyemediğinde veya derleyici seçenekleri doğru ayarladığınızda doğru hatalara neden olabilir.  
  
 Visual Studio kullanıcıları muazzam bir derleme hatalarını çözme geliştirme saat sayısını harcayabilir. Hataları bağımlılıklar veya ne zaman hata mesajları kötü, hangi hatanın kaynağını ortaya çıkarmaya zorlaştırabilir yazılır olduğunda bu çözümleme süresini artırır.  
  
 Bu nedenle ilk yerinde Visual Studio oluşmaz sunar otomatik tamamlama en iyi derleme hataları var ve IntelliSense dalgalı çizgiler. Şema doğrulayıcıları ve benzer araçları aynı türde geri bildirim sağlayın. Bu mekanizmaların önceden derleme hataları olasılığını lessening doğru biçimlendirilmiş kodu oluşturmak için Kullanıcı Kılavuzu.  
  
 Visual Studio, kullanıcıların okuma ve belge pencerelerini meydana gelen hatalara gezinmek araç penceresi sağlar. Klavye kısayolları, böylece kullanıcı, hızlı bir şekilde kod büyük miktarlarda gidin ve doğrudan sorun konuma gidin sağlanır. Visual Studio, böylece kullanıcı doğrudan hata hakkında daha ayrıntılı bilgi sağlayan bir Yardım konusu gidebilirsiniz belirli bir Yardım anahtar sözcüğü/context ID için bağlanması her bir yapı hata de sağlar.  
  
 Yazma NET, kısa derleme hataları:  
  
-   **Düz dil kullanmak** çok az kayıpla veya hiç derleyici terimler sorun açıklanmaktadır. Bir derleme hatası metnin aşırı teknik olmamalıdır.  
  
-   **Olası nedenleri verilmiştir.** Örneğin, "özellik ve değer arasında iki nokta üst üste eksik ' (özellik): (değer)' bildirimi."  
  
-   Olası düzeltmeler hakkında ayrıntılar sağlar. Yeterli alan yoksa, ek ayrıntılar ilgili Yardım konusunu yerleştirilebilir.  
  
### <a name="components-of-a-well-written-error-message"></a>İyi yazılmış hata iletisinin bileşenleri  
  
#### <a name="use-the-shell-dialog-service-for-error-messages"></a>Hata iletileri için Kabuk iletişim hizmeti kullanın.  
 Kabuk iletişim hizmeti kullanarak yazı tiplerini iletinin görünümünü özellikle, ayrı ayrı öğeler için önemli bir değişiklik yapılmadan denetlemenize olanak tanır. Kullanım **IErrorInfo** mekanizmaları ve bunları rapor kullanarak **IVsUIShell::SetErrorInfo/ReportErrorInfo**.  
  
#### <a name="choose-an-effective-and-appropriate-notification-presentation"></a>Etkili ve uygun bildirim sunu seçin.  
 Acil eylem (zaman uyumlu bildirim) veri kaybını önlemek için gerekliyse, kalıcı bir iletişim kutusu ile bir kritik uyarı kullanın. Kritik simgelerini hangi iletiyi okuma olmadan kapanan bunu olumsuz sonuçlara yol açabilir durumlar için ayrılmıştır. Veri kaybı bir uyarı düzeyi yanıt gerektiren önemli bir durumdur. Aşırı kullanımı kritik simgesinin önem derecesini kullanıcılara desensitizes. Hata iletisi bilgilendirici, kalıcı bir iletişim kutusu (zaman uyumsuz bildirim) alternatifleri göz önünde bulundurun.  
  
#### <a name="provide-a-clean-succinct-explanation-of-why-the-problem-occurred-rather-than-a-technical-explanation"></a>Neden bir teknik açıklama yerine bir hata oluştu, temiz, kısa bir açıklama sağlayın.  
 Açıklama teknik ayrıntılar kullanıcılarla overburdening bunları hata iletilerini yok say daha olası hale getirir. İyi Mesajlaşma örnekler:  
  
-   "İstenen dosyası açılamıyor."  
  
-   "Internet'e bağlantı kurulamıyor."  
  
#### <a name="provide-information-about-how-to-fix-the-problem"></a>Sorunun nasıl çözüleceğini hakkında bilgi sağlar.  
 Sorunun nasıl çözüleceğini kullanıcı öneriler sunar. Öneri varsa, kullanıcıyla dürüst. Teknik destek veya topluluk desteği gibi alternatif çevrimiçi kaynaklarına doğrudan bağlantılar sağlar. Sorunla ilgili belirli çevrimiçi bilgiler kullanıcıların işaret edecek şekilde deneyin. Bir hata kimliği için kullanıcıları belirli hata hakkında bir tartışma iş parçacığı bağlantılandırma göz önünde bulundurun. İyi Mesajlaşma örnekler:  
  
-   "Internet'e bağlı ve bu işlemi yeniden deneyin emin olun."  
  
-   "Dosyanın var olduğunu ve dosyayı açma iznine sahip olduğunuzdan emin olun."  
  
#### <a name="write-a-message-that-is-short-and-to-the-point"></a>Kısa ve noktasına olduğunu belirten bir ileti yazın.  
 Bir hata iletisi bildirebilir, açıklayan, ve bir çözüm sunar ancak fazla uzundur varsa hala yoksayılacak. Bir çözüm ayrıntıları düğmesi ile aşamalı açığa kullanmaktır. Örneğin, kısa bir açıklama/çözüm verin ve ardından Ayrıntılar düğmesini altında daha fazla bilgi alın. Hata hakkında daha fazla bilgi okumak kullanıcılar'ı seçerseniz, bunlar bunu yapabilirsiniz.  
  
 İleti dilde olmalıdır:  
  
-   **Etki alanı gerekli.** Kullanıcı anlayabileceği dilini kullanır. Müşterilerimizin geliştiriciler olsa da, bunlar genellikle sahibiz terminoloji ve bağlam yok.  
  
-   **Belirli.** Belirsiz ifadesi önlemek ve belirli adları ve konumları dahil edilen nesnelerin verin. Örneğin, "karakter geçersiz olduğu gibi" hata iletisi kullanışlı değildir. Hangi karakter? "Dosyası bulunamadı." Hangi dosya?  
  
-   **Courteous.** Yok kullanıcı nedenlerle veya bunları stupid eşitleyerek yapın. Tehlikeli veya saldırgan dil kaçının (KILL, yürütme, sonlandırma, önemli, geçersiz). Çok shouting olarak görülür ve olarak okunamaz büyük metin kaçının. Mizah kullanmayın.  
  
-   **Düzeltin.** Doğru yazım ve dilbilgisi (hatta alfalar içinde) kullanın. Yazım hatalarını profesyonel ve utanç.  
  
-   **Bağlam uygun.** Uygun düğme metni kullanın. "Tamam" düğmesini kaçının ve bunun yerine "Devam" veya "Evet/Hayır" kullanın  
  
### <a name="error-message-examples"></a>Hata iletisi örnekleri  
  
|İyi|Hatalı|  
|----------|---------|  
|"Aradığınız sayıdır artık hizmetinde. Lütfen numarayı denetleyin ve tekrar arama veya 0 işleci için arama."|-"Hata (449): Geçersiz sayı"<br />-"Bu işlenmeyen özel durum hatası işleminin başarıyla tamamlandığını belirtir."<br /><br /> ![Visual Studio'da hatalı hata iletisi](../../extensibility/ux-guidelines/media/0602-a_errordialog.png "0602 a_ErrorDialog")|  
  
## <a name="accessing-help"></a>Yardım erişme  
  
### <a name="overview"></a>Genel Bakış  
 MSDN belgelerine ek olarak, bir Visual Studio kullanıcı kullanıcı arabiriminde yardımcı olmak üzere çok sayıda erişim noktasına sahip. Bu erişim noktaları sürekli kullanılabilir olmasını sağlamak için ortamı tarafından sunulan Yardım sistemi yararlanmak özellik ekiplerine gerekir. Bu erişim noktalar şunlardır:  
  
-   **İletişim kutuları yönerge ve ek metin.** Yön veya açıklama, yüzey veya bilgi ipucu simge üzerine getirin kullanılabilir kullanıcı Arabirimi üzerindeki ya da verir statik metin.  
  
-   **F1 Yardımı** (yalnızca Düzenleyici). Visual Studio düzenleyicisinde, herhangi bir zamanda F1 tuşuna basarak geçerli seçim için belirli bir Yardım konusu getirir, bir kullanıcı güvenebilirsiniz. F1 ile ilişkili konuları uygun ve bilgilendirici olduğundan emin olun.  
  
-   **Yardım konuları bağlar.** Bir iletişim kutusu, araç penceresi ya da kullanıcı yardımcı teknoloji, özellik ya da bir görevi gerçekleştirmek hakkında bilgi hakkında daha fazla bilgi için konu başlatır tasarım yüzeyi içerisinde bir köprü.  
  
-   **Akıllı etiketler ve yapı iletişim kutuları gibi kullanıcı Arabirimi mekanizmalarını Yardımcısı.** Bu mekanizmaların kullanıcının bir kullanıcı Arabirimi öğesi anlaşılmasına yardımcı veya akıllı etiketler veya Oluşturucu iletişim kutuları gibi bir görev.  
  
-   **Kullanıcı Arabirimi Yardım düğmeleri** (kullanım dışı). İlgili F1 Yardımı konu erişmenizi başlık çubuğunda görünür bir gösterge.  
  
### <a name="text"></a>Metin  
  
#### <a name="instructional-and-supplemental-text-in-dialogs"></a>İletişim kutuları yönerge ve ek metin  
 Karmaşık görevleri destek iletişim kutularında, iletişim kutusunun veya karmaşık denetimler yakın üst genellikle UI içinde açıklayıcı metin vermek gerek olabilir. Bkz: [UI metin ve terminolojiyi](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) yazma stili hakkında bilgi.  
  
#### <a name="infotips"></a>InfoTips  
 Genellikle, açıklayıcı metin UI yerinde konumlandırmak için çok uzun olabilir veya dağınıklığı deneyimli kullanıcılar gibi HİSSEDİYORSUNUZ yalnızca yeni kullanıcılar için yararlı olabilir. Bu durumda, bir bilgi ipucu altında bir araç ipucu olarak yönerge ve bilgi amaçlı metin yerleştirilmelidir.  
  
 InfoTips için ilişkili olan ve henüz örtük belirli bilgi ipucu simgesi kullanması gereken denetimleri belirgin yerleştirilmelidir.  
  
 ![Visual Studio'da Bilgi İpucu](../../extensibility/ux-guidelines/media/0601-d_infotip.png "0601 d_InfoTip")  
  
 **Visual Studio'da bir bilgi ipucu örneği**  
  
### <a name="interactive-help-mechanisms"></a>Etkileşimli yardım mekanizmaları  
  
#### <a name="f1-help"></a>F1 Yardımı  
 F1 Yardımı gereklidir, bir düzenleyici veya tasarım yüzeyi içinde ancak Visual Studio ortamında olmayan başka bir yerde.  
  
#### <a name="hyperlinks-to-help-topics"></a>Yardım konuları köprüler  
 Köprüler, bir eylem gerçekleştirmek, IDE içinde gidin veya Yardım bir tarayıcıda başlatmak için kullanılabilir. Bkz: [UI metin ve terminolojisi](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) dil ve 07.10.01 hakkında ayrıntılar için düğmeler ve köprüleri visual ve düzeni yönergeler.  
  
#### <a name="help--buttons-in-dialog-title-bars-deprecated"></a>(Kullanım dışı) iletişim kutusu başlık çubukları [?] düğmeleri Yardım  
 Çoğunlukla, iletişim kutularının başlık çubuğunda Yardımı [?] düğmeleri kullanım dışı bırakılmıştır. Kullanıcı Arabirimi konuları artık belge modelimizi parçası olan ve bu nedenle olmayabilir bağlamak için ilgili konu. Aslında, başlık çubuğu düğmesi F1 Yardımı ile aynı şey edildi ve iletişim kutularında artık gereklidir. Köprüler daha yaygın olarak, yeni kullanıcı Arabiriminde kullanılır ancak bazı durumlarda, bu hala daha fazla kavramsal veya yordamsal bilgiler kullanılabilir olduğunu bir göstergesi olarak kullanılabilir.  
  
##### <a name="dialogs-created-through-the-environment"></a>Ortamı üzerinden oluşturulan iletişim kutuları  
 Birçok Kabuk iletişim kutuları aracılığıyla oluşturulan **VBDialogBoxParam** işlevi. Taşıma yardımcı olması için bu paylaşılan işlevi güncelleştirildi **yardımcı** iletişim kutusuna düğmesinden **?** Geriye dönük olarak bir mimari korurken düğmesi uyumlu ve genişletilebilir.  
  
 Özellikle, **VBDialogBoxParam** işlevi arar Kimliğine sahip bir düğme için iletişim şablona **IDHELP** (9) veya etiket **yardımcı** veya **&Yardım**. Yardım düğmesi bulunursa, gizli ve **WS_EX_CONTEXTHELP** stili yerleştirir iletişim eklenen **?** iletişim kutusu başlık çubuğunda düğmesi.  
  
 İletişim kutusu oluşturulurken bir yığın üzerine iletişim proc iter ve adlı önceden işlem iletişim proc ile iletişim kutusunu çağırır **DialogPreProc**. Zaman **?** düğmesine tıklandığında, gönderen bir **WM_SYSCOMMAND** , **SC_CONTEXTHELP** iletişim. **DialogPreProc** bu komut yakalar ve kendisine değişiklikleri bir **WM_HELP** özgün iletişim yordam geçirilen iletisi  
  
 Çoğu ortam oluşturulan iletişim kutuları iletişim kutusunda bir Yardım düğmesi vardır. İletişim kutusu görüntülendiğinde, Yardım düğmesini otomatik gizli ve yalnızca **?** Düğme çalışır. Varsa **?** Düğme şimdiye kadar kaldırıldı veya Windows'ta değişti, bu çözümü hızlı bir şekilde geri özgün Yardım düğmeleri taşımanızı sağlar.  
  
 Bu çözüm hatalar neden olabilecek dört varsayımlarda bulunur:  
  
-   İletişim kutusu Yardım düğmesi **IDHELP** (9).  
  
-   Yardım düğmesi gizli iletişim doğru arar.  
  
-   İletişim kutusu, kendi winproc'un yerine değil.  
  
-   İletişim kutusu içinde başka bir iletişim kutusu katıştırılmış değil.  
  
 İletişim msenv içinde bulunur ve kullanmayan **VBDialogBoxParam**, yararlanarak araştırmak **VBDialogBoxParam** kendi işleyici uygulamadan önce.  
  
##### <a name="dialogs-created-through-other-packages"></a>Diğer paketler aracılığıyla oluşturulan iletişim kutuları  
 Msenv dışında bulunan iletişim kutuları için kendi çözümü uygulayabilirsiniz. Bir paylaşılan iletişim kutusu sınıfında için VSPackage, başlık çubuğu düğmesini taşıma veya her iletişim kutusunda bir işleyici uygulama göz önünde bulundurun. Aşağıdaki kodu çatıyı başlamanıza yardımcı olmak için bir uygulama bulunur:  
  
```  
struct DLGPROCITEM  
{  
    FARPROC proc; // The info used to create the dialog.  
    DLGPROCITEM* procPrev;  
};  
  
DLGPROCITEM* g_dlgProcStack = NULL;  
  
// A dialog starter/wrapper function is used to push the new  
// dialog proc to the top of our dialog proc stack.  
  
int SomeDialogStarterFunction(hinst, id, proc, etc)  
{  
    if (g_dlgProcStack == NULL)  
    {  
        g_dlgProcStack = new DLGPROCITEM;  
        g_dlgProcStack->procPrev = NULL;  
    }  
    else  
    {  
        DLGPROCITEM* procItem = new DLGPROCITEM;  
        g_dlgProcStack->procPrev = g_dlgProcStack;  
        g_dlgProcStack = procItem;  
    }  
}  
  
// Pop this dialog proc off the dialog proc stack.  
  
DialogBoxIndirectParam...(...)  
{  
    DLGPROCITEM* procItem = g_dlgProcStack->procPrev;  
    delete g_dlgProcStack;  
    g_dlgProcStack = procItem;  
}  
  
// A wrapper dialog procedure will allow us to capture the  
// SC_CONTEXTHELP button on the title bar from Windows and  
// forward it as a simple WM_HELP message back to the dialog.  
  
INT_PTR CALLBACK DialogPreProc(HWND hwndDlg, UINT uMsg,  
    WPARAM wParam, LPARAM lParam)  
{  
    if (uMsg == WM_SYSCOMMAND && wParam == SC_CONTEXTHELP)  
    {  
        uMsg = WM_HELP;  
        wParam = 0;  
        lParam = 0;  
    }  
    return CallWindowProc((WNDPROC)g_dlgProcStack->proc,  
        hwndDlg, uMsg, wParam, lParam);  
}  
```  
  
##### <a name="help-buttons-in-managed-code"></a>Yönetilen kod Yardım düğmeleri  
 Pencere başlık çubuğu Yardım düğmenin varsayılan davranışı geçersiz kılma, yönetilen kodda kolaydır. Bu davranış gösteren tam demo uygulama aşağıdadır. Esas olarak, form geçersiz kılmanız gerekir **WndProc** yöntemi ve ardından yangın F1 Yardımı kapalı istekleri ne zaman bir **SC_CONTEXTHELP** ileti engelledik.  
  
```  
using System;  
using System.Windows.Forms;  
  
public class HelpForm : Form  
{  
    private const int SC_CONTEXTHELP = 0xF180;  
    private const int WM_SYSCOMMAND = 0x0112;  
  
    public HelpForm()  
    {  
        this.ClientSize = new System.Drawing.Size(300, 250);  
        this.HelpButton = true;  
        this.MaximizeBox = false;  
        this.MinimizeBox = false;  
        this.Name = "HelpForm";  
        this.Text = "Help Form";  
    }  
  
    protected override void WndProc(ref Message m)  
    {  
        if (m.Msg == WM_SYSCOMMAND && SC_CONTEXTHELP == (int)m.WParam)  
            ShowHelp();  
        else  
            base.WndProc(ref m);  
    }  
  
    private void ShowHelp()  
    {  
        MessageBox.Show("F1 Help goes here.");  
    }  
  
     [STAThread]  
    static void Main()  
    {  
        Application.EnableVisualStyles();  
        Application.EnableRTLMirroring();  
        Application.Run(new HelpForm());  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazı tipleri ve Visual Studio için biçimlendirme](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md)   
 [Visual Studio için düzeni](../../extensibility/ux-guidelines/layout-for-visual-studio.md)   
 [Bildirimler ve Visual Studio için ilerleme durumu](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md)