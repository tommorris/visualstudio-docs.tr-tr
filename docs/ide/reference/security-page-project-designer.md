---
title: "Güvenlik sayfası, Proje Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.ProjectPropertiesSecurity
- vb.XBAPProjectPropertiesSecurity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Project Designer, Security page
- Security page in Project Designer
ms.assetid: 641d9cd3-fa07-498a-8568-3c169bb4d3d5
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4eaa6a746f67c891e9e4979f9c5b06202383e5f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="security-page-project-designer"></a>Güvenlik Sayfası, Proje Tasarımcısı
**Güvenlik** sayfasında **Proje Tasarımcısı** kullanılarak dağıtılan uygulamalar için kod erişimi güvenlik ayarlarını yapılandırmak için kullanılan [!INCLUDE[ndptecclick](../../deployment/includes/ndptecclick_md.md)] dağıtım. Daha fazla bilgi için bkz: [ClickOnce uygulamaları için kod erişimi güvenliği](../../deployment/code-access-security-for-clickonce-applications.md).  
  
 Erişim için **güvenlik** sayfasında, bir proje düğümüne tıklayın **Çözüm Gezgini**ve ardından **proje** menüsünde tıklatın **özellikleri**. Zaman **Proje Tasarımcısı** görünen tıklatın **güvenlik** sekmesi.  
  
## <a name="security-settings"></a>Güvenlik ayarları  
 **ClickOnce güvenlik ayarlarını etkinleştir**  
 Güvenlik ayarları tasarım zamanında etkin olup olmadığını belirler. Ne zaman bu seçeneği işaretli değilse, diğer tüm seçenekleri üzerinde **güvenlik** sayfası kullanılamıyor.  
  
> [!NOTE]
>  Kullanarak bir uygulama yayımladığınızda **Yayımla** sihirbazında, bu seçenek otomatik olarak etkinleştirilir.  
  
 Bu seçeneği belirlediğinizde, iki radyo düğmeleri birini seçerek seçeneğiniz vardır: **tam güven uygulamasıdır** veya **kısmi güven uygulamasıdır**.  
  
 Varsayılan olarak, WPF Web tarayıcı uygulaması projeleri için bu seçenek seçilidir.  
  
 Varsayılan olarak, diğer proje türleri için bu seçeneği temizlenir.  
  
 **Bu tam güven bir uygulamadır**  
 Bu seçeneği seçerseniz, uygulama yüklendiğinde veya bir istemci bilgisayarda çalışması tam güven izinleri ister. Kaçının uygulamanızı verilecek için tam güven Mümkünse, kullanılarak sınırsız erişimi dosya sistemini ve kayıt defteri gibi kaynaklara.  
  
 Varsayılan olarak, WPF Web tarayıcı uygulaması projeleri için bu seçeneği, kısmi güven için ayarlanır.  
  
 Varsayılan olarak, diğer proje türleri için bu seçeneği, tam güven olarak ayarlanır.  
  
 **Kısmi güven uygulamasıdır**  
 Bu seçeneği seçerseniz, uygulama yüklendiğinde veya bir istemci bilgisayarda çalışması kısmi güven izinleri ister. *Kısmi güven* istenen kod erişim güvenliği izinleri altında izin verilen eylemleri anlamına gelir. Güvenlik izinlerini yapılandırma hakkında daha fazla bilgi için bkz: [ClickOnce uygulamaları için kod erişimi güvenliği](../../deployment/code-access-security-for-clickonce-applications.md).  
  
 Kısmi güven güvenlik ayarları seçeneklerinde yapılandırarak belirtebilirsiniz **ClickOnce güvenlik izinleri** alanı.  
  
## <a name="clickonce-security-permissions"></a>ClickOnce güvenlik izinleri  
 **Bölge, uygulamanızın yüklenir**  
 Varsayılan bir kod erişim güvenliği izinleri belirtir. Seçin **Internet** veya **yerel Intranet** kısıtlı izin ayarlamak veya seçin **(özel)** özel bir izni yapılandırmak için ayarlayın. Uygulama bir bölgede verilen daha fazla izin isterse bir ClickOnce güven istemi ek izinleri vermek son kullanıcı için görünür. Güvenlik izinlerini yapılandırma hakkında daha fazla bilgi için bkz: [ClickOnce uygulamaları için kod erişimi güvenliği](../../deployment/code-access-security-for-clickonce-applications.md).  
  
 Varsayılan olarak, WPF Web tarayıcı uygulaması projeleri için bu seçeneği ayarlanmış **Internet**.  
  
 **Permissions XML düzenleme**  
 İzinleri yapılandırmak için uygulama bildirim şablonu (app.manifest) için açılır **(özel)** izin kümesi.  
  
 **Gelişmiş**  
 Açılır [Gelişmiş Güvenlik Ayarları iletişim kutusu](../../ide/reference/advanced-security-settings-dialog-box.md), kısıtlı izinleri olan uygulamada hata ayıklama için ayarları yapılandırmak için kullanılır. Hata ayıklama sırasında bu ayarları denetlenir ve uygulamanızı bir bölgesi içinde tanımlanan daha fazla izin gerekebilir izni özel durumlarını gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Security.Permissions.WebBrowserPermission>   
 <xref:System.Security.Permissions.MediaPermission>   
 [ClickOnce uygulamaları için kod erişimi güvenliği](../../deployment/code-access-security-for-clickonce-applications.md)   
 [Nasıl yapılır: ClickOnce güvenlik ayarlarını etkinleştir](../../deployment/how-to-enable-clickonce-security-settings.md)   
 [Nasıl yapılır: ClickOnce uygulaması için bir güvenlik bölgesi ayarlama](../../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce uygulaması için özel izinleri ayarlama](../../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Nasıl yapılır: sınırlı izinler ile ClickOnce uygulamasında hata ayıklama](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [ClickOnce güvenliği ve dağıtımı](../../deployment/clickonce-security-and-deployment.md)   
 [Proje Özellikleri başvurusu](../../ide/reference/project-properties-reference.md)   
 [Gelişmiş Güvenlik Ayarları iletişim kutusu](../../ide/reference/advanced-security-settings-dialog-box.md)