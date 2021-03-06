---
title: Varolan projeyi Ekle komutu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- file.addexistingproject
helpviewer_keywords:
- Add Existing Project command
- File.AddExistingProject
ms.assetid: 71cf3e31-c76b-405b-ad6a-1b1bc654bd40
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 048ba8e43b66ac5ad4bbc1d0c09adb75a2d61e1d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630279"
---
# <a name="add-existing-project-command"></a>Varolan Projeyi Ekle Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [mevcut proje komut Ekle](https://docs.microsoft.com/visualstudio/ide/reference/add-existing-project-command).  
  
  
Mevcut bir projeyi çözüme ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.AddExistingProject filename  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 İsteğe bağlı. Tam yol ve proje adı, çözüme eklemek için projenin bir uzantıya sahip.  
  
 Varsa `filename` bağımsız değişken boşluk içeriyorsa, tırnak işaretleri içine alınmalıdır.  
  
 Dosya adı belirtilirse, bu kullanıcı, bir proje seçebilir böylece komut dosya iletişim kutusu açılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Otomatik Tamamlama, doğru yol ve dosya adı, türü bulmaya çalışır.  
  
## <a name="example"></a>Örnek  
 Bu örnek ekler [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] proje, TestProject1, geçerli çözüme.  
  
```  
>File.AddExistingProject "c:\visual studio projects\TestProject1.vbproj"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



