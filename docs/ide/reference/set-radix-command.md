---
title: Sayı Tabanını Ayarla Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.setradix
helpviewer_keywords:
- Set Radix command
- Debug.SetRadix command
ms.assetid: 6ffd1554-7530-4da4-b5f5-e276a5034f3b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f23e2492a183dcae2e2b3cb87e39b08f66a7c2ae
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="set-radix-command"></a>Sayı Tabanını Ayarla Komutu
Tamsayı değerlerini görüntülemek için kullanılan sayısal temel döndürür veya ayarlar.

## <a name="syntax"></a>Sözdizimi

```
Debug.SetRadix [10 | 16 | hex | dec]
```

## <a name="arguments"></a>Arguments
 `10` veya `16` veya `hex` veya `dec`

 İsteğe bağlı. Ondalık gösterir (10 veya Ara) veya onaltılık (16 veya onaltılı). Bağımsız değişken belirtilmezse, geçerli sayı tabanını değeri döndürülür.

## <a name="example"></a>Örnek
 Bu örnek, onaltılık biçimde tamsayı değerlerini görüntülemek için ortamını ayarlar.

```
>Debug.SetRadix hex
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)