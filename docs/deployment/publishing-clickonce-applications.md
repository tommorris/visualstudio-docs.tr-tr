---
title: "ClickOnce uygulamalarını yayımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "22"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 35d642256a199c8ee5bf5e67a6a0bfb414b9fccc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
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
|[Nasıl yapılır: Visual Studio dosyaları nereye kopyalayacağını belirtme](../deployment/how-to-specify-where-visual-studio-copies-the-files.md)|Visual Studio bildirimleri ve uygulama dosyalarını yere koyar ayarlanacağını açıklar.|  
|[Nasıl yapılır: Burada son kullanıcıların yükleme yapacakları konumu belirtin](../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)|Kullanıcılar uygulamayı indirmek ve yüklemek için nereye konumun nasıl ayarlanacağını açıklar.|  
|[Nasıl yapılır: ClickOnce çevrimdışı belirtin veya çevrimiçi yükleme modunu](../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)|Uygulama çevrimiçi veya çevrimdışı kullanılabilir olacak ayarlanacağını açıklar.|  
|[Nasıl yapılır: kümesi ClickOnce yayım sürümünü](../deployment/how-to-set-the-clickonce-publish-version.md)|ClickOnce ayarlamayı açıklar **yayımlama sürümü** yayımladığınız uygulama bir güncelleştirme olarak kabul edilip edilmeyeceğini belirler özelliği.|  
|[Nasıl yapılır: otomatik olarak artırma ClickOnce yayım sürümünü](../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)|Otomatik olarak düzeltme sayısını artırmak açıklar **PublishVersion** her uygulama yayımlayın.|  
  
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
|[Nasıl yapılır: değişiklik ClickOnce uygulaması için yayımlama dili](../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)|Bir dil ve kültür yerelleştirilmiş sürümle eşleştirmek üzere belirtileceğini açıklar.|  
|[Nasıl yapılır: ClickOnce uygulaması için Başlat menüsü adı belirtin](../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)|ClickOnce uygulaması için görünen adını değiştirmek açıklar.|  
|[Nasıl yapılır: teknik destek için bir bağlantı belirtin](../deployment/how-to-specify-a-link-for-technical-support.md)|Nasıl ayarlanacağını açıklar **destek URL'si** bir Web sayfası veya kullanıcılar nereye uygulama hakkında bilgi almak için dosya paylaşımı tanımlayan özelliği.|  
|[Nasıl yapılır: ClickOnce dağıtımı'nda bağımsız Önkoşullar için destek URL'sini belirtin](../deployment/how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment.md)|Bir uygulama bildirimi her önkoşul için tek tek destek URL'leri el ile değiştirmek nasıl gösterilmektedir.|  
|[Nasıl yapılır: ClickOnce uygulaması için bir yayımlama sayfası belirtme](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)|Oluştur ve varsayılan bir Web sayfası (publish.htm) yanı sıra uygulama yayımlama açıklanmaktadır|  
|[Nasıl yapılır: ClickOnce Varsayılan Web sayfasını özelleştirme](../deployment/how-to-customize-the-default-web-page-for-a-clickonce-application.md)|Otomatik olarak oluşturulan ve uygulamayı ile birlikte yayımlanan Web sayfasının nasıl özelleştirileceği açıklanır.|  
|[Nasıl yapılır: CD yüklemeleri için AutoStart'ı etkinleştirme](../deployment/how-to-enable-autostart-for-cd-installations.md)|Ortam eklendiğinde ClickOnce uygulaması otomatik olarak başlatılması için Otomatik Başlat'ı etkinleştirmek açıklar.|  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: ClickOnce uygulaması için dosya ilişkilendirmeleri oluşturma](../deployment/how-to-create-file-associations-for-a-clickonce-application.md)|ClickOnce uygulaması için dosya adı uzantısı desteği eklemeyi açıklar.|  
|[Nasıl yapılır: bir çevrimiçi ClickOnce uygulamasında sorgu dize bilgilerini alma](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)|ClickOnce uygulamasını çalıştırmak için kullanılan URL'de geçirilen parametrelerin nasıl alınacağını gösterir.|  
|[Nasıl yapılır: tasarımcıyı kullanarak ClickOnce uygulamalarında URL etkinleştirmeyi devre dışı](../deployment/how-to-disable-url-activation-of-clickonce-applications-by-using-the-designer.md)|Uygulamayı başlatmak için zorlama açıklar **Başlat** tasarımcıyı kullanarak menüsü.|  
|[Nasıl yapılır: ClickOnce uygulamalarında URL etkinleştirmeyi devre dışı bırak](../deployment/how-to-disable-url-activation-of-clickonce-applications.md)|Uygulamayı başlatmak için zorlama açıklar **Başlat** menüsü.|  
|[İzlenecek yol: ClickOnce dağıtım Tasarımcısı'nı kullanarak API'si ile isteğe bağlı derlemeleri indirme](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)|Yalnızca ilk Tasarımcısı'nı kullanarak uygulama tarafından kullanıldığında, bunların uygulama derlemeleri karşıdan açıklanmaktadır.|  
|[İzlenecek yol: ClickOnce dağıtım API'si ile isteğe bağlı derlemeleri indirme](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Yalnızca ilk uygulama tarafından kullanıldığında, bunların uygulama derlemeleri karşıdan açıklanmaktadır.|  
|[İzlenecek yol: ClickOnce dağıtım API'si ile uydu derlemelerini indirme](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)|Uydu derlemelerini isteğe bağlı olarak işaretler ve bir istemci makine bilgisayarın geçerli kültür ayarları için ihtiyaç duyduğu derlemeyi yüklemek açıklar.|  
|[İzlenecek yol: Bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)|.NET Framework yardımcı programlarını ClickOnce uygulamanızı dağıtmak için nasıl kullanılacağını açıklar.|  
|[İzlenecek yol:, Yeniden imzalama gerektirmeyen ve marka bilgisini koruyan bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information.md)|.NET Framework yardımcı programlarını bildirimleri yeniden imzalamadan ClickOnce uygulamanızı dağıtmak için nasıl kullanılacağını açıklar.|  
|[Nasıl yapılır: projeleri hedef platformlar için yapılandırma](../ide/how-to-configure-projects-to-target-platforms.md)|Bir 64-bit işlemci için değiştirerek nasıl yayımlayacağınızı açıklar **hedef CPU** veya **Platform hedefi** projenizdeki özelliği.|  
|[İzlenecek yol: Bir ClickOnce uygulamasını birden çok .NET Framework sürümleri üzerinde çalıştırmak için etkinleştirme](http://msdn.microsoft.com/en-us/7f4383af-ed87-4853-b4d4-02a3967a5fd9)|Yüklemek ve NET Framework birden fazla sürümünü çalıştırmak bir ClickOnce uygulamasını etkinleştirecek açıklanmaktadır.|  
|[İzlenecek yol: ClickOnce uygulaması için özel bir yükleyici oluşturma](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)|Bir ClickOnce uygulamasını yüklemek için özel bir yükleyici oluşturma açıklanmaktadır.|  
|[Nasıl yapılır: görsel stiller etkinken WPF uygulaması yayımlama](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md)|Görsel stillerin etkin kıldığı bir WPF uygulamasını yayımlamak istediğinizde görüntülenen bir hatayı gidermek için adım adım yönergeler sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce Başvurusu](../deployment/clickonce-reference.md)