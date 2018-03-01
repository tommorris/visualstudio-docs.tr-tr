---
title: "Hızlı Bakış komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bad8605a2a7b9f9606c448680d583c55a2762a75
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="quick-watch-command"></a>Hızlı Bakış Komutu
İfade alanında seçilen ya da belirtilen metni görüntüleyen [QuickWatch](../../debugger/watch-and-quickwatch-windows.md) penceresi. Bir değişken veya hata ayıklayıcı ya da bir kaydın içeriğini tarafından tanınan ifadesi geçerli değerini hesaplamak için bu iletişim kutusunu kullanın. Ayrıca, herhangi bir sabit olmayan değişken değeri veya tüm kayıt içeriğini değiştirebilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.QuickWatchq [text]  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 İsteğe bağlı. Eklemek için metin **QuickWatch** iletişim kutusu.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `text` olan atlanırsa şu anda seçili metin veya word imlecin Gözcü penceresi eklenir.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.QuickWatch  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir izleme izleme ve QuickWatch Windows Visual Studio kullanarak değişkenleri ayarlayın](../../debugger/watch-and-quickwatch-windows.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)