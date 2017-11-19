---
title: "Nasıl yapılır: VSIX paketi için bağımlılık ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d3f3b54e19d8418f35a733b73ea0616b53bd42ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>Nasıl yapılır: VSIX paketi için bağımlılık ekleme
Hedef bilgisayarda mevcut olmayan bağımlılıkları yükler VSIX paketi dağıtımı ayarlayabilirsiniz. Bunu gerçekleştirmek için source.extension.vsixmanifest dosyaya VSIX bağımlılıkları ekleyin.  
  
#### <a name="to-add-a-dependency"></a>Bir bağımlılık eklemek için  
  
1.  Source.extension.vsixmanifest dosyasında açma **tasarım** görünümü. Git **bağımlılıkları** sekmesinde **yeni**.  
  
2.  Yüklü bir uzantı eklemek için: içinde **yeni bağımlılık Ekle** iletişim kutusunda **yüklü uzantısı** ve daha sonra **adı**, listesindeki bir uzantı seçin.  
  
3.  Yüklü olmayan başka bir VSIX eklemek için:: içinde **yeni bağımlılık Ekle** iletişim kutusunda **dosyasının dosya sistemindeki** ve sonra da **Gözat** düğmesine tıklayarak VSIX seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [VSIX paketi anatomisi](../extensibility/anatomy-of-a-vsix-package.md)   
 [Uzantıları Windows Installer dağıtımı için hazırlama](../extensibility/preparing-extensions-for-windows-installer-deployment.md)