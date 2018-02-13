---
title: "Yayımla Sayfası, Proje Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.PropertyPage
helpviewer_keywords:
- Project Designer, Publish page
- Publish page in Project Designer
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d9f050662ed38814920e17b36f77bf6795aabfa9
ms.sourcegitcommit: 238cd48787391aa0ed1eb684f3f04e80f7958705
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2018
---
# <a name="publish-page-project-designer"></a>Yayın Sayfası, Proje Tasarımcısı
**Yayımla** sayfasında **Proje Tasarımcısı** ClickOnce dağıtım özelliklerini yapılandırmak için kullanılır.  
  
 Erişim için **Yayımla** sayfası, proje düğümü seçin **Çözüm Gezgini**ve ardından **proje** menüsünde tıklatın **özellikleri**. Zaman **Proje Tasarımcısı** görünen tıklatın **Yayımla** sekmesi.  
  
> [!NOTE]
>  Burada açıklanan ClickOnce özelliklerden bazıları da ayarlanabilir **PublishWizard**, kullanılabilir **yapı** menü veya tıklatarak **PublishWizard** bu düğmesi Sayfa.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Yayımlama klasörü konumu**  
 Uygulama burada yayımlanır konumunu belirtir. Bir sürücü yolu olabilir (`C:\deploy\myapplication`), bir dosya paylaşımı (`\\server\myapplication`), ya da bir FTP sunucusu (`ftp://ftp.microsoft.com/myapplication`). Metin mevcut olması gerektiğini unutmayın **yayımlama konumu** Gözat sırayla kutusunda (**...** ) düğmesinin çalışması için.  
   
 **Yükleme klasörü URL'si**  
 İsteğe bağlı. Kullanıcıların uygulamayı yüklemek için Git bir Web sitesini belirtir. Bu yalnızca zaman onu farklı gereklidir **yayımlama konumu**, örneğin, ne zaman uygulama yayımlanır bir basamak sunucusuna.  
  
 **Yükleme modu ve ayarlar**  
 Uygulamayı doğrudan çalıştırılıp çalıştırılmadığını belirleyen **yayımlama konumu** (zaman **uygulama yalnızca çevrimiçi kullanılabilir** seçilidir) veya yüklü ve eklenen **Başlat**  menü ve **Program Ekle veya Kaldır** öğesi **Denetim Masası** (zaman **uygulama de çevrimdışı kullanılabilir** seçilir).  
  
 WPF Web tarayıcısı uygulamaları için **uygulama de çevrimdışı kullanılabilir** seçeneği devre dışıdır, çünkü bu tür uygulamalar yalnızca çevrimiçi kullanılabilir durumdadır.  
  
 **Uygulama dosyaları**  
 Tek tek dosyaların nasıl ve nerede yüklendiğini belirtmek için kullanılan uygulama dosyaları iletişim kutusunu açar.  
  
 **Önkoşullar**  
 İle birlikte uygulamanın yüklenmesi için .NET Framework gibi önkoşul bileşenleri belirtmek için kullanılan Önkoşullar iletişim kutusu açılır.  
  
 **Güncelleştirmeler**  
 Uygulama için güncelleştirme davranışını belirtmek için kullanılan uygulama güncelleştirmeleri iletişim kutusunu açar. Kullanılabilir olduğunda **uygulama yalnızca çevrimiçi kullanılabilir** seçilir.  
  
 **Seçenekler**  
 Ek Gelişmiş yayımlama seçeneklerini belirtmek için kullanılan Yayımla Seçenekleri iletişim kutusunu açar.  
  
 **Sürüm yayımlayın.**  
 Uygulama için yayımlama sürüm numarasını ayarlar; sürüm numarasını değiştirildiğinde, uygulama bir güncelleştirme olarak yayımlanır. Yayımla sürümünü her parçası (**ana**, **küçük**, **yapı**, **düzeltme**) 65355 en büyük değerini olabilir (<xref:System.UInt16.MaxValue>), tarafından izin verilen maksimum <xref:System.Version>.  
  
 ClickOnce kullanarak bir uygulama birden fazla sürümünü yüklediğinizde, yükleme uygulamanın önceki sürümleri arşivindeki belirttiğiniz yayımlama konumu adlı bir klasöre taşır. Bu şekilde tutar önceki sürümlerde yükleme dizinini temizleyin önceki sürümünden klasörlerinin arşivleme.  
  
 **Her Yayımla düzeltmelerle otomatik olarak Artır**  
 İsteğe bağlı. Bu seçeneği seçili olduğunda (varsayılan), **düzeltme** Yayımla sürüm numarası parçası tarafından artırılır uygulama yayımlanan her zaman. Bu, bir güncelleştirme olarak yayımlanan uygulamaya neden olur.  
  
 **Yayımlama Sihirbazı**  
 Açılır Yayımlama Sihirbazı. Yayımlama Sihirbazı Tamamlanıyor çalışan aynı etkiye sahip **Yayımla** komutunu **yapı** menüsü.  
  
 **Şimdi Yayımla**  
 Geçerli ayarları kullanarak uygulamayı yayımlar. Eşdeğer **son** düğmesini **PublishWizard**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Nasıl yapılır: Visual Studio dosyaları nereye kopyalayacağını belirtme](../../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [Nasıl yapılır: Burada son kullanıcıların yükleme yapacakları konumu belirtin](../../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)   
 [Nasıl yapılır: teknik destek için bir bağlantı belirtin](../../deployment/how-to-specify-a-link-for-technical-support.md)   
 [Nasıl yapılır: ClickOnce çevrimdışı belirtin veya çevrimiçi yükleme modunu](../../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)   
 [Nasıl yapılır: CD yüklemeleri için AutoStart'ı etkinleştirme](../../deployment/how-to-enable-autostart-for-cd-installations.md)   
 [Nasıl yapılır: kümesi ClickOnce yayım sürümünü](../../deployment/how-to-set-the-clickonce-publish-version.md)   
 [Nasıl yapılır: otomatik olarak artırma ClickOnce yayım sürümünü](../../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [Nasıl yapılır: ClickOnce tarafından hangi dosyaların yayımlandığını belirtme](../../deployment/how-to-specify-which-files-are-published-by-clickonce.md)   
 [Nasıl yapılır: ClickOnce uygulamasıyla Önkoşulları Yükleme](../../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce uygulaması için güncelleştirmeleri yönetme](../../deployment/how-to-manage-updates-for-a-clickonce-application.md)   
 [Nasıl yapılır: değişiklik ClickOnce uygulaması için yayımlama dili](../../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce uygulaması için Başlat menüsü adı belirtin](../../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce uygulaması için bir yayımlama sayfası belirtme](../../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)   
 [ClickOnce Güvenliği ve Dağıtımı](../../deployment/clickonce-security-and-deployment.md)
