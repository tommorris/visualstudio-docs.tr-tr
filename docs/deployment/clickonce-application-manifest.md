---
title: ClickOnce Uygulama bildirimi | Microsoft Docs
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
- application manifests [ClickOnce]
- ClickOnce, application manifests
ms.assetid: 29570cec-4e53-4660-a850-abc4fa150243
caps.latest.revision: "23"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: a7df31b2d76639ec0eedc353e857fc1c0c8df39b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="clickonce-application-manifest"></a>ClickOnce Uygulama Bildirimi
A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimidir kullanılarak dağıtılan bir uygulamayı açıklayan bir XML dosyası [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]uygulama bildirimleri aşağıdaki öğeleri ve öznitelikleri vardır.  
  
|Öğe|Açıklama|Öznitelikler|  
|-------------|-----------------|----------------|  
|[\<Assembly > öğesi](../deployment/assembly-element-clickonce-application.md)|Gerekli. En üst düzey öğesi.|`manifestVersion`|  
|[\<assemblyIdentity > öğesi](../deployment/assemblyidentity-element-clickonce-application.md)|Gerekli. Birincil derlemenin tanımlayan [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `language`|  
|[\<trustInfo > öğesi](../deployment/trustinfo-element-clickonce-application.md)|Uygulama güvenlik gereksinimlerini tanımlar.|Yok.|  
|[\<entryPoint > öğesi](../deployment/entrypoint-element-clickonce-application.md)|Gerekli. Uygulama kodu giriş noktası tanımlar.|`name`|  
|[\<bağımlılık > öğesi](../deployment/dependency-element-clickonce-application.md)|Gerekli. Uygulamayı çalıştırmak için gereken her bağımlılığı tanımlar. İsteğe bağlı olarak, önceden yüklenmiş gereken derlemeleri tanımlar.|Yok.|  
|[\<Dosya > öğesi](../deployment/file-element-clickonce-application.md)|İsteğe bağlı. Uygulama tarafından kullanılan her nonassembly dosyayı tanımlar. Dosyayla ilişkili Bileşen Nesne Modeli (COM) yalıtım verileri içerebilir.|`name`<br /><br /> `size`<br /><br /> `group`<br /><br /> `optional`<br /><br /> `writeableType`|  
|[\<fileAssociation > öğesi](../deployment/fileassociation-element-clickonce-application.md)|İsteğe bağlı. Uygulamayla ilişkilendirilecek bir dosya uzantısı tanımlar.|`extension`<br /><br /> `description`<br /><br /> `progid`<br /><br /> `defaultIcon`|  
  
## <a name="remarks"></a>Açıklamalar  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Uygulama bildirim dosyasının tanımlayan kullanılarak dağıtılan bir uygulama [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Hakkında daha fazla bilgi için [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], bkz: [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md).  
  
## <a name="file-location"></a>Dosya konumu  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirimi dağıtımı tek bir sürümüne özeldir. Bu nedenle, bunlar ayrı ayrı dağıtım bildirimlerinden depolanması gerekir. Ortak ilişkili sürümden sonra adlı bir alt yerleştirmek için kuraldır.  
  
 Uygulama bildirimini dağıtımdan önce her zaman imzalanması gerekir. Bir uygulama bildirimi el ile değiştirmeniz halinde, uygulama bildirimini yeniden imzalayın, dağıtım bildirimini güncelleştirmek ve dağıtım bildirimini yeniden imzalamak için mage.exe kullanmanız gerekir. Daha fazla bilgi için bkz: [izlenecek yol: bir ClickOnce uygulamasını el ile dağıtma](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="file-name-syntax"></a>Dosya adı sözdizimi  
 Adı bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama bildirim dosyasının olmalıdır tam adı ve uzantısı uygulamanın tanımlandığı gibi `assemblyIdentity` .manifest uzantısının ardından öğesi. Örneğin, Example.exe uygulamasını bir uygulama bildirimi aşağıdaki dosya adı sözdizimi kullanırsınız.  
  
 `example.exe.manifest`  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği için bir uygulama bildirimi gösteren bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd" manifestVersion="1.0" xmlns:asmv3="urn:schemas-microsoft-com:asm.v3" xmlns:dsig="http://www.w3.org/2000/09/xmldsig#" xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2" xmlns="urn:schemas-microsoft-com:asm.v2" xmlns:asmv1="urn:schemas-microsoft-com:asm.v1" xmlns:asmv2="urn:schemas-microsoft-com:asm.v2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1">  
  <asmv1:assemblyIdentity name="My Application Deployment.exe" version="1.0.0.0" publicKeyToken="43cb1e8e7a352766" language="neutral" processorArchitecture="x86" type="win32" />  
  <application />  
  <entryPoint>  
    <assemblyIdentity name="MyApplication" version="1.0.0.0" language="neutral" processorArchitecture="x86" />  
    <commandLine file="MyApplication.exe" parameters="" />  
  </entryPoint>  
  <trustInfo>  
    <security>  
      <applicationRequestMinimum>  
        <PermissionSet Unrestricted="true" ID="Custom" SameSite="site" />  
        <defaultAssemblyRequest permissionSetReference="Custom" />  
      </applicationRequestMinimum>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <!--  
          UAC Manifest Options  
          If you want to change the Windows User Account Control level replace the   
          requestedExecutionLevel node with one of the following.  
  
        <requestedExecutionLevel  level="asInvoker" uiAccess="false" />  
        <requestedExecutionLevel  level="requireAdministrator" uiAccess="false" />  
        <requestedExecutionLevel  level="highestAvailable" uiAccess="false" />  
  
         If you want to utilize File and Registry Virtualization for backward   
         compatibility then delete the requestedExecutionLevel node.  
    -->  
        <requestedExecutionLevel level="asInvoker" uiAccess="false" />  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
  <dependency>  
    <dependentOS>  
      <osVersionInfo>  
        <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
      </osVersionInfo>  
    </dependentOS>  
  </dependency>  
  <dependency>  
    <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
      <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="4.0.20506.0" />  
    </dependentAssembly>  
  </dependency>  
  <dependency>  
    <dependentAssembly dependencyType="install" allowDelayedBinding="true" codebase="MyApplication.exe" size="4096">  
      <assemblyIdentity name="MyApplication" version="1.0.0.0" language="neutral" processorArchitecture="x86" />  
      <hash>  
        <dsig:Transforms>  
          <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
        </dsig:Transforms>  
        <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
        <dsig:DigestValue>DpTW7RzS9IeT/RBSLj54vfTEzNg=</dsig:DigestValue>  
      </hash>  
    </dependentAssembly>  
  </dependency>  
<publisherIdentity name="CN=DOMAINCONTROLLER\UserMe" issuerKeyHash="18312a18a21b215ecf4cdb20f5a0e0b0dd263c08" /><Signature Id="StrongNameSignature" xmlns="http://www.w3.org/2000/09/xmldsig#">  
...  
</Signature></r:issuer></r:license></msrel:RelData></KeyInfo></Signature></asmv1:assembly>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulamalarını Yayımlama](../deployment/publishing-clickonce-applications.md)