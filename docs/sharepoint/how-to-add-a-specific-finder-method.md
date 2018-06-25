---
title: 'Nasıl yapılır: belirli bir Bulucu yöntemi ekleme | Microsoft Docs'
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
- Business Data Connectivity service [SharePoint development in Visual Studio], Specific Finder
- BDC [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], get an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], Specific Finder
- Business Data Connectivity service [SharePoint development in Visual Studio], get an entity
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7319842d0c90b18b170fcd5e199dc255f45a3374
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758442"
---
# <a name="how-to-add-a-specific-finder-method"></a>Nasıl yapılır: belirli bir Bulucu yöntemi ekleme
  Tek varlık örneğini oluşturarak döndürebilir bir *belirli bir Bulucu* yöntemi. Bir kullanıcı, bir iş veri web bölümü veya dış listedeki bir varlık seçtiğinde iş verileri bağlantı (BDC) hizmeti belirli bir Bulucu yöntemi yürütür. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-a-specific-finder-method"></a>Belirli bir Bulucu yöntemi oluşturmak için
  
1.  Üzerinde **BDC Tasarımcısı**, bir varlık seçin.  
  
     Bir varlık ekleme hakkında bilgi için **BDC Tasarımcısı** Visual Studio'da görmek [nasıl yapılır: bir modele bir varlık ekleme](../sharepoint/how-to-add-an-entity-to-a-model.md).  
  
2.  Menü çubuğunda seçin **Görünüm** > **diğer pencereler**, **BDC yöntem ayrıntıları**.  
  
     **BDC yöntem ayrıntıları** penceresi açılır. Bu pencere hakkında daha fazla bilgi için bkz: [BDC modeli Tasarım araçları genel bakış](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  İçinde **bir yöntem ekleyin** listesinde, seçin **oluşturma belirli bir Bulucu yöntemi**.  
  
     Visual Studio aşağıdaki öğeleri modele ekler. Bu öğeleri görünür **BDC yöntem ayrıntıları** penceresi.  
  
    -   Bir yöntem.  
  
    -   Yöntem için giriş parametresi.  
  
    -   Yönteminin dönüş parametresi.  
  
    -   Her parametre için bir tür tanımlayıcı.  
  
    -   Yöntemi için yöntem örneği.  
  
     Daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
4.  Visual Studio'yu açın **özellikleri** penceresi.  
  
5.  Dönüş parametresi türü tanımlayıcısının bir varlık türü tanımlayıcısı yapılandırın. Bir varlık türü tanımlayıcısı oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir parametrenin tür tanımlayıcısını tanımlama](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
    > [!NOTE]  
    >  Varlığa bir Bulucu yöntemi eklediyseniz, bu adımı gerçekleştirmeniz gerekmez. Visual Studio Bulucu yönteminde tanımlı tür tanımlayıcı kullanır.  
  
    > [!NOTE]  
    >  Tanımlayıcı alanı varlık türünün otomatik olarak oluşturulan bir veritabanı tablosundaki bir alanı temsil ediyorsa ayarlamak **salt okunur** özelliği tanımlayıcı alanı **doğru**.  
  
6.  İçinde **yöntemi ayrıntılarını** penceresinde yöntemi yöntemi örneğini seçin.  
  
7.  İçinde **Özellikler penceresini**ayarlayın **dönüş parametre adı** özelliğini yönteminin dönüş parametresinin adı. Yöntem örneği özellikleri hakkında daha fazla bilgi için bkz: [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282).  
  
8.  İçinde **Çözüm Gezgini**oluşturulan hizmet kod dosyasının varlığı için kısayol menüsünü açın ve ardından **görünümü kodu**.  
  
     Varlık hizmeti kod dosyasını Kod Düzenleyicisi'nde açar. Varlık hizmeti kod dosyasını hakkında daha fazla bilgi için bkz: [iş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
9. Kod belirli bir Bulucu yöntemine ekleyin. Bu kod aşağıdaki görevleri gerçekleştirir:  
  
    -   Bir kayıt bir veri kaynağından alır.  
  
    -   Bir varlık BDC hizmetine döndürür.  
  
     Aşağıdaki örnekte, AdventureWorks örnek veritabanından SQL Server için kişi döndürür.  
  
    > [!NOTE]  
    >  Değerini `ServerName` alanını sunucunuzun adıyla.  
  
     [!code-csharp[SP_BDC#3](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#3)]  
  
## <a name="see-also"></a>Ayrıca bkz.
 [İş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Nasıl yapılır: bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-finder-method.md)   
 [Nasıl yapılır: bir yaratıcı yöntemi ekleme](../sharepoint/how-to-add-a-creator-method.md)   
 [Nasıl yapılır: bir Silici yöntemi ekleme](../sharepoint/how-to-add-a-deleter-method.md)   
 [Nasıl yapılır: bir güncelleyici yöntemi ekleme](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC modeli tasarım araçlarına genel bakış](../sharepoint/bdc-model-design-tools-overview.md)   
 [Nasıl yapılır: bir yönteme parametre ekleme](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Nasıl yapılır: yöntem örneği tanımlama](../sharepoint/how-to-define-a-method-instance.md)  
  
