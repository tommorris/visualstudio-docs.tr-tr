---
title: Başlat komutu | Microsoft Docs
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
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6e70a682d9b9ef67e9f0372173c3396a0706cd2f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692219"
---
# <a name="start-command"></a>Başlat Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Start komutunu](https://docs.microsoft.com/visualstudio/ide/reference/start-command).  
  
  
Başlangıç projesinde hata ayıklamaya başlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.Start [address]  
```  
  
## <a name="arguments"></a>Arguments  
 `address`  
 İsteğe bağlı. Adres, program yürütme bir kesme noktası kaynak kodundaki benzer askıya alır. Bu bağımsız değişken, yalnızca hata ayıklama modunda geçerlidir.  
  
## <a name="remarks"></a>Açıklamalar  
 **Başlat** komut çalıştırıldığında, belirtilen adresi için bir RunToCursor işlemi gerçekleştirir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, hata ayıklayıcıyı başlatır ve oluşan özel durumları yok sayar.  
  
```  
>Debug.Start  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



