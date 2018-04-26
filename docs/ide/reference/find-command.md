---
title: Bul Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- edit.find
helpviewer_keywords:
- Find command
- Edit.Find command
ms.assetid: f0c705dc-2b97-423d-abbf-5584d4827208
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 31810189ec7127548f68a3732afc701e8a7bac08
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="find-command"></a>Bul Komutu
Bir alt kümesi üzerinde kullanılabilir seçenekleri kullanarak dosyaları arar **dosyalarda Bul** sekmesinde **bulma ve değiştirme** penceresi.

## <a name="syntax"></a>Sözdizimi

```
Edit.Find findwhat [/case] [/doc | /proc | /open | /sel]
[/markall] [/options] [/reset] [/up] [/wild | /regex] [/word]
```

## <a name="arguments"></a>Arguments
 `findwhat` Gerekli. Eşleşen metin.

## <a name="switches"></a>Anahtarlar
 /Case veya /c isteğe bağlı. Eşleşme ortaya yalnızca büyük ve küçük harfleri tam olarak belirtilen eşleşiyorsa `findwhat` bağımsız değişkeni.

 / doc veya /d isteğe bağlı. Yalnızca geçerli belgede arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.

 /markall veya /m isteğe bağlı. Her satırda bir arama eşleşme geçerli belgedeki içeren bir grafik yerleştirir.

 /Open veya /o isteğe bağlı. Bir belge değilmiş gibi tüm açık belgeleri arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.

 / Options veya /t isteğe bağlı. Geçerli Bul seçeneği ayarlarını listesini görüntüler ve arama gerçekleştirmez.

 /proc veya /p isteğe bağlı. Yalnızca geçerli yordamı arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.

 / Reset veya /e isteğe bağlı. Bul seçeneklerini varsayılan ayarlarına geri döndürür ve bir arama gerçekleştirmez.

 /sel veya /s isteğe bağlı. Yalnızca geçerli seçimi arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.

 /UP veya /u isteğe bağlıdır. Dosya geçerli konumunu başına doğru dosyasında arar. Varsayılan olarak, dosya ve dosyanın sonuna aramaları geçerli konumda aramalar başlar.

 /Regex veya /r isteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişken olarak değişmez değer karakterleri yerine metin desenlerini göstermek gösterimler. Normal ifade karakter tam bir listesi için bkz: [normal ifadeler](../../ide/using-regular-expressions-in-visual-studio.md).

 /wild veya /l isteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişkeni olarak bir karakter ya da bir karakter dizisi temsil etmek için gösterimler.

 /Word veya /w isteğe bağlı. Yalnızca tam sözcükleri için arama yapar.

## <a name="example"></a>Örnek
 Bu örnek kod şu anda seçili bölümünde "somestring" sözcüğü için büyük küçük harfe duyarlı arama gerçekleştirir.

```
>Edit.Find somestring /sel /case
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)