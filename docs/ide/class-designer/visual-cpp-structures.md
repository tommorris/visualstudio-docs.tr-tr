---
title: Sınıf Tasarımcısında Visual C++ Yapılandırmaları
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 36d9e78a1944817d9384d0c55b9584e58a758ccc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="visual-c-structures-in-class-designer"></a>Sınıf tasarımcısında Visual C++ yapıları

**Sınıf Tasarımcısı** anahtar sözcüğüyle bildirilen C++ yapılarını destekler `struct`. Aşağıda bir örnek verilmiştir:

```cpp
struct MyStructure
{
   char a;
   int i;
   long j;
};
```

Kullanma hakkında daha fazla bilgi için `struct` yazın, bkz: [yapısı](/cpp/cpp/struct-cpp).

Sınıf diyagramında C++ yapısı Şekil arar ve etiket okur dışında bir sınıf şekli gibi çalışır **yapısı** ve yuvarlak köşeleri yerine kare köşeleri sahiptir.

|Kod öğesi|Sınıf Tasarımcısı görünümü|
|------------------|-------------------------|
|`struct StructureName {};`|**StructureName**<br /><br /> Yapı|

## <a name="see-also"></a>Ayrıca bkz.

- [Visual C++ Kodu ile Çalışma](working-with-visual-cpp-code.md)
- [Sınıflar ve Yapılar](/cpp/cpp/classes-and-structs-cpp)
- [struct](/cpp/cpp/struct-cpp)