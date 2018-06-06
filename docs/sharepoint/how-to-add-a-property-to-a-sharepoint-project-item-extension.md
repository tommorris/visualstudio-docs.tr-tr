---
title: 'Nasıl yapılır: bir SharePoint Proje öğe uzantısına özellik ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 50cbb0eb3a9c0c24abaa3734b7fa9cbd01e839b7
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766733"
---
# <a name="how-to-add-a-property-to-a-sharepoint-project-item-extension"></a>Nasıl yapılır: bir SharePoint Proje öğe uzantısına özellik ekleme
  Visual Studio'da zaten yüklü herhangi bir SharePoint proje öğesi bir özellik eklemek için bir proje öğesi uzantısı kullanabilirsiniz. Özellik görünür **özellikleri** proje öğesi seçildiğinde penceresi **Çözüm Gezgini**.  
  
 Aşağıdaki adımlar, bir proje öğesi uzantısı zaten oluşturduğunuzu varsayalım. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
### <a name="to-add-a-property-to-a-project-item-extension"></a>Bir proje öğe uzantısına özellik eklemek için  
  
1.  Sınıfı için bir proje öğesi türü ekleme özelliği temsil eden bir ortak özellik ile tanımlayabilirsiniz. Bir proje öğesi türü için birden çok özellik eklemek istiyorsanız, tüm özelliklerin aynı sınıfın veya farklı sınıfların tanımlayabilirsiniz.  
  
2.  İçinde <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> yöntemi, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> uygulaması, tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> olayı *projectItemType* parametresi.  
  
3.  Olay işleyicisi içinde <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> olay özellikleri sınıfına bir örnek ekler <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemPropertiesRequestedEventArgs.PropertySources%2A> olay bağımsız değişken parametre koleksiyonu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde adlı bir özellik eklemek gösterilmiştir **örnek özellik** için olay alıcı proje öğesi.  
  
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#8](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemextensionproperty.cs#8)]
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#8](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemextensionproperty.vb#8)]  
  
### <a name="understanding-the-code"></a>Kodu anlama  
 Aynı örneği emin olmak için `CustomProperties` sınıfı, her zaman kullanılır <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemPropertiesRequested> olayı oluşur, kod örneği için özellikleri nesnesi ekler <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> bu olay proje öğesi ilk defasında özelliği. Bu olay tekrar oluştuğunda kodu bu nesneyi alır. Kullanma hakkında daha fazla bilgi için <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> verileri proje öğeleri ile ilişkilendirmek için özelliğine bakın [SharePoint araç uzantıları ile özel verileri ilişkilendirme](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
 Özellik değeri değişiklikleri kalıcı hale getirmek için **ayarlamak** için erişimci `ExampleProperty` yeni değerini kaydeder <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> özelliği <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem> özelliği ilişkili olduğu nesne. Kullanma hakkında daha fazla bilgi için <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem.ExtensionData%2A> proje öğeleri verilerle kalıcı hale getirmek için özelliğine bakın [SharePoint Proje sisteminin uzantılarında veri kaydetme](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
### <a name="specifying-the-behavior-of-custom-properties"></a>Özel özellikler davranışını belirtme  
 Bir özel özellik nasıl görüntülenir ve içinde davranacağını tanımlayabilirsiniz **özellikleri** öznitelikleri uygulayarak penceresi <xref:System.ComponentModel> özellik tanımı için ad alanı. Aşağıdaki öznitelikler birçok senaryolarda kullanışlıdır:  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>: Görünür özelliğinin adını belirtir **özellikleri** penceresi.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>: Belirtir görüntülenen açıklama dizesi tabanında **özellikleri** özelliği seçildiğinde penceresi.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>: Özelliğin varsayılan değeri belirtir.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>: Görüntülenen dize arasında özel bir dönüştürme belirtir **özellikleri** penceresi ve bir dize olmayan özellik değeri.  
  
-   <xref:System.ComponentModel.EditorAttribute>: Özelliği değiştirmek için kullanılacak özel bir düzenleyici belirtir.  
  
## <a name="compiling-the-code"></a>Kod derleme  
 Bu örnekler bir sınıf kitaplığı projesi aşağıdaki derlemeler başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Uzantısını dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
 [Nasıl yapılır: bir SharePoint proje öğesi uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [Nasıl yapılır: bir SharePoint Proje öğe uzantısına bir kısayol menü öğesi ekleme](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)   
 [SharePoint proje öğelerini genişletme](../sharepoint/extending-sharepoint-project-items.md)   
 [İzlenecek yol: Bir SharePoint Proje Öğesi Türünü Genişletme](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  
