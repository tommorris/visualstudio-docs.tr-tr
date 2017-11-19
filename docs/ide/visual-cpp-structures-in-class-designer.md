---
title: "Sınıf tasarımcısında Visual C++ yapıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 85e2068e00f2164b44feb9aae61a47de426be735
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-c-structures-in-class-designer"></a>Sınıf Tasarımcısında Visual C++ Yapılandırmaları
Sınıf Tasarımcısı anahtar sözcüğüyle bildirilen C++ yapılarını desteklemektedir `struct`. Aşağıda bir örnek verilmiştir:  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ kodu (Sınıf Tasarımcısı) ile çalışma](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Sınıflar ve yapılar](/cpp/cpp/classes-and-structs-cpp)   
 [yapısı](/cpp/cpp/struct-cpp)