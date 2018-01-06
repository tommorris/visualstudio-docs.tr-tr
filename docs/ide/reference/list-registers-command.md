---
title: Liste kaydeder komutu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.listregisters
helpviewer_keywords:
- list registers command
- Debug.ListRegisters command
- ListRegisters command
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
caps.latest.revision: "7"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 016de257d1ce4e6d2aa95284adbe762a5c54eacf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="list-registers-command"></a>Yazmaçları Listele Komutu
Seçili değerini kaydeder ve olanak sağlayan görüntüler göstermek için kayıtları listesini değiştirin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]  
[/Watch [{register|registerGroup}...]]  
[/Unwatch [{register|registerGroup}...]]  
```  
  
## <a name="switches"></a>Anahtarlar  
 / Görüntüleme [{`register`&#124;`registerGroup`} ...]  
 Belirtilen değerlerini görüntüler `register` veya `registerGroup`. Öyle değilse `register` veya `registerGroup` belirtilirse, kayıtları varsayılan listesi görüntülenir. Hiçbir anahtar belirtilirse, davranışı aynıdır. Örneğin:  
  
 `Debug.ListRegisters /Display eax`  
  
 eşdeğerdir  
  
 `Debug.ListRegisters eax`  
  
 / Listesi  
 YAZMAÇ grupları listede tüm görüntüler.  
  
 / İzleme [{`register`&#124;`registerGroup`} ...]  
 Bir veya daha fazla ekler `register` veya `registerGroup` değerleri listesi.  
  
 / Unwatch [{`register`&#124;`registerGroup`} ...]  
 Bir veya daha fazla kaldırır `register` veya `registerGroup` listeden değerleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Diğer ad `r` yerine kullanılan `Debug.ListRegisters`.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `Debug.ListRegisters` diğer `r` kayıt Grup değerlerini görüntülemek için `Flags`.  
  
```  
r /Display Flags  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Hata ayıklama temelleri: Yazmaçlar penceresi](../../debugger/debugging-basics-registers-window.md)   
 [Nasıl yapılır: yazmaçlar penceresini kullanma](../../debugger/how-to-use-the-registers-window.md)