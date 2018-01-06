---
title: "Nasıl yapılır: .NET Framework'ün çoklu sürümleri üzerinde çalışan uygulamaları dağıtmak için ClickOnce kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
- ClickOnce applications, multiple .NET Framework versions
- ClickOnce deployment, multiple .NET Framework versions
- deploying applications [ClickOnce], multiple .NET Framework versions
ms.assetid: e0a8c330-21bc-4eb2-b936-fd0f3c3221f1
caps.latest.revision: "17"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c3153b4c6808d2a79a89a10e35830ec81ba15fd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-clickonce-to-deploy-applications-that-can-run-on-multiple-versions-of-the-net-framework"></a>Nasıl yapılır: .NET Framework'ün Birden Çok Sürümünde Çalışan Uygulamaları Dağıtmak için ClickOnce'ı Kullanma
ClickOnce dağıtım teknolojisini kullanarak birden çok .NET Framework sürümlerini hedefleyen bir uygulama dağıtabilirsiniz. Bu, oluşturma ve uygulama ve dağıtım bildirimlerini güncelleştirme gerektirir.  
  
> [!NOTE]
>  Birden çok .NET Framework sürümlerini hedefleyen uygulama değiştirmeden önce uygulamanız birden çok .NET Framework sürümü ile çalıştığından emin olmak. Sürüm ortak dil çalışma zamanı arasında farklı [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] .NET Framework 2.0, .NET Framework 3.0 ve .NET Framework 3.5 ile karşılaştırması.  
  
 Bu işlem, aşağıdaki adımları gerektirir:  
  
1.  Uygulama ve dağıtım bildirimlerini oluşturun.  
  
2.  Birden çok .NET Framework sürümleri listelemek için dağıtım bildirimi değiştirin.  
  
3.  App.config dosyasını uyumlu .NET Framework çalışma zamanı sürümlerini listeleyecek şekilde değiştirin.  
  
4.  Uygulama bildirimini bağımlı derlemeleri .NET Framework derlemeleri olarak işaretlemek için değiştirin.  
  
5.  Uygulama bildirimini imzalayın.  
  
6.  Güncelleştirin ve dağıtım bildirimini imzalayın.  
  
### <a name="to-generate-the-application-and-deployment-manifests"></a>Uygulama ve dağıtım bildirimlerini oluşturmak için  
  
-   Yayımlama Sihirbazı'nı veya Proje Tasarımcısı'nın Yayımla Sayfası uygulamayı yayımlamak ve uygulama ve dağıtım bildirim dosyası oluşturmak için kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md) veya [Yayımla Sayfası, Proje Tasarımcısı](../ide/reference/publish-page-project-designer.md).  
  
### <a name="to-change-the-deployment-manifest-to-list-the-multiple-net-framework-versions"></a>Birden çok .NET Framework sürümleri listelemek için dağıtım bildirimi değiştirmek için  
  
1.  Yayımla dizininde, Visual Studio'daki XML Düzenleyicisi'ni kullanarak dağıtım bildirimini açın. Dağıtım bildirimi .application dosya adı uzantısına sahip.  
  
2.  Arasındaki XML kodunu değiştir `<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">` ve `</compatibleFrameworks>` ile .NET Framework'ün uygulamanız için desteklenen sürümlerini listeleyen XML öğeleri.  
  
     Aşağıdaki tabloda kullanılabilir .NET Framework sürümleri ve dağıtım bildirimine ekleyebileceğiniz karşılık gelen XML bazılarını gösterir.  
  
    |.NET Framework sürümü|XML|  
    |----------------------------|---------|  
    |4 istemci|\<Framework targetVersion "4.0" profile = "İstemci" supportedRuntime = = "4.0.30319" / >|  
    |4 tam|\<Framework targetVersion "4.0" profile = "Tam" supportedRuntime = = "4.0.30319" / >|  
    |3.5 istemci|\<Framework targetVersion "3.5" profile = "İstemci" supportedRuntime = = "2.0.50727" / >|  
    |3.5 tam|\<Framework targetVersion "3.5" profile = "Tam" supportedRuntime = = "2.0.50727" / >|  
    |3.0|\<Framework targetVersion "3.0" supportedRuntime = = "2.0.50727" / >|  
  
### <a name="to-change-the-appconfig-file-to-list-the-compatible-net-framework-runtime-versions"></a>App.config dosyasını uyumlu .NET Framework çalışma zamanı sürümlerini listeleyecek şekilde değiştirmek için  
  
1.  Çözüm Gezgini'nde, Visual Studio'daki XML Düzenleyicisi'ni kullanarak App.config dosyasını açın.  
  
2.  Arasındaki XML kodunu değiştirin (veya ekleyin) `<startup>` ve `</startup>` ile .NET Framework'ün uygulamanız için desteklenen çalışma zamanlarını listeleyen XML öğeleri.  
  
     Aşağıdaki tabloda kullanılabilir .NET Framework sürümleri ve dağıtım bildirimine ekleyebileceğiniz karşılık gelen XML bazılarını gösterir.  
  
    |.NET framework çalışma zamanı sürümü|XML|  
    |------------------------------------|---------|  
    |4 istemci|\<supportedRuntime sürüm "v4.0.30319" sku = = ". NETFramework, sürüm = v4.0, profil istemci = "/ >|  
    |4 tam|\<supportedRuntime sürüm "v4.0.30319" sku = = ". NETFramework, sürüm v4.0 = "/ >|  
    |3.5 tam|\<supportedRuntime version="v2.0.50727"/ >|  
    |3.5 istemci|\<supportedRuntime sürüm "v2.0.50727" sku = = "İstemci" / >|  
  
### <a name="to-change-the-application-manifest-to-mark-dependent-assemblies-as-net-framework-assemblies"></a>Uygulama bildirimini bağımlı derlemeleri .NET Framework derlemeleri olarak işaretlemek için değiştirmek için  
  
1.  Yayımla dizininde, Visual Studio'daki XML Düzenleyicisi'ni kullanarak uygulama bildirimini açın. Dağıtım bildirimi .manifest dosya adı uzantısına sahip.  
  
2.  Ekleme `group="framework"` sentinel derlemeler için XML bağımlı (`System.Core`, `WindowsBase`, `Sentinel.v3.5Client`, ve `System.Data.Entity`). Örneğin, XML aşağıdaki gibi görünmelidir:  
  
    ```  
    <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" group="framework">  
    ```  
  
3.  Sürüm numarasını güncelleştirmek `<assemblyIdentity>` Microsoft.Windows.CommonLanguageRuntime'a öğesi en düşük genel payda olan .NET Framework sürüm numarası. Örneğin, uygulama .NET Framework 3.5 hedefliyorsa ve [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)], kullanım 2.0.50727.0 sürüm numarasını ve XML aşağıdaki gibi görünmelidir:  
  
    ```  
    <dependency>  
      <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
        <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="2.0.50727.0" />  
      </dependentAssembly>  
    </dependency>  
    ```  
  
### <a name="to-update-and-re-sign-the-application-and-deployment-manifests"></a>Güncelleştirme ve uygulama ve dağıtım yeniden imzalamak için bildirimler  
  
-   Güncelleştirme ve uygulama ve dağıtım bildirimlerini yeniden imzalayın. Daha fazla bilgi için bkz: [nasıl yapılır: yeniden imzalama uygulama ve dağıtım bildirimlerini](../deployment/how-to-re-sign-application-and-deployment-manifests.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [\<compatibleFrameworks > öğesi](../deployment/compatibleframeworks-element-clickonce-deployment.md)   
 [\<bağımlılık > öğesi](../deployment/dependency-element-clickonce-application.md)   
 [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md)   
 [Yapılandırma Dosyası Şeması](/dotnet/framework/configure-apps/file-schema/index)