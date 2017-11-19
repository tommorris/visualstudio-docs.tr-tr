---
title: "SharePoint Proje sisteminin uzantılarında veri kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SharePoint project items, saving string data
- project items [SharePoint development in Visual Studio], saving string data
- projects [SharePoint development in Visual Studio], saving string data
- SharePoint projects, saving string data
ms.assetid: 903b9da7-2eea-404c-9a7a-7bc15cb90d6c
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3605558fd1fd9263c5dad7ec7bc295b7f095a185
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="saving-data-in-extensions-of-the-sharepoint-project-system"></a>SharePoint Proje Sisteminin Uzantılarında Veri Kaydetme
  SharePoint Proje sisteminin genişlettiğinizde, bir SharePoint Proje kapatıldıktan sonra devam ederse dize verilerini kaydedebilirsiniz. Verileri genellikle proje veya belirli bir proje öğesi ile ilişkilidir.  
  
 Kalıcı gerekmez veri varsa, herhangi bir nesneye uygulayan SharePoint araçları nesne modelinde veri ekleyebilirsiniz <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> arabirimi. Daha fazla bilgi için bkz: [SharePoint araç uzantıları ile özel verileri ilişkilendirme](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
## <a name="saving-data-that-is-associated-with-a-project-item"></a>Verileri kaydetme ilişkili olduğu bir proje öğesi  
 Bir proje öğesi eklediğiniz bir özelliğin değerini gibi belirli bir SharePoint proje öğesi ile ilişkili verileri olduğunda .spdata dosya proje öğesi için veri kaydedebilirsiniz. Bunu yapmak için kullanın <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> özelliği bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> nesnesi. Bu özelliğe eklemek veri kaydedildi **ExtensionData** proje öğesi için .spdata dosyasındaki öğesi. Daha fazla bilgi için bkz: [ExtensionData öğesi](../sharepoint/extensiondata-element.md).  
  
 Aşağıdaki kod örneğinde nasıl kullanılacağı ortaya <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> özel bir SharePoint Proje öğe türüne tanımlanan bir dize özelliği değeri kaydetmek için özellik. Daha büyük bir örneğin bağlamında bu örnek için bkz [nasıl yapılır: bir özel SharePoint Proje öğe türüne özellik ekleme](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md).  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#14)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#14](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#14)]  
  
## <a name="saving-data-that-is-associated-with-a-project"></a>Verileri kaydetme ilişkili olduğu bir proje  
 SharePoint projelerine ekleme bir özellik değeri gibi proje düzeyi veri varsa, proje dosyası (.csproj veya .vbproj dosyası) veya proje kullanıcı seçeneği dosyası veri kaydedebilirsiniz (. csproj.user dosya veya. vbproj.user dosyası). Verileri kaydetmek üzere seçim yapın dosya kullanılacak verilerini nasıl istediğinizi bağlıdır:  
  
-   Veriler SharePoint Proje Aç tüm geliştiriciler için kullanılabilir olmasını istiyorsanız, veri proje dosyasına kaydedin. Bu dosyadaki veri Projeyi kullanıma diğer geliştiriciler için kullanılabilir olması için bu dosyayı her zaman kaynak denetimi veritabanları için teslim edilir.  
  
-   Visual Studio'da açın SharePoint Proje sahip geçerli Geliştirici kullanılabilir olması için veri istiyorsanız, veri proje kullanıcı seçeneği dosyasına kaydedin. Bu dosyadaki veri Projeyi kullanıma diğer geliştiriciler için kullanılabilir değildir. Bu dosya genellikle kaynak denetimi veritabanları için iade değil.  
  
### <a name="saving-data-to-the-project-file"></a>Proje dosyaya veri kaydetme  
 Proje dosyasına verileri kaydetmek için dönüştürme bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> nesnesine bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> nesnesini genişletin ve ardından <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> yöntemi. Aşağıdaki kod örneği, bir proje özelliğinin değeri proje dosyasına kaydetmek için bu yöntemi kullanmak gösterilmiştir. Bu örneği bağlamında daha büyük bir örnek görmek için bkz: [nasıl yapılır: SharePoint projelerine özellik ekleme](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).  
  
 [!code-vb[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#3)]
 [!code-csharp[SpExt_SPCustomPrjProperty#3](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#3)]  
  
 Dönüştürme hakkında daha fazla bilgi için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> nesneler Visual Studio Otomasyon nesne modeli veya tümleştirme nesne modeli, diğer türleri için bkz: [dönüştürme arasında SharePoint Proje sistem türleri ve diğer Visual Studio Proje türleri ](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md).  
  
### <a name="saving-data-to-the-project-user-option-file"></a>Proje kullanıcı seçeneği dosyaya veri kaydetme  
 Verileri proje kullanıcı seçeneği dosyasına kaydetmek için kullanın <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectUserFileData%2A> özelliği bir <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject> nesnesi. Aşağıdaki kod örneği, bir proje özelliğinin değeri proje kullanıcı seçeneği dosyasına kaydetmek için bu özelliği kullanmak gösterilmiştir. Bu örneği bağlamında daha büyük bir örnek görmek için bkz: [nasıl yapılır: SharePoint projelerine özellik ekleme](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md).  
  
 [!code-vb[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#2)]
 [!code-csharp[SpExt_SPCustomPrjProperty#2](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md)   
 [SharePoint araç uzantıları ile özel verileri ilişkilendirme](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md)   
 [SharePoint Proje sistem türleri ve diğer Visual Studio Proje türleri arasında dönüştürme](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)  
  
  