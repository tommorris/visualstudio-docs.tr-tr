---
title: 'Nasıl yapılır: bir güncelleyici yöntemi ekleme | Microsoft Docs'
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
- BDC [SharePoint development in Visual Studio], updating data
- BDC [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating data
- Business Data Connectivity service [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating entity instances
- BDC [SharePoint development in Visual Studio], updating entity instances
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3004e6b83f98ccf82e6086c4669618ef4fb48c8c
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755749"
---
# <a name="how-to-add-an-updater-method"></a>Nasıl yapılır: bir güncelleyici yöntemi ekleme
  Oluşturarak dış SharePoint listesindeki iş verileri güncelleştirmek kullanıcılar etkinleştirebilir bir *güncelleştirici* yöntemi. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-an-updater-method"></a>Bir güncelleyici yöntemi oluşturmak için  
  
1.  Bir varlık BDC designer'ı seçin.  
  
2.  Menü çubuğunda seçin **Görünüm** > **diğer pencereler** > **BDC yöntem ayrıntıları**.  
  
     BDC yöntem Ayrıntıları penceresi açılır. Bu pencere hakkında daha fazla bilgi için bkz: [BDC modeli Tasarım araçları genel bakış](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  İçinde **bir yöntem ekleyin** listesinde, seçin **oluşturma güncelleyici yöntemi**.  
  
     Visual Studio aşağıdaki öğeleri modele ekler. Bu öğeleri BDC yöntem Ayrıntıları penceresinde görünür.  
  
    -   Adlı bir yöntem **güncelleştirme**.  
  
    -   Yöntem için giriş parametresi.  
  
    -   Parametresi için bir tür tanımlayıcı. Varsayılan olarak, Visual Studio tanımladığınız varlık türü tanımlayıcısı için bir Bulucu yöntemi kullanır (örneğin: kişi).  
  
    -   Yöntemi için yöntem örneği.  
  
     Daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
    > [!NOTE]  
    >  Varlık türü tanıtıcısı otomatik olarak oluşturulan bir veritabanı tablosundaki bir alanı temsil ediyorsa ayarlamak **öncesi güncelleştirici alan** özelliğine **doğru**.  
  
4.  İçinde **Çözüm Gezgini**oluşturulan hizmet kod dosyasının varlığı için kısayol menüsünü açın ve ardından **görünümü kodu**.  
  
     Varlık hizmeti kod dosyasını açar **Kod düzenleyicisinde**. Bu dosya hakkında daha fazla bilgi için bkz: [iş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
5.  Kodu verileri güncelleştirmek için güncelleştirme yöntemine ekleyin. Aşağıdaki örnekte, AdventureWorks örnek veritabanındaki kişiyle ilgili bilgi için SQL Server güncelleştirir.  
  
    > [!NOTE]  
    >  Değerini `ServerName` alanını sunucunuzun adıyla.  
  
     [!code-csharp[SP_BDC#5](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#5)]
     [!code-vb[SP_BDC#5](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#5)]  
  
## <a name="see-also"></a>Ayrıca bkz.
 [İş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Nasıl yapılır: bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-finder-method.md)   
 [Nasıl yapılır: belirli bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Nasıl yapılır: bir yaratıcı yöntemi ekleme](../sharepoint/how-to-add-a-creator-method.md)   
 [Nasıl yapılır: bir güncelleyici yöntemi ekleme](../sharepoint/how-to-add-an-updater-method.md)   
 [Nasıl yapılır: bir Silici yöntemi ekleme](../sharepoint/how-to-add-a-deleter-method.md)   
 [BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md)   
 [Nasıl yapılır: bir yönteme parametre ekleme](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Nasıl yapılır: yöntem örneği tanımlama](../sharepoint/how-to-define-a-method-instance.md)  
  
 
