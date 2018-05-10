---
title: Dosya Aç Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.openfile
helpviewer_keywords:
- Open File command
- File.OpenFile command
- of command
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d238370586a9256d91f89f06fddbe3c58abc27e8
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="open-file-command"></a>Dosya Aç Komutu
Varolan bir dosyayı açar ve bir düzenleyicide belirtmenize olanak tanır.

## <a name="syntax"></a>Sözdizimi

```cmd
File.OpenFile filename [/e:editorname]
```

## <a name="arguments"></a>Arguments
 `filename`

 Gerekli. Tam veya kısmi yol ve dosya adı dosyayı açın. Boşluk içeren yollar tırnak işaretleri içine alınmalıdır.

## <a name="switches"></a>Anahtarlar
 / e:`editorname`

 İsteğe bağlı. Dosya açılacak düzenleyicinin adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı sağlanan **birlikte Aç** iletişim kutusu görüntülenir.

 / E:`editorname` bağımsız değişkeni açık ile iletişim kutusunda tırnak işaretleri içine göründükleri gibi Düzenleyici adları söz dizimini kullanır.

 Örneğin, bir dosyayı kaynak kod düzenleyicisinde açmak için aşağıdaki / e: için girersiniz`editorname` bağımsız değişkeni.

```cmd
/e:"Source Code (text) Editor"
```

## <a name="remarks"></a>Açıklamalar
 Bir yol girin gibi otomatik tamamlama doğru yolun ve dosya adı bulmaya çalışır.

## <a name="example"></a>Örnek
 Bu örnek stil dosyasını "Test1.css" Kaynak Kod Düzenleyicisi'nde açar.

```cmd
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Komut Penceresi](../../ide/reference/immediate-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)