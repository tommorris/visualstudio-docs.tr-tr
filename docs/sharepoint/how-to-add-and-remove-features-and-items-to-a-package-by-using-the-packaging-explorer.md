---
title: "Nasıl yapılır: ekleme ve kaldırma özellikler ve öğeler bir pakete paketleme Gezgini'ni kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.RAD.PackagingExplorer
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, packages
ms.assetid: 549d5848-f0c9-42c6-b7f5-bc1e626a30e6
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bafa2a4310a77f9f5a9f061e378ac05f2896d4ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer"></a>Nasıl yapılır: Paketleme Gezgini'ni Kullanarak Bir Pakete Özellikler ve Öğeler Ekleme ve Kaldırma
  SharePoint öğeleri ve özellikleri dağıtacağınız bir paket yapılandırmak için paketleme Gezgini'ni kullanabilirsiniz. .Wsp dosyanızı içinde SharePoint Proje öğeleri ve özellikleri ayarlayabilirsiniz.  
  
 Alternatif olarak, görüntülemek ve etkinleştirme sırasını değiştirmek için özellikleri yeniden sıralamak için paketleme Tasarımcısı'nı kullanabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: ekleyip özellikler ve öğeler bir paket için paket Tasarımcısını kullanarak](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md).  
  
## <a name="opening-the-packaging-explorer"></a>Paketleme Gezgini'ni açma  
 Visual Studio çözümünüzü en az bir SharePoint Proje varsa paketleme Gezgini'ni açmak için aşağıdaki yordamı kullanabilirsiniz. Alternatif olarak, paketleme Gezgini'ni otomatik olarak bir özellik veya paket tasarımcısını görüntülediğinizde açılır. Tüm özellik ve paket tasarımcıları kapattıktan sonra da paketleme Gezgini'ni kapatır.  
  
#### <a name="to-open-the-packaging-explorer"></a>Paketleme Gezgini'ni açmak için  
  
1.  Menü çubuğunda seçin **Görünüm**, **diğer pencereler**, **paketleme Gezgini'ni**.  
  
     **Paketleme Gezgini'ni** görünür **araç**.  
  
## <a name="adding-a-feature-to-a-package"></a>Bir paket için bir özellik ekleme  
 Paketleme Gezgini'ni kullanarak bir pakete yeni ve mevcut özellikleri ekleyebilirsiniz.  
  
#### <a name="to-add-a-sharepoint-feature"></a>Bir SharePoint özelliğini eklemek için  
  
1.  Açık **paketleme Gezgini'ni**projesi için kısayol menüsünü açın ve ardından **ekleme özelliği**.  
  
#### <a name="to-move-an-existing-sharepoint-feature"></a>Var olan bir SharePoint özelliğini taşımak için  
  
1.  Açık **paketleme Gezgini'ni**ve ardından aşağıdaki adımlardan birini gerçekleştirin:  
  
    -   Sürükleme bir **özelliği** başka bir projeye bir projeye ait.  
  
    -   Bir özellik için kısayol menüsünü açın, seçin **Kes**, özellik taşıyabilir ve ardından istediğiniz proje için kısayol menüsünü açın **Yapıştır**.  
  
    > [!NOTE]  
    >  Birden çok SharePoint Proje, çözümünüz varsa, bu yordamı kullanın.  
  
## <a name="validating-a-feature-or-package"></a>Bir özellik veya paketi doğrulama  
 SharePoint özellikleri ve paketleri olası sorunları dosyaları doğrulayarak tanımlayabilirsiniz. Uyarıları ve hataları çıktı penceresi ve Hata Listesi penceresi görüntülenir.  
  
#### <a name="to-validate-a-sharepoint-feature-or-package"></a>Bir SharePoint özelliğini veya paket doğrulamak için  
  
1.  Açık **paketleme Gezgini'ni**.  
  
2.  Bir özellik veya paket için bir kısayol menüsünü açın ve ardından **doğrulama**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Paketleme ve SharePoint çözümlerini dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  