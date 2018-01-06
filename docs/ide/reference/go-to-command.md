---
title: Komut Git | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 53c45ccf528375bc31b4d61fd6af0193aa295e6c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="go-to-command"></a>Git Komutu
İmleç belirtilen satıra taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Edit.GoTo [linenumber]  
```  
  
## <a name="arguments"></a>Arguments  
 `linenumber`  
 İsteğe bağlı. Gitmek için satır sayısını temsil eden bir tamsayı.  
  
## <a name="remarks"></a>Açıklamalar  
 Satır numaraları her seferde başlar. Varsa değerini `linenumber` birden küçükse, ilk satır görüntüler. Varsa değerini `linenumber` son satırında, son satır görüntüler sayısından büyük.  
  
 İçin bir değer `linenumber` belirtilmezse, **satıra Git** iletişim kutusunu görüntüler.  
  
 Bu komut için diğer ad GoToLn ' dir.  
  
## <a name="example"></a>Örnek  
  
```  
>Edit.GoTo 125  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)