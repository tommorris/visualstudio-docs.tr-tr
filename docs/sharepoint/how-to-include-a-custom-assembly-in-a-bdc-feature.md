---
title: "Nasıl yapılır: bir BDC özelliğine özel bir derlemeyi dahil etme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.BDC.Add_Assemblies_Dialog
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], add reference
- Business Data Connectivity service [SharePoint development in Visual Studio], custom assembly
- BDC [SharePoint development in Visual Studio], custom assembly
- BDC [SharePoint development in Visual Studio], add reference
ms.assetid: 2ddf44b9-5f51-4bca-b8bb-94c4bbd1c5f3
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: acf4038a5b3cafa1febcd4a44c3e82222d6f5d86
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-include-a-custom-assembly-in-a-bdc-feature"></a>Nasıl yapılır: Bir BDC Özelliğine Özel bir Derlemeyi Dahil Etme
  Projenizi derlemeleri aynı çözümde diğer projelerden başvuruda bulunabilir. Ancak, bu derlemeler projenin özellik dosyası kullanarak eklemeniz gerekir **Ata başvurulan derlemeler LobSystems için** iletişim kutusu.  
  
### <a name="to-include-a-custom-assembly-in-a-business-data-connectivity-bdc-feature"></a>Bir iş verileri bağlantı (BDC) özelliğine özel bir derlemeyi dahil etmek için  
  
1.  İçinde **Çözüm Gezgini**, BDC modeli içeren klasörü seçin.  
  
2.  Üzerinde **Görünüm** menüsünde tıklatın **Özellikler penceresini**.  
  
3.  İçinde **özellikleri** penceresinde, seçin **derlemeleri** özelliği ve üç nokta düğmesini (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips")).  
  
     **Ata başvurulan derlemeler LobSystems için** iletişim kutusu görüntülenir.  
  
4.  İçinde **bütünleştirilmiş seçin** listesinde, özel bir derlemeyi seçin.  
  
    > [!NOTE]  
    >  Derlemeleri yalnızca görünür **Ata başvurulan derlemeler LobSystems için** derleme içeren projesine bir başvuru eklediyseniz iletişim kutusu. Daha fazla bilgi için bkz: [nasıl yapılır: başvuru ekleme veya kaldırma Başvurusu Ekle iletişim kutusunu kullanarak](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9).  
  
5.  İçinde **başvuru özellikleri** grubunda, görünür listesini açın **LobSystem kapsam** özelliği, özel bir derlemeyi kullanın ve ardından yöntemleri LOB sistemine seçin **Tamam**  düğmesi.  
  
    > [!NOTE]  
    >  Özel derleme kodunda hata ayıklama için çözüm paketi derleme eklemeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: ekleme ve kaldırma ek derlemeler](../sharepoint/how-to-add-and-remove-additional-assemblies.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yerelleştirilmiş adlar, özellikler ve izinleri belirtmek için kaynak dosyası kullanın](../sharepoint/how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions.md)   
 [Nasıl yapılır: bir SharePoint projesine mevcut bir BDC modeli dosyası ekleme](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [İş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Nasıl yapılır: bir BDC modeli oluşturma](../sharepoint/how-to-create-a-bdc-model.md)   
 [İş Verilerini SharePoint ile Tümleştirme](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  