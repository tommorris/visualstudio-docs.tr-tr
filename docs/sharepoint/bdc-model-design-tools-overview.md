---
title: "BDC modeli Tasarım araçları genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.BDC.Method_Details
- VS.SharePointTools.BDC.Explorer
- VS.SharePointTools.BDC.Diagram
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], visual tools
- Business Data Connectivity service [SharePoint development in Visual Studio], visual tools
- Business Data Connectivity service [SharePoint development in Visual Studio], BDC Explorer
- BDC [SharePoint development in Visual Studio], method details
- Business Data Connectivity service [SharePoint development in Visual Studio], designer
- Business Data Connectivity service [SharePoint development in Visual Studio], method details
- BDC [SharePoint development in Visual Studio], BDC Explorer
- BDC [SharePoint development in Visual Studio], designer
ms.assetid: dbd7b746-9e93-4ed4-a546-4a6f17a4725f
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4572671971c6cf812c31286fba09bddb65080681
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="bdc-model-design-tools-overview"></a>BDC Modeli Tasarım Araçlarına Genel Bakış
  BDC Tasarımcısı kullanarak iş verileri bağlantı (BDC) modeli tasarlayabilirsiniz **BDC yöntem ayrıntıları** penceresinde ve **BDC Gezgini**.  
  
 **BDC Gezgini** model göz atın, model aramak ve tür tanımlayıcısı tanımlamak sağlar.  
  
## <a name="bdc-designer"></a>BDC Tasarımcısı  
 BDC Tasarımcısı modelinizde varlıklarını tanımlama ve görsel olarak birbirleriyle ilişkilerini düzenlemeyi sağlar. BDC Tasarımcısı aşağıdaki görevleri gerçekleştirmek için kullanın:  
  
-   Varlıkları modele ekleyin.  
  
-   Varlıkları modelden kaldırın.  
  
-   Varlıkları arasındaki ilişkileri tanımlayın.  
  
 BDC Tasarımcısı'nı açmak için projenizdeki model dosyasını çift tıklatın veya model dosyası için kısayol menüsünü açın ve ardından **açmak**. Sürükleyerek ya da kopyalayarak modele bir varlık eklemek bir **varlık** gelen **araç** tasarımcıya. İki varlık arasında bir ilişki oluşturmak için seçtiğiniz **ilişkilendirme** denetim **araç**ilk varlık seçin ve ardından ikinci varlığı seçin.  
  
## <a name="bdc-method-details-window"></a>BDC yöntemi Ayrıntıları penceresi  
 Kullanım **BDC yöntem ayrıntıları** örnekleri parametrelerini tanımlamak ve bir yöntemin tanımlayıcıları filtrelemek için penceresi.  
  
 Finder, belirli bir Bulucu, Creator, güncelleştirici ve Silici yöntemlerinde hemen oluşturabilirsiniz **BDC yöntem ayrıntıları** penceresi. Bu yöntemleri oluşturduğunuzda, Visual Studio yönteme parametre, örnekleri ve tür tanımlayıcısı gibi meta veri ekler. Size özel senaryonun karşılamak için bu meta verileri değiştirebilirsiniz.  
  
 Açmak için **BDC yöntem ayrıntıları** menü çubuğunda, pencere **Görünüm**, **diğer pencereler**, **BDC yöntem ayrıntıları**.  
  
 Yöntemleri görüntülemek için **BDC yöntem ayrıntıları** penceresinde BDC Tasarımcısı'nda varlığı seçin. Seçilen varlığın yöntemlerinin görünür **BDC yöntem ayrıntıları** penceresi. BDC Tasarımcısı'nda bir varlık seçmezseniz **BDC yöntem ayrıntıları** penceresi hiçbir bilgi görüntüler.  
  
 Genişlet veya daralt düğümler **BDC yöntem ayrıntıları** parametreleri, örneklerini tanımlayın ve tanımlayıcıları filtrelemek için penceresi. Kullanım **BDC Gezgini** tür tanımlayıcısı tanımlamak için.  
  
## <a name="bdc-explorer"></a>BDC Gezgini  
 **BDC Gezgini** modelini olun öğelerini görüntüler. Açmak için **BDC Gezgini**, menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **BDC Gezgini**. Model göz atmak için düğümleri genişletin **BDC Gezgini**. Her düğüm model dosyası XML bir öğeyi temsil eder.  
  
 Düğümler seçerken **BDC Gezgini**, seçtiğiniz her bir düğüm özelliklerini görünür **özellikleri** penceresi. Bu özelliklerin çoğu öznitelikler model dosyasında karşılık gelir. En üstte arama kutusunu kullanarak model arayabilirsiniz **BDC Gezgini**.  
  
> [!NOTE]  
>  **BDC Gezgini** tanımlayıcıları, özel özellikler, yerelleştirilmiş dizeleri, ilişki gruplar, Eylemler, filtre tanımlayıcıları, eylem denetim listeleri ve varsayılan parametre değerlerini görüntülemez.  
  
### <a name="defining-type-descriptors"></a>Tür tanımlayıcısı tanımlama  
 Kullanım **BDC Gezgini** tür tanımlayıcısı tanımlamak için. BDC Gezgini, bir kez bir tür tanımlayıcı tanımlayabilir ve bu tür tanımlayıcı modelinizdeki başka bir yerde daha sonra yeniden olanak sağlar. Bunu gerçekleştirmek için bir tür tanımlayıcı kopyalayın ve herhangi bir parametre yapıştırın veya tür tanımlayıcısı.  
  
> [!NOTE]  
>  Özgün bir tür tanımlayıcı yapılan değişiklikler, bu tür tanımlayıcı kopyalarını etkilemez.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: bir parametrenin tür tanımlayıcısını tanımlama](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir BDC modeli oluşturma](../sharepoint/how-to-create-a-bdc-model.md)   
 [Nasıl yapılır: bir modele bir varlık ekleme](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [Nasıl yapılır: bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-finder-method.md)   
 [Nasıl yapılır: belirli bir Bulucu yöntemi ekleme](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [Nasıl yapılır: bir yaratıcı yöntemi ekleme](../sharepoint/how-to-add-a-creator-method.md)   
 [Nasıl yapılır: bir Silici yöntemi ekleme](../sharepoint/how-to-add-a-deleter-method.md)   
 [Nasıl yapılır: bir güncelleyici yöntemi ekleme](../sharepoint/how-to-add-an-updater-method.md)   
 [Varlıklar arasında ilişkilendirme oluşturma](../sharepoint/creating-an-association-between-entities.md)   
 [İzlenecek yol:, iş verileri kullanarak SharePoint'te dış liste oluşturma](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)   
 [İş verilerini SharePoint ile tümleştirme](../sharepoint/integrating-business-data-into-sharepoint.md)   
 [İş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [İş Verileri Bağlantı Modeli Tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  