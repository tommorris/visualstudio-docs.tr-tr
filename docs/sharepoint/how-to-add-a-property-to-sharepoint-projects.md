---
title: 'Nasıl yapılır: SharePoint projelerine özellik ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 015725197c2c269a7b6aed2e20f0159e2a9f2fe6
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758565"
---
# <a name="how-to-add-a-property-to-sharepoint-projects"></a>Nasıl yapılır: SharePoint projelerine özellik ekleme
  Herhangi bir SharePoint projesine bir özellik eklemek için bir proje uzantısı kullanabilirsiniz. Özellik görünür **özellikleri** proje seçildiğinde penceresi **Çözüm Gezgini**.  
  
 Aşağıdaki adımlar, bir proje uzantısı zaten oluşturduğunuzu varsayalım. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint proje uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
### <a name="to-add-a-property-to-a-sharepoint-project"></a>Bir SharePoint projesine bir özellik eklemek için  
  
1.  SharePoint projelerine ekleme özelliği temsil eden bir ortak özelliği ile bir sınıf tanımlayın. Birden çok özellik eklemek istiyorsanız, tüm özelliklerin aynı sınıfın veya farklı sınıfların tanımlayabilirsiniz.  
  
2.  İçinde <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> yöntemi, <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> uygulaması, tanıtıcı <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> olayı *projectService* parametresi.  
  
3.  Olay işleyicisi içinde <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> olay özellikleri sınıfına bir örnek ekler <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectPropertiesRequestedEventArgs.PropertySources%2A> olay bağımsız değişken parametre koleksiyonu.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, iki özellik SharePoint projelerine ekleme gösterilmiştir. Bir özellik devam ederse, proje kullanıcı seçeneği dosyasında verilerini ( *. csproj.user* dosya veya *. vbproj.user* dosyası). Diğer proje dosyasında verilerini kalıcı (*.csproj* dosya veya *.vbproj* dosyası).  
  
 [!code-vb[SpExt_SPCustomPrjProperty#1](../sharepoint/codesnippet/VisualBasic/customspproperty/customproperty.vb#1)]
 [!code-csharp[SpExt_SPCustomPrjProperty#1](../sharepoint/codesnippet/CSharp/customspproperty/customproperty.cs#1)]  
  
### <a name="understand-the-code"></a>Kodu anlama  
 Aynı örneği emin olmak için `CustomProjectProperties` sınıfı, her zaman kullanılır <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectPropertiesRequested> olayı oluşur, kod örneği için özellikleri nesnesi ekler <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> bu olay gerçekleştiğinde proje ilk özelliği. Bu olay tekrar oluştuğunda kodu bu nesneyi alır. Kullanma hakkında daha fazla bilgi için <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> verileri projeleri ile ilişkilendirmek için özelliğine bakın [SharePoint ile özel verileri ilişkilendirme uzantıları Araçları](../sharepoint/associating-custom-data-with-sharepoint-tools-extensions.md).  
  
 Özellik değerleri, değişiklikleri kalıcı hale getirmek için **ayarlamak** erişimciler özellikleri için aşağıdaki API'leri kullanın:  
  
-   `CustomUserFileProperty` kullanan <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject.ProjectUserFileData%2A> özellik değerini proje kullanıcı seçeneği dosyasına kaydedin.  
  
-   `CustomProjectFileProperty` kullanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> değerini proje dosyasına kaydetmek için yöntem.  
  
 Bu dosyalardaki kalıcı veriler hakkında daha fazla bilgi için bkz: [SharePoint Proje sisteminin uzantılarında veri kaydetme](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
### <a name="specify-the-behavior-of-custom-properties"></a>Özel özellikler davranışını belirtin  
 Bir özel özellik nasıl görüntülenir ve içinde davranacağını tanımlayabilirsiniz **özellikleri** öznitelikleri uygulayarak penceresi <xref:System.ComponentModel> özellik tanımı için ad alanı. Aşağıdaki öznitelikler birçok senaryolarda kullanışlıdır:  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>: Görünür özelliğinin adını belirtir **özellikleri** penceresi.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>: Belirtir görüntülenen açıklama dizesi tabanında **özellikleri** özelliği seçildiğinde penceresi.  
  
-   <xref:System.ComponentModel.DefaultValueAttribute>: Özelliğin varsayılan değeri belirtir.  
  
-   <xref:System.ComponentModel.TypeConverterAttribute>: Görüntülenen dize arasında özel bir dönüştürme belirtir **özellikleri** penceresi ve bir dize olmayan özellik değeri.  
  
-   <xref:System.ComponentModel.EditorAttribute>: Özelliği değiştirmek için kullanılacak özel bir düzenleyici belirtir.  
  
## <a name="compile-the-code"></a>Kod derleme  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint
-    
-   Microsoft.VisualStudio.Shell
-     
-   Microsoft.VisualStudio.Shell.Interop
-     
-   Microsoft.VisualStudio.Shell.Interop.8.0
-     
-   System.ComponentModel.Composition  
  
## <a name="deploy-the-extension"></a>Uzantısı dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [Visual Studio'da SharePoint araçları için Uzantılar dağıtmak](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint projeleri genişletme](../sharepoint/extending-sharepoint-projects.md)   
 [Nasıl yapılır: bir SharePoint proje uzantısı oluşturma](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [Nasıl yapılır: bir kısayol menü öğesini SharePoint projelerine ekleme](../sharepoint/how-to-add-a-shortcut-menu-item-to-sharepoint-projects.md)   
 [SharePoint Proje sistemini genişletme](../sharepoint/extending-the-sharepoint-project-system.md)  
  
  
