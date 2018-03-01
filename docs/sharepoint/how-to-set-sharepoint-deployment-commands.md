---
title: "Nasıl yapılır: SharePoint dağıtım komutlarını ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 2f465deaaca406c28aab177434e72de9746fb101
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>Nasıl yapılır: SharePoint Dağıtım Komutlarını Ayarlama
  Dağıtım öncesi ve dağıtım sonrası Komutlar ayarlayarak, dağıtım işlemi özelleştirebilirsiniz. SharePoint çözümlerini Visual Studio'da hata ayıklarken önce ve sonra diğer dağıtım eylemleri şu komutları çalıştırın.  
  
### <a name="to-add-a-pre-deployment-command"></a>Dağıtım öncesi komut eklemek için  
  
1.  Menü çubuğunda seçin **proje**, *ProjectName***özellikleri**.  
  
2.  Seçin **SharePoint** sekmesi.  
  
3.  İçinde **dağıtım öncesi komut satırı** metin kutusuna, bu adımı özelleştirmek için MS-DOS veya MSBuild komut girin.  
  
     Dizin içeriği dağıtım tamamlanmadan önce listelemek için örneğin **dir**.  
  
### <a name="to-add-a-post-deployment-command"></a>Bir dağıtım sonrası komut eklemek için  
  
1.  Menü çubuğunda seçin **proje**, *ProjectName***özellikleri**.  
  
2.  Seçin **SharePoint** sekmesi.  
  
3.  İçinde **dağıtım sonrası komut satırı** metin kutusuna, bu adımı özelleştirmek için MS-DOS veya MSBuild komut girin.  
  
     Dağıtım tamamlandıktan sonra dizin içeriği listelemek için örneğin **dir**. Derlemenin derleme dizinden kopyalamak için bir MSBuild değişken kullanmak için girin **$(TargetPath) c:\DeploymentDirectory kopyalama**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint Çözümlerini Paketleme ve Dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  