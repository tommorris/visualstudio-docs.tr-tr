---
title: 'Nasıl yapılır: IIS özellik ayarlarını doğrulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- IIS, property settings
- debugging Web applications, troubleshooting
- IIS administration tool
- Web applications, setting properties
- properties [debugger], setting with IIS administration tool
ms.assetid: 9efc50bf-02fb-4750-9b3e-f03c38f10d8b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: acd232b76ece37737833d071c8551d1319d4f151
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31477985"
---
# <a name="how-to-verify-iis-property-settings"></a>Nasıl Yapılır: IIS Özellik Ayarlarını Doğrulama
IIS Yönetim Aracı'nı kullanarak bir Web uygulamasının özellikleri ayarlayabilirsiniz. Bu ayarlar doğrulanıyor genellikle sorun giderme, gerekli bir adım olması için bu özellikleri çalıştırmak, uygulama için doğru ayarlamanız gerekir.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-check-iis-settings-for-the-web-application"></a>Web uygulaması için IIS ayarlarını denetlemek için  
  
1.  Açık **Yönetimsel Araçlar** penceresi: üzerinde **Başlat** menüsündeki **programları**ve ardından **Yönetimsel Araçlar**. Varsa **Yönetimsel Araçlar** görünmez **programları** menüsü, ardından içinde arayın **Denetim Masası**.  
  
    -   Windows 2000'de seçin **Internet Services Manager**.  
  
    -   Windows XP'de seçin **Internet Information Services**.  
  
    -   Windows Server 2003'te çift **sunucunuzu yönetin**.  
  
         **Sunucunuzu yönetin** penceresi açılır. Altında **uygulama sunucusu**, tıklatın **bu uygulama sunucusunu yönet**.  
  
         **Uygulama sunucusu** penceresi açılır. Açık **Internet Information Services (IIS) Yöneticisi** sol bölmedeki düğüm.  
  
2.  İletişim kutusunda, makinenize ağaç denetimi düğümüne tıklayın. Tıklatın **Web siteleri** düğümünü ve Web uygulamasının düğümünü seçin. Bir Web sitesi düğümü ve bu nedenle bir eşdüzeyi ya da olacaktır **varsayılan Web sitesi** düğümü ya da varolan bir Web sitesi düğümü altında bir sanal dizin düğümü.  
  
3.  Web uygulaması sağ tıklayın ve kısayol menüsünde **özellikleri**.  
  
4.  Web uygulaması için güvenlik ayarlarını doğrulayın:  
  
    1.  Web uygulamasında **özellikleri** penceresinde tıklatın **dizin güvenliği** sekmesine ve tıklayın **Düzenle**.  
  
    2.  İçinde **kimlik doğrulama yöntemleri** iletişim kutusunda **anonim erişimi etkinleştir** ve **tümleşik Windows kimlik doğrulaması** henüz seçili değilse.  
  
    3.  Tıklatın **Tamam** kapatmak için **kimlik doğrulama yöntemleri** iletişim kutusu.  
  
5.  ATL sunucu uygulamaya ait DEBUG fiilini ISAPI uzantısı ile ilişkili olduğundan emin olun. Daha fazla bilgi için bkz: [nasıl yapılır: uzantısı ile hata ayıklama fiili ilişkilendirmek](http://msdn.microsoft.com/en-us/50d261d3-4bd4-41c0-b44e-3591086f121e).  
  
6.  İçin bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulama, uygulama kümesinde bir uygulama adı için sanal klasör emin olun **Internet Information Services (IIS) Yöneticisi'ni**, **Internet Services Manager** veya  **Internet Information Services**.  
  
    1.  Web uygulamasında **özellikleri** penceresinde, seçin **Directory** sekmesinde, sanal bir dizinde uygulamasıysa veya **giriş dizini** sekmesinde, bu uygulama, bir Web sitesi.  
  
    2.  Doğrulayın adlarında **yerel yol** burada uygulamayı gerçekten dağıtılan dizinin adı ile eşleşir.  
  
    3.  Altında **uygulama ayarları**, uygulamayı içeren kök dizinin adını yazın.  
  
    4.  Tıklatın **Tamam** kapatmak için **özellikleri** iletişim kutusu.  
  
7.  İçin bir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulama tıklatın **ASP.NET** sekmesinde ve doğrulayın doğru sürümü [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] belirtilir.  
  
8.  Tıklatın **Tamam** kapatmak için **özellikleri** iletişim kutusu.  
  
9. Tıklatın **Tamam** kapatmak için **Internet Information Services (IIS) Yöneticisi'ni**, **Internet Services Manager**, veya **Internet Information Services**iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sorun giderme](../debugger/debugging-web-applications-troubleshooting.md)