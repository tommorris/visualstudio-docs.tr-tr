---
title: "Sınıf tasarımcısında Visual C++ numaralandırmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad55c68e16fcd340d69178dc24a4b92cada9e2f3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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