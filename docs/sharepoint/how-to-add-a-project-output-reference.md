---
title: 'Nasıl yapılır: proje çıktı başvurusu ekleme | Microsoft Docs'
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
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 97bfe044ef89691afdb1a8e845867ce2e177dbb9
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767969"
---
# <a name="how-to-add-a-project-output-reference"></a>Nasıl yapılır: proje çıktı başvurusu ekleme
  SharePoint olmayan proje derlemeler (veya Silverlight projeleri .xap dosyalarında) SharePoint'e dağıtmak için proje çıktı başvurusu ekleyin.  
  
 Bu işlem, iki proje arasındaki çözümü derleme bağımlılık oluşturur. SharePoint Proje oluşturulan ve dağıtılan önce proje çıktı başvuruları ile ilişkili projeleri oluşturulur.  
  
### <a name="to-add-a-project-output-reference"></a>Proje çıktı başvurusu ekleme
  
1.  En az bir SharePoint Proje ve bir SharePoint olmayan proje içeren bir çözüm yükleyin.  
  
2.  İçinde **Çözüm Gezgini**, SharePoint proje düğümünde bir öğe seçin.  
  
3.  İçinde **özellikleri** penceresinde, seçin **proje çıktı başvuruları** özelliği ve ardından üç nokta (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP. Asp.net Mobil Tasarımcı elips")) yanında düğmesi.  
  
4.  İçinde **proje çıktı başvuruları** iletişim kutusunda, seçin **Ekle** düğmesi.  
  
5.  Özellikler bölmesinde oku seçin **dağıtım türü** özelliği ve ardından uygun değeri başvuruda, gibi SharePoint olmayan öğe için **ElementFile**.  
  
6.  Oku seçin **proje adı**olmayan SharePoint proje öğesi adını seçin ve ardından **Tamam** düğmesi.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [Paketleme ve dağıtım bilgileri proje öğeleri sağlama](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Nasıl yapılır: denetimleri güvenli denetim olarak işaretle](../sharepoint/how-to-mark-controls-as-safe-controls.md)   
 [SharePoint Çözümlerini Paketleme ve Dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  