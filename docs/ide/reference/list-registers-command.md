---
title: Liste kaydeder komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.listregisters
helpviewer_keywords:
- list registers command
- Debug.ListRegisters command
- ListRegisters command
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4bd4dac2cc8faf6d98ee130e0796254035b1ca2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 / Görüntüleme [{`register`&#124;`registerGroup`}...]  
 Belirtilen değerlerini görüntüler `register` veya `registerGroup`. Öyle değilse `register` veya `registerGroup` belirtilirse, kayıtları varsayılan listesi görüntülenir. Hiçbir anahtar belirtilirse, davranışı aynıdır. Örneğin:  
  
 `Debug.ListRegisters /Display eax`  
  
 eşdeğerdir  
  
 `Debug.ListRegisters eax`  
  
 / Listesi  
 YAZMAÇ grupları listede tüm görüntüler.  
  
 / İzleme [{`register`&#124;`registerGroup`}...]  
 Bir veya daha fazla ekler `register` veya `registerGroup` değerleri listesi.  
  
 / Unwatch [{`register`&#124;`registerGroup`}...]  
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