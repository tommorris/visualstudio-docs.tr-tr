---
title: 'Nasıl yapılır: bir Bulucu yöntemi ekleme | Microsoft Docs'
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
- BDC [SharePoint development in Visual Studio], get entities
- Business Data Connectivity service [SharePoint development in Visual Studio], return entities
- BDC [SharePoint development in Visual Studio], return entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Finder method
- Business Data Connectivity service [SharePoint development in Visual Studio], get entities
- BDC [SharePoint development in Visual Studio], Finder method
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3c7233f344282b5ce5793f7b6733e5e657534023
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756986"
---
# <a name="how-to-add-a-finder-method"></a>Nasıl yapılır: bir Bulucu yöntemi ekleme
  Bir web bölümü veya listedeki varlıkların listesini görüntülemek iş verileri bağlantı (BDC) hizmetini etkinleştirmek için oluşturmalısınız bir *Bulucu* yöntemi. Bir Bulucu yöntemi varlık örneklerinin bir koleksiyonunu döndürür özel bir yöntemdir. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-a-finder-method"></a>Bir Bulucu yöntemi oluşturmak için  
  
1.  Üzerinde **BDC Tasarımcısı**, bir varlık seçin.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: bir modele bir varlık ekleme](../sharepoint/how-to-add-an-entity-to-a-model.md).  
  
2.  Menü çubuğunda seçin **Görünüm** > **diğer pencereler** > **BDC yöntem ayrıntıları**.  
  
     **BDC yöntem ayrıntıları** penceresi açılır. Hakkında daha fazla bilgi için **BDC yöntem ayrıntıları** penceresinde bkz [BDC modeli Tasarım araçları genel bakış](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  İçinde **bir yöntem ekleyin** listesinde, seçin **oluşturma Bulucu yöntemi**.  
  
     Visual Studio bir yöntemi, dönüş parametresi ve bir tür tanımlayıcı ekler.  
  
4.  Tür tanımlayıcısı bir varlık koleksiyon türü tanımlayıcısı olarak yapılandırın. Bir varlık koleksiyon türü tanımlayıcısı oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir parametrenin tür tanımlayıcısını tanımlama](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
    > [!NOTE]  
    >  Belirli bir Bulucu yöntemi varlığa eklediyseniz, bu adımı gerçekleştirmeniz gerekmez. Visual Studio belirli bir Bulucu yöntemine tanımlı tür tanımlayıcı kullanır.  
  
5.  İçinde **Çözüm Gezgini**oluşturulan hizmet kod dosyasının varlığı için kısayol menüsünü açın ve ardından **görünümü kodu**. Hizmeti kod dosyasını hakkında daha fazla bilgi için bkz: [iş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
6.  Kodu Bulucu yöntemine ekleyin. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Verileri veri kaynağından alır.  
  
    -   BDC hizmete varlıkların listesini döndürür.  
  
     Aşağıdaki örnekte bir koleksiyonunu döndürür `Contact` AdventureWorks örnek veritabanından veri için SQL Server kullanarak varlıklar.  
  
    > [!NOTE]  
    >  Değerini `ServerName` alanını sunucunuzun adıyla.  
  
     [!code-csharp[SP_BDC#2](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#2)]
     [!code-vb[SP_BDC#2](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#2)]  
  
## <a name="see-also"></a>Ayrıca bkz.
 [BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md)   
 [İş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Nasıl yapılır: belirli bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Nasıl yapılır: bir yaratıcı yöntemi ekleme](../sharepoint/how-to-add-a-creator-method.md)   
 [Nasıl yapılır: bir Silici yöntemi ekleme](../sharepoint/how-to-add-a-deleter-method.md)   
 [Nasıl yapılır: bir güncelleyici yöntemi ekleme](../sharepoint/how-to-add-an-updater-method.md)   
 [Nasıl yapılır: bir yönteme parametre ekleme](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Nasıl yapılır: yöntem örneği tanımlama](../sharepoint/how-to-define-a-method-instance.md)  
  
  
