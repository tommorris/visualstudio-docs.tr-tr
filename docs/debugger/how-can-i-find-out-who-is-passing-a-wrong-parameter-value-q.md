---
title: "Kimin Yanlış Parametre Değeri Geçirdiğini Nasıl Bulabilirim? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.parameters
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], parameters
- parameters [debugger]
- passing parameters, troubleshooting wrong values
- functions [debugger], detecting wrong parameter values
- parameter values, troubleshooting
ms.assetid: 1f1ae455-0e25-4e9d-b33f-53908f5bd6ce
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 503a7cec06e049099b2470910d17e4e79b823924
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-can-i-find-out-who-is-passing-a-wrong-parameter-value"></a>Kimin Yanlış Parametre Değeri Geçirdiğini Nasıl Bulabilirim?
## <a name="problem-description"></a>Sorun açıklaması  
 My işlevleri biri için yanlış parametre değeri geçirilir. Bu işlev dünyanın dört bir yanındaki yer çağrılır. Nasıl bulabilirim ne yanlış değer geçiyor çıkışı?  
  
## <a name="solution"></a>Çözüm  
  
#### <a name="to-resolve-this-problem"></a>Bu sorunu gidermek için  
  
1.  Konum kesme noktası işlevi başında ayarlayın.  
  
2.  Kesme noktası sağ tıklatıp **koşul**.  
  
3.  İçinde **kesme noktası koşulu** iletişim kutusu, tıklatıldığında **koşulu** onay kutusunu. Bkz: [kesme noktaları Gelişmiş](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).  
  
4.  Bir ifade girin `Var==3`, metin kutusuna, burada `Var` hatalı değeri içeren parametre adı ve `3` hatalı değer geçirildi.  
  
5.  Seçin **true'dur** tıklayın ve radyo düğmesinin **Tamam** düğmesi.  
  
6.  Şimdi programı yeniden çalıştırın. Programın işlevi başında durdurmak kesme neden olduğunda `Var` parametre değeri içeriyor `3`.  
  
7.  Çağıran işlevi bulmak ve kendi kaynak koduna gezinmek için çağrı yığını penceresini kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: çağrı yığını penceresinde kullanmak](../debugger/how-to-use-the-call-stack-window.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Kesme noktaları](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)