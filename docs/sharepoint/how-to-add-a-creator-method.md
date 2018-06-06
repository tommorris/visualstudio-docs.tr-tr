---
title: 'Nasıl yapılır: bir yaratıcı yöntemi ekleme | Microsoft Docs'
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
- BDC [SharePoint development in Visual Studio], Creator
- BDC [SharePoint development in Visual Studio], adding entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entity instances
- BDC [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Creator
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: dd566eacba7f94cfe7617e9396440c90dc32f51e
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767148"
---
# <a name="how-to-add-a-creator-method"></a>Nasıl yapılır: bir yaratıcı yöntemi ekleme
  Bir yaratıcı yöntemi bir varlık veri kaynağı için yeni veri ekler. Kullanıcıların seçtiğinizde iş verileri bağlantı (BDC) hizmeti bu yöntemi çağırır **yeni öğe** düğmesini **Şerit** modelini temel alan bir listesi. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-add-a-creator-method"></a>Bir yaratıcı yöntemi ekleme  
  
1.  Üzerinde **BDC Tasarımcısı**, bir varlık seçin.  
  
2.  Menü çubuğunda seçin **Görünüm** > **diğer pencereler** >**BDC yöntem ayrıntıları**.  
  
     **BDC yöntem ayrıntıları** penceresi açılır. Bu pencere hakkında daha fazla bilgi için bkz: [BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  İçinde **bir yöntem ekleyin** listesinde, seçin **oluşturan yöntem oluşturma**.  
  
     Visual Studio modele aşağıdaki öğeleri ekler ve bu öğeleri görüntülenmesini **BDC yöntem ayrıntıları** penceresi.  
  
    -   Adlı bir yöntem **oluşturma**.  
  
    -   Yöntem için giriş parametresi.  
  
    -   Yönteminin dönüş parametresi.  
  
    -   Parametreler için tanımlayıcıları yazın.  
  
    -   Yöntemi için yöntem örneği.  
  
     Daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
4.  İçinde **Çözüm Gezgini**oluşturulan hizmet kod dosyasının varlığı için kısayol menüsünü açın ve ardından **görünümü kodu**.  
  
     Varlık hizmeti kod dosyasını Kod Düzenleyicisi'nde açar. Varlık hizmeti kod dosyasını hakkında daha fazla bilgi için bkz: [iş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
5.  Veri kaynağına veri ekler yaratıcı yöntemi için kodu ekleyin. Aşağıdaki örnekte bir kişi için SQL Server AdventureWorks örnek veritabanına ekler.  
  
    > [!NOTE]  
    >  Değerini `ServerName` alanını sunucunuzun adıyla.  
  
     [!code-csharp[SP_BDC#4](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#4)]
     [!code-vb[SP_BDC#4](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#4)]  
  
## <a name="see-also"></a>Ayrıca bkz.
 [İş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Nasıl yapılır: bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-finder-method.md)   
 [Nasıl yapılır: belirli bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Nasıl yapılır: bir Silici yöntemi ekleme](../sharepoint/how-to-add-a-deleter-method.md)   
 [Nasıl yapılır: bir güncelleyici yöntemi ekleme](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md)   
 [Nasıl yapılır: bir yönteme parametre ekleme](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Nasıl yapılır: Metot Örneği Tanımlama](../sharepoint/how-to-define-a-method-instance.md)  
  
  