---
title: Command penceresi çıktısı günlüğü tut komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- tools.logcommandwindowoutput
helpviewer_keywords:
- log Command window output command
- View.LogCommandWindowOutput command
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 16eb42011a15539193e9d69724d299c73e5cecc4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="log-command-window-output-command"></a>Command penceresi çıktısı günlüğü tut komutu
Girdi ve çıktı kopyaları tüm **komutu** bir dosyaya penceresi.

## <a name="syntax"></a>Sözdizimi

```
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]
```

## <a name="arguments"></a>Arguments
 `filename`

 İsteğe bağlı. Günlük dosyasının adı. Varsayılan olarak, dosyayı kullanıcının profili klasöründe oluşturulur. Dosya adı zaten varsa, günlük varolan dosyanın sonuna eklenir. Hiçbir dosya belirtilirse, belirtilen son dosyası kullanılır. Önceki bir dosya varsa, cmdline.log adlı bir varsayılan günlük dosyası oluşturulur.

> [!TIP]
> Günlük dosyasının kaydedildiği konumu değiştirmek için yol boşluk içeriyorsa tırnak işaretleri dosyasının tam yolunu girin.


## <a name="switches"></a>Anahtarlar
 /on

 İsteğe bağlı. Günlüğü başlatır **komutu** belirtilen dosya penceresinde ve yeni bilgiler ile dosya ekler.

 / Kapalı

 İsteğe bağlı. Günlüğü durdurur **komutu** penceresi.

 / üzerine yaz

 İsteğe bağlı. Belirtilen dosya, `filename` bağımsız değişkeni ile eşleşen varolan bir dosyanın, dosyanın üzerine yazılır.

## <a name="remarks"></a>Açıklamalar
 Hiçbir dosya belirtilirse, dosya cmdline.log varsayılan olarak oluşturulur. Varsayılan olarak, bu komut için diğer ad günlüktür.

## <a name="examples"></a>Örnekler
 Bu örnekte yeni bir günlük dosyası olan cmdlog, oluşturur ve komut günlük başlatır.

```
>Tools.LogCommandWindowOutput cmdlog
```

 Bu örnekte oturum açma komutları durdurur.

```
>Tools.LogCommandWindowOutput /off
```

 Bu örnek daha önce kullanılan günlük dosyasında komutları günlüğe sürdürür.

```
>Tools.LogCommandWindowOutput /on
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)