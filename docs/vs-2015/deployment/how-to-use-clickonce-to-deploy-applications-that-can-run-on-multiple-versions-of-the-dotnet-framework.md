---
title: "Nasıl yapılır: .NET Framework'ün birden çok sürümü üzerinde çalışan uygulamaları dağıtmak için ClickOnce'ı kullanma | Microsoft Docs"
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: c9ee766472adf215a29852f776b566997df2e28b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686329"
---
# <a name="how-to-use-clickonce-to-deploy-applications-that-can-run-on-multiple-versions-of-the-net-framework"></a>Nasıl yapılır: .NET Framework'ün Birden Çok Sürümünde Çalışan Uygulamaları Dağıtmak için ClickOnce'ı Kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: dağıtma uygulamaları, çalışabileceği .NET Framework'ün birden çok sürümü için kullanım ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-use-clickonce-to-deploy-applications-that-can-run-on-multiple-versions-of-the-dotnet-framework).  
  
ClickOnce dağıtım teknolojisini kullanarak birden çok .NET Framework sürümünü hedefleyen bir uygulama dağıtabilirsiniz. Bu, oluşturmak ve uygulama ve dağıtım bildirimlerini güncelleştirme gerektirir.  
  
> [!NOTE]
>  Birden çok .NET Framework sürümünü hedefleyecek şekilde uygulamayı değiştirmeden önce uygulamanızın birden çok .NET Framework sürümü ile çalıştığından emin olmalısınız. Sürümü ortak dil çalışma zamanı arasında farklı [!INCLUDE[net_v40_short](../includes/net-v40-short-md.md)] .NET Framework 2.0, .NET Framework 3.0 ve .NET Framework 3.5 karşılaştırması.  
  
 Bu işlem, aşağıdaki adımları gerektirir:  
  
1.  Uygulama ve dağıtım bildirimlerini oluşturur.  
  
2.  Birden çok .NET Framework sürümü listelemek için dağıtım bildirimini değiştirin.  
  
3.  Uyumlu .NET Framework çalışma zamanı sürüm listelemek için app.config dosyasını değiştirin.  
  
4.  Bağımlı derlemeler .NET Framework derlemeleri olarak işaretlemek için uygulama bildirimini değiştirin.  
  
5.  Uygulama bildirimini imzalayın.  
  
6.  Güncelleştirin ve dağıtım bildirimini imzalayın.  
  
### <a name="to-generate-the-application-and-deployment-manifests"></a>Uygulama ve dağıtım bildirimleri oluşturmak için  
  
-   Uygulamayı yayımlamak ve uygulama ve dağıtım bildirim dosyaları oluşturmak için yayınlama Sihirbazı'nı veya yayımlama sayfası Proje Tasarımcısı'nı kullanın. Daha fazla bilgi için [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md) veya [yayımlama sayfası, Proje Tasarımcısı](../ide/reference/publish-page-project-designer.md).  
  
### <a name="to-change-the-deployment-manifest-to-list-the-multiple-net-framework-versions"></a>Birden çok .NET Framework sürümü listelemek için dağıtım bildirimini değiştirmek için  
  
1.  Yayımla dizininde, dağıtım bildirimini Visual Studio XML düzenleyicisi kullanarak açın. Dağıtım bildirimi .application dosya adı uzantısına sahiptir.  
  
2.  XML kodu arasında değiştirin `<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">` ve `</compatibleFrameworks>` ile uygulamanız için desteklenen .NET Framework sürümlerini listeler XML öğeleri.  
  
     Aşağıdaki tabloda kullanılabilir .NET Framework sürümleri ve dağıtım bildirimine ekleyebileceğiniz karşılık gelen XML bazıları gösterilmektedir.  
  
    |.NET Framework sürümü|XML|  
    |----------------------------|---------|  
    |4 istemcisi|\<Framework targetVersion "4.0" profile = "İstemci" supportedRuntime = = "4.0.30319" / >|  
    |4 tam|\<Framework targetVersion "4.0" profile = "Tam" supportedRuntime = = "4.0.30319" / >|  
    |3.5 istemci|\<Framework targetVersion "3.5" profile = "İstemci" supportedRuntime = = "2.0.50727" / >|  
    |3.5 tam|\<Framework targetVersion "3.5" profile = "Tam" supportedRuntime = = "2.0.50727" / >|  
    |3.0|\<Framework targetVersion "3.0" supportedRuntime = = "2.0.50727" / >|  
  
### <a name="to-change-the-appconfig-file-to-list-the-compatible-net-framework-runtime-versions"></a>Uyumlu .NET Framework çalışma zamanı sürüm listelemek için app.config dosyasını değiştirmek için  
  
1.  Çözüm Gezgini'nde, Visual Studio XML Düzenleyicisi'ni kullanarak App.config dosyasını açın.  
  
2.  XML kodu arasında değiştirin (veya ekleyin) `<startup>` ve `</startup>` ile uygulamanız için desteklenen .NET Framework çalışma zamanları listeler XML öğeleri.  
  
     Aşağıdaki tabloda kullanılabilir .NET Framework sürümleri ve dağıtım bildirimine ekleyebileceğiniz karşılık gelen XML bazıları gösterilmektedir.  
  
    |.NET framework çalışma zamanı sürümü|XML|  
    |------------------------------------|---------|  
    |4 istemcisi|\<supportedRuntime sürümü = "v4.0.30319" sku = ". NETFramework, sürüm = v4.0, profil istemci = "/ >|  
    |4 tam|\<supportedRuntime sürümü = "v4.0.30319" sku = ". NETFramework, sürüm = v4.0 "/ >|  
    |3.5 tam|\<supportedRuntime version="v2.0.50727"/ >|  
    |3.5 istemci|\<supportedRuntime sürümü = "v2.0.50727" sku = "İstemci" / >|  
  
### <a name="to-change-the-application-manifest-to-mark-dependent-assemblies-as-net-framework-assemblies"></a>Bağımlı derlemeler .NET Framework derlemeleri olarak işaretlemek için uygulama bildirimini değiştirmek için  
  
1.  Yayımla dizininde, uygulama bildirimini Visual Studio XML düzenleyicisi kullanarak açın. Dağıtım bildirimi .manifest dosya adı uzantısına sahiptir.  
  
2.  Ekleme `group="framework"` sentinel bütünleştirilmiş kodların bağımlı XML (`System.Core`, `WindowsBase`, `Sentinel.v3.5Client`, ve `System.Data.Entity`). Örneğin, XML, aşağıdaki gibi görünmelidir:  
  
    ```  
    <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" group="framework">  
    ```  
  
3.  Sürüm numarasını güncelleştirmek `<assemblyIdentity>` Microsoft.Windows.CommonLanguageRuntime'a öğesine en küçük ortak paydası .NET Framework sürüm numarası. Örneğin, uygulama .NET Framework 3.5 hedefliyorsa ve [!INCLUDE[net_v40_short](../includes/net-v40-short-md.md)], kullanım 2.0.50727.0 sürüm numarasını ve XML aşağıdaki gibi görünmelidir:  
  
    ```  
    <dependency>  
      <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
        <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="2.0.50727.0" />  
      </dependentAssembly>  
    </dependency>  
    ```  
  
### <a name="to-update-and-re-sign-the-application-and-deployment-manifests"></a>Bildirimlerini güncelleştirin ve uygulama ve dağıtım yeniden imzalamak için  
  
-   Güncelleştirme ve uygulama ve dağıtım bildirimlerini yeniden imzalama. Daha fazla bilgi için [nasıl yapılır: yeniden imzalama uygulama ve dağıtım bildirimlerini](../deployment/how-to-re-sign-application-and-deployment-manifests.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [\<compatibleFrameworks > öğesi](../deployment/compatibleframeworks-element-clickonce-deployment.md)   
 [\<bağımlılık > öğesi](../deployment/dependency-element-clickonce-application.md)   
 [ClickOnce dağıtım bildirimi](../deployment/clickonce-deployment-manifest.md)   
 [Yapılandırma Dosyası Şeması](http://msdn.microsoft.com/library/69003d39-dc8a-460c-a6be-e6d93e690b38)



