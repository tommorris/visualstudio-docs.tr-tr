---
title: Hızlı Bakış Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 957f521b23bc56a6bfa4f8de315f130d5f82d8d3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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

- [Bir izleme izleme ve QuickWatch Windows Visual Studio kullanarak değişkenleri ayarlayın](../../debugger/watch-and-quickwatch-windows.md)
- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)