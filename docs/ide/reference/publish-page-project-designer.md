---
title: Yayın Sayfası, Proje Tasarımcısı
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.PropertyPage
helpviewer_keywords:
- Project Designer, Publish page
- Publish page in Project Designer
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c323fd5f5f54bbc5c53934505c43dd20a9d58591
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31950497"
---
# <a name="publish-page-project-designer"></a>Yayın Sayfası, Proje Tasarımcısı
**Yayımla** sayfasında **Proje Tasarımcısı** ClickOnce dağıtım özelliklerini yapılandırmak için kullanılır.

 Erişim için **Yayımla** sayfası, proje düğümü seçin **Çözüm Gezgini**ve ardından **proje** menüsünde tıklatın **özellikleri**. Zaman **Proje Tasarımcısı** görünen tıklatın **Yayımla** sekmesi.

> [!NOTE]
> Burada açıklanan ClickOnce özelliklerden bazıları da ayarlanabilir **PublishWizard**, kullanılabilir **yapı** menü veya tıklatarak **PublishWizard** bu düğmesi Sayfa.


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

- [ClickOnce Uygulamalarını Yayımlama](../../deployment/publishing-clickonce-applications.md)
- [Nasıl yapılır: Yayımlama Sihirbazını Kullanarak ClickOnce Uygulaması Yayımlama](../../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)
- [Nasıl yapılır: Visual Studio'nun Dosyaları Nereye Kopyalayacağını Belirtme](../../deployment/how-to-specify-where-visual-studio-copies-the-files.md)
- [Nasıl yapılır: Son Kullanıcıların Yükleme Yapacakları Konumu Belirtme](../../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)
- [Nasıl yapılır: Teknik Destek için bir Bağlantı Belirtme](../../deployment/how-to-specify-a-link-for-technical-support.md)
- [Nasıl yapılır: ClickOnce Çevrimdışı veya Çevrimiçi Yükleme Modunu Belirtme](../../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)
- [Nasıl yapılır: CD Yüklemeleri için AutoStart'ı Etkinleştirme](../../deployment/how-to-enable-autostart-for-cd-installations.md)
- [Nasıl yapılır: ClickOnce Yayım Sürümü'nü Ayarlama](../../deployment/how-to-set-the-clickonce-publish-version.md)
- [Nasıl yapılır: ClickOnce Yayım Sürümünü Otomatik Olarak Artırma](../../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)
- [Nasıl yapılır: ClickOnce Tarafından Hangi Dosyaların Yayımlandığını Belirtme](../../deployment/how-to-specify-which-files-are-published-by-clickonce.md)
- [Nasıl yapılır: ClickOnce Uygulamasıyla Önkoşulları Yükleme](../../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)
- [Nasıl yapılır: ClickOnce Uygulaması için Güncelleştirmeleri Yönetme](../../deployment/how-to-manage-updates-for-a-clickonce-application.md)
- [Nasıl yapılır: ClickOnce Uygulaması için Yayımlama Dilini Değiştirme](../../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)
- [Nasıl yapılır: ClickOnce Uygulaması için Başlat Menüsü Adı Belirtme](../../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)
- [Nasıl yapılır: ClickOnce Uygulaması için bir Yayımlama Sayfası Belirtme](../../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)
- [ClickOnce Güvenliği ve Dağıtımı](../../deployment/clickonce-security-and-deployment.md)
