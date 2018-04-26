---
title: İzle Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
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
ms.openlocfilehash: 97fe1c6865b8934d2c0329547e98323c75bf3ec0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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

- [Otomatik değişkenler ve yerel Windows](../../debugger/autos-and-locals-windows.md)
- [Bir izleme izleme ve QuickWatch Windows Visual Studio kullanarak değişkenleri ayarlayın](../../debugger/watch-and-quickwatch-windows.md)
- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)