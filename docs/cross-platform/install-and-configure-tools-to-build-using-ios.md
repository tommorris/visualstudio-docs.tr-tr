---
title: İOS kullanılarak derleme ve Yapılandırma Araçları'nı yükleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-mobile
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d0c311c9-9eb9-42c5-ba07-25604362cd28
author: corob-msft
ms.author: corob
manager: douge
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 5374001e63f83f13e0956314e9af88808d624dae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="install-and-configure-tools-to-build-using-ios"></a>İOS kullanılarak derleme ve Yapılandırma Araçları'nı yükleme
Platformlar arası Mobil Geliştirme için Visual C++ düzenlemek, hata ayıklama ve iOS simülatörü'nü veya bir iOS aygıtı iOS kodu dağıtmak için kullanabilirsiniz, ancak lisans kısıtlamaları nedeniyle kodu gerekir oluşturulur ve Uzaktan Mac'te çalışan Derleme ve Visual Studio kullanarak iOS uygulamaları çalıştırmak için ayarlamak ve uzak aracısını yapılandırmak gereken [vcremote](http://go.microsoft.com/fwlink/p/?LinkId=534988), Mac üzerinde Uzak Aracı tanıtıcıları Visual Studio'dan istekleri oluşturmak ve Mac veya Mac Simulator'da iOS bağlı iOS cihazında uygulamayı çalıştırır  
  
> [!NOTE]
>  Mac yerine bulutta barındırılan Mac Hizmetleri kullanma hakkında daha fazla bilgi için bkz: [oluşturma ve benzetimini yapma bulutta iOS](https://taco.visualstudio.com/en-us/docs/build_ios_cloud/). Apache Cordova için Visual Studio Araçları'nı kullanarak oluşturmak için yönergeleri verilmiştir. Platformlar arası Mobil Geliştirme için Visual C++ kullanarak oluşturmak için yönergeleri kullanmak için vs mda uzaktan vcremote değiştirin.  
  
 İOS kullanarak oluşturmak için gerekli araçları yüklendikten sonra yolları hızlı bir şekilde yapılandırmak ve iOS geliştirme Visual Studio ve Mac için Uzak aracısını güncelleştirmek için bu konuya bakın  
  
 [Önkoşulları](#Prerequisites)  
  
 [İOS için Uzak aracı yükleme](#Install)  
  
 [Uzak Aracı Başlat](#Start)  
  
 [Visual Studio'da uzak Aracısı'nı yapılandırma](#ConfigureVS)  
  
 [Yeni bir güvenlik PIN oluştur](#GeneratePIN)  
  
 [Yeni bir sunucu sertifikası oluşturma](#GenerateCert)  
  
 [Uzak Aracı Mac yapılandırın](#ConfigureMac)  
  
##  <a name="Prerequisites"></a> Önkoşullar  
 Yükleyin ve iOS için kodu geliştirmek için Uzak aracı kullanmak için öncelikle bu Önkoşullar olması gerekir:  
  
-   OS X Mavericks veya sonraki sürümü çalıştıran bir Mac bilgisayar  
  
-   Bir [Apple kimliği](https://appleid.apple.com/)  
  
-   Etkin bir [iOS Developer Program](https://developer.apple.com/programs/ios/) Apple hesabıyla  
  
-   [Xcode 6](https://developer.apple.com/xcode/downloads/)  
  
     Xcode 6 uygulama Mağazası'ndan indirilebilir.  
  
-   Xcode komut satırı araçları  
  
     Xcode komut satırı araçlarını yüklemek için Terminal Mac uygulamasını açın ve aşağıdaki komutu girin:  
  
     `xcode-select --install`  
  
-   Xcode'da yapılandırılmış kimlik imzalama iOS  
  
     İmzalama kimlik iOS edinme hakkında ayrıntılı bilgi için bkz: [Bakımı bilgisayarınızı imzalama kimlikleri ve sertifikaları](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/MaintainingCertificates/MaintainingCertificates.html) iOS Geliştirici Kitaplığı'nda. Xcode'da imzalama kimliğinizi ayarlayın veya görmek için açık **Xcode** menü ve **Tercihler**. Seçin **hesapları** ve Apple Kimliğinizi seçin ve ardından **ayrıntıları görüntüle** düğmesi.  
  
-   Geliştirme için bir iOS cihazı kullanıyorsanız, bir sağlama profili Xcode'da cihazınız için yapılandırılmış.  
  
     Sağlama profilleri oluşturma hakkında ayrıntılı bilgi için bkz: [oluşturma sağlama profilleri kullanma üye Merkezi](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/MaintainingProfiles/MaintainingProfiles.html#//apple_ref/doc/uid/TP40012582-CH30-SW24) iOS Geliştirici Kitaplığı'nda.  
  
-   [Node.js](http://nodejs.org/)  
  
-   Npm güncelleştirilmiş bir sürümü  
  
     Node.js ile birlikte gelen npm sürümü vcremote yüklemek için güncel olmayabilir. Npm güncelleştirmek için Terminal Mac uygulamasını açın ve aşağıdaki komutu girin:  
  
     `sudo npm install -g npm@latest`  
  
##  <a name="Install"></a> İOS için Uzak aracı yükleme  
 Platformlar arası Mobil Geliştirme için Visual C++ yüklediğinizde Visual Studio ile iletişim kurabilir [vcremote](http://go.microsoft.com/fwlink/p/?LinkId=534988), dosyaları aktarmak, yapı ve iOS uygulamanızı çalıştırmak için Mac'inizde çalıştıran uzak bir aracı ve komutları hata ayıklama gönderir.  
  
 Uzak Aracı yüklemeden önce uyduğunuzdan emin olun [Önkoşullar](#Prerequisites) yüklenip [platformlar arası Mobil Geliştirme için Visual C++](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md#InstallTheTools).  
  
###  <a name="DownloadInstall"></a> Uzak Aracı karşıdan yükleyip  
  
-   Mac Terminal uygulamadan girin:  
  
     `sudo npm install -g --unsafe-perm vcremote`  
  
     Genel yükleme (**-g**) anahtar önerilir ancak gerekli değildir.  
  
     Yükleme sırasında vcremote yüklü olduğundan ve Mac üzerinde Geliştirici modu etkinleştirildi [Homebrew](http://brew.sh/) ve iki npm paket, vcremote-lib ve vcremote-yardımcı programları da yüklenir.  
  
    > [!NOTE]
    >  Homebrew yüklemek için sudo (Yönetici) erişimi olmalıdır. Sudo olmadan vcremote yüklemeniz gerekiyorsa, Homebrew usr/yerel konumda el ile yükleyin ve kendi bin klasörü yolunu ekleyin. Daha fazla bilgi için bkz: [Homebrew belgelerine](https://github.com/Homebrew/homebrew/wiki/Installation). Geliştirici modu el ile etkinleştirmek için Terminal uygulamada şu komutu girin: `DevToolsSecurity -enable`  
  
 Visual Studio'nun yeni bir sürüme güncelleştirirseniz, uzak aracı da geçerli sürüme güncelleştirmeniz gerekir. Uzak Aracı güncelleştirmek için karşıdan yükleme ve uzak aracı yüklemek için adımları yineleyin.  
  
##  <a name="Start"></a> Uzak Aracı Başlat  
 Uzak Aracı oluşturmak ve iOS kodunuzu çalıştırmak Visual Studio için çalışıyor olmalıdır. İletişim kurabilir önce visual Studio ile uzak aracı eşleştirilmelidir. Varsayılan olarak, uzak aracı Visual Studio ile kullanmak üzere bir PIN gerektiren güvenli bir bağlantı modunda çalışır.  
  
###  <a name="RemoteAgentStartServer"></a> Uzak Aracı başlatmak için  
  
-   Mac Terminal uygulamadan girin:  
  
     `vcremote`  
  
     Bu bir varsayılan derleme dizini ile uzak aracı başlatır ~ / vcremote. Ek yapılandırma seçenekleri için bkz [Mac Uzak Aracı yapılandırma](#ConfigureMac).  
  
 İlk kez aracısını başlatın ve yeni bir istemci sertifikası oluşturmak istediğiniz zaman aracıyı Visual Studio içinde ana bilgisayar adını, bağlantı noktası ve PIN dahil olmak üzere yapılandırmak için gerekli bilgileri sağlanır.  
  
 ![Güvenli bir PIN oluşturmak için vcremote kullanın](../cross-platform/media/cppmdd_vcremote_generateclientcert.png "CPPMDD_vcremote_generateClientCert")  
  
 Uzak Aracı ana bilgisayar adını kullanarak Visual Studio'da yapılandırmak istiyorsanız, erişilebilir olduğunu doğrulamak için konak adını kullanarak Windows Mac ping işlemi uygulayın. Aksi takdirde, IP adresini kullanmanız gerekebilir.  
  
 Oluşturulan PIN'in bir zaman kullanım içindir ve yalnızca sınırlı bir süre için geçerlidir. Süresi sona ermeden önce Visual Studio ile uzak aracı eşleştirin değil, yeni bir PIN oluşturmak gerekir. Daha fazla bilgi için bkz: [yeni bir güvenlik PIN oluşturmak](#GeneratePIN).  
  
 Güvenli olmayan modda uzak aracı kullanabilirsiniz. Güvenli modda, PIN olmadan Visual Studio uzak aracı eşlenmiş.  
  
#### <a name="to-disable-secured-connection-mode"></a>Güvenli bağlantı modu devre dışı bırakmak için  
  
-   Güvenli bağlantı vcremote modunda devre dışı bırakmak için Mac'inizde Terminal uygulamada şu komutu girin:  
  
     `vcremote --secure false`  
  
#### <a name="to-enable-secured-connection-mode"></a>Güvenli bağlantı modunu etkinleştirmek için  
  
-   Güvenli bağlantı modunu etkinleştirmek için şu komutu girin:  
  
     `vcremote --secure true`  
  
 Uzak Aracı başladıktan sonra siz durduruncaya kadar Visual Studio'dan kullanabilirsiniz.  
  
#### <a name="to-stop-the-remote-agent"></a>Uzak Aracı durdurmak için  
  
-   Terminal penceresi vcremote çalışıyor, girin `Control+C`.  
  
##  <a name="ConfigureVS"></a> Visual Studio'da uzak Aracısı'nı yapılandırma  
 Visual Studio'dan uzak aracıya bağlanmak için Visual Studio seçenekleri Uzaktan yapılandırma belirtmeniz gerekir.  
  
#### <a name="to-configure-the-remote-agent-from-visual-studio"></a>Visual Studio'dan uzak aracısını yapılandırmak için  
  
1.  Aracı Mac'inizde çalışmıyorsa adımları [uzak aracı Başlat](#Start). Mac vcremote başarıyla eşleştirin, bağlanmak ve projenizi derleme Visual Studio için çalışıyor olmalıdır.  
  
2.  Ana bilgisayar adı veya IP adresini Mac Mac'inizde Al  
  
     IP adresi kullanarak alabileceğiniz **ifconfig** bir Terminal penceresi komutu. Etkin ağ arabirimi altında listelenen INet adresi kullanın.  
  
3.  Visual Studio menü çubuğunda seçin **Araçları**, **seçenekleri**.  
  
4.  İçinde **seçenekleri** iletişim kutusunda, genişletin **Çapraz Platform**, **C++**, **iOS**.  
  
5.  İçinde **ana bilgisayar adı** ve **bağlantı noktası** alanları, onu başlatıldığında uzak aracı tarafından belirtilen değerleri girin. Ana bilgisayar adı DNS adı veya IP adresini Mac olabilir 3030 varsayılan bağlantı noktasıdır.  
  
    > [!NOTE]
    >  Ana bilgisayar adını kullanarak Mac ping yapılamıyor, IP adresini kullanmanız gerekebilir.  
  
6.  Varsayılan güvenli bağlantı modunda uzak aracı kullanıyorsanız denetleyin **güvenli** onay kutusunu uzak aracı tarafından belirtilen PIN değeri enter **PIN** alan. Güvenli olmayan bağlantıya modda uzak aracı kullanırsanız temizleyin **güvenli** onay kutusunu bırakıp **PIN** alanı boş.  
  
7.  Seçin **çifti** eşleştirme etkinleştirmek için.  
  
     ![İOS derlemeler için vcremote bağlantı yapılandırma](../cross-platform/media/cppmdd_options_ios.PNG "CPPMDD_Options_iOS")  
  
     Ana bilgisayar adı veya bağlantı noktası değiştirene kadar eşleştirme devam ettirir. İçinde bağlantı noktası veya ana bilgisayar adını değiştirirseniz **seçenekleri** Seç iletişim kutusu, değişikliği geri almak için **Revert** önceki eşleştirme için geri düğmesine.  
  
     Eşleştirmenin başarılı olmazsa, uzak aracı içindeki adımları izleyerek çalıştığını doğrulayın [uzak aracı Başlat](#Start). Uzak Aracı PIN oluşturulan bu yana çok süre geçtiyse, adımları [yeni bir güvenlik PIN oluşturmak](#GeneratePIN) Mac ve yeniden deneyin. Ana bilgisayar adı, Mac kullanıyorsanız IP adresini kullanarak deneyin **ana bilgisayar adı** yerine alan.  
  
8.  Klasör adında güncelleştirme **uzak kök** Mac üzerinde giriş (~) dizininizde uzak aracı tarafından kullanılan klasörü belirtmek için alanını Varsayılan olarak, uzak aracı /Users/ kullanır`username`/vcremote uzak kök olarak.  
  
9. Seçin **Tamam** uzak eşleştirme bağlantı ayarlarını kaydetmek için.  
  
 Visual Studio Mac Uzak aracı her kullanışınızda bağlanmak için aynı bilgileri kullanır. Visual Studio çiftine ile uzak aracı yeniden Mac'inizde yeni bir güvenlik sertifikası oluşturmak ya da kendi ana bilgisayar adı veya IP adresi değişiklikleri sürece gerekmez.  
  
##  <a name="GeneratePIN"></a> Yeni bir güvenlik PIN oluştur  
 Uzak aracı ilk kez başlattığınızda, oluşturulan PIN'in sınırlı bir süre için geçerli olduğu — varsayılan olarak 10 dakika. Süresi sona ermeden önce Visual Studio uzak aracıya eşleştirin yok, yeni bir PIN oluşturmak gerekir.  
  
#### <a name="to-generate-a-new-pin"></a>Yeni bir PIN oluşturmak için  
  
1.  Aracısını durdurun ya da Mac üzerinde ikinci bir Terminal uygulama penceresi açın ve, komut girmek için kullanın.  
  
2.  Bu komut, Terminal uygulamaya girin:  
  
     `vcremote generateClientCert`  
  
     Uzak Aracı yeni bir geçici PIN oluşturur. Yeni PIN kullanarak Visual Studio kullanmak üzere adımlarını yineleyin [Visual Studio'da uzak aracı yapılandırma](#ConfigureVS).  
  
##  <a name="GenerateCert"></a> Yeni bir sunucu sertifikası oluşturma  
 Güvenlik nedeniyle, Visual Studio uzak aracı ile IP adresi veya ana bilgisayar adını, Mac için bağlı bu çifti sunucu sertifikaları Bu değerleri değiştirirseniz, yeni bir sunucu sertifikası oluşturun ve sonra Visual Studio yeni değerlerle yeniden yapılandırmanız gerekir.  
  
#### <a name="to-generate-a-new-server-certificate"></a>Yeni bir sunucu sertifikası oluşturmak için  
  
1.  Vcremote aracısını durdurun.  
  
2.  Bu komut, Terminal uygulamaya girin:  
  
     `vcremote resetServerCert`  
  
3.  Onayınız istendiğinde girin `Y`.  
  
4.  Bu komut, Terminal uygulamaya girin:  
  
     `vcremote generateClientCert`  
  
     Yeni bir geçici PIN oluşturur.  
  
5.  Yeni PIN kullanarak Visual Studio kullanmak üzere adımlarını yineleyin [Visual Studio'da uzak aracı yapılandırma](#ConfigureVS).  
  
##  <a name="ConfigureMac"></a> Uzak Aracı Mac yapılandırın  
 Çeşitli komut satırı seçeneklerini kullanarak uzak aracı yapılandırabilirsiniz. Örneğin, yapı isteklerini dinlemek ve en çok dosya sisteminde korumak için yapı sayısını belirtmek için bağlantı noktası belirtebilirsiniz. Varsayılan sınır 10 derlemeleri'dır. Uzak Aracı kapatma sırasında en büyük değeri aşıyor derlemeleri kaldırır.  
  
#### <a name="to-configure-the-remote-agent"></a>Uzak Aracı yapılandırmak için  
  
-   Uzak Aracı komutlarda Terminal uygulama tam listesini görmek için girin:  
  
     `vcremote --help`  
  
-   Güvenli modu devre dışı bırakın ve basit HTTP tabanlı bağlantıları etkinleştirmek için şunu girin:  
  
     `vcremote --secure false`  
  
     Bu seçeneği kullandığınızda, temizleyin **güvenli** onay kutusunu bırakıp **PIN** aracı Visual Studio'da yapılandırırken alanı boş.  
  
-   Uzak Aracı dosyaları için bir konum belirtmek için şunu girin:  
  
     `vcremote --serverDir directory_path`  
  
     Burada *directory_path* günlük dosyaları, yapılar ve sunucu sertifikaları yerleştirmek için Mac konumunda bulunuyor. Varsayılan olarak, bu /Users/ konumdur*kullanıcıadı*/vcremote. Yapılar, bu konumda yapı numarasına göre düzenlenir.  
  
-   Yakalamak için bir arka plan işlemi kullanılacak `stdout` ve `stderr` server.log adlı bir dosyaya girin:  
  
     `vcremote > server.log 2>&1 &`  
  
     Server.log dosya derleme sorunları gidermenize yardımcı olur.  
  
-   Komut satırı parametreleri yerine bir yapılandırma dosyası kullanarak aracı çalıştırmak için şunu girin:  
  
     `vcremote --config config_file_path`  
  
     Burada *config_file_path* JSON biçiminde bir yapılandırma dosyası yolu. Başlangıç seçenekleri ve bunların değerleri çizgi içermemelidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platformlar Arası Mobil Geliştirme için Visual C++’ı yükleme](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)