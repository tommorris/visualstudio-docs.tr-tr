---
title: Sunucu ve istemci yapılandırma sorunları ClickOnce dağıtımlarında | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications, ClickOnce
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
- Windows applications, ClickOnce deployments
ms.assetid: 929e5fcc-dd56-409c-bb57-00bd9549b20b
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 11cc26689b20f989cb449f67387052caf3096811
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="server-and-client-configuration-issues-in-clickonce-deployments"></a>ClickOnce Dağıtımlarında Sunucu ve İstemci Yapılandırma Sorunları
Windows Server Internet Information Services (IIS) kullanın ve dağıtımınız Windows tanımadığı bir dosya türü içeriyorsa, bir Microsoft Word dosyası gibi dosya aktarmak IIS reddeder ve dağıtımınız başarısız olur.  
  
 Ayrıca, bazı Web sunucuları ve uygulama yazılımı gibi Web [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], dosyaların bir listesini içeren ve dosya türleri karşıdan yükleyemiyor. Örneğin, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] tüm Web.config dosyalarının indirilmesini engeller. Bu dosyalar kullanıcı adları ve parolalar gibi hassas bilgiler içerebilir.  
  
 Bu kısıtlama çekirdek karşıdan yüklemek için bir soruna neden olmaz ancak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dosyaları bildirimleri ve derlemeler gibi bu kısıtlama engelleyebilir parçası olarak dahil edilen veri dosyalarının yüklenmesini, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. İçinde [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], bu tür dosyaları IIS Yapılandırma Yöneticisi'nden indirme yasaklayan işleyiciyi kaldırarak bu hatayı çözebilirsiniz. Ek bilgi için IIS server belgelerine bakın.  
  
 Bazı Web sunucuları .dll, .config ve .mdf gibi uzantılara sahip dosyaları engelleyebilir. Windows tabanlı uygulamalar genellikle bazı uzantılara sahip dosyaları içerir. Bir kullanıcı çalıştırmayı denediğinde, bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bir Web sunucusu üzerinde engellenen bir dosyaya erişen uygulama, bir hata oluşur. Tüm dosya uzantıları, kaldırma yerine [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] varsayılan olarak her uygulama dosyasını ".deploy" dosya uzantısına sahip yayımlar. Bu nedenle, yöneticinin yalnızca aşağıdaki üç dosya uzantıları engellemesini kaldırmak için Web sunucusunu yapılandırma gerekir:  
  
-   .Application  
  
-   .manifest  
  
-   .deploy  
  
 Ancak, bu seçeneğin işaretini kaldırarak devre dışı bırakabilirsiniz **".deploy" dosya uzantısını kullanan** seçeneği [yayımlama Seçenekler iletişim kutusu](http://msdn.microsoft.com/en-us/fd9baa1b-7311-4f9e-8ffb-ae50cf110592), bu durumda, tüm dosya uzantılarını engellemesini kaldırmak için Web sunucusu yapılandırmanız gerekir uygulamada kullanılır.  
  
 Burada yüklemediğiniz IIS kullanıyorsanız .manifest ve .application .deploy, örneğin, yapılandırma gerekir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], veya başka bir Web sunucusu (örneğin, Apache) kullanıyorsanız.  
  
## <a name="clickonce-and-secure-sockets-layer-ssl"></a>ClickOnce ve Güvenli Yuva Katmanı (SSL)  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama düzgün çalışır SSL üzerinden Internet Explorer SSL sertifikası hakkında bir istem zaman görüntülemesi dışında. Bir sorun olduğunda site adları eşleşmiyor gibi bir sertifika veya sertifika süresi doldu olduğunda istemi yükseltilebilir. Yapmak için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bir SSL bağlantısı üzerinden çalışma, sertifikanın güncel olduğundan ve sertifika verileri site verilerini eşleştiğinden emin olun.  
  
## <a name="clickonce-and-proxy-authentication"></a>ClickOnce ve Proxy kimlik doğrulaması  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] .NET Framework 3. 5 ' başlayarak Windows tümleşik proxy kimlik doğrulaması için destek sağlar. Hiçbir özel machine.config yönergeleri gerekli değildir. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Temel veya Özet gibi diğer kimlik doğrulama protokolleri için destek sağlamaz.  
  
 Ayrıca, bu özelliği etkinleştirmek için .NET Framework 2.0 için bir düzeltme uygulayabilirsiniz. Daha fazla bilgi için bkz. http://go.microsoft.com/fwlink/?LinkId=158730.  
  
 Daha fazla bilgi için bkz: [ \<defaultProxy > öğesi (ağ ayarları)](/dotnet/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings).  
  
## <a name="clickonce-and-web-browser-compatibility"></a>ClickOnce ve Web tarayıcı uyumluluğu  
 Şu anda [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] yüklemeleri yalnızca dağıtım bildirimi URL'si, Internet Explorer kullanarak açılırsa başlayacaktır. Yalnızca Internet Explorer varsayılan Web tarayıcısı olarak ayarlandıysa, URL Microsoft Office Outlook gibi başka bir uygulamadan başlatılan bir dağıtım başarıyla başlatılacaktır.  
  
> [!NOTE]
>  Mozilla Firefox dağıtım sağlayıcısı boş değilse veya Microsoft .NET Framework Assistant uzantısı yüklü desteklenir. Bu uzantı, .NET Framework 3.5 SP1 ile paketlenmiştir. XBAP desteği NPWPF eklentisi ihtiyaç duyulduğunda etkinleştirilir.  
  
## <a name="activating-clickonce-applications-through-browser-scripting"></a>ClickOnce uygulamalarını tarayıcısı komut dosyası aracılığıyla etkinleştirme  
 Geliştirilmiş başlatır özel bir Web sayfası, bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] etkin komut dosyası kullanarak uygulama uygulamanın bazı makinelerde başlatmaz bulabilirsiniz. Internet Explorer içeriyor olarak adlandırılan bir ayar **dosya yüklemeleri için otomatik olarak sor**, bu davranışı etkiler. Bu ayar kullanılabilir **güvenlik** sekmesinde kendi **seçenekleri** bu davranışı etkileyen menüsü. Çağrılır **dosya yüklemeleri için otomatik olarak sor**, altında listelenen ve **indirmeleri** kategorisi. Özellik kümesine **etkinleştirmek** için ve intranet Web sayfaları için varsayılan **devre dışı** Internet Web sayfaları için varsayılan olarak. Ne zaman bu ayar **devre dışı**, yapmaya etkinleştirmek bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama programlı olarak (örneğin, gerçekleşen tarafından `document.location` özelliği) engellenir. Bu durumda, kullanıcılar uygulamaları yalnızca kullanıcı tarafından başlatılan bir indirme aracılığıyla Örneğin, uygulamanın URL için ayarlanmış bir köprüyü tıklatarak başlatabilirsiniz.  
  
## <a name="additional-server-configuration-issues"></a>Ek sunucu yapılandırma sorunları  
  
##### <a name="administrator-permissions-required"></a>Yönetici izinleri gerekli  
 HTTP ile yayımlıyorsanız hedef sunucuda yönetici izinleri olmalıdır. IIS bu izin düzeyini gerektirir. HTTP kullanarak yayımlamadığında, yalnızca hedef yolda yazma izni.  
  
##### <a name="server-authentication-issues"></a>Sunucu kimlik doğrulama sorunları  
 "Adsız erişim devre dışı" uzak bir sunucuya yayımladığınızda, aşağıdaki uyarı alırsınız:  
  
```  
"The files could not be downloaded from http://<remoteserver>/<myapplication>/.  The remote server returned an error: (401) Unauthorized."  
```  
  
> [!NOTE]
>  Bir site varsayılan kimlik bilgilerinizi dışında kimlik bilgileri ister ve güvenlik iletişim kutusunda, tıklatın, NTLM (NT Sınama yanıtı) kimlik doğrulaması çalışması yapabilirsiniz **Tamam** sorulduğunda sağlanan kaydetmek istiyorsanız sonraki oturumlar için kimlik bilgileri. Ancak, bu geçici çözüm için temel kimlik doğrulaması çalışmaz.  
  
## <a name="using-third-party-web-servers"></a>Üçüncü taraf Web sunucularını kullanma  
 Dağıtıyorsanız bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama IIS dışında bir Web sunucusundan, sorun yaşayabilirsiniz sunucu anahtarı için yanlış içerik türü döndürmesi durumunda [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi ve uygulama bildirimi gibi dosyalar. Bu sorunu gidermek için sunucuya yeni içerik türlerini ekleyin ve tüm dosya adı uzantısı eşlemeler aşağıdaki tabloda listelenen emin olmak nasıl hakkındaki belgeler yerinde olduğundan, Web sunucunuzun Yardım'a bakın.  
  
|Dosya adı uzantısı|İçerik türü|  
|-------------------------|------------------|  
|`.application`|`application/x-ms-application`|  
|`.manifest`|`application/x-ms-manifest`|  
|`.deploy`|`application/octet-stream`|  
|`.msu`|`application/octet-stream`|  
|`.msp`|`application/octet-stream`|  
  
## <a name="clickonce-and-mapped-drives"></a>ClickOnce ve eşlenen sürücüler  
 ClickOnce uygulaması yayımlama için Visual Studio kullanırsanız, eşlenmiş sürücü yükleme konumu olarak belirtemezsiniz. Ancak, eşlenmiş sürücüden Bildirim oluşturucu ve düzenleyici (Mage.exe ve MageUI.exe) kullanarak yüklemek için ClickOnce uygulaması değiştirebilirsiniz. Daha fazla bilgi için bkz: [Mage.exe (bildirim üretme ve düzenleme aracı)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) ve [MageUI.exe (bildirim üretme ve düzenleme aracı, grafik istemci)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client).  
  
## <a name="ftp-protocol-not-supported-for-installing-applications"></a>FTP protokolünü uygulamaları yüklemek için desteklenmiyor  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] herhangi bir HTTP 1.1 Web sunucusu veya dosya sunucusu uygulamaları yüklemeyi destekler. FTP, Dosya Aktarım Protokolü, uygulamaları yüklemek için desteklenmiyor. FTP yalnızca uygulamaları yayımlamak için kullanabilirsiniz. Aşağıdaki tabloda bu farklar özetlenmektedir:  
  
|URL türü|Açıklama|  
|--------------|-----------------|  
|FTP: / /|Yayımlayabilirsiniz bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bu protokolü kullanarak uygulama.|  
|http://|Yükleyebileceğiniz bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bu protokolü kullanarak uygulama.|  
|https://|Yükleyebileceğiniz bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bu protokolü kullanarak uygulama.|  
|File://|Yükleyebileceğiniz bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bu protokolü kullanarak uygulama.|  
  
## <a name="windows-xp-sp2-windows-firewall"></a>Windows XP SP2: Windows Güvenlik Duvarı'nı  
 Varsayılan olarak, Windows XP SP2, Windows Güvenlik Duvarı'nı etkinleştirir. Windows XP'nin yüklü olduğu bir bilgisayarda uygulamanızı geliştiriyorsanız, yayımlama ve çalıştırmak koruyabilmeyi [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] IIS çalıştıran yerel sunucu uygulamalardan. Ancak, Windows Güvenlik Duvarı'nı açmazsanız, IIS çalıştıran başka bir bilgisayardan o sunucuya erişemez. Windows Güvenlik Duvarı'nı yönetme hakkında yönergeler için bkz.  
  
## <a name="windows-server-enable-frontpage-server-extensions"></a>Windows Server: FrontPage sunucu uzantılarını etkinleştirme  
 Microsoft FrontPage Server Extensions HTTP kullanan bir Windows Web server yayımlama uygulamaları için gereklidir.  
  
 Varsayılan olarak, Windows Server yüklü FrontPage Server Extensions sahip değil. Kullanmak istiyorsanız, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] FrontPage Server Extensions ile HTTP kullanan bir Windows Server Web sunucusuna yayımlamak için FrontPage Server Extensions önce yüklemelisiniz. Windows Server'da sunucunuzu yönetin Yönetim Aracı'nı kullanarak yükleme gerçekleştirebilirsiniz.  
  
## <a name="windows-server-locked-down-content-types"></a>Windows Server: Kilitli içerik türleri  
 IIS üzerinde [!INCLUDE[WinXPSvr](../debugger/includes/winxpsvr_md.md)] belirli bilinen içerik türleri (örneğin, .htm, .html, .txt ve benzeri) dışında tüm dosya türlerini kilitler. Dağıtımını etkinleştirmek için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamalar, bu sunucu kullanılarak .application, .manifest ve uygulamanız tarafından kullanılan başka bir özel dosya türleri dosyaların yüklenmesine izin verecek IIS ayarlarını değiştirmeniz gerekebilir.  
  
 Bir IIS sunucusu kullanarak dağıtırsanız, inetmgr.exe çalıştırın ve yeni dosya türleri için varsayılan Web Sayfası Ekle:  
  
-   .Application ve .manifest uzantıları için MIME türü "application/x-ms-application." olmalıdır. Diğer dosya türleri için MIME türü "application/octet-stream." olmalıdır  
  
-   Uzantısı ile bir MIME türü oluşturursanız, "*" ve MIME türü "application/octet-stream" indirilmesi engellenmemiş dosya türlerinin sağlayacaktır. (Ancak, dosya türleri Örneğin, .aspx ve .asmx indirilemiyor engellenen.)  
  
 Windows Server'da MIME türlerini yapılandırma ile ilgili ayrıntılı yönergeler için Microsoft Bilgi Bankası makalesi KB326965, "IIS 6.0 mu değil hizmet bilinmeyen MIME türleri" başvurun [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 326965](http://support.microsoft.com/default.aspx?scid=kb;en-us;326965).  
  
## <a name="content-type-mappings"></a>İçerik türü eşlemeleri  
 HTTP üzerinden yayımlarken, içerik türü (MIME türü olarak da bilinir) .application dosyası için "application/x-ms-application." olması gerekir Varsa [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] sunucuda yüklüyse, bu sizin için otomatik olarak ayarlanır. Bu yüklü değil ise sonra bir MIME türü ilişkilendirmesini oluşturmanıza gerek [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulaması vroot (veya tüm sunucu).  
  
 Bir IIS sunucusu kullanarak dağıtırsanız, inetmgr.exe çalıştırın ve yeni bir içerik türü "application/x-ms-application".application uzantısı ekleyin.  
  
## <a name="http-compression-issues"></a>HTTP sıkıştırma sorunları  
 İle [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], gerçekleştirebilirsiniz HTTP sıkıştırmasına indirmeler, akış istemciye göndermeden önce bir veri akışını sıkıştırmak için GZIP algoritmasını kullanan bir Web sunucusu teknolojisi. İstemci — bu durumda, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]— dosyaları okumadan önce akışı açar.  
  
 IIS kullanıyorsanız, HTTP sıkıştırma kolayca etkinleştirebilirsiniz. HTTP sıkıştırmasını etkinleştirdiğinizde, ancak yalnızca belirli dosya türleri için etkin — yani, HTML ve metin dosyaları. Derlemeler (.dll) için sıkıştırmayı etkinleştirmek için XML (.xml), dağıtım bildirimleri (.application) ve uygulama bildirimleri (.manifest), bu dosya türlerini IIS'nin sıkıştırmasını türlerinin bir listesini eklemeniz gerekir. Dağıtımınız için dosya türlerini ekleyene kadar yalnızca metin ve HTML dosyaları sıkıştırılır.  
  
 IIS için ayrıntılı yönergeler için bkz: [HTTP sıkıştırma için ek belge türlerini belirleme konusunda](http://go.microsoft.com/fwlink/?LinkId=178459).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce dağıtım sorunlarını giderme](../deployment/troubleshooting-clickonce-deployments.md)   
 [ClickOnce dağıtım stratejisini seçme](../deployment/choosing-a-clickonce-deployment-strategy.md)   
 [Uygulama Dağıtımının Önkoşulları](../deployment/application-deployment-prerequisites.md)