---
title: "Açıklamalar"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 0FE5E929-1846-4F48-B5E3-70990FAF9504
ms.openlocfilehash: cb44dc755721f6095c9a07ad3e6fec1f6849e149
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
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
