---
title: Başlat Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
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
ms.openlocfilehash: c1e5ade7d02882633504ac5615ee751b2533adde
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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

- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)