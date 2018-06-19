---
title: Yeni Dosya Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.newfile
helpviewer_keywords:
- File.NewFile command
- New File command
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a519de555f35df4fac91a9960993a0f163c4de5a
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704752"
---
# <a name="new-file-command"></a>Yeni Dosya Komutu
Yeni bir dosya oluşturur ve açar. Dosya çeşitli dosyalar klasörü altında görünür.

## <a name="syntax"></a>Sözdizimi

```cmd
File.NewFile [filename] [/t:templatename] [/editor:editorname]
```

## <a name="arguments"></a>Arguments
 `filename`

 İsteğe bağlı. Dosya adı. Hiçbir adı belirtilirse, varsayılan adı sağlanır. Hiçbir şablon adı listeleniyorsa, bir metin dosyası oluşturulur.

## <a name="switches"></a>Anahtarlar
 / t:`templatename`

 İsteğe bağlı. Oluşturulacak dosya türünü belirtir.

 / T:`templatename` bağımsız değişkeni sözdizimi yeni dosya iletişim kutusunda bulunan bilgileri yansıtır. Ardından bir eğik kategori adı girin (`\`) ve şablon adı ve tüm dizeyi tırnak işaretleri içine alın.

 Örneğin, yeni bir oluşturmak için [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] kaynak dosyasını, / t: şunları girersiniz`templatename` bağımsız değişkeni.

```cmd
/t:"Visual C++\C++ File (.cpp)"
```

 Yukarıdaki örnekte Visual C++ kategorisinde C++ dosya şablonu altındadır gösterir **yeni dosya** iletişim kutusu.

 / e:`editorname`

 İsteğe bağlı. Dosya açılacak düzenleyicinin adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı sağlanan **birlikte Aç** iletişim kutusu görüntülenir.

 / E:`editorname` bağımsız değişkeni açık ile iletişim kutusunda tırnak işaretleri içine göründükleri gibi Düzenleyici adları söz dizimini kullanır.

 Örneğin, bir dosyayı kaynak kod düzenleyicisinde açmak için aşağıdaki / e: için girersiniz`editorname` bağımsız değişkeni.

```cmd
/e:"Source Code (text) Editor"
```

## <a name="example"></a>Örnek
 Bu örnekte yeni bir Web sayfası "test1.htm" oluşturur ve Kaynak Kod Düzenleyicisi'nde açar.

```cmd
>File.NewFile test1 /t:"General\HTML Page" /e:"Source Code (text) Editor"
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Komut Penceresi](../../ide/reference/immediate-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)