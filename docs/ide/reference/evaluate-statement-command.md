---
title: Deyimi Değerlendir Komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0c2ec882bb2fdc9d0f3b74a0552c85a7b286617c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="evaluate-statement-command"></a>Deyimi Değerlendir Komutu
Değerlendirir ve belirli deyim görüntüler.

## <a name="syntax"></a>Sözdizimi

```
Debug.EvaluateStatement text
```

## <a name="arguments"></a>Arguments
 `text` Gerekli. Değerlendirilecek ifade.

## <a name="remarks"></a>Açıklamalar
 Girmek için kullanılan penceresi **EvaluateStatement** komutu belirleyen bir eşittir işareti (=) bir karşılaştırma işleci veya atama işleci olarak yorumlanır.

 İçinde **komutu** penceresinde, bir eşittir işareti (=) bir karşılaştırma işleci yorumlanır. Örneğin, bunu, değişkenlerin değerleri `a` ve `b` farklı, sonra komutu

```
>Debug.EvaluateStatement(a=b)
```

 bir değeri döndürür `false`.

 İçinde **hemen** penceresinde, buna karşın bir eşittir işareti (=) atama işleci yorumlanır. Bu nedenle, örneğin, komutu

```
>Debug.EvaluateStatement(a=b)
```

 değişkene atar `a` değişkenin değerini `b`.

## <a name="example"></a>Örnek

```
>Debug.EvaluateStatement(a+b)
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Yazdır Komutu](../../ide/reference/print-command.md)
- [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)
- [Komut Penceresi](../../ide/reference/command-window.md)
- [Bul/komut kutusu](../../ide/find-command-box.md)
- [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)