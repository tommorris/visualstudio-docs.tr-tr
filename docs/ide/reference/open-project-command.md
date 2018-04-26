---
title: Proje Aç Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.openproject
helpviewer_keywords:
- op command
- File.OpenProject command
- Open Project command
ms.assetid: baa85f86-041b-49f4-9ced-0c397dc180e1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 09241e72119a0a0973995b16152941bbe5272c3f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="open-project-command"></a>Proje Aç Komutu
Varolan projeyi açar.

## <a name="syntax"></a>Sözdizimi

```
File.OpenProject filename
```

## <a name="arguments"></a>Arguments
 `filename`

 Gerekli. Projenin açmak için tam yol ve dosya adı.

 Sözdizimi `filename` bağımsız değişken gerektiriyor boşluk içeren yollar tırnak işaretleri kullanın.

## <a name="remarks"></a>Açıklamalar
 Otomatik Tamamlama doğru yolun ve dosya adı, türü bulmaya çalışır.

 Bu komutu hata ayıklama sırasında kullanılamaz.

## <a name="example"></a>Örnek
 Bu örnek açar [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] proje, Test1.

```
>File.OpenProject "C:\My Projects\Test1\Test1.vbproj"
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)