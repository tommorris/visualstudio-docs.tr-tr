---
title: .NET Framework 4 veya .NET Framework 4. 5'e geçiş Office projelerini çalıştırmak için gereken değişiklikler
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 53a6b138509648af102a50217a8bab4d32b27a2a
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34693922"
---
# <a name="required-changes-to-run-office-projects-that-you-migrate-to-the-net-framework-4-or-the-net-framework-45"></a>.NET Framework 4 veya .NET Framework 4. 5'e geçiş Office projelerini çalıştırmak için gereken değişiklikler
  Bir Office projesinin hedef Framework'ü değiştirilirse [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha önceki .NET Framework sürümünden çözümü geliştirme bilgisayarındaki ve son kullanıcı bilgisayarlarında çalıştığından emin olmak için aşağıdaki görevleri gerçekleştirmeniz gerekir:  
  
-   Kaldırma <xref:System.Security.SecurityTransparentAttribute> Visual Studio 2008'den yükseltme yaptıysanız, projeye ait.  
  
-   Gerçekleştirmek bir **temiz** çalıştırmak veya geliştirme bilgisayarındaki projede hataları ayıklamak için Visual Studio'da komutu.  
  
-   .NET Framework projesi için önkoşul güncelleştirin.  
  
-   Hedef Framework'ü değiştirdiğiniz önce ClickOnce kullanarak, daha önce dağıttıysanız, son kullanıcılar da çözümü yeniden yüklemeniz gerekir.  
  
 Her bir bu görevler hakkında daha fazla bilgi için aşağıdaki ilgili bölümlere bakın.  
  
## <a name="remove-the-securitytransparent-attribute-from-projects-that-you-upgrade-from-visual-studio-2008"></a>Visual Studio 2008'den yükseltme projeleri SecurityTransparent özniteliğini kaldırın  
 Visual Studio 2008 ve hedef Framework'ü bir Office proje yükseltirseniz, proje sonradan değişikliklerini [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra kaldırmanız <xref:System.Security.SecurityTransparentAttribute> projeden. Visual Studio otomatik olarak bu öznitelik için kaldırmaz. Bu öznitelik kaldırmazsanız, projeyi derlerken bir hata iletisi alırsınız.  
  
 Visual Studio yükseltilmiş projenin hedef çerçevesini değiştirebilir durumları hakkında daha fazla bilgi için [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], bkz: [yükseltme ve Office çözümleri geçirmek](../vsto/upgrading-and-migrating-office-solutions.md).  
  
#### <a name="to-remove-the-securitytransparentattribute"></a>SecurityTransparentAttribute'unu kaldırmak için  
  
1.  Projesini Visual Studio'da Aç açın **Çözüm Gezgini**.  
  
2.  Altında **özellikleri** düğümünü (C# ' ta) veya **My proje** düğümünü (Visual Basic) için kod düzenleyicisinde açmak için AssemblyInfo kod dosyasını çift tıklatın.  
  
    > [!NOTE]  
    >  Visual Basic projelerinde'ı tıklatmalısınız **tüm dosyaları göster** düğmesini **Çözüm Gezgini** AssemblyInfo kod dosyasını görmek için.  
  
3.  Bulun <xref:System.Security.SecurityTransparentAttribute> ve dosyadan kaldırın veya açıklamadan çıkarın.  
  
    ```vb  
    <Assembly: SecurityTransparent()>  
    ```  
  
    ```csharp  
    [assembly: SecurityTransparent()]  
    ```  
  
## <a name="perform-the-clean-command-to-debug-or-run-a-project-on-the-development-computer"></a>Hata ayıklama veya bir proje geliştirme bilgisayarınızda çalışmaya temiz komutu gerçekleştirme  
 Bir Office proje projenin hedef çerçevesini değiştirilmeden önce oluşturulduysa [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra gerçekleştirmeniz gereken bir **temiz** komut ve hedef Framework'ü değiştirildikten sonra projeyi yeniden derleyin. Varsa gerçekleştirme bir **temiz** komutunu alırsınız bir <xref:System.Runtime.InteropServices.COMException> çalıştığınızda hata ayıklama veya güncellendiyse projesini çalıştırın.  
  
 Hakkında daha fazla bilgi için **temiz** komutu, bkz: [yapı Office çözümleri](../vsto/building-office-solutions.md).  
  
## <a name="update-the-prerequisites-for-deployment"></a>Güncelleştirme dağıtımı için Önkoşullar  
 Bir Office projesine hedeflediğinizde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra da karşılık gelen .NET Framework önkoşullarını da güncelleştirmeniz gerekir **Önkoşullar** iletişim kutusu. Aksi takdirde ClickOnce dağıtımı veya InstallShield Limited Edition proje olup olmadığını denetler ve .NET Framework'ün önceki sürümünü yükler.  
  
 Son kullanıcı bilgisayarlarında dağıtımı için Önkoşullar güncelleştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: Office çözümlerini çalıştırmak için son kullanıcı bilgisayarlarında Önkoşulları Yükleme](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98).  
  
## <a name="reinstall-solutions-on-end-user-computers"></a>Son kullanıcı bilgisayarlarında çözümleri yeniden  
 .NET Framework 3.5 hedefleyen Office çözümünü dağıtmak için ClickOnce kullanırsanız ve projeyi yeniden hedefleyin [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra son kullanıcılar çözümü kaldırıp yeniden yayınladıktan sonra sonra çözümü yeniden yüklemeniz gerekir. Güncellendiyse çözümü yeniden yayımlamanız ve çözüm son kullanıcı bilgisayarlarında güncelleştirilir, son kullanıcıların alacak bir <xref:System.Runtime.InteropServices.COMException> güncellenen çözümü çalıştırdıklarında.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümlerini .NET Framework 4 veya sonraki bir sürümüne geçirme](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)  
  
  