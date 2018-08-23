---
title: Sayı tabanı komut kümesi | Microsoft Docs
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
- debug.setradix
helpviewer_keywords:
- Set Radix command
- Debug.SetRadix command
ms.assetid: 6ffd1554-7530-4da4-b5f5-e276a5034f3b
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 99b5623fff4e2919bb34bc7dd4ba60d14ba93077
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634223"
---
# <a name="set-radix-command"></a>Sayı Tabanını Ayarla Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Set taban komutu](https://docs.microsoft.com/visualstudio/ide/reference/set-radix-command).  
  
  
Tamsayı değerleri görüntülemek için kullanılan sayısal taban döndürür veya ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.SetRadix [10 | 16 | hex | dec]  
```  
  
## <a name="arguments"></a>Arguments  
 `10` veya `16` veya `hex` veya `dec`  
 İsteğe bağlı. Ondalık gösterir (10 veya Ara) ya da onaltılık (16 veya onaltılık). Ardından bir bağımsız değişken yoksayılırsa geçerli taban değeri döndürülür.  
  
## <a name="example"></a>Örnek  
 Bu örnek, tamsayı değerlerini onaltılık biçimde görüntülemek için ortamı ayarlar.  
  
```  
>Debug.SetRadix hex  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



