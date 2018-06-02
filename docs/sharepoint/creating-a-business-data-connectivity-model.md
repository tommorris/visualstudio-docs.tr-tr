---
title: İş verileri bağlantı modeli oluşturma | Microsoft Docs
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
- Business Data Connectivity service [SharePoint development in Visual Studio], model
- BDC [SharePoint development in Visual Studio], creating a model
- Business Data Connectivity service [SharePoint development in Visual Studio], creating a model
- SharePoint development in Visual Studio, Business Data Connectivity service
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6c6fc0b1169ff906d7cda36eeeb5a74410cf46a9
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691502"
---
# <a name="creating-a-business-data-connectivity-model"></a>İş verileri bağlantı modeli oluşturma
  İş verileri bağlantı (BDC) modeli oluşturma veya Visual Studio kullanarak mevcut bir BDC modeli özelleştirebilirsiniz. Her SharePoint Proje yalnızca bir model içerebilir. Daha fazla bilgi için bkz: [iş verilerini SharePoint tümleştirme](../sharepoint/integrating-business-data-into-sharepoint.md).  
  
## <a name="create-a-new-model"></a>Yeni bir model oluşturma
 Yeni bir model oluşturmak için Oluştur bir **iş verileri bağlantı modeli** proje veya ekleme bir **iş verileri bağlantı modeli** öğesinin bir **boş SharePoint proje**.  
  
> [!NOTE]  
>  Bilmeniz gereken [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] bilgisayarınızda yüklü.  
  
 Visual Studio Proje için bir klasör ekler. Bu klasör için belirttiğiniz ada sahip **iş verileri bağlantı modeli** öğesi **Yeni Öğe Ekle** iletişim kutusu. Yeni bir oluşturursanız **iş verileri bağlantı modeli** proje, Visual Studio klasör adları **BdcModel1**.  
  
 Visual Studio aşağıdaki dosyalarını yeni klasöre ekler:  
  
|Dosya|Açıklama|  
|----------|-----------------|  
|Model tanım dosyası|Varlıklar, yöntemleri, iş kolu (LOB) sistem nesneleri ve modeli açıklayan diğer meta verileri tanımlayan XML içeriyor.<br /><br /> BDC Tasarımcısı'nı kullanarak bu dosyadaki meta verilerini değiştirmek **BDC Gezgini**, **BDC yöntem ayrıntıları** penceresinde ve **özellikleri** penceresi.|  
|Varlık hizmeti kod dosyasını|Alma, güncelleştirme ve varsayılan varlık örneklerini silme yöntemlerini içerir.|  
  
 Bir varlık özelliklerini tanımlamak için varlık kod dosyasını düzenleyin. Daha fazla bilgi için bkz: [nasıl yapılır: bir modele bir varlık ekleme](../sharepoint/how-to-add-an-entity-to-a-model.md).  
  
 Varlık örneklerini silme almak ve güncelleştirmek için varlık hizmeti kod dosyasını kodu ekleyin. Daha fazla bilgi için bkz: [iş verileri bağlantı modeli tasarlama](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
 Projeyi derlerken Visual Studio derleme oluşturur. Proje derleme kodu ekleyin proje için diğer öğeleri eklemeyin emin olun (örneğin: bir **sıralı iş akışı** öğesi veya **Web Bölümü** öğesi). Çözüm paketi derleme genel derleme önbelleğine kopyalamaz çünkü çözümü dağıttığınızda bu öğe için kod çalışmaz.  Çözüm paketi BDC veritabanına SharePoint yalnızca derleme dağıtır.  
  
> [!NOTE]  
>  Projenin hata ayıklamasını yaparken visual Studio derleme konumlarının her ikisinde de, yerel bilgisayarınızda kopyalar.  
  
## <a name="add-an-existing-model"></a>Varolan modeli ekleme
 SharePoint Designer gibi diğer araçlar kullanılarak oluşturulmuş bir model içeri aktarabilirsiniz. Projeniz aşağıdaki durumlarda var olan bir model almayı da tercih edebilirsiniz:  
  
-   Bir SharePoint sunucu grubuna zaten dağıtılmış bir model özelleştirmek için.  
  
-   Paketi ve var olan bir model için birden çok SharePoint server grupları dağıtmak için.  
  
 Her iki durumda da aldığınız modelde tanımlanmış LOB sistemlerini etkilenmez ve beklendiği şekilde çalışmaya devam eder. Bir SharePoint projesine mevcut bir model eklemek için Visual Studio'yu kullanma **varolan öğeyi Ekle** iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint projesine mevcut bir BDC modeli dosyası ekleme](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md).  
  
 Bir seçenek olarak seçerek alınan modele bir LOB Sistem türü .NET Framework derlemesinin ekleyebilirsiniz **eklemek .NET derlemesi LobSystem**. Bu, özel kod yazmanıza ve içe aktarılan model için meta verileri tanımlamak için bir tasarımcı kullanmanıza olanak sağlar.  
  
## <a name="related-topics"></a>İlgili konular
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Nasıl yapılır: BDC Modeli Oluşturma](../sharepoint/how-to-create-a-bdc-model.md)|Yeni bir BDC modeli oluşturma gösterir.|  
|[Nasıl yapılır: Bir SharePoint Projesine Mevcut bir BDC Modeli Dosyası Ekleme](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)|Bir SharePoint projesine mevcut bir model içeri aktarma gösterir.|  
|[Nasıl yapılır: Yerelleştirilmiş Adlar. Özellikler ve İzinleri Belirtmek için Kaynak Dosyası Kullanma](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)|Model bir Web Bölümü veya Web sayfası tarafından tüketilen model meta verileri ile birleştirilen dizeleri sunmak açıklar.|  
|[Nasıl yapılır: Bir BDC Özelliğine Özel bir Derlemeyi Dahil Etme](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)|Özelliğine özel bir derlemeyi dahil etme kullanmayı gösterir.|  
  
 