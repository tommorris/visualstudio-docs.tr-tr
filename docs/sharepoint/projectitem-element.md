---
title: "ProjectItem öğesi | Microsoft Docs"
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
helpviewer_keywords: ProjectItem element
ms.assetid: df588235-12a1-4798-bc56-ef81843de17f
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 240518544f906e68ad443adf55fef20ef2bac879
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="projectitem-element"></a>ProjectItem Öğesi
  Bir SharePoint proje öğesi temsil eder. .Spdata dosyasının gerekli kök öğesidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ProjectItem DefaultFile = "File that opens in the editor when you open the project item"  
    FeatureReceiverClass = "Class that implements a feature receiver for the project item"  
    FeatureReceiverAssembly = "Assembly that defines a feature receiver for the project item"  
    SupportedTrustLevels = "Trust levels that the project item supports"  
    SupportedDeploymentScopes = "Deployment scopes that the project item supports"  
    Type="Identifier for the project item">  
  <Files>...</Files>  
  <ProjectItemFolder>...</ProjectItemFolder>  
  <SafeControls>...</SafeControls>  
  <FeatureProperties>...</FeatureProperties>  
  <ExtensionData>...</ExtensionData>  
</ProjectItem>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|**DefaultFile**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> SharePoint proje öğesi açtığınızda, Visual Studio düzenleyicisinde açar dosyasının dosya adı dahil olmak üzere, göreli yol **Çözüm Gezgini**. .Spdata dosyasını içeren klasörün göreli yoludur.|  
|**FeatureReceiverClass**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> Özellik alıcısı sınıfı bu SharePoint proje öğesi için tam adı. Özellik alıcıları hakkında daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).|  
|**FeatureReceiverAssembly**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> Bu SharePoint proje öğesi için bir özellik alıcısı tanımlayan derleme tam olarak nitelenmiş adını belirtir. Özellik alıcıları hakkında daha fazla bilgi için bkz: [sağlama paketleme ve dağıtım bilgileri proje öğelerinde](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md). Tam nitelikli derleme adları hakkında daha fazla bilgi için bkz: [derleme adları](/dotnet/framework/app-domains/assembly-names).|  
|**SupportedTrustLevels**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> Bu SharePoint proje öğesi destekleyen güven düzeyleri belirtir. Bu değer aşağıdaki dizelerden biri olabilir: Korumalı alan, FullTrust veya tüm. Değer Sandboxed ve FullTrust tüm belirtir.<br /><br /> Atadığınız değerine karşılık gelen bir özel SharePoint proje öğesi türü, bu özniteliğin değeri <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> uygulamanızda özelliği <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> yöntemi. Bu öznitelik için farklı bir değer belirtirseniz, böylece belirttiğiniz aynı güven düzeyine belirtir Visual Studio değerin üzerine yazar <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedTrustLevels%2A> özelliği.|  
|**SupportedDeploymentScopes**|İsteğe bağlı **xs: String** özniteliği.<br /><br /> Bu SharePoint proje öğesi destekleyen dağıtım kapsamları belirtir. Bu değer, bir veya daha fazla aşağıdaki dizelerden oluşan bir virgülle ayrılmış dizedir: Grup, Site, Web, WebApplication veya paket. Örneğin, "Web sitesi".<br /><br /> Atadığınız değerine karşılık gelen bir özel SharePoint proje öğesi türü, bu özniteliğin değeri <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> uygulamanızda özelliği <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> yöntemi. Bu öznitelik için farklı bir değer belirtirseniz, böylece belirttiğiniz aynı güven düzeyine belirtir Visual Studio değerin üzerine yazar <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition.SupportedDeploymentScopes%2A> özelliği.|  
|**Türü**|Gerekli **xs: String** özniteliği.<br /><br /> SharePoint proje öğesi tanımlayıcısı. Bir özel SharePoint proje öğesi türü, geçişi için dize tanımlayıcısıdır <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).<br /><br /> Visual Studio ile dahil yerleşik SharePoint Proje öğeleri için tanımlayıcıları listesi için bkz: [SharePoint proje öğelerini genişletme](../sharepoint/extending-sharepoint-project-items.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|İsteğe bağlı öğe.<br /><br /> SharePoint proje öğesi ile ilişkili olan özel veri öğeleri koleksiyonunu temsil eder.<br /><br /> Yalnızca bir tane içerebilir **ExtensionData** öğesi.|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|İsteğe bağlı öğe.<br /><br /> SharePoint için dağıtıldığında sahip bir özellik dahil olan özellik değerlerini koleksiyonunu temsil eder.<br /><br /> Yalnızca bir tane içerebilir **FeatureProperties** öğesi.|  
|[Dosyaları](../sharepoint/files-element.md)|İsteğe bağlı **FileCollectionType** öğesi.<br /><br /> SharePoint proje öğesi özellik öğesi dosyaları gibi ve SharePoint olmayan bağımlı projeleri çıktısını dağıtmak için dosyaları belirtir.<br /><br /> Ya da içermelidir bir **dosyaları** veya **Projectıtemfolder** öğesi, ancak ikisini birden değil.|  
|[Projectıtemfolder](../sharepoint/projectitemfolder-element.md)|İsteğe bağlı **ProjectItemFolderType** öğesi.<br /><br /> Eşlenmiş bir klasörde temsil eder.<br /><br /> Ya da içermelidir bir **dosyaları** veya **Projectıtemfolder** öğesi, ancak ikisini birden değil.|  
|[SafeControls](../sharepoint/safecontrols-element.md)|İsteğe bağlı öğe.<br /><br /> ASPX denetimleri ve SharePoint sitesindeki herhangi bir ASPX sayfasında erişmek herhangi bir kullanıcı için güvenli olarak tasarlanmış Web Bölümleri koleksiyonunu temsil eder.<br /><br /> Yalnızca bir tane içerebilir **SafeControls** öğesi.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
 Yok.  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Şema adı**|SharePoint proje öğesi şeması|  
|**Dosya doğrulama**|ProjectItemModelSchema.xsd|  
|**Boş olamaz**|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje Öğesi Şema Başvurusu](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  