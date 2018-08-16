---
title: 'Nasıl yapılır: kaynak dosyası ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3406e65ad96b93cd21890d61270c0ed989ad496c
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756577"
---
# <a name="how-to-add-a-resource-file"></a>Nasıl yapılır: kaynak dosyası ekleme
  Kaynak dosyaları eklemek için komuttur çözüm düğümüne ve Çözüm Gezgini'nde özelliği düğümleri kısayol menüsünde. Daha fazla bilgi için bkz: [yerelleştirme SharePoint çözümlerini](../sharepoint/localizing-sharepoint-solutions.md).  
  
### <a name="to-add-a-global-resource-file-to-a-sharepoint-solution"></a>Bir SharePoint çözüm genel kaynak dosyası eklemek için  
  
1.  İçinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], bir SharePoint çözüm açın.  
  
2.  İçinde **Çözüm Gezgini**, bir SharePoint proje düğümü seçin ve ardından, menü çubuğunda, **proje** > **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, seçin **Genel kaynaklar dosyası** şablonu ve ardından **Ekle** düğmesi.  
  
    > [!NOTE]  
    >  Yalnızca bir SharePoint proje öğesi seçildiğinde Genel kaynaklar dosyası proje öğesi şablonu görüntülenir.  
  
4.  İçinde **kaynak ekleme** iletişim kutusunda, İngilizce (ABD) gibi kaynak dosyası için bir kültür seçin.  
  
     Bu adım, çözümünüzün biçimde, kaynak genel kaynak dosyası ekler * x ***.*** kültür ***.** resx, gibi *Resource1.en US.resx*.  
  
5.  Zaman **Kaynak Düzenleyici** açılır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], kaynak kaynak dosyasına ekleyin.  
  
### <a name="to-add-a-feature-resource-file-to-a-sharepoint-feature"></a>Bir SharePoint özelliğini bir özellik kaynak dosyası eklemek için  
  
1.  SharePoint çözüm içinde açık değilse [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], çözümü açın.  
  
2.  İçinde **Çözüm Gezgini**, bir özelliği adı için kısayol menüsünü açın **özellikleri** düğümünü ve ardından **özelliği kaynak ekleme**.  
  
     Bu adım, biçiminde özellik kaynak dosyası ekler * ResourceFileName ***.*** kültür ***.** resx, gibi *Feature1.en US.resx*.  
  
3.  Zaman **Kaynak Düzenleyici** açılır [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], kaynak kaynak dosyasına ekleyin.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [SharePoint çözümleri geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
 
