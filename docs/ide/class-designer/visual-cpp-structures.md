---
title: Sınıf tasarımcısında Visual C++ yapıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: d0621b5a2a82786a41e8d566954f03341affa905
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="visual-c-structures-in-class-designer"></a>Sınıf Tasarımcısında Visual C++ Yapılandırmaları
Sınıf Tasarımcısı anahtar sözcüğüyle bildirilen C++ yapılarını desteklemektedir `struct`. Aşağıda bir örnek verilmiştir:  
  
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
[Visual C++ kodu ile çalışma](working-with-visual-cpp-code.md)   
[Sınıflar ve yapılar](/cpp/cpp/classes-and-structs-cpp)   
[struct](/cpp/cpp/struct-cpp)