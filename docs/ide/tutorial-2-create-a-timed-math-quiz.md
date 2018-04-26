---
title: 'Eğitmen 2: Zamanlı Matematik Testi Oluşturma'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: d7165d08-ace3-457d-b57d-fb8f80760a6f
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 55142712972ce5d5fd44e76dbad042daca18edc6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="tutorial-2-create-a-timed-math-quiz"></a>Eğitmen 2: Zamanlı Matematik Testi Oluşturma
Bu öğreticide, test alanın belirtilen süre içinde dört rastgele aritmetik sorunları yanıtlamalısınız testi oluşturun. Aşağıdakilerin nasıl yapıldığını öğreneceksiniz:  

-   Kullanarak rastgele sayılar oluşturma `Random` sınıfı.  

-   Tetiklemek kullanarak belirli bir zamanda oluşacak şekilde olayları bir **Zamanlayıcı** denetim.  

-   Program akışı kullanarak denetim `if else` deyimleri.  

-   Temel aritmetik işlemler kodda gerçekleştirin.  

 İşiniz bittiğinde, test aşağıdaki resimde gibi dışında farklı numaralarıyla arar.  

 ![Matematik testi dört sorunlarıyla](../ide/media/express_finishedquiz.png "Express_FinishedQuiz")  
Bu öğreticide oluşturduğunuz test  

 Test tamamlanmış bir sürümünü indirmek için bkz: [tam matematik testi öğretici örnek](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).  

> [!NOTE]
>  Bu öğretici hem Visual C# ve Visual Basic kapsar, kullanmakta olduğunuz programlama diline özgü bilgileri böylece odaklanır.  

## <a name="related-topics"></a>İlgili Konular  

|Başlık|Açıklama|  
|-----------|-----------------|  
|[1. Adım: Proje Oluşturma ve Formunuza Etiketler Ekleme](../ide/step-1-create-a-project-and-add-labels-to-your-form.md)|Başlangıç projesi oluşturma özelliklerini değiştirme ve ekleme `Label` kontrol eder.|  
|[2. Adım: Rasgele bir Toplama Problemi Oluşturma](../ide/step-2-create-a-random-addition-problem.md)|Bir toplama problemi oluşturma ve kullanma `Random` rastgele sayılar oluşturmak için sınıfı.|  
|[3. Adım: Geri Sayım Zamanlayıcısı Ekleme](../ide/step-3-add-a-countdown-timer.md)|Test zaman aşımına geri sayım Zamanlayıcısı ekleyin.|  
|[4. Adım: CheckTheAnswer() Yöntemi Ekleme](../ide/step-4-add-the-checktheanswer-parens-method.md)|Test alanın sorun için doğru yanıt girilen olup olmadığını denetlemek için bir yöntem ekleyin.|  
|[5. Adım: NumericUpDown Denetimleri için Giriş Olay İşleyicileri Ekleme](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md)|Olabilmesi, test kolaylaştırmak olay işleyicileri ekleyin.|  
|[6. Adım: Çıkarma Problemi Ekleme](../ide/step-6-add-a-subtraction-problem.md)|Rastgele sayılar oluşturur, Zamanlayıcı kullanır ve doğru yanıtlar için denetler çıkarma problemi ekleme.|  
|[7. Adım: Çarpma ve Bölme Problemleri Ekleme](../ide/step-7-add-multiplication-and-division-problems.md)|Rastgele sayılar oluşturma, Zamanlayıcı kullanan ve doğru yanıtlar için denetleme çarpma ve bölme sorunları ekleyin.|  
|[8. Adım: Testi Özelleştirme](../ide/step-8-customize-the-quiz.md)|Sıralamayı değiştirme ve ipucu ekleme gibi diğer özellikleri deneyin.|
