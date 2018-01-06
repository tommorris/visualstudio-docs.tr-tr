---
title: "Nasıl yapılır: ekleme ve kaldırma özellikler ve öğeler bir paket için paket Tasarımcısını kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.RAD.PackageDesignerDesign
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, packages
ms.assetid: 7dfa2c5d-3ac7-4573-abac-12a5e16efd1d
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 37dfee49fe18fda276c1cde27bd79bcae1a13f48
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer"></a>Nasıl yapılır: Paket Tasarımcısını Kullanarak Bir Pakete Özellikler ve Öğeler Ekleme ve Kaldırma
  Bir SharePoint çözüm oluşturduğunuzda, Visual Studio çözümü paketinde varsayılan SharePoint özelliklerini ekler. Son dağıtım öncesinde ekleyin ve SharePoint Proje öğeleri ve SharePoint paketi değiştirmek için özellikler kaldırın.  
  
 Alternatif olarak, SharePoint Proje öğeleri eklemek ve kaldırmak için paketleme Gezgini'ni kullanın. Ayrıca, görüntüleyin ve SharePoint Proje öğeleri ve (.wsp) paketine konulduğundan özellikleri hiyerarşisini değiştirin. Daha fazla bilgi için bkz: [nasıl yapılır: ekleyip özellikler ve öğeler bir pakete paketleme Gezgini'ni kullanarak](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer.md).  
  
## <a name="adding-features-to-a-sharepoint-package"></a>Bir SharePoint pakete özellik ekleme  
 Bir SharePoint pakete özellikleri eklemek için paket tasarımcısını kullanabilirsiniz.  
  
#### <a name="to-add-sharepoint-features-with-the-package-designer"></a>Paket tasarımcısını SharePoint özelliklerle eklemek için  
  
1.  Açık **paketini Tasarımcısı**.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: bir SharePoint çözüm paketini özelleştirme](../sharepoint/how-to-customize-a-sharepoint-solution-package.md).  
  
2.  Bir veya daha fazla aşağıdaki adımları gerçekleştirerek bir veya daha fazla SharePoint özellikleri ekleyin:  
  
    1.  Her öğeyi çift tıklatın **çözümü öğelerde** eklemek istediğiniz listesi.  
  
    2.  Ekleyin ve ardından istediğiniz öğeyi seçin **Ekle** düğmesini (>).  
  
    3.  Seçin **Tümünü Ekle** düğmesi (>>) aynı anda tüm öğeler eklemek için.  
  
     Örneğin, bir öğeyi çift tıklayarak **çözümü öğelerde** eklemek için liste **paket öğeleri** listesi.  
  
     SharePoint Proje öğeleri ve özellikleri görünür **paket öğeleri** listesi.  
  
## <a name="removing-features-from-a-sharepoint-package"></a>Bir SharePoint paketinden özellikleri kaldırma  
 Bir SharePoint paket özellikleri kaldırmak için paket tasarımcısını kullanabilirsiniz.  
  
#### <a name="to-remove-sharepoint-features-with-the-package-designer"></a>Paket tasarımcısını SharePoint özelliklerle kaldırmak için  
  
1.  İçinde **paket öğeleri** listesinde, kaldırmak ve ardından istediğiniz öğeyi seçin **kaldırmak** (<) düğmesini veya seçin **Tümünü Kaldır** düğmesi (<<) kaldırmak için tüm öğeler.  
  
     SharePoint öğeleri görünür **çözümü öğelerde** listesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint çözüm paketleri oluşturma](../sharepoint/creating-sharepoint-solution-packages.md)   
 [Nasıl yapılır: Bir SharePoint Çözüm Paketini Özelleştirme](../sharepoint/how-to-customize-a-sharepoint-solution-package.md)  
 [Nasıl yapılır: bir paket oluşturun](http://msdn.microsoft.com/en-us/b24be45c-e91d-49bb-afb0-7b265404214b)  
  
  