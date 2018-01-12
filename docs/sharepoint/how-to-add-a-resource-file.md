---
title: "Nasıl yapılır: kaynak dosyası ekleme | Microsoft Docs"
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
helpviewer_keywords:
- resource files [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, resource files
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 47cae5fac3ddbcbc34535176701d0293ae4f66ba
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-resource-file"></a>Nasıl yapılır: Kaynak Dosyası Ekleme
  Kaynak dosyaları eklemek için komuttur çözüm düğümüne ve Çözüm Gezgini'nde özelliği düğümleri kısayol menüsünde. Daha fazla bilgi için bkz: [SharePoint Çözümlerini Yerelleştirme](../sharepoint/localizing-sharepoint-solutions.md).  
  
### <a name="to-add-a-global-resource-file-to-a-sharepoint-solution"></a>Bir SharePoint çözüm genel kaynak dosyası eklemek için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], bir SharePoint çözüm açın.  
  
2.  İçinde **Çözüm Gezgini**, bir SharePoint proje düğümü seçin ve ardından, menü çubuğunda, **proje**, **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **Genel kaynaklar dosyası** şablonu ve ardından **Ekle** düğmesi.  
  
    > [!NOTE]  
    >  Yalnızca bir SharePoint proje öğesi seçildiğinde Genel kaynaklar dosyası proje öğesi şablonu görüntülenir.  
  
4.  İçinde **kaynak ekleme** iletişim kutusunda, İngilizce (ABD) gibi kaynak dosyası için bir kültür seçin.  
  
     Bu adım, çözümünüzün biçimde, kaynak genel kaynak dosyası ekler*x***.** *kültür***.** resx gibi Resource1.en US.resx.  
  
5.  Zaman **Kaynak Düzenleyici** açılır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], kaynak kaynak dosyasına ekleyin.  
  
### <a name="to-add-a-feature-resource-file-to-a-sharepoint-feature"></a>Bir SharePoint özelliğini bir özellik kaynak dosyası eklemek için  
  
1.  SharePoint çözüm içinde açık değilse [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], çözümü açın.  
  
2.  İçinde **Çözüm Gezgini**, bir özelliği adı için kısayol menüsünü açın **özellikleri** düğümünü ve ardından **özelliği kaynak ekleme**.  
  
     Bu adım, biçiminde özellik kaynak dosyası ekler *ResourceFileName***.** *kültür***.** resx gibi Feature1.en US.resx.  
  
3.  Zaman **Kaynak Düzenleyici** açılır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], kaynak kaynak dosyasına ekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  