---
title: "Nasıl yapılır: SharePoint dağıtım komutlarını ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, deploying
ms.assetid: 289c8c33-a603-434e-889f-a0d0a1736ecb
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 65c67972dddedcd05338d793883b2dcba0789d48
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Paketleme ve SharePoint çözümlerini dağıtma](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  