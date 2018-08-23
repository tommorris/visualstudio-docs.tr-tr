---
title: Değer iletişim kutusu değiştiremezsiniz | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Cannot Change Value dialog box
- variables [debugger], editing
ms.assetid: 19e930c2-5fbf-4c83-aae8-a1dc3f8fcae8
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a464be8e52a96da027e26ae48c5efb73ca2b5bf3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631871"
---
# <a name="cannot-change-value-dialog-box"></a>Değer Değiştirilemez İletişim Kutusu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [olamaz değişikliği değer iletişim kutusu](https://docs.microsoft.com/visualstudio/debugger/cannot-change-value-dialog-box).  
  
Hata  
 `The value of this variable cannot be changed` &#124;`The name` *adı* `does not exist in the current context` &#124; *çeşitli başka iletiler*  
  
 Hata ayıklayıcı penceresindeki (Otomatikler, izleme veya yerel öğeler windows) veya QuickWatch iletişim kutusundaki geçersiz bir değer için bir değişken içeriğini değiştirmeye çalıştığınızda bu ileti kutusu görünür. Örneğin, bir karakter dizesindeki bir tamsayı değişkeninin değeri ayarlamaya çalışırsanız, bu ileti kutusu görünür.  
  
## <a name="solution"></a>Çözüm  
 Hata ayıklayıcı pencereye yazın giriş olduğundan emin olun veya QuickWatch iletişim kutusu ayarlamaya çalıştığınız değişken için geçerli bir değeri temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcıdaki ifadeler](../debugger/expressions-in-the-debugger.md)



