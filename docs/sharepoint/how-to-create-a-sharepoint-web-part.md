---
title: "Nasıl yapılır: bir SharePoint Web Bölümü oluşturma | Microsoft Docs"
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
- Web Parts [SharePoint development in Visual Studio], adding
- Web Parts [SharePoint development in Visual Studio], creating
ms.assetid: 0d037522-c25e-4c24-93b7-518db0f791b7
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f5d4f06b13c1c27c9f4b5e245e73929596dcf423
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-sharepoint-web-part"></a>Nasıl yapılır: Bir SharePoint Web Bölümü Oluşturma
  Oluşturabilir ve web bölümünü ekleyerek özelleştirme bir **Web Bölümü** öğesi herhangi bir SharePoint projesine ve kod dosyası web bölümü için veya bir tasarımcı kullanarak düzenleme. Daha fazla bilgi için bkz: [nasıl yapılır: Tasarımcı kullanarak bir SharePoint Web Bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md).  
  
### <a name="to-create-a-sharepoint-web-part"></a>Bir SharePoint Web bölümü oluşturmak için  
  
1.  Oluşturun veya bir SharePoint proje açın.  
  
     Daha fazla bilgi için bkz: [SharePoint Proje ve proje öğesi şablonları](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  SharePoint proje düğümünde seçin **Çözüm Gezgini** ve ardından **proje**, **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, genişletin **SharePoint** düğümünü ve ardından **2010** düğümü.  
  
4.  SharePoint şablonları listesinden seçip **Web Bölümü**.  
  
5.  İçinde **adı** kutusunda web bölümü için bir ad belirtin ve ardından **Ekle** düğmesi.  
  
     Web bölümü görünür **Çözüm Gezgini**. Bir web bölümü içeren dosyaları hakkında daha fazla bilgi için bkz: [SharePoint Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md).  
  
6.  İçinde **Çözüm Gezgini**, az önce oluşturduğunuz web bölümü için kod dosyasını açın.  
  
     Örneğin, web bölümünün adı WebPart1 ise, WebPart1.vb (Visual Basic'te) veya (C# ' ta) WebPart1.cs açın.  
  
7.  Kod dosyasında denetimlerine ekleme <xref:System.Web.UI.Control.CreateChildControls%2A> yöntemi.  
  
     Bir örnek için bkz: [izlenecek yol: SharePoint için bir Web Bölümü oluşturma](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint için Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Nasıl yapılır: Tasarımcı kullanarak bir SharePoint Web Bölümü oluşturma](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [İzlenecek yol: SharePoint için bir Web Bölümü oluşturma](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)   
 [İzlenecek Yol: Tasarımcı Kullanarak SharePoint için bir Web Bölümü Oluşturma](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)  
  
  