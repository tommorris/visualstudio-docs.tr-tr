---
title: İzle komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.watch
helpviewer_keywords:
- Watch command
- Debug.Watch command
ms.assetid: aa02e647-d9f5-4905-a651-52a8df595795
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a82816acfbb995b47dfb34337b20488ad3787f04
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)