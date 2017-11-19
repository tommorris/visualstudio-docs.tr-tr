---
title: "Windows Installer temel kavramları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Installer, VSPackages
- VSPackages, Windows Installer basics
ms.assetid: 497e479b-add8-4644-870a-917f15306b97
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e46f5a3b4dd320ce71dfeea1a9d4fd4650e5c3d7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="windows-installer-basics"></a>Windows Installer temelleri
Windows Installer yükler ve uygulamalar veya yazılım ürünleri bir kullanıcının bilgisayarındaki, Windows Installer bileşenleri (WICs veya yalnızca bileşenleri de denir) olarak adlandırılan birimler halinde bu görevleri gerçekleştiren kaldırır. Bir GUID temel birimidir, yükleme ve başvuru Windows Yükleyicisi'ni kullanarak kurulumlarını sayım her WIC tanımlar.  
  
 Windows Installer'ın kapsamlı belgeler için Platform SDK konusuna bakın [Windows Installer](http://msdn.microsoft.com/library/aa372866.aspx).  
  
## <a name="authoring-a-vspackage"></a>Bir VSPackage yazma  
 Windows Installer, Windows Installer yüklemek, kaldırmak veya bir ürün onarmak için ve Kurulum kullanıcı arabirimi (UI) çalıştırmak için gereken bilgileri içeren yükleme paketleri kullanır. Her yükleme paketi bir yükleme veritabanı, bir özet bilgileri akış ve veri akışlarını yüklemesinin çeşitli bölümlerini içeren bir .msi dosyası içerir. Yükleyici kullanmak için bir yükleme yazmanız gerekir. Yükleyici bileşenleri kavramı çevresinde yüklemeleri düzenler ve ilişkisel bir veritabanında yüklenmesiyle ilgili bilgileri depolar için kapsamlı bir yükleme paketi yazma işlemi aşağıdaki adımları kapsar:  
  
1.  Sürüm oluşturma ve yan yana stratejileri desteklemek için yazma kurulumunuzu planlayın.  
  
2.  Kullanıcılara sunulması için özellikleri tanımlayın.  
  
3.  VSPackage ve bağımlılıkları bileşenlerine düzenleyin.  
  
4.  Yükleme veritabanı bilgileri ile doldurun.  
  
5.  Yükleme paketi doğrulayın.  
  
 Bu belge, öncelikle birinci ve üçüncü adımları işleminin ile ilgilidir. Sürüm ve sonraki sürümleri için hesap stratejisi bakım çerçeve için şu adımları sırasında VSPackage özelliklerinizi WICs organize [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Kalan üç adımı ayrıntı Platform SDK'sındaki Windows Installer belgelerinde ele alınmaktadır.  
  
## <a name="key-terms"></a>Anahtar terimleri  
 Windows Installer teknolojisi ilgili anahtar terimlerin tanımları verilmiştir.  
  
 Kaynak  
 Dosyaları, kayıt defteri anahtarlarını, kısayolları, veya vb., yüklenmiş olabilir bir bilgisayar. Bu kaynakları mantıksal olarak Windows Installer bileşenlerine gruplandırılır.  
  
 Windows Installer bileşeni (WIC)  
 Yüklü olan ve bir birim olarak kaldırılması ilgili kaynaklar mantıksal bir gruplandırmasını gösteren yükleme temel birimidir. Windows Installer bileşenleri bir benzersiz bileşen kimliği veya GUID tarafından tanımlanır. Ayrıca, Windows Installer, başvuru WIC düzeyinde sayım tutar. En yüksek sürüm esneklik için DLL gibi birden fazla birincil kaynağı verilen WIC içerir. Tanımlamak ve bir WIC doldurmak, bir GUID vermek ve bunu dağıttıktan sonra birleşim değiştiremeyeceğinizi unutmayın. Daha fazla bilgi için bkz: [bileşenleri düzenleme uygulamalara](http://msdn.microsoft.com/library/aa370561.aspx).  
  
 Paket (Redist paketi)  
 .Msi dosyası ve dış kaynak dosyalar bu dosyayı işaret edebilir oluşur dağıtım birimidir. Bir paketi, Windows Installer UI çalıştırın ve yükleme veya uygulamayı kaldırmak için gereken tüm bilgileri içerir.  
  
 .msi dosyası  
 Yönergeler ve bir uygulamayı yüklemek için gerekli verileri içeren bir COM yapılandırılmış depolama dosyası. Her paketi en az bir .msi dosyası içerir. .Msi dosyasını yükleyici veritabanı, bir özet bilgileri akış ve büyük olasılıkla bir veya daha fazla dönüşümler ve iç kaynak dosyaları içerir. Dosyaların yüklenmesine bir dolap sıkıştırılmış ve .msi dosyasını akışında depolanan veya depolanan, sıkıştırılmış veya sıkıştırılmamış kaynak ortamdaki .msi dosyası dışında. Daha fazla bilgi için bkz: [Windows Installer dosya uzantıları](http://msdn.microsoft.com/library/aa372842\(VS.85\).aspx).  
  
## <a name="windows-installer-rules-enforcement"></a>Windows Installer kuralları zorlama  
 İki kural kümesini kurulumunuzu ait bileşenleri kaynaklarına dağıtımını belirler. İkinci Küme yükleme yazar olarak zorlaması gereken sırada bir kural kümesi Windows Installer kendisi tarafından korunur.  
  
> [!NOTE]
>  Yalnızca .msi dosyanızın bir doğrulama çalıştırırsanız Windows Installer kural zorlama oluşur. Bununla birlikte, bu kurallar en iyi yöntemler olarak işlemek için dikkatli olmalıdır. Daha fazla bilgi için bkz: [bir yükleme veritabanı doğrulama](http://msdn.microsoft.com/library/aa372477\(VS.85\).aspx) ve [paket doğrulama](http://msdn.microsoft.com/library/aa370569\(VS.85\).aspx).  
  
#### <a name="installer-enforced-rules"></a>Yükleyici tarafından zorlanan kuralları  
  
-   Belirli bir bileşene tüm dosyaları aynı dizinine yüklenmelidir. Buna karşılık, klasörlere ayırmak için yüklenen dosyalar bileşenleri ayırmak için ait olmalıdır.  
  
-   Bileşen başına yalnızca bir anahtar yolu olabilir. Tüm bileşen temsil eden yalnızca bir dosya veya kayıt defteri anahtarı anahtar yoludur.  
  
#### <a name="component-provider-responsibilities"></a>Bileşen sağlayıcısı sorumlulukları  
  
-   Sonraki sürümlerde de ayrı ayrı sevk edilebilir herhangi iki kaynakları ayrı bileşenlerinde var olmalıdır. Yalnızca, bu kaynakları hiçbir zaman ayrı olarak sevk belirli zaman kaynakları aynı bileşenin gruplandırılmalıdır. Aslında, önerilir tüm birincil kaynaklar (örneğin, DLL'ler) her zaman ayrı WICs içinde yok. Daha fazla bilgi için bkz: [tanımlama yükleyici bileşenleri](http://msdn.microsoft.com/library/aa368269\(VS.85\).aspx).  
  
-   Şimdiye kadar sürümlü bir kaynak içinde birden fazla WIC sevk etmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bileşen kuralları bozuk olması durumunda ne olur?](http://msdn.microsoft.com/library/aa372795\(VS.85\).aspx)