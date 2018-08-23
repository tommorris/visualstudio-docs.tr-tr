---
title: Git komut | Microsoft Docs
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
- edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 123398be5bf8b4aece11e2624390507cec2252d0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683624"
---
# <a name="go-to-command"></a>Git Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Git komutunu](https://docs.microsoft.com/visualstudio/ide/reference/go-to-command).  
  
  
İmleci belirtilen satıra taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Edit.GoTo [linenumber]  
```  
  
## <a name="arguments"></a>Arguments  
 `linenumber`  
 İsteğe bağlı. Gitmek için satır sayısını temsil eden bir tamsayı.  
  
## <a name="remarks"></a>Açıklamalar  
 Satır numaraları tek başlar. Varsa değerini `linenumber` değerden daha az, ilk satır görüntüler. Varsa değerini `linenumber` son satırın son satır görüntüler sayısından büyüktür.  
  
 İçin bir değer `linenumber` belirtilmezse, **satıra Git** iletişim kutusu görüntüler.  
  
 Bu komut diğer GoToLn adıdır.  
  
## <a name="example"></a>Örnek  
  
```  
>Edit.GoTo 125  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



