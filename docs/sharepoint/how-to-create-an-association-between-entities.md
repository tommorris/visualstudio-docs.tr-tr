---
title: 'Nasıl yapılır: varlıklar arasında ilişkilendirme oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- AssociationGroupTool
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], create an assocation
- Business Data Connectivity service [SharePoint development in Visual Studio], associations between entities
- BDC [SharePoint development in Visual Studio], associations between entities
- Business Data Connectivity service [SharePoint development in Visual Studio], create an assocation
- Business Data Connectivity service [SharePoint development in Visual Studio], associate external content types
- Business Data Connectivity service [SharePoint development in Visual Studio], relate entities
- BDC [SharePoint development in Visual Studio], relate entities
- BDC [SharePoint development in Visual Studio], associate external content types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c341586fbd2a22f38385a6c613058318f5c2d6a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-an-association-between-entities"></a>Nasıl yapılır: Varlıklar Arasında İlişkilendirme Oluşturma
  İş verileri bağlantı (BDC) modelinizdeki ilişkilendirmeleri oluşturarak varlıklar arasındaki ilişkiler tanımlayabilirsiniz. Visual Studio tüketicileri modelin her bir ilişkilendirme hakkında bilgi sağlayan yöntemler oluşturur. Bu yöntemler, SharePoint web bölümleri, liste veya veri ilişkileri kullanıcı arabiriminde (UI) görüntülemek için özel uygulamaları tarafından kullanılabilecek.  
  
 BDC Tasarımcısı'nda ilişkilendirmeleri iki tür oluşturabilirsiniz: yabancı anahtar tabanlı ilişkileri ve yabancı anahtar kullanmadan ilişkilendirmeleri. Daha fazla bilgi için bkz: [arasında bir ilişki varlıkları oluşturma](../sharepoint/creating-an-association-between-entities.md).  
  
### <a name="to-create-an-association-between-entities"></a>Varlıklar arasında ilişkilendirme oluşturmak için  
  
1.  Üzerinde **BusinessDataConnectivity** sekmesinde **araç**, seçin **ilişkilendirme** öğesi.  
  
2.  BDC Tasarımcısı kaynak varlık seçin ve ardından hedef varlık seçin.  
  
     **İlişkilendirme Düzenleyicisi** görüntülenir.  
  
3.  Bir yabancı anahtar tabanlı ilişkisi oluşturmak isteyip istemediğinizi seçin **yabancı anahtar ilişkilendirmesi olduğundan** onay kutusu.  
  
    1.  İçinde **kaynak kimliği** sütunu **tanımlayıcı eşleştirme** tablo, görünür eşleşen her tür tanımlayıcı yanındaki tanımlayıcı seçin **alan** sütun.  
  
         Örneğin, **kaynak kimliği** sütun, select `ContactID` yanına `ReadList.salesOrderList.SalesOrderList.SalesOrder.ContactID` tür tanımlayıcısı ve `ReadItem.salesOrder.SalesOrder.ContactID` tür tanımlayıcısı.  
  
4.  Bir yabancı anahtar kullanmadan ilişkisi oluşturmak istiyorsanız, temizleyin **yabancı anahtar ilişkilendirmesi olduğundan** onay kutusu.  
  
5.  Seçin **Tamam** düğmesi.  
  
6.  BDC Designer'ı kaynak varlık ve hedef varlık ilişkiyi gösteren bir çizgi görünür.  
  
     Visual Studio hizmeti hedef varlık ve hizmet sınıf kaynak varlık ilişkisi Gezgini yönteme ekler. İlişkilendirme Gezinti yöntemleri hakkında daha fazla bilgi için bkz: [desteklenen işlemler](http://go.microsoft.com/fwlink/?LinkId=169286).  
  
7.  Kaynak varlık ilişkisi Gezgini yönteminde hedef varlık koleksiyonunu döndürür kodu ekleyin.  
  
8.  Hedef varlık ilişkisi Gezgini yönteminde ilişkili kaynak varlık döndüren kodu ekleyin.  
  
     İlişkilendirme Gezgini yöntemleri örnekler için bkz: [arasında bir ilişki varlıkları oluşturma](../sharepoint/creating-an-association-between-entities.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Varlıklar arasında ilişkilendirme oluşturma](../sharepoint/creating-an-association-between-entities.md)   
 [İş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Nasıl yapılır: bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-finder-method.md)   
 [Nasıl yapılır: belirli bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Nasıl yapılır: bir yaratıcı yöntemi ekleme](../sharepoint/how-to-add-a-creator-method.md)   
 [Nasıl yapılır: bir Silici yöntemi ekleme](../sharepoint/how-to-add-a-deleter-method.md)   
 [Nasıl yapılır: bir güncelleyici yöntemi ekleme](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md)   
 [Nasıl yapılır: bir yönteme parametre ekleme](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Nasıl yapılır: yöntem örneği tanımlama](../sharepoint/how-to-define-a-method-instance.md)   
 [Nasıl yapılır: bir parametrenin tür tanımlayıcısını tanımlama](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [İzlenecek yol: İş Verileri Kullanarak SharePoint'te Dış Liste Oluşturma](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)  
  
  