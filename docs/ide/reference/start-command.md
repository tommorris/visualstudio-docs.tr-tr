---
title: Başlat komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a4c372d3f384eeaa0ac137188e325ccde777cd4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="start-command"></a>Başlat Komutu
Başlangıç projesi hata ayıklama başlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.Start [address]  
```  
  
## <a name="arguments"></a>Arguments  
 `address`  
 İsteğe bağlı. Hangi program, kaynak kodunda kesme noktası benzer durduran adresi. Bu bağımsız değişken yalnızca hata ayıklama modunda geçerli değil.  
  
## <a name="remarks"></a>Açıklamalar  
 **Başlat** komutu çalıştırıldığında, belirtilen adresine RunToCursor işlemi gerçekleştirir.  
  
## <a name="example"></a>Örnek  
 Bu örnek, hata ayıklayıcı başlatır ve oluşan özel durumlar yok sayar.  
  
```  
>Debug.Start  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)