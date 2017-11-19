---
title: "İzlenecek yol: Tasarım zamanında hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1d497535f8511c3f9e6c55e80157507ed36184b0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-debugging-at-design-time"></a>İzlenecek Yol: Tasarım Zamanında Hata Ayıklama
Visual Studio'yu kullanabilirsiniz **hemen** uygulamanızı çalışırken bir işlevi veya alt yordama yürütmek için penceresi. İşlev veya alt yordama bir kesme noktası içeriyorsa, Visual Studio uygun noktada yürütme çalışmamasına neden olur. Hata ayıklayıcı windows sonra programın durumunu incelemek için de kullanabilirsiniz. Bu özellik, tasarım zamanında hata ayıklama adı verilir.  
  
 Aşağıdaki yordam, bu özelliği nasıl kullanabileceğinizi gösterir.  
  
### <a name="to-hit-breakpoints-from-the-immediate-window"></a>Kesme noktaları hemen penceresinden isabet  
  
1.  Bir Visual Basic konsol uygulamasına aşağıdaki kodu yapıştırın:  
  
    ```  
    Module Module1  
  
        Sub Main()  
            MySub()  
        End Sub  
  
        Function MyFunction() As Decimal  
            Static i As Integer  
            i = i + 1  
            Dim s As String  
  
            s = "Add Breakpoint here"  
            Return 4  
        End Function  
  
        Sub MySub()  
            MyFunction()  
        End Sub  
    End Module  
    ```  
  
2.  Okuma ve satırında bir kesme noktası belirleyerek `s="Add BreakPoint Here"`.  
  
3.  Aşağıdakileri yazın **hemen** penceresi:`?MyFunction<enter>`  
  
4.  Kesme noktası isabet aldı ve çağrı yığını doğru olduğundan emin olun.  
  
5.  Üzerinde **hata ayıklama** menüsünde tıklatın **devam**, hala Tasarım modunda olup olmadığını ve doğrulayın.  
  
6.  Aşağıdakileri yazın **hemen** penceresi:`?MyFunction<enter>`  
  
7.  Aşağıdakileri yazın **hemen** penceresi:`?MySub<enter>`  
  
8.  Kesme noktası isabet ve statik değişkenin değerini inceleyin doğrulayın `i` içinde **Yereller** penceresi. 3 değeri olmalıdır.  
  
9. Çağrı yığını doğru olduğundan emin olun.  
  
10. Üzerinde **hata ayıklama** menüsünde tıklatın **devam**, hala Tasarım modunda olup olmadığını ve doğrulayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)