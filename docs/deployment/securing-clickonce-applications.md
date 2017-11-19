---
title: "ClickOnce uygulamalarının güvenliğini sağlama | Microsoft Docs"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce security
- ClickOnce deployment, security
- deploying applications, ClickOnce security
ms.assetid: a05b5f2f-d1f2-471a-8096-8b11f7554265
caps.latest.revision: "45"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 331cdf8ddc449ea8d1d29af346b8f7faea549c00
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="securing-clickonce-applications"></a>ClickOnce Uygulamalarının Güvenliğini Sağlama
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]kod erişim güvenliği sınırlamalarına kod korumalı kaynaklara ve işlemlere sahip erişimi sınırlamak yardımcı olmak için .NET Framework uygulamaları tabidir. Bu nedenle, yazmak için kod erişim güvenliği etkilerini anlamak önemlidir, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaların uygun şekilde. Uygulamalarınız erişim için Internet ve Intranet gibi tam güven veya kısmi bölgeler kullanabilir.  
  
 Ayrıca ClickOnce, uygulama yayımcısının özgünlüğünü doğrulamak ve dosyaların karışmadığını ispatlamak üzere dağıtım bildirimleri ve uygulamayı imzalamak için sertifikalar kullanır. İmzalama isteğe bağlı bir adımdır; bu, bildirimler üretildikten sonra uygulama dosyalarını değiştirmeyi kolaylaştırır. Ancak, imzalı bildirimler olmadan, uygulama yükleyicisinin ortadaki adam güvenlik saldırılarında müdahaleye uğramadığından olmak zordur. Bu nedenle, uygulamalarınızı güvenlik altına almak için uygulama ve dağıtım bildirimlerinizi imzalamanızı öneririz.  
  
## <a name="zones"></a>Bölgeler  
 Kullanılarak dağıtılan uygulamalar [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] teknolojisi güvenlik bölgesi tarafından tanımlanan Eylemler ve izinler kümesi için kısıtlanmış. Güvenlik bölgeleri, Internet Explorer'da tanımlanmış ve uygulamanın konumunu temel alır. Aşağıdaki tablo dağıtım konumunu temel alan varsayılan izinleri listeler:  
  
|Dağıtım Konumu|Güvenlik Bölgesi|  
|-------------------------|-------------------|  
|Web'den çalıştırın|Internet Bölgesi|  
|Web'den yükleyin|Internet Bölgesi|  
|Ağ dosya paylaşımından yükleyin|Yerel Intranet bölgesi|  
|CD-ROM'dan yükleyin|Tam Güven|  
  
 Varsayılan izinler uygulamanın özgün sürümüyle dağıtılan konumu temel alır; uygulama güncelleştirmeleri de bu izinleri devralır. Uygulama Web veya ağ konumundan güncelleştirmeleri denetlemek için yapılandırılmış ve daha yeni bir sürüm varsa, özgün yükleme tam güven izinleri yerine Internet ve Intranet bölgesi için izinleri alabilir. Kullanıcıların uyarılmasını önlemek için, Sistem Yöneticisi belirli bir uygulama yayımcısını güvenilir kaynak olarak tanımlayan bir ClickOnce dağıtım ilkesi belirtebilir. Bu ilkenin dağıtılmış olduğu bilgisayarlar için, izinler otomatik olarak verilecek ve kullanıcı uyarılmayacaktır. Daha fazla bilgi için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md). Güvenilir uygulama dağıtımını yapılandırmak için, sertifika makine veya kuruluş düzeyinde yüklenebilir. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulamaları için bir istemci bilgisayara güvenilir bir yayımcı eklemek](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md).  
  
## <a name="code-access-security-policies"></a>Kod Erişim Güvenliği İlkeleri  
 Bir uygulama için izinler ayarlarında belirlenir [ \<trustInfo > öğesi](../deployment/trustinfo-element-clickonce-application.md) uygulama bildirimi öğesidir. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Projenin ayarlarına dayanarak bu bilgiyi otomatik olarak oluşturur **güvenlik** özellik sayfası. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama istediği özel izinler verilir. Örneğin, dosya erişiminin tam güven izinlerini gerektirdiği yerde uygulama tam güven izinleri isterse, uygulamaya tam güven izinleri değil de sadece dosya erişim izni verilir. Geliştirirken, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama, uygulama gereken belirli özel izinleri isteği emin olun. Çoğu durumda, uygulamanızı kısmi güvenle sınırlamak için Internet veya yerel Intranet bölgelerini kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md). Uygulamanız özel izinleri gerektiriyorsa, özel bir bölge oluşturabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).  
  
 Uygulamanın dağıtıldığı bölge için varsayılan izin kümesinin parçası olmayan bir izni dahil etme, son kullanıcının güncelleme ve yükleme zamanında iznin verilmesi için uyarılmasına sebep olur. Kullanıcıların uyarılmasını önlemek için, sistem yöneticisi belirli bir uygulama yayımcısını güvenilir kaynak olarak tanımlayan bir ClickOnce dağıtım ilkesi belirtebilir. Bu ilkenin dağıtılmış olduğu bilgisayarlar üzerinde, izinler otomatik olarak verilecek ve kullanıcı uyarılmayacaktır.  
  
 Geliştirici olarak, uygulamanızın uygun izinlerle çalıştığından emin olmak sizin sorumluluğunuzdur. Uygulama çalışma zamanı sırasında bir bölge dışında izinler isterse, güvenlik özel durumu ortaya çıkabilir. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Hedef güvenlik bölgesi uygulamanızda hata ayıklama olanak tanır. ve güvenli uygulamaları geliştirme hakkında Yardım sağlar. Daha fazla bilgi için bkz: [nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md).  
  
 Kod erişimi güvenliği ve ClickOnce hakkında daha fazla bilgi için bkz: [ClickOnce uygulamaları için kod erişimi güvenliği](../deployment/code-access-security-for-clickonce-applications.md).  
  
## <a name="code-signing-certificates"></a>Kod İmzalama Sertifikaları  
 Kullanarak bir uygulamayı yayımlamak için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım, bir ortak/özel anahtar çifti kullanarak uygulama için uygulama ve dağıtım bildirimlerini imzalayabilirsiniz. Bir bildirim imzalamak için Araçlar kullanılabilir **imzalama** sayfasında **Proje Tasarımcısı**. Daha fazla bilgi için bkz: [imzalama sayfası, Proje Tasarımcısı](../ide/reference/signing-page-project-designer.md). Alternatif olarak, bildirimler bir anahtar dosya ile yayımlama işlemi sırasında Yayımlama Sihirbazı'nı kullanarak imzalayabilirsiniz.  
  
 Bildirimler imzalandıktan sonra, Authenticode imzasına bağlı yayımcı bilgisi uygulamanın güvenilir bir kaynaktan olduğunu kullanıcıya göstermek için izinler iletişim kutusunda gösterilir.  
  
 ClickOnce ve sertifikaları hakkında daha fazla bilgi için bkz: [ClickOnce ve Authenticode](../deployment/clickonce-and-authenticode.md).  
  
## <a name="aspnet-form-based-authentication"></a>ASP.NET Form Tabanlı Kimlik Doğrulaması  
 Hangi dağıtımlara her kullanıcı erişebileceğini denetlemek istiyorsanız, anonim erişim için etkinleştirmemelisiniz [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] bir Web sunucusu üzerinde dağıtılan uygulamalar. Alternatif olarak, kullanıcı erişimini bir kullanıcı kimliği üzerinde yüklenmiş dağıtımlar için, Windows kimlik doğrulaması kullanarak etkinleştirebilirsiniz.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]ASP.NET form tabanlı kimlik doğrulamasını desteklemez, çünkü kalıcı tanımlama bilgilerini kullanır; Internet Explorer önbelleğinde bulunduğu ve izinsiz giriş çünkü bu bir güvenlik riski sunar. Bu nedenle, dağıtıyorsanız [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamaları, Windows kimlik doğrulaması yanı sıra tüm kimlik doğrulama senaryosu desteklenmiyor.  
  
## <a name="passing-arguments"></a>Bağımsız Değişkenleri Geçirme  
 Bağımsız değişkenler geçirmek varsa ek güvenlik önlemleri oluşur bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]geliştiricilerin Web üzerinden dağıtılan uygulamalar için bir sorgu dizesi girmesini sağlar. Sorgu dizesi, uygulamayı başlatmak için kullanılan URL'nin sonunda bir dizi ad-değer çiftleri şeklini alır:  
  
 `http://servername.adatum.com/WindowsApp1.application?username=joeuser`  
  
 Varsayılan olarak, sorgu dizesi bağımsız değişkenleri devre dışıdır. Öznitelik etkinleştirmek için `trustUrlParameters` uygulamanın dağıtım bildiriminde ayarlamanız gerekir. Bu değer arasında ayarlanabilir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] MageUI.exe gelen ve giden. Geçirme etkinleştirme hakkında ayrıntılı adımlar için sorgu dizeleri için bkz: [nasıl yapılır: çevrimiçi bir ClickOnce uygulamasında sorgu dize bilgilerini alma](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md).  
  
 Bir komut satırı veya veritabanı için olan sorgu dizesi aracılığıyla elde edilen bağımsız değişkenleri güvenli oldukları konusunda emin olmadan geçirmeyin. Güvenli olmayan bağımsız değişkenler rasgele komutları çalıştırarak uygulamanızı yönetmek için kötü amaçlı kullanıcılara izin verebilecek veritabanı ve komut satırı kaçış karakterlerini içeren dizelerdir.  
  
> [!NOTE]
>  Sorgu dizesi bağımsız değişkenler için bağımsız değişken geçirmek için tek yolu bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] başlangıçta uygulama. Bağımsız değişken geçiremezsiniz bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] komut satırından uygulama.  
  
## <a name="deploying-obfuscated-assemblies"></a>Gizlenmiş (Obfuscated) Derlemeleri Dağıtma  
 Visual Studio içerir ücretsiz [PreEmptive tarafından koruması - Dotfuscator Community Edition](../ide/dotfuscator/index.md), hangi kod gizleme ve etkin bir koruma önlemleri aracılığıyla ClickOnce uygulamaları korumak için kullanabilirsiniz.  Ayrıntılar için lütfen bkz [Dotfuscator Community Edition Kullanıcı Kılavuzu'nun ClickOnce bölümünde](https://www.preemptive.com/dotfuscator/ce/docs/help/5.27/advanced_clickonce.html).

## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce dağıtım stratejisini seçme](../deployment/choosing-a-clickonce-deployment-strategy.md)