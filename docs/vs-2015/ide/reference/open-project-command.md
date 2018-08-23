---
title: Açık proje komutu | Microsoft Docs
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
- file.openproject
helpviewer_keywords:
- op command
- File.OpenProject command
- Open Project command
ms.assetid: baa85f86-041b-49f4-9ced-0c397dc180e1
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9c8f70d5605f4ee47171992e3a94c145cbdc8785
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633477"
---
# <a name="open-project-command"></a>Proje Aç Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [açık proje komutu](https://docs.microsoft.com/visualstudio/ide/reference/open-project-command).  
  
  
Varolan projeyi açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.OpenProject filename  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Gerekli. Tam yol ve dosya adını projenizi açın.  
  
 Sözdizimi `filename` bağımsız değişken gerektiriyor boşluk içeren yolları tırnak işaretleri kullanın.  
  
## <a name="remarks"></a>Açıklamalar  
 Otomatik Tamamlama, doğru yol ve dosya adı, türü bulmaya çalışır.  
  
 Bu komut hata ayıklama sırasında kullanılamaz.  
  
## <a name="example"></a>Örnek  
 Bu örnek açılır [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] Test1 proje.  
  
```  
>File.OpenProject "C:\My Projects\Test1\Test1.vbproj"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



