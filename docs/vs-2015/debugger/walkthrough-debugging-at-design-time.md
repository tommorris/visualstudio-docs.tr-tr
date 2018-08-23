---
title: 'İzlenecek yol: Tasarım zamanında hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd63fca37bbb55f99ecb99a18596c128451bd807
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689609"
---
# <a name="walkthrough-debugging-at-design-time"></a>İzlenecek Yol: Tasarım Zamanında Hata Ayıklama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [izlenecek yol: tasarım zamanında hata ayıklama](https://docs.microsoft.com/visualstudio/debugger/walkthrough-debugging-at-design-time).  
  
Visual Studio kullanabileceğiniz **hemen** uygulamanız çalışmıyorken bir işlevi veya alt yordamı yürütmek için penceresi. İşlev veya alt yordam bir kesme noktası içeriyorsa, Visual Studio uygun noktada yürütmeyi keser. Ardından, programınızın durumunu incelemek için hata ayıklayıcı penceresini kullanabilirsiniz. Bu özellik tasarım zamanında hata ayıklama çağrılır.  
  
 Aşağıdaki yordam, bu özelliği nasıl kullanabileceğinizi gösterir.  
  
### <a name="to-hit-breakpoints-from-the-immediate-window"></a>Hemen penceresinde kesme noktaları isabet  
  
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
  
2.  Okuma, satırında bir kesme noktası ayarlamak `s="Add BreakPoint Here"`.  
  
3.  Aşağıdakileri yazın **hemen** penceresi: `?MyFunction<enter>`  
  
4.  Kesme noktalarına isabet ettirilmedi ve çağrı yığını doğru olduğunu doğrulayın.  
  
5.  Üzerinde **hata ayıklama** menüsünde tıklatın **devam**, yine de tasarım modunda olduğunu doğrulayın.  
  
6.  Aşağıdakileri yazın **hemen** penceresi: `?MyFunction<enter>`  
  
7.  Aşağıdakileri yazın **hemen** penceresi: `?MySub<enter>`  
  
8.  Kesme noktasına isabet ve statik değişkenin değerini inceleyin doğrulayın `i` içinde **Yereller** penceresi. Bu değeri 3 olmalıdır.  
  
9. Çağrı yığınını doğru olduğundan emin olun.  
  
10. Üzerinde **hata ayıklama** menüsünde tıklatın **devam**, yine de tasarım modunda olduğunu doğrulayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)   
 [Hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md)



