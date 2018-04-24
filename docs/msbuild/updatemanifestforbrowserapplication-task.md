---
title: UpdateManifestForBrowserApplication görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UpdateManifestForBrowserApplication task [WPF MSBuild]
- adding the <hostInBrowser /> element to the application manifest [WPF MSBuild]
- building XBAP projects [WPF MSBuild]
- UpdateManifestForBrowserApplication task [WPF MSBuild], parameters
ms.assetid: 653339f7-654b-4d64-a26a-5c9f27036895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f944d8546fd9124bc881f8421943d34a86698c5
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="updatemanifestforbrowserapplication-task"></a>UpdateManifestForBrowserApplication Görevi
<xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> Görev eklemek için çalıştırılır  **\<HostInBrowser / >** uygulama bildirimi öğesine (*projectname*. exe.manifest) olduğunda bir [!INCLUDE[TLA#tla_xbap](../msbuild/includes/tlasharptla_xbap_md.md)] projesi oluşturulur.  
  
## <a name="task-parameters"></a>Görev parametreleri  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ApplicationManifest`|Gerekli **ITaskItem []** parametresi.<br /><br /> Eklemek istediğiniz uygulama bildirim dosyasının adını ve yolunu belirtir `<hostInBrowser />` öğesi.|  
|`HostInBrowser`|Gerekli **Boolean** parametresi.<br /><br /> Uygulama bildirimini içerecek biçimde değiştirmek belirtir  **\<HostInBrowser / >** öğesi. Varsa **true**, yeni bir `<` **HostInBrowser / >** öğesi dahil  **\<entryPoint / >** öğesi. Bu öğe Not ekleme toplu: varsa bir  **\<HostInBrowser / >** öğesi zaten varsa, bunun üzerine veya kaldırıldığında değil. Bunun yerine, ek bir  **\<HostInBrowser / >** öğesi oluşturulur. Varsa **yanlış**, uygulama bildirimi değiştirilemez.|  
  
## <a name="remarks"></a>Açıklamalar  
 [!INCLUDE[TLA2#tla_xbap#plural](../msbuild/includes/tla2sharptla_xbapsharpplural_md.md)] kullanarak çalıştırmak [!INCLUDE[TLA#tla_clickonce](../msbuild/includes/tlasharptla_clickonce_md.md)] dağıtımı ve bu nedenle, gereken tarafından yayımlanan dağıtım ve uygulama bildirimleri destekleme ile. [!INCLUDE[TLA#tla_msbuild](../msbuild/includes/tlasharptla_msbuild_md.md)] kullanan [GenerateApplicationManifest](http://msdn2.microsoft.com/library/6wc2ccdc.aspx) bir uygulama bildirimi oluşturmak için görev.  
  
 Ardından, bir uygulama tarayıcıdan ek öğenin barındırılacak şekilde yapılandırmak için  **\<HostInBrowser / >** aşağıdaki örnekte Göster olarak uygulama bildirimine eklenmiş olması gerekir:  
  
```xml  
<!--MyXBAPApplication.exe.manifest-->  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly ... >  
    <asmv1:assemblyIdentity ... />  
    <application />  
    <entryPoint>  
      ...  
      <hostInBrowser xmlns="urn:schemas-microsoft-com:asm.v3" />  
    </entryPoint>  
  ...  
/>  
```  
  
 <xref:Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication> Görevi çalıştırılana ne zaman bir [!INCLUDE[TLA2#tla_xbap](../msbuild/includes/tla2sharptla_xbap_md.md)] projesi eklemek için yapılandırıldığında `<hostInBrowser />` öğesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, emin olmak gösterilmiştir `<hostInBrowser />` öğesi, bir uygulama bildirim dosyasında bulunur.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UpdateManifestForBrowserApplication"  
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UpdateManifestForBrowserApplicationTask">  
    <UpdateManifestForBrowserApplication  
      ApplicationManifest="MyXBAPApplication.exe.manifest"  
      HostInBrowser="true" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF MSBuild başvurusu](../msbuild/wpf-msbuild-reference.md)   
 [Görev başvurusu](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild başvurusu](../msbuild/msbuild-reference.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [WPF uygulaması (WPF) oluşturma](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)   
 [WPF XAML Tarayıcı Uygulamalarına Genel Bakış](/dotnet/framework/wpf/app-development/wpf-xaml-browser-applications-overview)