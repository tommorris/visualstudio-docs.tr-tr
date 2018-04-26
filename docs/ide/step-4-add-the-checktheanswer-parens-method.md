---
title: '4. adım: CheckTheAnswer() yöntemleri ekleme'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: c66f3831-b4a0-40bc-a109-8f46f4db35ed
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d5fa5cdbd526eaa5ab84baf903f352697f9e01a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="step-4-add-the-checktheanswer-method"></a>4. Adım: CheckTheAnswer() Yöntemi Ekleme
Bu öğreticinin dördüncü bölümünde bir yöntem yazacaksınız `CheckTheAnswer()`, matematik sorunlara yanıtlar doğru olup olmadığını belirler. Bu konuda bir öğretici serisi kodlama temel kavramları hakkında bir parçasıdır. Öğretici genel bakış için bkz: [Eğitmen 2: bir zaman aşımına matematik test oluşturma](../ide/tutorial-2-create-a-timed-math-quiz.md).  

> [!NOTE]
>  Visual Basic'te aşağıdaki varsa, kullanacağınız `Function` anahtar sözcüğü her zamanki yerine `Sub` anahtar sözcüğü çünkü bu yöntemi bir değer döndürür. Gerçekten bu basit bir işlemdir: bir alt bir değer döndürmüyor ancak bir işlev desteklemez.  

### <a name="to-verify-whether-the-answers-are-correct"></a>Yanıtlar doğru olup olmadığını doğrulamak için  

1.  Ekleme `CheckTheAnswer()` yöntemi.  

     Bu yöntem çağrıldığında, addend1 ve addend2 değerlerini ekler ve toplam değeri sonucu karşılaştırır `NumericUpDown` denetim. Değerlerin eşit olup olmadığını yöntemi değerini döndürür. `true`. Aksi takdirde, yöntemi bir değeri döndürür `false`. Kodunuzu aşağıdaki gibi görünmelidir.  

     [!code-vb[VbExpressTutorial3Step4#8](../ide/codesnippet/VisualBasic/step-4-add-the-checktheanswer-parens-method_1.vb)]
     [!code-csharp[VbExpressTutorial3Step4#8](../ide/codesnippet/CSharp/step-4-add-the-checktheanswer-parens-method_1.cs)]  

     Ardından, yöntem yeni çağrı için Zamanlayıcı'nın onay olay işleyicisi için kod güncelleştirerek yanıt kontrol edeceğiz `CheckTheAnswer()` yöntemi.  

2.  Aşağıdaki kodu ekleyin `if else` deyimi.  

     [!code-vb[VbExpressTutorial3Step4#10](../ide/codesnippet/VisualBasic/step-4-add-the-checktheanswer-parens-method_2.vb)]
     [!code-csharp[VbExpressTutorial3Step4#10](../ide/codesnippet/CSharp/step-4-add-the-checktheanswer-parens-method_2.cs)]  

     Yanıt doğruysa, `CheckTheAnswer()` döndürür `true`. Olay işleyicisi Zamanlayıcı durdurur, eklenen kutlama iletisi gösterir ve sonra yapar **Başlat** yeniden kullanılabilir düğmesine tıklayın. Aksi takdirde, test devam eder.  

3.  Programınızı kaydetmek, çalıştırmak, bir test başlatmak ve toplama problemi doğru bir yanıt sağlar.  

    > [!NOTE]
    >  Yanıtınız girdiğinizde, varsayılan değer yanıtınızı girmek için başlatın ya da sıfır el ile silmeniz gerekir önce ya da seçmeniz gerekir. Bu davranış daha sonra Bu öğreticide düzeltmeniz.  

     Doğru yanıt sağladığınızda, bir ileti kutusu açılır ve **Başlat** düğmesi kullanılabilir olur ve Zamanlayıcı durdurur.  

### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  

-   Öğretici bir sonraki adıma dönmek için bkz: [5. adım: ekleme girin olay işleyicileri NumericUpDown denetimleri için](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md).  

-   Eğitmen önceki adıma dönmek için bkz: [3. adım: geri sayım Zamanlayıcısı ekleme](../ide/step-3-add-a-countdown-timer.md).
