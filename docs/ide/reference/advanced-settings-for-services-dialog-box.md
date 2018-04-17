---
title: Hizmetleri iletişim kutusu için Gelişmiş ayarları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vb.ProjectPropertiesAdvancedServices
helpviewer_keywords:
- Advanced Settings for Services dialog box
ms.assetid: 6dde4a2d-85e1-4275-aa55-24b84111be91
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 51d3b8b8353bae0b4c0d308150a8834a27848d51
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="advanced-settings-for-services-dialog-box"></a>Hizmetler İçin Gelişmiş Ayarlar İletişim Kutusu
İstemci uygulama hizmetleri sağlamak için Basitleştirilmiş erişim [!INCLUDE[ajax_current_short](../../ide/reference/includes/ajax_current_short_md.md)] oturum açma, roller ve Windows Forms ve Windows Presentation Foundation (WPF) uygulamalardan profili Hizmetleri. Kullanabileceğiniz **Hizmetleri** sayfasındaki **Proje Tasarımcısı** istemci uygulama hizmetleri yapılandırmak için. Hakkında daha fazla bilgi için **Hizmetleri** sayfasında, bkz: [Hizmetler Sayfası, Proje Tasarımcısı](../../ide/reference/services-page-project-designer.md).  
  
 Kullanım **hizmetler için Gelişmiş ayarlar** iletişim kutusunun **Hizmetleri** sayfasındaki **Proje Tasarımcısı** istemci uygulama hizmetleri için Gelişmiş ayarları yapılandırmak için. Bu ayarları kullanarak, daha az yaygın senaryoları etkinleştirmek için bazı varsayılan uygulama hizmet davranışları geçersiz kılabilirsiniz. Daha fazla bilgi için bkz: [istemci uygulama hizmetleri](/dotnet/framework/common-client-technologies/client-application-services).  
  
 Erişim için **hizmetler için Gelişmiş ayarları** iletişim kutusunda, proje düğümü seçin **Çözüm Gezgini**ve ardından **özellikleri** üzerinde **proje**  menüsü. Zaman **Proje Tasarımcısı** görünen tıklatın **Hizmetleri** sekmesini ve ardından **Gelişmiş** düğmesi. İstemci uygulama hizmetleri etkinleştirinceye kadar bu düğme devre dışı bırakılacak.  
  
## <a name="task-list"></a>Görev Listesi

- [Nasıl Yapılır: İstemci Uygulama Servislerini Yapılandırma](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)

## <a name="uielement-list"></a>UIElement Listesi

 **Yerel olarak çevrimdışı oturum açma etkinleştirmek için parola karması Kaydet**  
 Kullanıcının parolasının şifrelenmiş biçimde yerel olarak uygulama çevrimdışı modda olduğunda oturum açmak kullanıcının etkinleştirmek için önbelleğe alınır olup olmadığını belirtir. Bu seçenek varsayılan olarak seçilidir.
  
 **Sunucu tanımlama bilgisinin süresinin her tekrar oturum açmasını iste**  
 Daha önce kimliği doğrulanmış kullanıcılar otomatik olarak roller veya profili hizmeti uygulamanız erişir ve sunucu kimlik doğrulama tanımlama bilgisi süresi doldu, yeniden kimlik doğrulaması olup olmadığını belirtir. Uygulama hizmetlerini erişimini ve açık yeniden kimlik doğrulaması tanımlama bilgisinin zaman aşımına uğradıktan gerekmesi için bu seçeneği belirleyin. Bu kullanım kalmaz sonra uygulama çalışır durumda bırakın kullanıcılar süresiz olarak authenticated emin olmak genel konumda dağıtılan uygulamalar için kullanışlıdır. Bu seçenek varsayılan olarak işaretli değildir.  
  
 **Rol hizmeti önbellek zaman aşımı**  
 İstemci rol sağlayıcısı rol hizmetine erişim yerine önbelleğe alınmış rol değerleri kullanır süreyi belirtir. Rolleri sık güncelleştirildiği rolleri sık veya daha büyük bir değere güncelleştirildiğinde bu zaman aralığı düşük bir değere ayarlayın. Varsayılan değer bir gündür.  
  
 Çağırdığınızda önbelleğe alınan rol değerleri veya rol hizmeti rol sağlayıcısı erişen <xref:System.Web.Security.RolePrincipal.IsInRole%2A> yöntemi. Program aracılığıyla önbelleğini temizlemek ve uzak hizmete erişmek için bu yöntem zorlamak üzere çağrı <xref:System.Web.ClientServices.Providers.ClientRoleProvider.ResetCache%2A> yöntemi.  
  
 **Özel bağlantı dizesini kullan**  
 İstemci hizmet sağlayıcıları, özel bir veri deposu için yerel önbelleği mi kullanacağınızı belirtir. Varsayılan olarak, hizmet sağlayıcılarının önbelleği için yerel dosya sistemi kullanır. Bu seçeneğin belirlenmesi varsayılan bir bağlantı dizesi içeren metin kutusu otomatik olarak doldurur. Otomatik olarak oluşturmak ve bir SQL Server Compact Edition veritabanını kullanmak için varsayılan bağlantı dizesini kullanmaya devam edebilir veya varolan bir SQL Server veritabanına bir bağlantı dizesi belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: istemci uygulama hizmetleri yapılandırma](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services). Bu seçenek varsayılan olarak işaretli değildir.  
  
## <a name="see-also"></a>Ayrıca bkz.

[İstemci Uygulama Servisleri](/dotnet/framework/common-client-technologies/client-application-services)  
[Hizmetler Sayfası, Proje Tasarımcısı](../../ide/reference/services-page-project-designer.md)  
[Nasıl Yapılır: İstemci Uygulama Servislerini Yapılandırma](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)