---
title: Açıklamalar
description: Mac için Visual Studio kaynak düzenleyicisinde açıklamaları kullanılarak bu makalede
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 0FE5E929-1846-4F48-B5E3-70990FAF9504
ms.openlocfilehash: 4a7dfd0daaddad9f91d461689a0174469dd253c2
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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
