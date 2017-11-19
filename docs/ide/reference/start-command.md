---
title: "Başlat komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f83fbf1427951057f2154e032fb58b178c8b39fc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)