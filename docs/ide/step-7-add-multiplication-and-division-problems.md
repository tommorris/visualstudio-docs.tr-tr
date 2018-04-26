---
title: '7. Adım: Çarpma ve Bölme Problemleri Ekleme'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: e638959e-f6a4-4eb4-b2e9-f63b7855cf8f
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dbeeca2e53addab923fa3f62c661543497ea1f35
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="step-7-add-multiplication-and-division-problems"></a>7. Adım: Çarpma ve Bölme Problemleri Ekleme
Bu öğreticinin yedinci bölümünde çarpma ve bölme sorunları eklemek ancak bu değişiklik hakkında düşünmeden. Değerlerini depolama içerir ilk adım, göz önünde bulundurun.  

### <a name="to-add-multiplication-and-division-problems"></a>Çarpma ve bölme sorunları eklemek için  

1.  Dört fazla tamsayı değişken forma ekleyin.  

     [!code-vb[VbExpressTutorial3Step7#15](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_1.vb)]
     [!code-csharp[VbExpressTutorial3Step7#15](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_1.cs)]  

2.  Daha önce yaptığınız gibi değiştirebilir `StartTheQuiz()` yöntemi çarpma ve bölme sorunlara yönelik rastgele sayılar doldurun.  

     [!code-vb[VbExpressTutorial3Step7#16](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_2.vb)]
     [!code-csharp[VbExpressTutorial3Step7#16](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_2.cs)]  

3.  Değiştirme `CheckTheAnswer()` , BT'nin ayrıca çarpma ve bölme sorunları denetler şekilde yöntemi.  

     [!code-vb[VbExpressTutorial3Step7#17](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_3.vb)]
     [!code-csharp[VbExpressTutorial3Step7#17](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_3.cs)]  

     Çarpma oturum (×) kolayca giremezsiniz ve bölme klavyeyi kullanarak oturum açma (÷), böylece Visual C# ve Visual Basic bir yıldız işareti (*) çarpma ve bölme bir eğik çizgi işareti (/) kabul edin.  

4.  Zamanlayıcı'nın onay olay işleyicisi son parçası süresi dolmadan zaman doğru yanıt olarak doldurur şekilde değiştirin.  

     [!code-vb[VbExpressTutorial3Step7#23](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_4.vb)]
     [!code-csharp[VbExpressTutorial3Step7#23](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_4.cs)]  

5.  Programınızı kaydedin ve çalıştırın.  

     Test tutmayı aşağıda gösterildiği gibi test tamamlamak için dört sorunlara yanıt vermeniz gerekir.  

     ![Matematik testi dört sorunlarıyla](../ide/media/express_finishedquiz.png "Express_FinishedQuiz")  
Dört sorunlarıyla matematik testi  

### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  

-   Öğretici bir sonraki adıma dönmek için bkz: [adım 8: testi özelleştirme](../ide/step-8-customize-the-quiz.md).  

-   Eğitmen önceki adıma dönmek için bkz: [6. adım: çıkarma problemi ekleme](../ide/step-6-add-a-subtraction-problem.md).
