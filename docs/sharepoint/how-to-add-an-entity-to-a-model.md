---
title: 'Nasıl yapılır: bir modele bir varlık ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- EntityTool
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], entity
- Business Data Connectivity service [SharePoint development in Visual Studio], adding an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], entity
- BDC [SharePoint development in Visual Studio], adding an entity
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f59f5e1b31baf9f731f58c9f21163c2a54f2a238
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-an-entity-to-a-model"></a>Nasıl yapılır: Modele bir Varlık Ekleme
  Bir varlık oluşturmak için Visual Studio'dan bir varlık denetim ekleme **araç** iş verileri bağlantı (BDC) tasarımcıya.  
  
### <a name="to-add-an-entity-to-the-model"></a>Modele bir varlık eklemek için  
  
1.  Bir BDC projesi oluşturduğunuzda veya mevcut bir BDC projesini açın. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
2.  İçinde **araç**, gelen **BusinessDataCatalog** grubunda, ekleme bir **varlık** tasarımcıya denetim.  
  
     Yeni varlık Tasarımcısı üzerinde görüntülenir. Visual Studio ekler bir `<Entity>` projenizdeki BDC modeli dosyası XML öğesi. Bir varlık öğe öznitelikleri hakkında daha fazla bilgi için bkz: [varlık](http://go.microsoft.com/fwlink/?LinkId=169296).  
  
3.  Varlık için kısayol menüsünü designer'ı açın, seçin **Ekle**ve ardından **tanımlayıcısı**.  
  
     Yeni bir tanımlayıcı varlık üzerinde görüntülenir.  
  
    > [!NOTE]  
    >  Varlık ve tanımlayıcı adını değiştirebilirsiniz **özellikleri** penceresi.  
  
4.  Varlık alanlarını bir sınıfta tanımlayın. Projeye yeni bir sınıf ekleyin veya Nesne İlişkisel Tasarımcısı (O/R Tasarımcısı) gibi diğer araçları kullanarak oluşturduğunuz varolan bir sınıfa kullanın. Aşağıdaki örnek Contact adlı bir varlık sınıfı gösterir.  
  
     [!code-csharp[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/CSharp/sp_bdc_entity_data_class/bdcmodel1/contact.cs#1)]
     [!code-vb[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/VisualBasic/sp_bdc_entity_data_class/bdcmodel1/contact.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir yaratıcı yöntemi ekleme](../sharepoint/how-to-add-a-creator-method.md)   
 [Nasıl yapılır: bir Silici yöntemi ekleme](../sharepoint/how-to-add-a-deleter-method.md)   
 [Nasıl yapılır: bir güncelleyici yöntemi ekleme](../sharepoint/how-to-add-an-updater-method.md)   
 [Nasıl yapılır: bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-finder-method.md)   
 [Nasıl yapılır: Belirli bir Bulucu Metodu Ekleme](../sharepoint/how-to-add-a-specific-finder-method.md)  
  
  