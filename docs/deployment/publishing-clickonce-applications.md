---
title: ClickOnce uygulamalarını yayımlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Options
- Microsoft.VisualStudio.Publish.ClickOnceProvider.PublishWizard.Help
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, publishing
- ClickOnce applications, publishing
- applications [Visual Studio], ClickOnce deployment
- deploying applications [ClickOnce], publishing ClickOnce applications
ms.assetid: eb6dfe79-f54c-4331-8e36-073688e70973
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a5f0c04a23844664b5bbfa67a6e83809c250b8a9
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="publishing-clickonce-applications"></a>ClickOnce Uygulamalarını Yayımlama
Yayımlama sırasında bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ilk kez uygulama yayımlama özellikleri Yayımlama Sihirbazı'nı kullanarak ayarlayabilirsiniz. Yalnızca birkaç özellikleri Sihirbazı'nda bulunur; diğer tüm özellikleri varsayılan değerlerine ayarlanır.  
  
 Üzerinde yapılan özelliklerini yayımlamak için sonraki değişiklikler **Yayımla** sayfasındaki **Proje Tasarımcısı**.  
  
## <a name="publish-wizard"></a>Yayımlama Sihirbazı  
 Uygulamanızı yayımlamak için temel ayarları ayarlamak için Yayımlama Sihirbazı'nı kullanabilirsiniz. Bu, aşağıdaki yayımlama özellikleri içerir:  
  
-   Klasör konumu - Visual Studio (yerel bilgisayar, ağ dosya paylaşımı, FTP sunucusu veya Web sitesi) dosyaları nerede kopyalayacak yayımlama  
  
-   Yükleme klasörü konumu - son kullanıcıların yükleme (ağ dosya paylaşımı, FTP sunucusu, Web sitesi, CD/DVD kaynağı)  
  
-   Son kullanıcıların bir ağ bağlantısı olan veya olmayan uygulama erişebiliyorsa çevrimiçi veya çevrimdışı kullanılabilirliği-  
  
-   Güncelleştirme sıklığı - ne sıklıkta uygulama için yeni güncelleştirmeleri denetler.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
## <a name="publish-page"></a>Yayımla Sayfası  
 **Yayımla** sayfasında **Proje Tasarımcısı** ClickOnce dağıtım özelliklerini yapılandırmak için kullanılır. Aşağıdaki tablo konuları listeler  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: Visual Studio'nun Dosyaları Nereye Kopyalayacağını Belirtme](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)|Visual Studio bildirimleri ve uygulama dosyalarını yere koyar ayarlanacağını açıklar.|  
|[Nasıl yapılır: Son Kullanıcıların Yükleme Yapacakları Konumu Belirtme](../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)|Kullanıcılar uygulamayı indirmek ve yüklemek için nereye konumun nasıl ayarlanacağını açıklar.|  
|[Nasıl yapılır: ClickOnce Çevrimdışı veya Çevrimiçi Yükleme Modunu Belirtme](../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)|Uygulama çevrimiçi veya çevrimdışı kullanılabilir olacak ayarlanacağını açıklar.|  
|[Nasıl yapılır: ClickOnce Yayım Sürümü'nü Ayarlama](../deployment/how-to-set-the-clickonce-publish-version.md)|ClickOnce ayarlamayı açıklar **yayımlama sürümü** yayımladığınız uygulama bir güncelleştirme olarak kabul edilip edilmeyeceğini belirler özelliği.|  
|[Nasıl yapılır: ClickOnce Yayım Sürümünü Otomatik Olarak Artırma](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)|Otomatik olarak düzeltme sayısını artırmak açıklar **PublishVersion** her uygulama yayımlayın.|  
  
 Daha fazla bilgi için bkz: [Yayımla Sayfası, Proje Tasarımcısı](../ide/reference/publish-page-project-designer.md)  
  
### <a name="application-files-dialog-box"></a>Uygulama dosyaları iletişim kutusu  
 Bu iletişim kutusu projenizi dosyalarında yayımlama, dinamik karşıdan yükleme ve güncelleştirme için kategorilendirilmiş belirtmenize olanak sağlar. Varsayılan olarak dışarıda değil veya bir indirme grubuna sahip proje dosyalarını listeleyen bir kılavuz içerir.  
  
 Dosyaları dışlamak için dosyaları veri dosyası veya önkoşul işaretlemek ve Visual STUDİO'da koşullu yüklemek için dosya grubu oluşturmak için bkz [nasıl yapılır: belirtin, dosyaları yayımlanır ClickOnce tarafından](../deployment/how-to-specify-which-files-are-published-by-clickonce.md). Mage.exe kullanarak veri dosyalarını da işaretleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulamasına bir veri dosyası dahil](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md).  
  
### <a name="prerequisites-dialog-box"></a>Önkoşullar İletişim Kutusu  
 Bu iletişim kutusu yüklendikleri nasıl hangi önkoşul bileşenlerinin de yüklüyse, belirtir. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulamasına Önkoşullar yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md) ve [Önkoşullar iletişim kutusu](../ide/reference/prerequisites-dialog-box.md).  
  
### <a name="application-updates-dialog-box"></a>Uygulama güncelleştirmeleri iletişim kutusu  
 Bu iletişim kutusu, uygulamayı yükleme güncelleştirmeleri nasıl denetleyeceğini belirtir. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulaması için güncelleştirmeleri yönetme](../deployment/how-to-manage-updates-for-a-clickonce-application.md).  
  
### <a name="publish-options-dialog-box"></a>Yayımla Seçenekleri iletişim kutusu  
 Yayımla Seçenekleri iletişim kutusu, bir uygulamanın dağıtım seçeneklerini belirtir.  
  
|||  
|-|-|  
|[Nasıl yapılır: ClickOnce Uygulaması için Yayımlama Dilini Değiştirme](../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)|Bir dil ve kültür yerelleştirilmiş sürümle eşleştirmek üzere belirtileceğini açıklar.|  
|[Nasıl yapılır: ClickOnce Uygulaması için Başlat Menüsü Adı Belirtme](../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)|ClickOnce uygulaması için görünen adını değiştirmek açıklar.|  
|[Nasıl yapılır: Teknik Destek için bir Bağlantı Belirtme](../deployment/how-to-specify-a-link-for-technical-support.md)|Nasıl ayarlanacağını açıklar **destek URL'si** bir Web sayfası veya kullanıcılar nereye uygulama hakkında bilgi almak için dosya paylaşımı tanımlayan özelliği.|  
|[Nasıl yapılır: Bir ClickOnce Dağıtımı'nda Bağımsız Önkoşullar için Destek URL'sini Belirtme](../deployment/how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment.md)|Bir uygulama bildirimi her önkoşul için tek tek destek URL'leri el ile değiştirmek nasıl gösterilmektedir.|  
|[Nasıl yapılır: ClickOnce Uygulaması için bir Yayımlama Sayfası Belirtme](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)|Oluştur ve varsayılan bir Web sayfası (publish.htm) yanı sıra uygulama yayımlama açıklanmaktadır|  
|[Nasıl yapılır: ClickOnce Varsayılan Web sayfasını özelleştirme](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)|Otomatik olarak oluşturulan ve uygulamayı ile birlikte yayımlanan Web sayfasının nasıl özelleştirileceği açıklanır.|  
|[Nasıl yapılır: CD Yüklemeleri için AutoStart'ı Etkinleştirme](../deployment/how-to-enable-autostart-for-cd-installations.md)|Ortam eklendiğinde ClickOnce uygulaması otomatik olarak başlatılması için Otomatik Başlat'ı etkinleştirmek açıklar.|  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: ClickOnce Uygulaması için Dosya İlişkilendirmeleri Oluşturma](../deployment/how-to-create-file-associations-for-a-clickonce-application.md)|ClickOnce uygulaması için dosya adı uzantısı desteği eklemeyi açıklar.|  
|[Nasıl yapılır: Çevrimiçi bir ClickOnce Uygulamasında Sorgu Dize Bilgilerini Alma](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)|ClickOnce uygulamasını çalıştırmak için kullanılan URL'de geçirilen parametrelerin nasıl alınacağını gösterir.|  
|[Nasıl yapılır: Tasarımcıyı Kullanarak ClickOnce Uygulamalarında URL Etkinleştirmeyi Devre Dışı Bırakma](../deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer.md)|Uygulamayı başlatmak için zorlama açıklar **Başlat** tasarımcıyı kullanarak menüsü.|  
|[Nasıl yapılır: ClickOnce Uygulamalarında URL Etkinleştirmeyi Devre Dışı Bırakma](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)|Uygulamayı başlatmak için zorlama açıklar **Başlat** menüsü.|  
|[İzlenecek yol: Tasarımcıyı Kullanarak ClickOnce Dağıtım API'si ile İsteğe Bağlı Derlemeleri İndirme](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)|Yalnızca ilk Tasarımcısı'nı kullanarak uygulama tarafından kullanıldığında, bunların uygulama derlemeleri karşıdan açıklanmaktadır.|  
|[İzlenecek yol: ClickOnce Dağıtım API'si ile İsteğe Bağlı Derlemeleri İndirme](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Yalnızca ilk uygulama tarafından kullanıldığında, bunların uygulama derlemeleri karşıdan açıklanmaktadır.|  
|[İzlenecek yol: ClickOnce Dağıtım API'si ile Uydu Derlemelerini İndirme](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Uydu derlemelerini isteğe bağlı olarak işaretler ve bir istemci makine bilgisayarın geçerli kültür ayarları için ihtiyaç duyduğu derlemeyi yüklemek açıklar.|  
|[İzlenecek yol: ClickOnce Uygulamasını El ile Dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)|.NET Framework yardımcı programlarını ClickOnce uygulamanızı dağıtmak için nasıl kullanılacağını açıklar.|  
|[İzlenecek yol: Yeniden İmzalama Gerektirmeyen ve Marka Bilgisini Koruyan bir ClickOnce Uygulamasını El ile Dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md)|.NET Framework yardımcı programlarını bildirimleri yeniden imzalamadan ClickOnce uygulamanızı dağıtmak için nasıl kullanılacağını açıklar.|  
|[Nasıl Yapılır: Projeleri Hedef Platformlar İçin Yapılandırma](../ide/how-to-configure-projects-to-target-platforms.md)|Bir 64-bit işlemci için değiştirerek nasıl yayımlayacağınızı açıklar **hedef CPU** veya **Platform hedefi** projenizdeki özelliği.|  
|[İzlenecek yol: Bir ClickOnce uygulamasını birden çok .NET Framework sürümleri üzerinde çalıştırmak için etkinleştirme](http://msdn.microsoft.com/en-us/7f4383af-ed87-4853-b4d4-02a3967a5fd9)|Yüklemek ve NET Framework birden fazla sürümünü çalıştırmak bir ClickOnce uygulamasını etkinleştirecek açıklanmaktadır.|  
|[İzlenecek Yol: ClickOnce Uygulaması için Özel bir Yükleyici Oluşturma](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)|Bir ClickOnce uygulamasını yüklemek için özel bir yükleyici oluşturma açıklanmaktadır.|  
|[Nasıl yapılır: Görsel Stiller Etkinken WPF Uygulaması Yayımlama](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md)|Görsel stillerin etkin kıldığı bir WPF uygulamasını yayımlamak istediğinizde görüntülenen bir hatayı gidermek için adım adım yönergeler sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce Başvurusu](../deployment/clickonce-reference.md)