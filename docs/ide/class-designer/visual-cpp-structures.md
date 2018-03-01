---
title: "Sınıf tasarımcısında Visual C++ yapıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d6f2aa3893a230abd52dd5cf19ed9d751e56e50c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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