---
title: "Nasıl yapılır: olay alıcısı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.SPE.EventReceiver
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, event receivers
- event receivers [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 1b00d82679388c50d6d111209a9a206bd9587a3a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-an-event-receiver"></a>Nasıl yapılır: Olay Alıcısı Oluşturma
  Oluşturarak *Olay alıcıları*, bir kullanıcı SharePoint öğeleri listeler gibi veya liste öğesi ile etkileşim sırasında yanıt verebilir. Örneğin, bir kullanıcı takvimi değiştirir veya kişi listesinden bir ad sildiğinde olay alıcı kodda tetiklenebilir. Bu konuda izleyerek bir liste örneği için olay alıcı eklemek nasıl öğrenebilirsiniz.  
  
 Bu adımları tamamlamak için yüklemiş olmalısınız [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve Windows ve SharePoint sürümleri desteklenir. Daha fazla bilgi için bkz: [SharePoint çözümleri geliştirmek için gereksinimleri](../sharepoint/requirements-for-developing-sharepoint-solutions.md). Bu örnek bir SharePoint Proje gerektirdiğinden, ayrıca konudaki yordamı tamamlamış olmalıdır [izlenecek yol: bir Site sütunu, içerik türü ve SharePoint listesi oluşturma](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).  
  
## <a name="adding-an-event-receiver"></a>Olay alıcısı ekleme  
 Oluşturduğunuz proje [izlenecek yol: SharePoint için Site sütunu, içerik türü ve liste oluşturma](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md) özel site sütunları, özel bir listesi ve bir içerik türü içerir. Aşağıdaki yordamda, bu proje bir basit olay işleyicisi (olay alıcı) listeleri gibi SharePoint öğelerinde meydana gelen olayları nasıl ele alınacağını göstermek için bir liste örneği için eklenerek.  
  
#### <a name="to-add-an-event-receiver-to-the-list-instance"></a>Liste örneği için olay alıcı eklemek için  
  
1.  Oluşturduğunuz Proje Aç [izlenecek yol: bir Site sütunu, içerik türü ve SharePoint listesi oluşturma](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md).  
  
2.  İçinde **Çözüm Gezgini**, adlı SharePoint projesi düğümünü seçin **Clinic**.  
  
3.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.  
  
4.  Ya da altında **Visual C#** veya **Visual Basic**, genişletin **SharePoint** düğümünü ve ardından **2010** öğesi.  
  
5.  İçinde **şablonları** bölmesinde seçin **olay alıcısı**, adlandırın **TestEventReceiver1**ve ardından **Tamam** düğmesi.  
  
     **SharePoint Özelleştirme Sihirbazı'nı** görüntülenir.  
  
6.  İçinde **ne tür bir olay alıcısına istiyor musunuz?** listesinde, seçin **liste öğesi olayları**.  
  
7.  İçinde **öğesinin ne olay kaynağı olmalıdır?** listesinde, seçin **hastalar (Clinic\Patients)**.  
  
8.  İçinde **aşağıdaki olayları işlemek** listesinde, onay kutusunu işaretleyin **bir öğe eklendi**ve ardından **son** düğmesi.  
  
     Yeni olay alıcısı için kod dosyası adlı tek bir yöntem içerir `ItemAdded`. Sonraki adımda, her kişi Scott kahverengi varsayılan olarak adlandırılır böylece bu yöntem için kod ekleyeceksiniz.  
  
9. Varolan `ItemAdded` yöntemi aşağıdaki kod ve F5 tuşuna seçin:  
  
     [!code-csharp[SP_EventReceiver#1](../sharepoint/codesnippet/CSharp/CustomField1/TestEventReceiver1/TestEventReceiver1.cs#1)]
     [!code-vb[SP_EventReceiver#1](../sharepoint/codesnippet/VisualBasic/CustomField1_VB/EventReceiver1/EventReceiver1.vb#1)]  
  
     Kod çalışır ve SharePoint sitesi web tarayıcısında görüntülenir.  
  
10. Hızlı Başlatma çubuğunda seçin **hastalar** bağlamak ve ardından **Yeni Öğe Ekle** bağlantı.  
  
     Yeni öğe girişi formu açılır.  
  
11. Veri alanları girin ve ardından **kaydetmek** düğmesi.  
  
     Seçtiğiniz sonra **kaydetmek** düğmesini **hasta adı** sütun Scott kahverengi adına otomatik olarak güncelleştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümleri Geliştirme](../sharepoint/developing-sharepoint-solutions.md)  
  
  