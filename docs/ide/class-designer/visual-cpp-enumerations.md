---
title: Sınıf tasarımcısında Visual C++ numaralandırmaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: ac804f35c2d917e5443e61d4f2e53cde81165070
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="visual-c-enumerations-in-class-designer"></a>Sınıf Tasarımcısında Visual C++ Numaralandırmaları
Sınıf Tasarımcısı destekleyen C++ `enum` ve kapsamlı `enum class` türleri. Aşağıda bir örnek verilmiştir:  
  
```cpp
enum CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
// or...  
enum class CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};
```  
  
Sınıf diyagramında C++ numaralandırması Şekil arar ve çalıştığını yapısı şekli gibi etiketi okur dışında **Enum** veya **Enum sınıfı**, mavi yerine pembe ve üst ve sol renkli kenarlık vardır Kenar boşlukları. Numaralandırma şekiller ve yapısı şekiller kare köşeleri vardır.  
  
Kullanma hakkında daha fazla bilgi için `enum` yazın, bkz: [numaralandırmalar](/cpp/cpp/enumerations-cpp).  
  
## <a name="see-also"></a>Ayrıca bkz.
[Visual C++ kodu ile çalışma](working-with-visual-cpp-code.md)   
[Sabit Listeleri](/cpp/cpp/enumerations-cpp)