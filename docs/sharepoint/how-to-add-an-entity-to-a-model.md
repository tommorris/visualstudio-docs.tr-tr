---
title: "Nasıl yapılır: bir modele bir varlık ekleme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EntityTool
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
ms.assetid: 139a6639-dabe-4e14-bb64-e5f4efb6f2fb
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d8cc1bf4871ef91c5b08cb77963a70e422ee3cdc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Nasıl yapılır: belirli bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-specific-finder-method.md)  
  
  