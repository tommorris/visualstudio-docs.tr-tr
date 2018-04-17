---
title: Komut Git | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6b817fd11d2a731ad2c6347949f03906328c741f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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