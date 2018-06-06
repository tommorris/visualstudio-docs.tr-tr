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
ms.openlocfilehash: 533deb22f37af012ab9c4fd3a8d369edad64ce06
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766834"
---
# <a name="how-to-add-a-resource-file"></a>Nasıl yapılır: kaynak dosyası ekleme
  Kaynak dosyaları eklemek için komuttur çözüm düğümüne ve Çözüm Gezgini'nde özelliği düğümleri kısayol menüsünde. Daha fazla bilgi için bkz: [SharePoint Çözümlerini Yerelleştirme](../sharepoint/localizing-sharepoint-solutions.md).  
  
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
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
 