---
title: Yükleme ve Visual Studio ve Azure Hizmetleri Güvenlik Duvarı veya proxy sunucunun arkasında kullanma | Microsoft Docs
description: Etki alanı URL'leri, bağlantı noktalarını ve beyaz liste ile istediğiniz olabilir veya kuruluşunuzun bir güvenlik duvarı veya proxy sunucusu kullanıyorsa açmak protokolleri gözden geçirin
ms.custom: ''
ms.date: 02/12/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs
ms.assetid: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 304c31a9cfd389bb3a5af6b1a8191f41d881165b
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/14/2018
---
# <a name="install-and-use-visual-studio-and-azure-services-behind-a-firewall-or-proxy-server"></a>Yükleme ve Visual Studio ve Azure Hizmetleri Güvenlik Duvarı veya proxy sunucunun arkasında kullanma

Sizin veya kuruluşunuzun bir güvenlik duvarı veya proxy sunucu gibi güvenlik önlemleri kullanıyorsa, ardından vardır "beyaz liste" ve bağlantı noktaları ve böylece yüklediğinizde ve görsel Stu en iyi deneyimi sahip açmak isteyebilirsiniz protokolleri isteyebilirsiniz etki alanı URL'leri dio ve Azure Hizmetleri.

* **[Visual Studio yükleme](#install-visual-studio)**: tüm bileşenleri ve istediğiniz iş yüklerini erişiminiz beyaz liste etki alanı URL'lere bu tablolar içerir.

* **[Visual Studio ve Azure hizmetlerini kullanma](#use-visual-studio-and-azure-services)**: Bu tablo beyaz liste ve bağlantı noktalarını ve protokolleri tüm özellikleri ve istediğiniz hizmetleri erişiminiz açmak için etki alanı URL'lere içerir.

## <a name="install-visual-studio"></a>Visual Studio yükleme

### <a name="urls-to-whitelist"></a>Beyaz liste URL'leri

Visual Studio yükleyicisi dosyaları çeşitli etki alanlarına ve indirme sunucularını yüklediği için kullanıcı Arabirimi veya dağıtım betikleri güvenilir olarak beyaz liste isteyebilirsiniz etki alanı URL'leri aşağıda verilmiştir.

#### <a name="microsoft-domains"></a>Microsoft etki alanları

| Etki Alanı | Amaç |
| ------ | ------- |
| go.microsoft.com | Kurulum URL çözümleme |
| aka.MS | Kurulum URL çözümleme |
| download.VisualStudio.microsoft.com | Paketleri indirme konumu Kurulumu |
| download.microsoft.com | Paketleri indirme konumu Kurulumu |
| download.VisualStudio.com | Paketleri indirme konumu Kurulumu |
| DL.xamarin.com | Paketleri indirme konumu Kurulumu |
| visualstudiogallery.msdn.microsoft.com | Visual Studio uzantıları konumu indirin |
| www.visualstudio.com | Belge konumu |
| docs.microsoft.com | Belge konumu |
| MSDN.microsoft.com | Belge konumu |
| www.microsoft.com | Belge konumu |
| *.windows.net | Oturum açma konumu |
| *.microsoftonline.com | Oturum açma konumu |
| *.live.com | Oturum açma konumu |
|  |  | |

#### <a name="non-microsoft-domains"></a>Microsoft olmayan etki alanları

| Etki Alanı | Bu iş yükleri yükler |
| ------ | ------- |
| Archive.apache.org |  JavaScript (Cordova) ile Mobil Geliştirme |
| cocos2d-x.org | C++ (Cocos) ile oyun geliştirme |
| download.epicgames.com | C++ (Unreal Engine) ile oyun geliştirme |
| download.Oracle.com | JavaScript (Java SDK) ile Mobil Geliştirme <br /><br />.NET ile mobil geliştirme (Java SDK'sı) |
| download.unity3d.com | Unity (Unity) ile oyun geliştirme |
| netstorage.unity3d.com | Unity (Unity) ile oyun geliştirme |
| DL.Google.com | JavaScript (Android SDK ve NDK, öykünücüsü) ile Mobil Geliştirme <br /><br />.NET (Android SDK ve NDK, öykünücüsü) ile Mobil Geliştirme |
| www.incredibuild.com | C++ (IncrediBuild) ile oyun geliştirme |
| incredibuildvs2017i.azureedge.net | C++ (IncrediBuild) ile oyun geliştirme |
| www.python.org | Python geliştirme (Python) <br /><br />Veri bilimi ve analitik uygulamaları (Python) |
|  |  | |

## <a name="use-visual-studio-and-azure-services"></a>Visual Studio ve Azure Hizmetleri kullanın

### <a name="urls-to-whitelist-and-ports-and-protocols-to-open"></a>Beyaz liste ve bağlantı noktalarını ve protokolleri açmak için URL'leri

Bir güvenlik duvarı veya proxy sunucunun arkasındaki Visual Studio ya da Azure hizmetlerini kullanırken gereken her şeyi erişiminiz olduğundan emin olmak için beyaz liste ve bağlantı noktalarını ve protokolleri açmak isteyebilirsiniz gereken URL'leri şunlardır.

| Hizmet veya senaryosu | DNS uç noktası | Protokol | Bağlantı Noktası | Açıklama |
| --- | --- | --- | --- | --- |
| URL<br>çözüm | go.microsoft.com<br><br>aka.MS | | |Uzun URL'ler çözmek URL'leri kısaltmak için kullanılan
| Başlangıç Sayfası | vsstartpage.blob.core.windows.net | | 443| Geliştirici Visual Studio Başlangıç sayfası gösterilir haberleri görüntülemek için kullanılır |
| Hedeflenen<br> Bildirim <br>Hizmet | targetednotifications.azurewebsites.NET <br><br>www.research.net | | 80<br><br>443| Bildirimler yalnızca belirli türleri makineler/kullanım senaryoları için geçerli bir liste için genel bir listesini filtrelemek için kullanılır |
| Uzantısı <br>Güncelleştirme denetimi | visualstudiogallery.msdn.microsoft.com<br><br>&#42;. windows.net <br>&#42;.microsoftonline.com <br>&#42;. live.com  | | 443 | Yüklenmiş bir uzantı kullanılabilir bir güncelleştirme olduğunda bildirimleri sağlamak için kullanılan <br><br> Bir oturum açma konumu olarak kullanılır|
| AI proje <br>Tümleştirme | az861674.vo.msecnd.net  | | 443<br> | Kayıtlı Application Insights hesabınıza kullanım verileri göndermek için yeni projeler yapılandırmak için kullanılan |
| Kod Mercek | codelensprodscus1su0.app.<br>codelens.visualstudio.com | |443 | Düzenleyicisi bir dosyayı en son güncelleştirildiği, değişiklikleri zaman çizelgesi, değişiklikleri ilişkili iş öğeleri, yazarlar ve hakkında daha fazla bilgi sağlamak üzere kullanılır|
|Deneysel <br>özelliğini etkinleştirme  | visualstudio-devdiv-c2s.msedge.net | |80 | Özellik değişiklikleri veya Deneysel yeni özellikleri etkinleştirmek için kullanılan |
| Kimliği "rozeti" <br>(kullanıcı adı ve avatar)<br>and <br>Dolaşım ayarları | app.vssps.visualstudio.com <br><br>app.vsspsext.visualstudio.com<br><br>app.vssps.visualstudio.com<br><br> ns-sb2-prod-ch1-002.cloudapp.net <br><br>az700632.vo.msecnd.net  | |443 | Kullanıcının kullanıcı adı ve avatar IDE içinde görüntülemek için kullanılır <br><br> Ayarı değişiklikleri bir makineden diğerine dolaşan olduğundan emin olmak için kullanılır |
| Uzak bağlantı ayarları | az700632.vo.msecnd.net | | 443| Visual Studio'da sorunlara neden bilinen uzantıları devre dışı bırakmak için kullanılan   |
| Windows Araçları | Developer.microsoft.com <br><br>dev.windows.com  <br><br>appdev.microsoft.com |HTTPS |443 | Windows uygulama mağazası senaryoları için kullanılır  |
| JSON şeması <br>Bulma <br><br>JSON şeması <br>Tanım<br><br>JSON şeması <br>Desteği <br>Azure kaynakları| JSON.schemastore.org <br>schemastoreorg.azurewebsites.NET<br><br>JSON schema.org<br><br>schema.management.azure.com| http<br>HTTPS<br><br>http<br><br>HTTPS |80<br>443 <br><br> 443<br><br>443 | Bul ve kullanıcı JSON belgeleri düzenlerken kullanabilir JSON şemaları indirmek için kullanılan <br><br>JSON meta doğrulama şeması elde etmek üzere kullanılır<br><br>Azure Resource Manager dağıtım şablonları için geçerli şema elde etmek üzere kullanılır|
| NPM paket <br>keşif  |Skimdb.npmjs.com <br><br>Registry.npmjs.org <br><br>Api.npms.io  | HTTPS<br><br>HTTP/s<br><br>HTTPS | 443<br><br>80/443<br><br>443| NPM paketler için arama için gerekli ve istemci tarafı komut dosyası paketinin yüklenmesi web projelerinde kullanılır |
|Bower paketi<br> simgeler<br><br>Bower paketi <br>search  |Bower.io <br><br>bowercache.azurewebsites.net <br>go.microsoft.com <br>Registry.bower.io | http<br><br>HTTPS<br>http<br>HTTPS|80<br><br>443<br>80<br>443 |Varsayılan bower paket simgesi sağlar  <br><br>Bower paketler için arama özelliğini sağlar |
|NuGet<br><br>NuGet paketi<br> keşif | Api.nuget.org <br>www.nuget.org <br>Nuget.org<br><br>crl3.digicert.com <br>crl4.digicert.com <br>OCSP.digicert.com <br>cacerts.digicert.com  | HTTPS<br><br>HTTP/s |443<br><br>80/443<br> |İmzalı NuGet paketlerini doğrulamak için kullanılır.<br><br>NuGet paketlerini ve sürümleri için arama yapmak için gerekli |
|GitHub depo bilgileri  |api.github.com  |HTTPS | 443| Bower paketler hakkında ek bilgi almak için gerekli |
| Web Linters|Eslint.org<br><br>www.Bing.com <br><br>www.coffeelint.org  | http|80 | |
| Cookiecutter<br>Explorer şablonu<br>keşif <br><br>Cookiecutter <br>Proje Gezgini<br> Oluşturma | api.github.com <br>RAW.githubusercontent.com <br>go.microsoft.com<br><br>pypi.org <br> pypi.Python.org  | HTTPS | 443<br> | Çevrimiçi Şablonlar bizim önerilen besleme ve github depolarının keşfetmek için kullanılan <br><br>Bir kerelik cookiecutter Python paket Python paket dizinini (Pypı) isteğe bağlı yüklemesi gerektiren cookiecutter şablonu bir proje oluşturmak için kullanılan|
| Python paket <br>keşif<br><br>Python paket <br>yönetim<br><br>Python <br>Yeni Proje <br>templates| pypi.org<br> <br>pypi.Python.org <br>Bootstrap.pypa.io<br><br>go.microsoft.com| HTTPS| 443| PIP paketler için arama özelliğini sağlar<br><br>Eksik ise pip otomatik olarak yüklemek için kullanılan <br><br> Oluşturmak için kullanılan <br><br>Proje şablonları cookiecutter şablonu URL'lere yeni proje iletişim kutusunda aşağıdaki Python çözmek için kullanılır:<br> -Sınıflandırıcı proje<br>-Proje kümeleme <br> -Regression proje <br> -PyGame PyKinect kullanma <br> -Pyvot proje |
| Office web <br>eklentisi <br> Bildirimi <br>Doğrulama <br>Hizmet | verificationservice.osi.office.net | HTTPS | 443 | Office web eklentiler için bildirimler doğrulamak için kullanılır |
| SharePoint ve <br>Office eklentileri | SharePoint.com | HTTPS | 443 | Yayımlama ve SharePoint ve Office eklentileri SharePoint Online'a sınamak için kullanılan |
| İş Akışı Yöneticisi <br>Test hizmeti<br> Ana bilgisayar |  | http | 12292 | İş akışları ile SharePoint eklentileri test etmek için otomatik olarak oluşturulan bir güvenlik duvarı kuralı |
| Otomatik olarak toplanan <br>Güvenilirlik istatistikleri <br>ve diğer <br>Müşteri Deneyimi <br>Geliştirme programlar (CEIP)<br> Azure SDK'sı ve <br>için SQL araçları <br><br> | vortex.data.microsoft.com<br> <br>dc.services.visualstudio.com |HTTPS | 443| Güvenilirlik istatistikleri (kilitlenme/yanıt vermemesine veriler) kullanıcıdan Microsoft'a göndermek için kullanılır. Windows hata bildirimi etkinse, gerçek kilitlenme/yanıt vermemesine dökümleri hala karşıya yüklenecek; yalnızca istatistiksel bilgileri gizlenir; <br>Visual Studio Araçları SQL için anonim kullanım desenlerini Visual Studio Azure Araçları SDK uzantısı ve kullanım düzenlerini ortaya çıkarmak için kullanılan |
| Visual Studio <br> Müşteri Deneyimi <br>Geliştirme Programı (CEIP) <br><br>PerfWatson.exe | vortex.data.microsoft.com<br>dc.services.visualstudio.com<br>visualstudio-devdiv-c2s.msedge.net<br>az667904.vo.msecnd.net <br>scus-breeziest-in.cloudapp.net<br> | HTTPS| 443 | Anonim kullanım desenlerini ve hata günlükleri toplamak için kullanılan <br><br>UI dondurma sorunları izlemek için kullanılır|
| Oluşturma ve<br>Yönetimi <br>Azure kaynakları | Management.Azure.com <br>Management.Core.Windows.NET   | HTTPS | 443 | Web uygulamaları, Azure işlevleri veya Web işleri yayımlama desteklemek için Azure Web siteleri veya diğer kaynakları oluşturmak için kullanılır |
| Güncelleştirilmiş web tooling yayımlama <br>Denetim ve uzantısı <br>Önerileri  | marketplace.visualstudio.com  <br> visualstudiogallery.msdn.microsoft.com  | HTTPS | 443 | İçin kullanılabilirliğini denetlemek için kullanılan güncelleştirilmiş araç yayımlayın. Devre dışı bırakılırsa, uzantı Web'de yayımlama için önerilen olası görüntülenmeyebilir |
| Güncelleştirilmiş Azure kaynak <br>Uç nokta bilgileri oluşturma  | *.blob.core.windows.net | HTTPS | 443 | Azure kaynakları oluşturma belirli Azure Hizmetleri için kullanılan uç noktalarını güncelleştirmek için kullanılır. Devre dışı bırakılırsa, en son indirilen veya konumlar yerine kullanılır uç yerleşik |
| Uzaktan hata ayıklama ve <br>Uzaktan profil oluşturma <br>Azure Web siteleri | &#42;. cloudapp.net <br> &#42;. azurewebsites.net | | 4022 | Uzaktan hata ayıklayıcı Azure Web siteleri'ne eklemek için kullanılır. Devre dışı bırakılırsa, Azure Web siteleri için uzaktan hata ayıklayıcı ekleme çalışmaz |
| Active Directory <br>Grafik | Graph.Windows.NET | HTTPS | 443 | Yeni Azure Active Directory uygulamaları sağlamak için kullanılır. Ayrıca Office 365 MSGraph - bağlı hizmeti sağlayıcısı tarafından kullanılır |
| Azure işlevleri <br>CLI güncelleştirme <br>Onay | functionscdn.azureedge.net | HTTPS | 443 | Azure işlevleri CLI güncelleştirilmiş sürümlerini denetlemek için kullanılır. Devre dışı bırakılırsa, önbelleğe alınmış kopyasını (veya Azure işlevleri bileşen tarafından gerçekleştirilen kopya) CLI bunun yerine kullanılacak |
| Cordova | npmjs.org<br>gradle.org | HTTP/s | 80/443 | HTTP kullanılır Gradle derleme sırasında; yüklemeleri için HTTPS projelerinde Cordova eklenti eklemek için kullanılır|
| Bulut Gezgini | 1. &#60;clusterendpoint&#62; <br>Service Fabric <br>2. &#60;yönetim uç noktası&#62;<br>Genel bulut Exp <br>3. &#60;uç nokta grafiği&#62;<br>Genel bulut Exp<br>4. &#60;depolama hesabı uç noktası&#62;<br>Depolama düğümleri <br>5. &#60;azure portalı URL'leri&#62;<br>Genel bulut Exp <br>6. &#60;anahtar kasası uç noktaları&#62; <br>Azure Kaynak Yöneticisi'ni VM düğümleri<br>7. &#60;PublicIPAddressOfCluster&#62;<br>Service Fabric uzaktan hata ayıklama ve ETW izlemeleri |   <br>1. https<br>2. https<br>3. https<br>4. https<br>5. https<br>6. https<br>7: tcp| 1. 19080<br>2. 443 <br>3. 443 <br>4. 443 <br>5. 443 <br>6. 443 <br>7. dinamik   | 1. Örnek: test12.eastus.cloudapp.com<br>2. Abonelikleri alır ve Azure kaynaklarını alır/yönetir<br>3. Azure yığın abonelikleri alır.<br>4. Depolama kaynaklarını yönetir (örnek: mystorageaccount.blob.core.windows.net)<br>5. "Portalı'nda Aç" bağlam menüsü seçeneğini (Azure portalında bir kaynak açılır)<br>6. Oluşturur ve VM hata ayıklama için anahtar kasalarını kullanır (örnek: myvault.vault.azure.net) <br><br>7. Dinamik olarak küme ve kullanılabilir bağlantı noktaları düğüm sayısına dayalı olarak bağlantı noktaları bloğunu ayırır. <br><br>Bir bağlantı noktası bloğu ile en az 10 bağlantı noktaları düğüm sayısını üç kez almaya çalışır.<br><br>Akış izlemeleri için 810 bağlantı noktası blok almak için bir deneme yapılır. Bu bağlantı noktası blok hiçbirini zaten kullanılıyor, girişiminde sonraki bloğu almak ve benzeri için yapılır. (810 bağlantı noktalarından büyük olasılıkla kullanılır, yük dengeleyici boştur) <br><br>Benzer şekilde, hata ayıklama için bağlantı noktalarını blokları dört kümesini ayrılmıştır: <br>-connectorPort: 30398, <br>-forwarderPort: 31398, <br>-forwarderPortx86: 31399,<br>-fileUploadPort: 32398<br>|
| Bulut Hizmetleri | 1. RDP<br><br>2. core.windows.net <br><br>3. management.azure.com<br> Management.Core.Windows.NET <br><br>4. &#42;. blob.core.windows.net <br>&#42;. queue.core.windows.net<br>&#42;. table.core.windows.net <br><br>5. portal.azure.com <br><br>6. &#60;kullanıcının bulut hizmeti&#62;. cloudapp.net <br> &#60;kullanıcının VM&#62;. &#60;bölge&#62;. azure.com | 1. rdp <br><br> 2. https <br><br> 3. https <br><br> 4. https <br><br> 5. https <br><br>6. tcp | 1. 3389 <br><br> 2. 443 <br><br> 3. 443 <br><br>4. 443 <br><br>5. 443 <br><br> 6. bir) 30398 <br> 6. b) 30400 <br> 6. c) 31398 <br> 6. d) 31400 <br> 6. e) 32398 <br> 6. f) 32400 | 1.  Bulut Hizmetleri VM için Uzak Masaüstü <br><br> 2.  Depolama hesabı bileşeni özel tanılama yapılandırması <br><br> 3.  Azure portalı <br><br> 4. Sunucu Gezgini - Azure depolama &#42; müşteri depolama hesabı adı  <br><br> 5.  Portalı'nı açmak için bağlantılar &#47; abonelik sertifikası indir &#47; yayımlama ayarları dosyası <br><br>6. bir) Bağlayıcısı bulut hizmeti ve VM için uzaktan hata ayıklama için yerel bağlantı noktası<br> 6. b) bulut hizmeti ve VM için uzaktan hata ayıklama için bağlayıcı genel bağlantı noktası <br> 6. c) ileticisi bulut hizmeti ve VM için uzaktan hata ayıklama için yerel bağlantı noktası <br> 6. d) bulut hizmeti ve VM için uzaktan hata ayıklama ileticisi genel bağlantı noktası  <br> 6. e) dosya yükleyici bulut hizmeti ve VM için uzaktan hata ayıklama için yerel bağlantı noktası <br> 6. f) dosya yükleyici bulut hizmeti ve VM için uzaktan hata ayıklama için genel bağlantı noktası |
| Service Fabric | 1. <br>OCS. Microsoft.com<br>aka.MS <br>go.microsoft.com <br><br>2. <br>vssftools.blob.core.windows.net <br>Vault.azure.com <br>Portal.azure.com <br><br> 3. &#42; vault.azure.net<br><br> 4. <br>app.vsaex.visualstudio.com<br>&#42;. vsspsext.visualstudio.com<br>clouds.vsrm.visualstudio.com <br>clouds.visualstudio.com<br>app.vssps.visualstudio.com <br>&#42;. visualstudio.com | HTTPS | 443 | 1. Belgeler <br><br> 2. Küme özellik oluşturma <br><br>3. &#42; Azure anahtar kasası adı (örnek:-test11220180112110108.vault.azure.net  <br><br>  4. &#42; Dinamiktir (örnek: vsspsextprodch1su1.vsspsext.visualstudio.com) |
| Anlık Görüntü <br>Hata ayıklayıcı | 1. go.microsoft.com <br>2. management.azure.com <br> 3. &#42;azurewebsites.net <br> 4. &#42;scm.azurewebsites.net<br>5. api.nuget.org/v3/index.json <br>6. msvsmon | 1. https <br>2. https  <br>3. http <br>4. https <br>5. https <br>6. Concord <br> | 1. 443<br> 2. 443<br>3. 80  <br>4. 443<br> 5. 443<br> 6. 4022 (visual Studio sürümü bağımlı) | 1. Uygulama hizmeti SKU boyutunu .json dosyası sorgulama <br>2. Çeşitli Azure RM çağrıları <br>3. Site Isınma çağrısıyla  <br>4. Müşteri App Service Kudu endpoint hedeflenen <br>5. Nuget.org içinde yayımlanan sorgu Site uzantısı sürümü <br>6. Uzaktan hata ayıklama kanal |
|Azure akış analizi <br><br>Hdınsight | Management.Azure.com |HTTPS|443 |Görüntülemek, gönderme, çalıştırmak ve ASA işleri yönetmek için kullanılır <br><br> HDI kümeleri göz atın ve göndermek için kullanılan, tanılama ve HDI işleri hata ayıklama |
| Azure Data Lake | &#42;. azuredatalakestore.net <br>&#42;.azuredatalakeanalytics.net | HTTPS | 443 | Derleme, gönderme, görüntülemek, tanılama ve işleri hata ayıklamak için kullanılır. ADLS dosyalara göz atmak için kullanılır. dosyaları yükleme ve indirme için kullanılır |
|Paketleme hizmeti | [hesap].visualstudio.com <br/> [hesap].*.visualstudio.com <br/> *.blob.core.windows.net <br/> registry.npmjs.org </br> nodejs.org <br/> dist.nuget.org <br/> nuget.org | HTTPS | 443 | *. Npmjs.org, *. nuget.org, ve *. nodejs.org, yalnızca belirli görev senaryoları oluşturmak için gereken (örneğin: NuGet aracı yükleyicisi, düğüm aracı Yükleyici) veya ortak upstreams akışlarınızı ile kullanmak istiyorsanız. Diğer üç etki alanı paketleme hizmet çekirdek işlevleri için gereklidir. |
|||||||

## <a name="troubleshoot-network-related-errors"></a>Ağ ile ilgili hataları giderme

Yüklediğinizde veya bir güvenlik duvarı veya proxy sunucunun Visual Studio'yu kullanın bazı durumlarda, ağ veya proxy ile ilgili hataları çalışmasında. Bu tür hata iletileri için çözümleri hakkında daha fazla bilgi için bkz: [yüklediğinizde veya Visual Studio kullandığınızda ağ ile ilgili sorun giderme](troubleshooting-network-related-errors-in-visual-studio.md) sayfası.

## <a name="get-support"></a>Destek alma

Sizin için birkaç daha fazla destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunlarını izlemek ve yanıtlar bulmak [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio'da ağ ile ilgili sorun giderme hataları](troubleshooting-network-related-errors-in-visual-studio.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Visual Studio 2017 yükleyin](install-visual-studio.md)
