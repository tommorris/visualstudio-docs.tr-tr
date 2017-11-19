---
redirect_url: shell/visual-studio-shell-integrated
title: "Visual Studio Kabuğu (tümleşik) | Microsoft Docs"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, integrated mode features
- Shell [Visual Studio], integrated mode features
ms.assetid: 0b40d495-f17f-4bb9-ace8-b365a7172784
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0d92a6c7250e22972a2b352b74b974601ff6065c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-shell-integrated"></a>Visual Studio Kabuğu (tümleşik)
Visual Studio tümleşik Kabuk tümleşik geliştirme ortamı (IDE), hata ayıklayıcı ve kaynak denetimi tümleştirmesi içerir. Hiçbir programlama dili dahil edilir. Ancak, tümleşik kabuk programlama dilleri eklemenize olanak sağlayan bir çerçeve sağlar.  
  
 Visual Studio tümleşik Kabuk gerçekte bir yalıtılmış Visual Studio Kabuğu'nu artı tümleşik Kabuk belirli bileşenlerini içeren bir ek yükleme birleşimidir.  Tümleşik Kabuk uygulamanızı hem yalıtılmış Kabuk yeniden dağıtılabilir paketi içermelidir [Microsoft Visual Studio Kabuğu (Yalýtýlmýþ) yeniden dağıtılabilir paketi](http://go.microsoft.com/fwlink/?LinkId=616022) yanı sıra tümleşik Kabuk yeniden dağıtılabilir paketi gelen [Microsoft Visual Studio Kabuğu (tümleşik) yeniden dağıtılabilir paketi](http://go.microsoft.com/fwlink/?LinkId=616021).  
  
> [!NOTE]
>  Yalıtılmış ve tümleşik Kabuk yeniden dağıtılabilir paketleri erişebilmeniz için önce bir kısa müşteri araştırması doldurmak için istenir.  Out anket doldurduktan sonra yeniden dağıtılabilir paketi yükleme bağlantıları ile Visual Studio bağlanmak sayfasına yönlendirilirsiniz.  Visual Studio Connect sitesindeki altında için sonraki ziyaretlerinizde indirme bağlantıları bulabilirsiniz **programları &#124; VISUAL STUDIO 2015 TÜMLEŞİK ve YALITILMIŞ KABUK** sekmesi.  
  
 Tümleşik Kabuk uygulamanızı Visual Studio tam bir sürümünü aynı bilgisayara yüklerseniz, uygulamanızın bileşenleri doğrudan Visual Studio'ya entegre.  
  
## <a name="features-in-the-integrated-shell"></a>Tümleşik Kabuk özellikleri  
  
|||  
|-|-|  
|Özellik alanı|Özellik|  
|Dil Desteği|-Yok|  
|IDE|<ul><li>Ayarlar<br /><br /> <ul><li>Ayarları oluştur</li><li>İçeri ve dışarı aktarma ayarları</li><li>Ayarlarını Sıfırla</li></ul></li><li>**Araç kutusu** tümleştirme</li><li>**Görev listesi** tümleştirme</li><li>Yardım Tümleştirme</li><li>**Seçenekler** iletişim kutusu</li><li>Yazı tipleri ve renkler Yönetimi</li><li>**Çıktı** penceresi</li><li>**Komut** penceresi</li><li>Pencere Yönetimi</li><li>Komutlar, menüler ve anahtar bağlama</li><li>Etki alanına özgü dil (DSL) çalışma zamanı</li></ul>|  
|Proje sistemi ve proje türleri|-Çözümleri ve çözüm klasörleri<br />-Çözüm Yapılandırma Yöneticisi<br />-Öğesi yönetimi<br />-Single-project ve birden çok proje çözümleri<br />-Uygulama Tasarımcısı (Basitleştirilmiş Proje Özellikleri)<br />-Web Başvurusu Ekle<br />-Hizmet Başvurusu Ekle<br />Single-project<br />-Web sitesi proje türleri<br />-Web uygulama projeleri|  
|Derleme|-IDE özel derleme adımları<br />-Ön derleme fikri mülkiyet (IP) koruma<br />-Kod imzalama<br />     MSBuild|  
|Düzenleyici|-Kod Tarama Araçları (Birleşik bulma, kaynak tanımı, devralma)<br />-Kod gezinme<br />-IntelliSense<br />-Akıllı etiketler<br />-Yeniden düzenleme<br />-Asıl listeleme<br />-IntelliSense filtreleme<br />-   **Kod tanımı** penceresi|  
|Tasarımcı|-Windows Presentation Foundation Tasarımcısı<br />-Windows Form Tasarımcısı<br />-Web Tasarımcısı ve HTML düzenleyicisi|  
|Veri|-   **Sunucu Gezgini** (Basitleştirilmiş: yalnızca veri). Bkz. Not 1.<br />-   **Veri kaynakları** penceresi<br />-Veri denetimleri tam kümesi<br />-XML Düzenleyicisi<br />-Veri bağlamak için yerel veri kaynağı (. MDF veya. MDB)<br />-Veri nesnesine bağlama<br />-Veri Web hizmetine bağlama<br />-Yerel veritabanı sunucusuna veri bağlama<br />-Uzak veritabanı sunucusuna veri bağlama<br />-Uzak Veri için DDL araçları<br />-   **Sunucu Gezgini** genişletilebilirlik ([!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] örnekleri)|  
|Hata ayıklayıcı|-Yerel hata ayıklama. Bkz. Not 2.<br />-Yönetilen hata ayıklama<br />-Yerel hata ayıklama<br />-Yerel işlem ekleme<br />-Uzak işlem ekleme<br />-Anonim temsilci<br />-Uygulama etki alanları<br />-ASPX hata ayıklama<br />-Öznitelikleri<br />-Break Func-değerlendirme sırasında<br />-Kesme noktaları<br />-Kesme noktası kısıtlamaları<br />-Çağrı yığını<br />-   **Komut** penceresi<br />-İş parçacıkları arası hata ayıklama<br />-Veri ipuçları<br />-Veri Görselleştirici<br />-Yönetilen hata ayıklama Yardımcıları (Mda'lar) hata ayıklayıcı desteği<br />-Tür ileticisi hata ayıklayıcı desteği<br />-OTB DTEEvents desteği<br />-JMC Adımlayıcı<br />-Hata ayıklayıcı AppID test (DBGCLR)<br />-Hata ayıklayıcı profili<br />-Hata ayıklayıcı Araçlar ve Seçenekler<br />-Yineleyici hata ayıklama<br />-Tasarım zamanı ifade değerlendirmesi<br />-C# ifade değerlendiricisi<br />-Ayrıştırma<br />-Düzenle ve devam et<br />-İfade değerlendiricisi windows (izleme, yerel öğeler, otomobiller)<br />-Özel durum Yardımcısı<br />-Özel durumlar<br />-Yürütme<br />-Genel türler<br />-Sağ kaynak alma<br />-HPC/küme hata ayıklama<br />-Tümleşik çok dil hata ayıklama<br />-Birlikte çalışma hata ayıklama<br />-Just-in-time hata ayıklama<br />-Yerel hata ayıklama<br />-Yönetilen hata ayıklama<br />-El ile denetim (işlemler pencere)<br />-Bellek<br />-Mini döküm desteği<br />-Modülleri<br />-Birden çok işlem hata ayıklama<br />-Yerel hata ayıklama<br />-Yeni hata ayıklama altyapısı desteği<br />-İyileştirilmiş kodda hata ayıklama<br />-Output windows filtreleme<br />-Barındırma yönetilen hata ayıklama için işleme<br />-İşlemler<br />-Quickwatch<br />-Kaydeder<br />-Yığınında kaydeder<br />-Uzaktan hata ayıklama<br />-Dönüş değerleri<br />-Komut dosyası hata ayıklaması<br />-Kaynak hizmeti desteği<br />-Güvenlik<br />-Yana<br />-SQL<br />-Simge sunucusu<br />-Noktalarını izleme<br />-İş parçacığı<br />-Görselleştirmeleri<br />-Genişletilebilir Stil Sayfası Dil Dönüşümleri (XSLT) hata ayıklayıcı|  
|64-bit desteği|-64-bit yönetilen ve yerel kodu için tüm diller hata ayıklama<br />-x64 yerel destek|  
|Kaynak kodu denetimi (SCC)|-Temel SCC tümleştirme. Bkz. Not 3.<br />-Araçlar ve Seçenekler doğrulama|  
|Genişletilebilirlik|-VSPackages ve MEF Bileşenleri kullanma|  
  
## <a name="notes"></a>Notlar  
  
#### <a name="1-data-tools"></a>1. Veri Araçları  
 Tümleşik Kabuk veri genişletilebilirlik desteği ve Basitleştirilmiş gibi veritabanı geliştirme araçlarını içeren **Çözüm Gezgini**. Ancak, SQL Server Express, SQL Raporlama ve Crystal Reports tümleşik Kabuk dahil edilmez.  
  
#### <a name="2-debugging-support"></a>2. Hata ayıklama desteği  
 Tümleşik Kabuk Visual Studio Community sürümü dahil aynı hata ayıklama altyapısını içerir. Hata ayıklama altyapısı yönetilen kod ve ilgili özellikleri için ortak hata ayıklayıcı çalıştırmak gibi Attach, kesme, Düzenle ve devam et ve diğerleri içerir. Ancak, hata ayıklama Altyapısı SQL Server veritabanı hata ayıklama desteklemez.  
  
 Ancak desteği temel hata ayıklayıcı paketinde bulunan yerel hata ayıklama için ek dilleri desteklemek için genişletilemez.  
  
#### <a name="3-source-code-control-integration"></a>3. Kaynak kodu denetimi tümleştirmesinin  
 Tümleşik Kabuk kaynak kodu denetimi (SCC) uygulamak için ve Tümleştirme Bileşenleri ortak kaynak MSSCCI tabanlı denetimi sağlamak için API'ler sağlar.  
  
 SCC tümleştirme normal bir özellik olan Visual Studio Pro sürümü olmamasına karşın, SCC tümleştirme tümleşik Kabuk sağlanır.  
  
#### <a name="4-build-support"></a>4. Derleme desteği  
 Tümleşik Kabuk yapı desteği sağlar. Derlemelerde hakkında bilgi bulabilirsiniz [MSBuild başvurusu](../msbuild/msbuild-reference.md).  
  
## <a name="features-not-included-in-the-integrated-shell"></a>Tümleşik Kabuk bulunmayan özellikler  
 Tümleşik Kabuk bulunmayan özelliklerin bir listesi verilmiştir:  
  
-   Sınıf Tasarımcısı  
  
-   [PreEmptive tarafından koruması - Dotfuscator](../ide/dotfuscator/index.md)  
  
-   Dil özellikleri  
  
-   VSHost  
  
-   Visual Studio dil yok veya ilişkili proje şablonları veya proje öğesi şablonları, tümleşik Kabuk dahil edilir. Hiçbir dile özgü diğer özellikleri, örnek Visual Basic kod parçacıkları için dahil uygulamalarıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)