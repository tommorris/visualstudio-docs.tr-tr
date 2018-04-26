---
title: '8. Adım: Testi Özelleştirme'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 82e059383a706c45e6882b97611f680a3d49baeb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="step-8-customize-the-quiz"></a>8. Adım: Testi Özelleştirme
Öğreticinin son bölümünde testi özelleştirme ve zaten öğrendiklerinizi üzerinde genişletmek için bazı yollar ele alacağız. Örneğin, program yanıt hiçbir zaman bir kesir olduğu rastgele bölme problemleri nasıl oluşturduğunu hakkında düşünün. Daha fazla bilgi için Aç `timeLabel` farklı bir renk denetlemek ve test alanın bir ipucu sağlar.  

### <a name="to-customize-the-quiz"></a>Test özelleştirmek için  

-   Yalnızca beş saniyede bir test kaldığında kapatma **timeLabel** denetim kırmızı ayarlayarak kendi **BackColor** özelliği (`timeLabel.BackColor = Color.Red;`). Test bittiğinde rengi sıfırlayın.  

-   Test alanın doğru yanıt NumericUpDown denetimine girildiğinde ses çalma bir ipucu sağlar. (Her denetim için bir olay işleyicisi yazma `ValueChanged()` test alanın denetimin değeri değiştiğinde harekete olayı.)  

### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  

-   Test tamamlanmış bir sürümünü indirmek için bkz: [tam matematik testi öğretici örnek](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).  

-   Sonraki öğretici gitmek için bkz: [öğretici 3: eşleşen bir oyun oluşturmak](../ide/tutorial-3-create-a-matching-game.md).  

-   Eğitmen önceki adıma dönmek için bkz: [adım 7: ekleme çarpma ve bölme problemleri](../ide/step-7-add-multiplication-and-division-problems.md).
