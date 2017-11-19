---
title: "Nasıl yapılır: proje çıktı başvurusu ekleme | Microsoft Docs"
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
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
ms.assetid: 9d6bc25e-bf0d-4483-a691-2ad7a796fa80
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: faf46489be0b9a56485fc93c2138a7f6702c4778
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-project-output-reference"></a>Nasıl yapılır: Proje Çıktı Başvurusu Ekleme
  SharePoint olmayan proje derlemeler (veya Silverlight projeleri .xap dosyalarında) SharePoint'e dağıtmak için proje çıktı başvurusu ekleyin.  
  
 Bu işlem, iki proje arasındaki çözümü derleme bağımlılık oluşturur. SharePoint Proje oluşturulan ve dağıtılan önce proje çıktı başvuruları ile ilişkili projeleri oluşturulur.  
  
### <a name="to-add-a-project-output-reference"></a>Proje çıktı başvurusu ekleme  
  
1.  En az bir SharePoint Proje ve bir SharePoint olmayan proje içeren bir çözüm yükleyin.  
  
2.  İçinde **Çözüm Gezgini**, SharePoint proje düğümünde bir öğe seçin.  
  
3.  İçinde **özellikleri** penceresinde, seçin **proje çıktı başvuruları** özelliği ve ardından üç nokta (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP. Asp.net Mobil Tasarımcı elips")) yanında düğmesi.  
  
4.  İçinde **proje çıktı başvuruları** iletişim kutusunda, seçin **Ekle** düğmesi.  
  
5.  Özellikler bölmesinde oku seçin **dağıtım türü** özelliği ve ardından uygun değeri başvuruda, gibi SharePoint olmayan öğe için **ElementFile**.  
  
6.  Oku seçin **proje adı**olmayan SharePoint proje öğesi adını seçin ve ardından **Tamam** düğmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paketleme ve dağıtım bilgileri proje öğeleri sağlama](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Nasıl yapılır: denetimleri güvenli denetim olarak işaretle](../sharepoint/how-to-mark-controls-as-safe-controls.md)   
 [Paketleme ve SharePoint çözümlerini dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  