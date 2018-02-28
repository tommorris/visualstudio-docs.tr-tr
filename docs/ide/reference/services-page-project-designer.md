---
title: "Hizmetler Sayfası, Proje Tasarımcısı | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.ProjectPropertiesServices
helpviewer_keywords:
- Services page in Project Designer
- Project Designer, Services page
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 218f75c57d27cd424324eff8987561e9bee25e93
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="services-page-project-designer"></a>Hizmetler Sayfası, Proje Tasarımcısı

İstemci uygulama hizmetleri sağlamak için Basitleştirilmiş erişim [!INCLUDE[ajax_current_short](../../ide/reference/includes/ajax_current_short_md.md)] oturum açma, roller ve Windows Forms ve Windows Presentation Foundation (WPF) uygulamalardan profili Hizmetleri. Kullanabileceğiniz **Hizmetleri** sayfasında **Proje Tasarımcısı** etkinleştirmek ve istemci uygulama hizmetleri projeniz için yapılandırmak için.

İstemci uygulama hizmetleri ile kullanıcıların kimliğini doğrulamak, her kullanıcının atanmış veya rol belirlemek ve ağ üzerinden paylaşabilirsiniz kullanıcı başına uygulama ayarlarını depolamak için merkezi bir sunucu kullanabilirsiniz. Daha fazla bilgi için bkz: [istemci uygulama hizmetleri](/dotnet/framework/common-client-technologies/client-application-services).

Erişim için **Hizmetleri** sayfası, proje düğümü seçin **Çözüm Gezgini**ve ardından **özellikleri** üzerinde **proje** menüsü. Zaman **Proje Tasarımcısı** görünen tıklatın **Hizmetleri** sekmesi.

## <a name="task-list"></a>Görev Listesi

[Nasıl Yapılır: İstemci Uygulama Servislerini Yapılandırma](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)  
  
## <a name="uielement-list"></a>UIElement Listesi

 **Yapılandırma**  
 Bu denetim, bu sayfada düzenlenebilir değil. Bu denetim açıklaması için bkz: [derleme sayfası, Proje Tasarımcısı (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) veya [derleme sayfası, Proje Tasarımcısı (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Platform**  
 Bu denetim, bu sayfada düzenlenebilir değil. Bu denetim açıklaması için bkz: [derleme sayfası, Proje Tasarımcısı (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) veya [derleme sayfası, Proje Tasarımcısı (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **İstemci uygulama hizmetleri etkinleştir**  
 İstemci uygulama hizmetleri etkinleştirmek için seçin. Hizmet konumları belirlemeniz gerekir **Hizmetleri** sayfa istemci uygulama hizmetleri kullanın.  
  
 **Windows kimlik doğrulamasını kullan**  
 Kimlik doğrulama sağlayıcısı Windows tabanlı kimlik doğrulaması, diğer bir deyişle, Windows işletim sistemi tarafından sağlanan kimlik kullanacağını gösterir.  
  
 **Forms kimlik doğrulamasını kullan**  
 Kimlik doğrulama sağlayıcısı form kimlik doğrulaması kullanacağını gösterir. Başka bir deyişle, uygulamanız için oturum açma kullanıcı arabirimi sağlamanız gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: istemci uygulama hizmetleri ile uygulama kullanıcı oturum açma](/dotnet/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services).  
  
 **Kimlik doğrulama hizmeti konumu**  
 Yalnızca form kimlik doğrulaması ile kullanılır. Kimlik doğrulama hizmeti konumunu belirtir.  
  
 **İsteğe bağlı: Kimlik bilgileri sağlayıcısı**  
 Yalnızca form kimlik doğrulaması ile kullanılır. Gösterir <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> kimlik doğrulama hizmeti uygulamanız çağırdığında bir oturum açma iletişim kutusu görüntülemek için kullanacağı uygulama `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> yöntemi ve geçişleri boş dizeler veya `null` parametre. Bu kutuyu boş bırakırsanız, geçerli bir kullanıcı adı ve parola geçmelidir <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> yöntemi. Kimlik bilgileri sağlayıcısı bir bütünleştirilmiş kod tam tür adı olarak belirtmeniz gerekir. Daha fazla bilgi için bkz: <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName> ve [derleme adları](/dotnet/framework/app-domains/assembly-names). En basit biçimiyle bir bütünleştirilmiş kod tam tür adı aşağıdaki örneğe benzer:`MyNamespace.MyLoginClass, MyAssembly`  
  
 **Rol hizmeti konumu**  
 Rol hizmetinin konumunu belirtir.  
  
 **Web ayarları hizmet konumu**  
 Profil (Web Ayarları) hizmetinin konumunu belirtir.  
  
 **Gelişmiş**  
 Açılır [Hizmetleri iletişim kutusu için Gelişmiş ayarları](../../ide/reference/advanced-settings-for-services-dialog-box.md), hangi varsayılan davranışı geçersiz kılma kullanabilirsiniz. Örneğin, yerel dosya sistemine kullanmak yerine çevrimdışı depolama için bir veritabanı belirtmek için bu iletişim kutusunu kullanabilirsiniz. Daha fazla bilgi için bkz: [Hizmetleri iletişim kutusu için Gelişmiş ayarları](../../ide/reference/advanced-settings-for-services-dialog-box.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

[İstemci uygulama hizmetleri](/dotnet/framework/common-client-technologies/client-application-services)   
[Hizmetleri iletişim kutusu için Gelişmiş ayarlar](../../ide/reference/advanced-settings-for-services-dialog-box.md)   
[Nasıl yapılır: istemci uygulama hizmetlerini yapılandırma](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)   
[Derle sayfası, Proje Tasarımcısı (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
[Derleme Sayfası, Proje Tasarımcısı (C#)](../../ide/reference/build-page-project-designer-csharp.md)   
