---
title: Açıklamalar
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 0FE5E929-1846-4F48-B5E3-70990FAF9504
ms.openlocfilehash: 0d49896a3c265dfdc5a25c46e80de498adfffb07
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="comments"></a>Açıklamalar

Hata ayıklama veya koduyla denemeler, kod blokları ya da geçici olarak yorum yapmak veya uzun süreli yararlı olabilir. 

Tüm bir kod bloğunu açıklama eklemek için:

* Kod seçip **geçiş satırı yorumları** ve bağlam menüsünden

VEYA

* Kullanım `cmd + /` keybinding seçili kodu.

Bu yöntemler, açıklama ve kodun bölümlerine için kullanılabilir. C# dosyalarını, satır yorumlar ek düzeyleri, bölgeler açıklanmış ve uncommented sırasında hala koruma gerçek açıklamaları olması kodlarının sağlayan eklenebilir: 

 ![birden çok düzeyli açıklamaları](media/source-editor-image8.png)

Açıklamalar, onunla etkileşimde bulunabilir gelecekteki geliştiriciler için kod belgeleme için faydalıdır. Bunlar genellikle şu şekilde her iki dilde eklenen çok satırlı yorumlar biçiminde gerçekleştirilir:

**C#**

``` cs
/*
 This is a multi-line
 comment in C#
*/
```
**F#**

```fsharp
(*
 This is a multi-line
  comment in F#
*)
```
