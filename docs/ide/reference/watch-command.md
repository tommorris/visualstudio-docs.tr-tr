---
title: "İzle komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.watch
helpviewer_keywords:
- Watch command
- Debug.Watch command
ms.assetid: aa02e647-d9f5-4905-a651-52a8df595795
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b3234206f72e1ed6cb1e4aa46aad431bac046835
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="watch-command"></a>İzle Komutu
Oluşturur ve belirtilen bir örneğini açar bir **izleme** penceresi. Kullanabileceğiniz bir **izleme** değişkenleri, ifadeler ve kayıtları, bu değerleri düzenlemek ve sonuçları kaydetmek için değerleri hesaplamak için penceresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.Watch[index]  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Gerekli. Gözcü penceresi örneği sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 `index` Bir tamsayı olmalıdır. Geçerli değerler 1, 2, 3 veya 4 arasındadır.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.Watch1  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomatik değişkenler ve yerel Windows](../../debugger/autos-and-locals-windows.md)   
 [Bir izleme izleme ve QuickWatch Windows Visual Studio kullanarak değişkenleri ayarlayın](../../debugger/watch-and-quickwatch-windows.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)