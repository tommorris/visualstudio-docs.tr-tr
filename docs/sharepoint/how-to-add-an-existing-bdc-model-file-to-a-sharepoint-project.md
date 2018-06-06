---
title: 'Nasıl yapılır: bir SharePoint projesine mevcut bir BDC modeli dosyası ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.BDC.ImportDialog
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], import a model
- Business Data Connectivity service [SharePoint development in Visual Studio], reuse a model
- BDC [SharePoint development in Visual Studio], import a model
- BDC [SharePoint development in Visual Studio], remove a model
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4ca7f4befcb75a48e5b03637c143edfdd81b428a
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767747"
---
# <a name="how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project"></a>Nasıl yapılır: bir SharePoint projesine mevcut bir BDC modeli dosyası ekleme
  Özelleştirme paketini ve iş verileri bağlantı (BDC) modeli model dosyası eklemek için Visual Studio kullanarak yeniden dağıtma (*.bdcm*) herhangi bir SharePoint grubu projesi için. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
### <a name="to-add-a-bdc-model-file-to-a-sharepoint-project"></a>Bir SharePoint projesine bir BDC modeli dosyası eklemek için  
  
1.  İçinde **Çözüm Gezgini**, bir SharePoint proje klasörünü seçin.  
  
2.  Menü çubuğunda seçin **proje** > **varolan öğeyi Ekle**.  
  
3.  İçinde **varolan öğeyi Ekle** iletişim kutusu, projenize ekleyin, dosyayı seçin ve ardından istediğiniz model tanım dosyasının konumuna göz atın **Ekle** düğmesi.  
  
     Model tanımlamıyorsa bir *türü .NET derlemesi iş kolu (LOB) sistemine*, **eklemek .NET derlemesi LobSystem** iletişim kutusu açılır.  
  
4.  İletişim kutusu görüntülenirse, aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Özel kod yazmanıza ve bir tasarımcı kullanacak içe aktarılan model için meta verileri tanımlamak için seçmek istiyorsanız **Evet** düğmesi, sistem adı ve ardından **Tamam** düğmesi.  
  
    -   Aksi takdirde seçin **Hayır** düğmesine tıklayın ve ardından **Tamam** düğmesi.  
  
     **İş verileri bağlantı modeli** öğe projeye eklenmiş.  
  
## <a name="see-also"></a>Ayrıca bkz.
 [İş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Nasıl yapılır: bir BDC modeli oluşturma](../sharepoint/how-to-create-a-bdc-model.md)   
 [Nasıl yapılır: yerelleştirilmiş adlar, özellikler ve izinleri belirtmek için kaynak dosyası kullanın](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [Nasıl yapılır: bir BDC özelliğine özel bir derlemeyi dahil etme](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [İş Verilerini SharePoint ile Tümleştirme](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
 