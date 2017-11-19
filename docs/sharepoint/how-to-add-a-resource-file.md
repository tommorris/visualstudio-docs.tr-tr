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
ms.assetid: 2b4ac232-992e-4070-8e98-6f11eb88e1a8
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7233bc1a739bd3bf6544aad879f898bf3848ee7b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  