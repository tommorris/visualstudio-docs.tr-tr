---
title: 'Nasıl yapılır: SharePoint çözümleri için özel özellik ve paket doğrulama kuralları oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending deployment
- SharePoint development in Visual Studio, validation rules
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0c68df756e24fc45603d34dd6982a09889bd5203
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-custom-feature-and-package-validation-rules-for-sharepoint-solutions"></a>Nasıl yapılır: SharePoint Çözümleri için Özel Özellik ve Paket Doğrulama Kuralları Oluşturma
  Visual Studio tarafından üretilen çözüm paketi doğrulamak için özel doğrulama kuralları oluşturabilirsiniz. Seçerek bir özelliğin tamamı veya paket tam doğrulama gerçekleştirebilirsiniz **doğrulama** bir paket veya özelliği bağlam menüsünden **PackagingExplorer**. Paket ya da özellik geçerli bir durumda olacaktır, belirlemek için projeye yeni SharePonit proje öğeleri veya özellikleri eklediğinizde, kısmi doğrulama gerçekleştirilir.  
  
### <a name="to-create-a-custom-package-validation-rule"></a>Özel paket doğrulama kuralı oluşturmak için  
  
1.  Bir sınıf kitaplığı projesi oluşturun.  
  
2.  Aşağıdaki derlemelere başvurular ekleyin:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  Aşağıdaki arabirimlerinden biri, uygulayan bir sınıf oluşturun:  
  
    -   Bir paket doğrulama kuralı oluşturmak için uygulaması <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> arabirimi.  
  
    -   Bir özellik doğrulama kuralı oluşturmak için uygulaması <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> arabirimi.  
  
4.  Ekleme <xref:System.ComponentModel.Composition.ExportAttribute> sınıfa. Bu öznitelik bulmak ve doğrulama kuralı yüklemek Visual Studio sağlar. Geçirmek <xref:Microsoft.VisualStudio.SharePoint.Validation.IPackageValidationRule> veya <xref:Microsoft.VisualStudio.SharePoint.Validation.IFeatureValidationRule> öznitelik oluşturucunun türü.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde bir özel özellik doğrulama kuralının nasıl oluşturulacağı gösterilmektedir.  
  
 [!code-vb[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/VisualBasic/featurevalidation/extension/customvalidationrule.vb#1)]
 [!code-csharp[SPExtensibility.FeatureValidation#1](../sharepoint/codesnippet/CSharp/featurevalidation/extension/customfeaturevalidationrule.cs#1)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bu örnekte aşağıdaki derlemelere başvuruları gerektirir:  
  
-   Microsoft.VisualStudio.SharePoint.  
  
-   System.ComponentModel.Composition.  
  
## <a name="deploying-the-extension"></a>Uzantısını dağıtma  
 Uzantıyı dağıtmak için oluşturma bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] uzantısı (VSIX) paketini derleme ve uzantısıyla dağıtmak istediğiniz diğer dosyalar için. Daha fazla bilgi için bkz: [dağıtma uzantıları Visual Studio'da SharePoint araçları için](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Paketleme ve Dağıtımını Genişletme](../sharepoint/extending-sharepoint-packaging-and-deployment.md)  
  
  