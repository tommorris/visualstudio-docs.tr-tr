---
title: ClickOnce Dağıtımları içinde belirli hataları giderme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.ErrorPrompt.UncRequired
- Microsoft.VisualStudio.Publish.ClickOnceProvider.ErrorPrompt.NoInstallUrl
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications, ClickOnce
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
ms.assetid: 22dfe8f1-8271-4708-9c25-6bbb13920ac8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c37bcfb086acf265a719abe688c6738fbcbfc01
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234016"
---
# <a name="troubleshooting-specific-errors-in-clickonce-deployments"></a>ClickOnce Dağıtımları İçinde Belirli Hataları Giderme
Bu makalede, dağıtırken oluşabilecek aşağıdaki yaygın hataları listeler bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama ve her sorunu gidermek için adımları sağlar.  
  
## <a name="general-errors"></a>Genel hata  
  
#### <a name="when-you-try-to-locate-an-application-file-nothing-occurs-or-xml-renders-in-internet-explorer-or-you-receive-a-run-or-save-as-dialog-box"></a>Ne zaman hiçbir şey olmaz, bir uygulama dosyası bulmaya veya Internet Explorer'da XML işler ya da bir çalıştırma veya Farklı Kaydet iletişim kutusu görüntüleniyor  
 Bu hata olasılıkla sunucu veya istemci üzerinde düzgün şekilde kaydedilmemiş içerik türleri (MIME türleri olarak da bilinir) kaynaklanır.  
  
 İlk olarak, sunucunun ilişkilendirmek için yapılandırıldığından emin olun `.application` içeriğe sahip uzantı türü "application/x-ms-application."  
  
 Sunucunun doğru yapılandırılmışsa denetleyin [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] bilgisayarınızda yüklü. Varsa [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] yüklü olduğu ve bu sorun, kaldırıp yeniden yüklemeyi deneyin hala görüyorsunuz [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] istemci üzerinde içerik türünü yeniden kaydetmek için.  
  
#### <a name="error-message-says-unable-to-retrieve-application-files-missing-in-deployment-or-application-download-has-been-interrupted-check-for-network-errors-and-try-again-later"></a>Hata iletisi diyor, "Uygulama alınamıyor. Dağıtımda eksik dosyalar"veya"uygulamanın indirilmesi kesintiye, ağ hataları kontrol edin ve daha sonra yeniden deneyin"  
 Bu iletiyi bildiren tarafından başvurulan bir veya daha fazla [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bildirimleri karşıdan yüklenemiyor. Bu hata ayıklama için kolay URL yüklemeye yoldur, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] onu yükleyemiyor söyler. Bazı olası nedenleri şunlardır:  
  
-   Günlük dosyası "(403) Yasak" diyorsa, veya "(404) bulunamadı" doğrulamak Web sunucusu bu dosyayı indirmeyi engellemez şekilde yapılandırılır. Daha fazla bilgi için bkz: [sunucu ve istemci yapılandırma sorunları ClickOnce Dağıtımları içinde](../deployment/server-and-client-configuration-issues-in-clickonce-deployments.md).  
  
-   Sunucu tarafından engellenen .config dosyası, bölümüne bakın. "yüklemeye çalıştığınızda indirme hatası bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] .config dosyasına sahip uygulama" Bu makalenin ilerisinde yer.  
  
-   Sebebiyle oluşup oluşmadığını belirlemek `deploymentProvider` etkinleştirmesi için kullanılan URL farklı bir konuma işaret dağıtım bildiriminde URL.  
  
-   Tüm dosyaları sunucu üzerinde mevcut olduğundan emin olun; [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] günlük hangi dosya bulunamadı söyler.  
  
-   Ağ bağlantısı sorunları olup olmadığını; karşıdan yükleme sırasında istemci bilgisayar çevrimdışı olursa bu ileti alabilir.  
  
#### <a name="download-error-when-you-try-to-install-a-clickonce-application-that-has-a-config-file"></a>.Config dosyasına sahip bir ClickOnce uygulaması yüklemeye çalıştığında karşıdan yükleme hatası  
 Varsayılan olarak, Visual Basic Windows tabanlı bir uygulama bir App.config dosyası içerir. Bir kullanıcı bu işletim sistemi yükleme güvenlik nedenleriyle .config dosyaları engellediğinden, Windows Server 2003 kullanan bir Web sunucusundan yüklemeye çalıştığında bir sorun olacaktır. Yüklenecek .config dosyasını etkinleştirmek için **".deploy" dosya uzantısını kullanan** içinde **Yayımla Seçenekleri** iletişim kutusu.  
  
 Ayrıca içerik türü (MIME türleri olarak da bilinir) uygun şekilde .application, .manifest ve .deploy dosyaları için ayarlamanız gerekir. Daha fazla bilgi için Web sunucunuzun belgelerine bakın.  
  
 Daha fazla bilgi için "Windows Server 2003: yansıtır içerik türleri" konusuna bakın. [sunucu ve istemci yapılandırma sorunları ClickOnce Dağıtımları içinde](../deployment/server-and-client-configuration-issues-in-clickonce-deployments.md).  
  
#### <a name="error-message-application-is-improperly-formatted-log-file-contains-xml-signature-is-invalid"></a>Hata iletisi: "Uygulama yanlış biçimlendirilmiş;" "XML imzası geçersiz" günlük dosyası içerir  
 Bildirim dosyasının güncelleştirilmiş ve yeniden oturum emin olun. Kullanarak uygulamanızı yeniden yayımlamanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] veya uygulamayı yeniden imzalamak için Mage kullanın.  
  
#### <a name="you-updated-your-application-on-the-server-but-the-client-does-not-download-the-update"></a>Uygulamanızı sunucuda güncelleştirildi, ancak istemci güncelleştirmesini indir değil  
 Bu sorun aşağıdaki görevlerden birini tamamlayarak:  
  
-   İncelemek `deploymentProvider` dağıtım bildiriminde URL. BITS ile aynı konumda güncelleştirdiğiniz emin olun, `deploymentProvider` işaret eder.  
  
-   Dağıtım bildiriminde güncelleştirme aralığını doğrulayın. Bu aralık altı saatte bir kez gibi düzenli bir aralıkta ayarlanırsa [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bu aralık geçene kadar bir güncelleştirme için tarama değil. Uygulama başladığında her zaman için bir güncelleştirme taraması yapması için bildirimi değiştirebilirsiniz. Güncelleştirme aralığını değiştirmek güncelleştirmeler yüklenir, ancak uygulama etkinleştirme yavaşlatır doğrulamak için bir kolay geliştirme süresince seçeneğidir.  
  
-   Uygulama başlangıç menüsünde yeniden başlatmayı deneyin. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Güncelleştirme arka planda algılamış olabilir, ancak sonraki etkinleştirmede BITS yüklemek isteyip istemediğinizi sorar.  
  
#### <a name="during-update-you-receive-an-error-that-has-the-following-log-entry-the-reference-in-the-deployment-does-not-match-the-identity-defined-in-the-application-manifest"></a>Güncelleştirme sırasında aşağıdaki günlük girdisini içeren bir hata iletisi: "dağıtım başvurusunda uygulama bildiriminde tanımlanan kimlikle eşleşmiyor."  
 El ile dağıtım ve uygulama bildirimleri düzenlediniz ve derleme kimliğini açıklaması ile eşitlenmemiş hale gelmesine bir bildiriminde neden olmuş nedeniyle bu hata oluşabilir. Bir derlemenin kimliği, ad, sürüm, kültür ve ortak anahtar belirteci oluşur. Bildirimlerinizi kimlik açıklamasında inceleyin ve tüm farklılıkları düzeltin.  
  
#### <a name="first-time-activation-from-local-disk-or-cd-rom-succeeds-but-subsequent-activation-from-start-menu-does-not-succeed"></a>İlk kez yerel disk veya CD-ROM'dan etkinleştirme başarılı ancak Başlat menüsünden sonraki etkinleştirme başarılı olmaz  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama için güncelleştirmeleri almak için dağıtım Provider URL'sini kullanır. URL'nin işaret konumun doğru olduğundan emin olun.  
  
#### <a name="error-cannot-start-the-application"></a>Hata: "uygulaması başlatılamıyor"  
 Bu hata iletisi, genellikle bu uygulamanın yüklenmesi bir sorun olduğunu gösterir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] depolar. Uygulamada bir hata var ya da deposu bozuk. Günlük dosyası hatanın oluştuğu söyleyebilir.  
  
 Aşağıdakileri yapmanız gerekir:  
  
-   Dağıtım bildirimi kimliğini, uygulama bildirimi kimliğini ve ana uygulama EXE kimliğini tüm benzersiz olduğundan emin olun.  
  
-   Dosya yollarınızın 100 karakterden uzun olmadığını doğrulayın. Uygulamanız çok uzun dosya yollarını içeriyorsa, depolayabileceğiniz en fazla yol sınırlamalar aşabilir. Yolları kısaltmayı deneyin ve yeniden yükleyin.  
  
#### <a name="privatepath-settings-in-application-config-file-are-not-honored"></a>Uygulama yapılandırma dosyasında PrivatePath ayarları onaylanmaz  
 PrivatePath (yolları Fusion yoklama) kullanmak için uygulama tam güven izni istemeniz gerekir. Tam güven isteyin ve yeniden denemek için uygulama bildirimini değiştirmeyi deneyin.  
  
#### <a name="during-uninstall-a-message-appears-saying-failed-to-uninstall-application"></a>Kaldırma sırasında bir ileti "uygulamayı kaldırmak için başarısız oldu" görüntülenir  
 Bu ileti genellikle uygulamanın zaten kaldırılmış veya deposu bozuk gösterir. Tıklattıktan sonra **Tamam**, **Program Ekle/Kaldır** girişi kaldırılacak.  
  
#### <a name="during-installation-a-message-appears-that-says-that-the-platform-dependencies-are-not-installed"></a>Yükleme sırasında platform bağımlılıklarının yüklü olmadığını bildiren bir ileti görüntülenir  
 Uygulamayı çalıştırmak için gereken GAC (Genel Derleme Önbelleği) bir önkoşul eksik.  
  
## <a name="publishing-with-visual-studio"></a>Visual Studio ile yayımlama  
  
#### <a name="publishing-in-visual-studio-fails"></a>Visual Studio'da yayımlama başarısız  
 Sunucuya yayımlayın hakkı, hedeflediğiniz olduğundan emin olun. Bir terminal sunucusu bilgisayara bir yönetici olarak değil, normal bir kullanıcı olarak oturum açarsanız, örneğin, büyük olasılıkla yerel Web sunucusuna yayımlamak için gereken haklarına sahip.  
  
 Bir URL ile yayımlıyorsanız hedef bilgisayar FrontPage Server Extensions etkin olduğundan emin olun.  
  
#### <a name="error-message-unable-to-create-the-web-site-site-the-components-for-communicating-with-frontpage-server-extensions-are-not-installed"></a>Hata iletisi: Web sitesi oluşturulamadı '\<site >'. FrontPage Server Extensions ile iletişim kurmak için bileşenlerin yüklü değil.  
 Microsoft Visual Studio Web geliştirme yayımlamakta olduğunuz makinede bileşeni yüklü olduğundan emin olun. Express kullanıcıları için bu bileşeni varsayılan olarak yüklü değil. Daha fazla bilgi için bkz. [http://go.microsoft.com/fwlink/?LinkId=102310](http://go.microsoft.com/fwlink/?LinkId=102310).  
  
#### <a name="error-message-could-not-find-file-microsoftwindowscommon-controls-version6000-culture-publickeytoken6595b64144ccf1df-processorarchitecture-typewin32"></a>Hata iletisi: dosya bulunamadı. ' Microsoft.Windows.Common-denetimleri, sürüm 6.0.0.0, kültür = = *, PublicKeyToken 6595b64144ccf1df, ProcessorArchitecture = =\*, türü win32 ='  
 Görsel stiller etkinken WPF uygulaması yayımlamaya çalıştığınızda bu hata iletisi görüntülenir. Bu sorunu çözmek için bkz: [nasıl yapılır: görsel stiller etkinleştirilmiş olan bir WPF uygulaması yayımlama](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md).  
  
## <a name="using-mage"></a>Mage kullanma  
  
#### <a name="you-tried-to-sign-with-a-certificate-in-your-certificate-store-and-a-received-blank-message-box"></a>Sertifika deponuza ve alınan boş ileti kutusu içinde bir sertifika ile oturum açma girişiminde  
 İçinde **imzalama** iletişim kutusunda, şunları yapmalısınız:  
  
-   Seçin **depolanan bir sertifika ile oturum**, ve  
  
-   Listeden bir sertifika seçin; İlk sertifika varsayılan seçim değil.  
  
#### <a name="clicking-the-dont-sign-button-causes-an-exception"></a>"Oturum yok" düğmesini tıklatarak bir özel duruma neden olur  
 Bu sorunun bilinen bir hatadır. Tüm [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bildirimlerinin imzalı olması gereklidir. Yalnızca imzalama seçeneklerden birini seçin ve ardından **Tamam**.  
  
## <a name="additional-errors"></a>Ek hataları  
 Aşağıdaki tabloda kullanıcı yüklediğinde, bir istemci bilgisayar kullanıcısının alabileceği bazı yaygın hata iletilerini gösterir bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. Her hata iletisi, en olası neden hatanın açıklamasını yanındaki listelenir.  
  
|Hata iletisi|Açıklama|  
|-------------------|-----------------|  
|Uygulama başlatılamıyor. Uygulama yayımcısına başvurun.<br /><br /> Uygulama başlatılamıyor. Yardım için uygulama satıcısına başvurun.|Uygulama başlatılamıyor ve belirli herhangi bir neden bulunabilir oluşur genel hata iletileri şunlardır. Sık sık uygulama bir şekilde bozulmuş anlamına gelir veya [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] deposu bozuk.|  
|Devam edemiyor. Uygulama yanlış biçimlendirilmiş. Yardım için uygulama yayımcısına başvurun.<br /><br /> Uygulama doğrulama başarılı olmadı. Devam edilemiyor.<br /><br /> Uygulama dosyaları alınamıyor. Dosyalar dağıtımda bozulur.|Dağıtımdaki bildirim dosyalarından birini sözdizimsel olarak geçerli değil veya karşılık gelen dosya ile uzlaştırılamıyor bir karma içerir. Bu hata, ayrıca derleme içine gömülü bildirimi bozuk olduğunu gösteriyor olabilir. Dağıtımınızı yeniden oluşturun ve uygulamanızı yeniden derleyin veya bulun ve hataları bildirimlerinizde bulunan el ile giderin.|  
|Uygulama alınamıyor. Kimlik doğrulama hatası.<br /><br /> Uygulama yükleme başarılı olmadı. Sunucudaki uygulama dosyalarını bulamıyor. Yardım için uygulama yayımcısına veya yöneticinize başvurun.|Bunları erişim izni olmadığından dağıtımdaki bir veya daha fazla dosyalar indirilemiyor. Bunun nedeni dağıtımınızda bulunan dosyalardan biri korumalı bir dosyayı kabul Web sunucusu yapar uzantılı bir sona ererse, oluşabilecek bir Web sunucusu tarafından döndürülen 403 Yasak hatası olabilir. Ayrıca, bir veya daha fazla uygulamanın dosyaları içeren bir dizine erişmek için bir kullanıcı adı ve parola gerektirebilir.|  
|Uygulama karşıdan yüklenemiyor. Uygulamayı gerekli dosyalar eksik. Yardım için uygulama satıcısına veya sistem yöneticinize başvurun.|Bir veya daha fazla uygulama bildiriminde listelenen dosya sunucusunda bulunamıyor. Denetleyin dağıtımın tüm bağımlı dosyaları karşıya yüklediğiniz ve yeniden deneyin.|  
|Uygulama yükleme başarılı olmadı. Ağ bağlantınızı denetleyin veya sistem yöneticinize veya ağ hizmeti sağlayıcısına başvurun.|[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Sunucunun ağ bağlantısı kurulamıyor. Sunucu kullanılabilirliğini ve ağ durumunu inceleyin.|  
|URLDownloadToCacheFile başarısız oldu; HRESULT '\<numarası >'. Yüklemeye çalışırken bir hata oluştu '\<Dosya >'.|Kullanıcı Internet Explorer Gelişmiş Güvenlik seçeneğini "Arasında güvenli değiştiriliyorsa uyar ve modu güvenli değil" dağıtım hedef bilgisayarda ayarlamışsa ve yüklenen ClickOnce uygulamasının kurulum URL'si güvenli olmayan güvenli bir siteye yönlendirilir (veya Internet Explorer uyarı keser tersi), yükleme başarısız olur.<br /><br /> Bu hatayı gidermek için aşağıdaki görevlerden birini yapabilirsiniz:<br /><br /> -Güvenlik seçeneğini kaldırın.<br />-Olun Kurulum URL'SİNİN güvenlik modları değiştirecek bir şekilde emin yönlendirildiği değil.<br />-Gerçek kurulum URL'sine noktası ve yeniden yönlendirme tamamen kaldırın.|  
|Bir sabit diske yazılırken bir hata oluştu. Olabilir yeterli alan kullanılabilir disk üzerinde. Yardım için uygulama satıcısına veya sistem yöneticinize başvurun.|Bu uygulamayı depolamak için yeterli disk alanı gösterebilir, ancak uygulama dosyaları diske kaydetmeye çalışırken de daha genel bir g/ç hatası gösteriyor olabilir.|  
|Uygulama başlatılamıyor. Disk üzerinde yeterli alan yok.|Sabit disk dolu. Boş alan açın ve uygulamayı yeniden çalıştırmayı deneyin.|  
|Çok fazla dağıtılan etkinleştirmeleri aynı anda yüklemeye çalışıyorsunuz.|[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aynı anda çalışabilecek farklı uygulama sayısını sınırlar. Bu büyük ölçüde yerel karşı hizmet reddi saldırılarını kötü amaçlı saldırılara karşı korunmaya yardımcı olur [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] hizmeti; kullanıcılar aynı uygulama hızlı art arda tekrar tekrar başlatmaya çalışırsanız, yalnızca tek bir örneği ile son bulur uygulama.|  
|Kısayollar ağ üzerinden devre dışı bırakılamaz.|Kısayollar bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama yerel sabit diskte yalnızca başlatılabilir. Uzak bir sunucudaki bir kısayol dosyasına işaret eden bir URL açarak başlatılamaz.|  
|Uygulama kısmi güvende çevrimiçi çalıştırmak için çok büyük. Yardım için uygulama satıcısına veya sistem yöneticinize başvurun.|Kısmi güvende çalışacak bir uygulama, varsayılan değer 250 MB olan çevrimiçi uygulama kotasını boyutunu yarısı büyük olamaz.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce Dağıtım Sorunlarını Giderme](../deployment/troubleshooting-clickonce-deployments.md)