---
title: Sınıf tasarımcısında Visual C++ yapılandırmaları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a701aae6e9c504d24d149dd5941a0f9623111ce2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634124"
---
# <a name="visual-c-structures-in-class-designer"></a>Sınıf Tasarımcısında Visual C++ Yapılandırmaları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [sınıf tasarımcısında Visual C++ yapılandırmaları](https://docs.microsoft.com/visualstudio/ide/visual-cpp-structures-in-class-designer).  
  
Sınıf Tasarımcısı, anahtar sözcüğü ile bildirilen C++ yapıları destekleyen `struct`. Bir örneği verilmiştir:  
  
```  
struct MyStructure  
{  
   char a;  
   int i;  
   long j;  
};  
```  
  
 Kullanma hakkında daha fazla bilgi için `struct` yazın, bkz: [yapı](http://msdn.microsoft.com/library/3c6ba273-e248-4ff1-8c69-d2abcf1263c6).  
  
 Sınıf diyagramında C++ yapı şeklinde görünür ve etiketi dışında sınıf şeklinin gibi çalışır **yapı** ve yuvarlak köşeler yerine dörtgen köşelerine sahiptir.  
  
|Kod öğesi|Sınıf Tasarımcısı görünümü|  
|------------------|-------------------------|  
|`struct StructureName {};`|**StructureName**<br /><br /> Yapı|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ kodu (Sınıf Tasarımcısı) ile çalışma](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Sınıflar ve yapılar](http://msdn.microsoft.com/library/516dd496-13fb-4f17-845a-e9ca45437873)   
 [struct](http://msdn.microsoft.com/library/3c6ba273-e248-4ff1-8c69-d2abcf1263c6)



