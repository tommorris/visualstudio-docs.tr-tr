---
title: İzle komutu | Microsoft Docs
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
- debug.watch
helpviewer_keywords:
- Watch command
- Debug.Watch command
ms.assetid: aa02e647-d9f5-4905-a651-52a8df595795
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d06e15f23a8f75e4a771b9db1991f5aba2ffc0d8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690954"
---
# <a name="watch-command"></a>İzle Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [bakış komutu](https://docs.microsoft.com/visualstudio/ide/reference/watch-command).  
  
  
Oluşturur ve belirtilen bir örneğini açar bir **Watch** penceresi. Kullanabileceğiniz bir **Watch** penceresi değişkenleri ve ifadeleri kayıtları, bu değerleri düzenleme ve sonuçları kaydetmek için değerleri hesaplamak için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.Watch[index]  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Gerekli. İzleme penceresi örneği sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 `index` Bir tamsayı olmalıdır. Geçerli değerler 1, 2, 3 veya 4 arasındadır.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.Watch1  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otolar ve yerel öğeler Windows](../../debugger/autos-and-locals-windows.md)   
 [Nasıl yapılır: bir değişken penceresinde değer düzenleme](http://msdn.microsoft.com/library/36f464ab-c900-4c0b-9ab3-557b3d9cdab5)   
 [Nasıl yapılır: QuickWatch iletişim kutusunu kullanın](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



