---
title: 'Nasıl yapılır: VSIX paketine bağımlılık ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ebd835fef9df8fbdeb67bdf9c7e6eff31bcf4730
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689875"
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Nasıl yapılır: VSIX paketine bağımlılık ekleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: VSIX paketine bağımlılık ekleme](https://docs.microsoft.com/visualstudio/extensibility/how-to-add-a-dependency-to-a-vsix-package).  
  
Zaten hedef bilgisayarda mevcut olmayan herhangi bir bağımlılığın yükleyen bir VSIX paketi dağıtımı ayarlayabilirsiniz. Bunu yapmak için VSIX bağımlılıklarını nde source.extension.vsixmanifest dosyası içerir.  
  
#### <a name="to-add-a-dependency"></a>Bir bağımlılık eklemek için  
  
1.  Source.extension.vsixmanifest dosyasını açın **tasarım** görünümü. Git **bağımlılıkları** sekmesine **yeni**.  
  
2.  Yüklü uzantı eklemek için: içinde **yeni bağımlılık Ekle** iletişim kutusunda **uzantısı yüklü** ve ardından **adı**, listedeki bir uzantı seçin.  
  
3.  Yüklü başka bir VSIX eklemek için:: içinde **yeni bağımlılık Ekle** iletişim kutusunda **dosya sisteminde dosya** ve ardından **Gözat** düğmesine VSIX'i seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSIX Uzantı Şeması 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [Bir VSIX paketinin anatomisi](../extensibility/anatomy-of-a-vsix-package.md)   
 [Uzantıları Windows Installer Dağıtımı için Hazırlama](../extensibility/preparing-extensions-for-windows-installer-deployment.md)

