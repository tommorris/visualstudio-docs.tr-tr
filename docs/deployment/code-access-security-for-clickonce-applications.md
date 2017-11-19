---
title: "ClickOnce uygulamaları için kod erişimi güvenliği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XBAPProjectPropertiesSecurity.HowTo
- vb.XBAProjectPropertiesSecurity.HowTo
- vb.ProjectPropertiesSecurity.HowTo
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [ClickOnce], security
- ClickOnce applications, caspol
- security [ClickOnce], WPF browser-hosted applications
- security [ClickOnce], ClickOnce applications
- ClickOnce applications, code access security policies
- security, ClickOnce
ms.assetid: 04b104d0-0bd3-4ccb-b164-1de92d234487
caps.latest.revision: "31"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: ac2da96844587401a7156669e79a9bdcfe750070
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="code-access-security-for-clickonce-applications"></a>ClickOnce Uygulamaları İçin Kod Erişimi Güvenliği
ClickOnce uygulamaları .NET Framework'e dayalı ve kod erişimi güvenlik kısıtlamalarına tabidir. Bu nedenle, kod etkilerini erişim güvenliği ve buna göre ClickOnce uygulamaları yazmanız anlamak önemlidir.  
  
 Kod erişim güvenliği, .NET Framework'teki kod korumalı kaynaklara ve işlemlere sahip erişimi sınırlamak yardımcı olan bir mekanizmadır. Uygulama Yükleyicisi konum için uygun bölge kullanmak ClickOnce uygulamanızı kod erişim güvenliği izinleri yapılandırmanız gerekir. Çoğu durumda, seçtiğiniz **Internet** izinler sınırlı sayıda bölgenin veya **yerel Intranet** daha geniş bir izin kümesi bölgenin.  
  
## <a name="default-clickonce-code-access-security"></a>Varsayılan ClickOnce kod erişimi güvenliği  
 Varsayılan olarak, yüklü olduğunda veya istemci bilgisayarda çalışması ClickOnce uygulaması tam güven izinleri alır.  
  
-   Tam güven izinleri olan bir uygulama gibi dosya sistemi ve kayıt defteri kaynaklara sınırsız erişimi. Bu büyük olasılıkla uygulamanız (ve son kullanıcının sistem) kötü amaçlı kod tarafından kullanılmasına izin verir.  
  
-   Bir uygulama tam güven izinleri gerektirdiğinde, son kullanıcı uygulama izinleri istenebilir. Bu uygulamayı gerçek anlamda bir ClickOnce deneyimi sağlamaz ve istemi potansiyel olarak daha az deneyimli kullanıcılar için kafa karıştırıcı olabilir anlamına gelir.  
  
    > [!NOTE]
    >  Bir uygulama CD-ROM gibi çıkarılabilir medyadan yükleme sırasında kullanıcıya sorulmaz. Ayrıca, kullanıcıların güvenilir bir kaynaktan bir uygulamayı yüklediğinizde istenmez böylece bir ağ yöneticisi ağ ilkesi yapılandırabilirsiniz. Daha fazla bilgi için bkz: [güvenilir uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md).  
  
 ClickOnce uygulaması için izinleri kısıtlamak için uygulamanızın gerektirdiği izinler için en uygun bölgeyi istemek, uygulamanız için kod erişimi güvenlik izinleri değiştirebilirsiniz. Çoğu durumda, uygulamanın dağıtıldığı dilimini seçebilirsiniz. Örneğin, uygulamanızın Kurumsal uygulama ise, kullanabileceğiniz **yerel Intranet** bölgesi. Uygulamanız bir internet uygulamasıysa kullanabileceğiniz **Internet** bölgesi.  
  
## <a name="configuring-security-permissions"></a>Güvenlik izinlerini yapılandırma  
 Kod erişim güvenliği izinleri sınırlamak için uygun bölgeyi istemek için ClickOnce uygulamanızı her zaman yapılandırmanız gerekir. Güvenlik izinlerini yapılandırabilirsiniz **güvenlik** sayfasında **Proje Tasarımcısı**.  
  
 **Güvenlik** sayfasındaki **Proje Tasarımcısı** içeren bir **ClickOnce güvenlik ayarlarını etkinleştir** onay kutusu. Bu onay kutusu seçili olduğunda, uygulamanız için dağıtım bildirimi güvenlik izni isteklerini eklenir. Yükleme sırasında kullanıcının istenen izinleri uygulamanın dağıtıldığı bölge için varsayılan izinler aşarsa izinleri vermek için istenir. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce güvenlik ayarlarını etkinleştir](../deployment/how-to-enable-clickonce-security-settings.md).  
  
 Farklı konumlardan dağıtılan uygulamalar sormadan farklı düzeylerde izinler verilir. Örneğin, Internet'ten uygulama dağıtıldığında, bir yüksek oranda kısıtlayıcı izinler kümesini alır. Yerel Intranet bağlantısı yüklendiğinde, daha fazla izin alır ve bir CD-ROM'dan yüklendiğinde tam güven izinleri alır.  
  
 İzinleri yapılandırmak için başlangıç noktası bir güvenlik bölgesi'nden seçebilirsiniz **bölge** listesini **güvenlik** sayfası. Uygulamanızı büyük olasılıkla birden fazla bölgeden dağıtılacaksa, en az izinlerle bölgeyi seçin. Daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md).  
  
 Ayarlanabilir özellikler izin kümesine göre değişiklik gösterir; tüm izin kümeleri yapılandırılabilir özelliklere sahip. Uygulamanızın isteyebileceği izinleri tam listesi hakkında daha fazla bilgi için bkz: <xref:System.Security.Permissions>. Özel bir bölge için izinlerin nasıl ayarlanacağı hakkında daha fazla bilgi için bkz: [nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).  
  
## <a name="debugging-an-application-that-has-restricted-permissions"></a>Sınırlı izinlere sahip bir uygulama hata ayıklama  
 Bir geliştirici olarak, büyük olasılıkla tam güven izinleri olan geliştirme bilgisayarınıza çalıştırın. Bu nedenle, kısıtlı izinlerle çalıştıklarında kullanıcıların görebilirsiniz uygulama hata ayıklarken aynı güvenlik özel durumları görmezsiniz.  
  
 Bu özel durumları yakalamak için son kullanıcı ile aynı izinlerle uygulamada hata ayıklama gerekiyor. Kısıtlı izinlerle hata ayıklama etkinleştirilebilir **güvenlik** sayfasında **Proje Tasarımcısı**.  
  
 Üzerinde etkinleştirilmeyen her kod güvenlik talebi için kısıtlı izinleri olan bir uygulamada hata ayıklama işlemi yaparken, özel durumlar gerçekleştirilecektir **güvenlik** sayfası. Özel durum önlemek için kodunuzu değiştirme hakkında öneriler sağlayan bir özel durum Yardımcısı görüntülenir.  
  
 Ayrıca, kod yazdığınızda, IntelliSense özelliği Kod Düzenleyicisi'nde yapılandırmış olduğunuz güvenlik izinlerini dahil edilmeyen herhangi bir üye devre dışı bırakır.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md).  
  
## <a name="security-permissions-for-browser-hosted-applications"></a>Tarayıcıda barındırılan uygulamalar için güvenlik izinleri  
 Visual Studio, Windows Presentation Foundation (WPF) uygulamaları için aşağıdaki proje türlerini sağlar:  
  
-   WPF Windows uygulaması  
  
-   WPF Web tarayıcı uygulaması  
  
-   WPF Özel Denetim Kitaplığı  
  
-   WPF Hizmet Kitaplığı  
  
 Bu proje türleri yalnızca WPF Web tarayıcısı uygulamaları bir Web tarayıcısında barındırılan ve bu nedenle özel dağıtım ve güvenlik ayarları gerektirir. Bu uygulamalar için varsayılan güvenlik ayarlarını aşağıdaki gibidir:  
  
-   **ClickOnce güvenlik ayarlarını etkinleştir**  
  
-   **Kısmi güven uygulamasıdır**  
  
-   **Internet bölgesi** (izinle WPF Web tarayıcısı seçili uygulamaları için varsayılan)  
  
 İçinde **Gelişmiş güvenlik ayarları** iletişim kutusu, **seçili izin kümesi ile bu uygulamanın hatalarını ayıklama** onay kutusu seçili ve devre dışı. Tarayıcıda barındırılan uygulamalar için bölge içinde hata ayıklama kapatılamaz olmasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarının güvenliğini sağlama](../deployment/securing-clickonce-applications.md)   
 [Nasıl yapılır: ClickOnce güvenlik ayarlarını etkinleştir](../deployment/how-to-enable-clickonce-security-settings.md)   
 [Nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Güvenilir Uygulama dağıtımına genel bakış](../deployment/trusted-application-deployment-overview.md)   
 [Güvenlik sayfası, Proje Tasarımcısı](../ide/reference/security-page-project-designer.md)