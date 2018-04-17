---
title: 'Nasıl yapılır: özel SharePoint Proje öğe türüne özellik ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2da3ebd75ef8b195b0e4c6117b28a6bc294ac050
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-a-property-to-a-custom-sharepoint-project-item-type"></a>Nasıl yapılır: Özel bir SharePoint Proje Öğe Türüne Özellik Ekleme
  Özel bir SharePoint Proje öğe türüne tanımladığınızda, bir özellik için proje öğesi ekleyebilirsiniz. Özellik görünür **özellikleri** proje öğesi seçildiğinde penceresi **Çözüm Gezgini**.  
  
 Aşağıdaki adımlarda kendi SharePoint Proje öğe türüne önceden tanımlamış olduğunuz varsayılmaktadır. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
### <a name="to-add-a-property-to-a-definition-of-a-project-item-type"></a>Bir proje öğesi türü tanımına özellik eklemek için  
  
1.  Sınıfı için özel proje öğesi türü ekleme özelliği temsil eden bir ortak özellik ile tanımlayabilirsiniz. Özel proje öğesi türü için birden çok özellik eklemek istiyorsanız, tüm özelliklerin aynı sınıfın veya farklı sınıfların tanımlayabilirsiniz.  
  
2.  İçinde <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> yöntemi, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> uygulaması, tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> olayı *projectItemTypeDefinition* parametresi.  
  
3.  Olay işleyicisi içinde <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> olayı, özel özellikler sınıfının bir örneğini ekleme <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemPropertiesRequestedEventArgs.PropertySources%2A> olay bağımsız değişken parametre koleksiyonu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde adlı bir özellik eklemek gösterilmiştir **örnek özellik** özel bir proje öğesi türü.  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#11)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#11](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#11)]  
  
### <a name="understanding-the-code"></a>Kodu anlama  
 Aynı örneği emin olmak için `CustomProperties` sınıfı, her zaman kullanılır <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> olayı oluşur, kod örneği için özellikleri nesnesi kaydeder <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> bu olay proje öğesi ilk defasında özelliği. Bu olay tekrar oluştuğunda kodu bu nesneyi alır. Kullanma hakkında daha fazla bilgi için <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> proje öğeleri ile verileri kaydetmek için özelliğine bakın [SharePoint araç uzantıları ile özel verileri ilişkilendirme](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
 Özellik değeri değişiklikleri kalıcı hale getirmek için **ayarlamak** için erişimci `ExampleProperty` yeni değerini kaydeder <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> özelliği <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> özelliği ilişkili olduğu nesne. Kullanma hakkında daha fazla bilgi için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> proje öğeleri verilerle kalıcı hale getirmek için özelliğine bakın [SharePoint Proje sisteminin uzantılarında veri kaydetme](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
### <a name="specifying-the-behavior-of-custom-properties"></a>Özel özellikler davranışını belirtme  
 Bir özel özellik nasıl görüntülenir ve içinde davranacağını tanımlayabilirsiniz **özellikleri** öznitelikleri uygulayarak penceresi <xref:System.ComponentModel> özellik tanımı için ad alanı. Aşağıdaki öznitelikler birçok senaryolarda kullanışlıdır:  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>: Görünür özelliğinin adını belirtir **özellikleri** penceresi.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>: Belirtir görüntülenen açıklama dizesi tabanında **özellikleri** özelliği seçildiğinde penceresi.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>: Özelliğin varsayılan değeri belirtir.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>: Görüntülenen dize arasında özel bir dönüştürme belirtir **özellikleri** penceresi ve bir dize olmayan özellik değeri.  
  
-   <xref:System.ComponentModel.EditorAttribute>: Özelliği değiştirmek için kullanılacak özel bir düzenleyici belirtir.  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu kod örnekleri, bir sınıf kitaplığı projesi aşağıdaki derlemeler başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-project-item"></a>Proje öğesi dağıtma  
 Proje öğesi kullanmak diğer geliştiriciler etkinleştirmek için bir proje şablonu veya bir proje öğesi şablonu oluşturun. Daha fazla bilgi için bkz: [öğe şablonları oluşturma ve SharePoint Proje öğeleri için proje şablonları](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
 Proje öğesi dağıtmak için Oluştur bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme, şablonun ve proje öğesi ile dağıtmak istediğiniz diğer tüm dosyalar. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir SharePoint proje öğesi türü tanımlama](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [Nasıl yapılır: özel SharePoint Proje öğe türüne bir kısayol menü öğesi ekleme](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [Özel SharePoint Proje Öğesi Türleri Tanımlama](../sharepoint/defining-custom-sharepoint-project-item-types.md)  
  
  