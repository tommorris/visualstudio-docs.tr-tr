---
title: "SharePoint tarafından desteklenen MSBuild özellikleri | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, MSBuild properties
ms.assetid: 7b2b58c6-55cd-4682-a5d7-43874e70920d
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: af70078790c684ce774a203b265d7c767779ab15
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-properties-supported-by-sharepoint"></a>SharePoint Tarafından Desteklenen MSBuild Özellikleri
  Tüm [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] Microsoft.VisualStudio.SharePoint.targets dosya, proje dosyası veya proje kullanıcı dosyası içinde tanımlanmış özelliği kullanılabilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint projeleri. Ortak yanı sıra [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] SharePoint projesi tarafından sağlanan özellikleri SharePoint projelerine özel ek özellikleri tanımlar.  
  
 Ortak bir listesi için [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] özellikleri, görmek [yaygın MSBuild proje özellikleri](http://go.microsoft.com/fwlink/?LinkID=168687). .Targets dosyasında, proje dosyası (.csproj veya .vbproj) veya proje kullanıcı dosyasında programlama dili tarafından desteklenen özelliklerin tam listesi için konum (csproj.user veya. vbproj.user).  
  
## <a name="msbuild-properties-specific-to-sharepoint"></a>MSBuild özellikleri özel SharePoint için  
 Aşağıdaki tabloda [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] SharePoint projeleri için özellikle uygulanan özellikleri [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Diğer özellikleri vardır, ancak dahili kullanım içindir.  
  
|Özellik adı|Açıklama|  
|-------------------|-----------------|  
|SharePointSiteUrl|Temsil eden bir dize [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] SharePoint sitesi.|  
|SandboxedSolution|Çözüm Korumalı bir çözüm olup olmadığını belirten bir Boole değeri.|  
|ActiveDeploymentConfiguration|Etkin dağıtım yapılandırması.|  
|IncludeAssemblyInPackage|Derleme paket dosyasında dahil edilip edilmediğini gösteren bir Boole değeri.|  
|PreDeploymentCommand|Dağıtım öncesi komutu adımda yürütülecek komut temsil eden bir dize değeri.|  
|PostDeploymentCommand|Dağıtım sonrası komut adımda yürütülecek komut temsil eden bir dize değeri.|  
|CustomBeforeSharePointTargets|Yolunu temsil eden bir dize bir [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] hedefler dosyası. Hedef dosya varsa ve tanımlanır, herhangi bir SharePoint hedefleri veri önce içeri aktarılır. Bu özellik sevk edilen SharePoint hedefleri dosyayı değiştirmeden paket işlemi önceden tanımlanması paketleme ilgili özellikleri tarafından özelleştirmenizi sağlar, ancak hedefler dosyası hala tüm SharePoint projelerine yöneliktir.|  
|CustomAfterSharePointTargets|Yolunu temsil eden bir dize bir [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] hedefler dosyası. Hedef dosya varsa ve tanımlanır, SharePoint hedefleri verilerinin bir tüm içe aktarılır. Bu özellik paketleme ilgili özellikler ve hedefleri sevk edilen SharePoint hedefleri dosyasını değiştirmek zorunda kalmadan kılarak paket işlemi özelleştirmenizi sağlar, ancak hedefler dosyası hala tüm SharePoint projelerine yöneliktir.|  
|LayoutPath|Burada her paketlenmiş dosya geçici olarak yerleştirilir .wsp dosyasına eklenmeden önce kök dizini temsil eden bir dize. Bu yol eklemek, kaldırmak veya .wsp dosyasının içeriğini değiştirmek için kullandığı için paketlenmesi için dosyaları değiştirmek için BeforeLayout ve AfterLayout hedefleri geçersiz kıldığınızda bilmek yararlı olabilir.|  
|BasePackagePath|Paket yerleştirildiği klasörü temsil eden bir dize. Bu değeri Bin\Debug gibi projenin çıktı dizini kullanır.|  
|PackageExtension|Pakete eklenecek dosya adı uzantısını temsil eden bir dize. Wsp varsayılan değerdir.|  
|AssemblyDeploymentTarget|Proje derleme SharePoint sunucusu üzerinde dağıtıldığı konumu temsil eden bir dize. Değeri GlobalAssemblyCache (varsayılan) veya WebApplication olduğu. Bu özellik ayrıca Özellikler penceresinde ayarlayabilirsiniz.|  
|PackageWithValidation|Doğrulama önce paketleme gerçekleştirip gerçekleştirmediğini belirtir bir Boole değeri. Bu özellik, paketleri oluşturulurken doğrulama hataları yoksayma olanak tanır.|  
|ValidatePackageDependsOn|Önce ValidatePackage hedef yürütmek için ek hedefleri tanımlayan bir dize.|  
|TokenReplacementFileExensions|Paketlemesi sırasında yerine kendi belirteçlere sahip dosyaları tanımlayan bir dize.|  
  
## <a name="using-msbuild-properties-in-the-properties-page"></a>Özellikler sayfasında MSBuild özellikleri kullanma  
 Sabit kodlanmış dizelerde kullanmak yerine, esneklik için **dağıtım öncesi komut satırı** ve **dağıtım sonrası komut satırı** kutuları SharePoint Özellikler sayfasında, SharePoint kullanabilirsiniz. bağımsız değişken olarak özellikleri. Örneğin, belirli bir belirtme yerine [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] dize için SharePoint sitesi, bunun yerine kullanabileceğiniz `$(SharePointSiteUrl)`.  
  
> [!NOTE]  
>  Kullanabilirsiniz [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] değişken sözdizimi `$(` *propertyName* `)` veya ortam değişkeni sözdizimi `%` *propertyName* `%` bir özelliği belirtmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild Başvurusu](/visualstudio/msbuild/msbuild-reference)  
  
  