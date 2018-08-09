---
title: 'Eğitmen 2: zamanlı matematik testi oluşturma'
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
ms.openlocfilehash: b28afd645351577073eb7525cf4bed321afb09c0
ms.sourcegitcommit: 96a6d1f16d06ca28d309d05b6e9fbd52f628cdbc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40008401"
---
# <a name="tutorial-2-create-a-timed-math-quiz"></a>Eğitmen 2: zamanlı matematik testi oluşturma

Bu öğreticide, sınava giren belirli bir süre içinde dört rastgele aritmetik sorusuna yanıtlamalısınız bir test oluşturun. Aşağıdakilerin nasıl yapıldığını öğreneceksiniz:

-   Kullanarak rastgele sayılar üretin <xref:System.Random> sınıfı.

-   Kullanarak belirli bir zamanda oluşacak olayları tetikleme bir <xref:System.Windows.Forms.Timer> denetimi.

-   Kullanarak program akışını denetleme `if else` deyimleri.

-   Kodda temel aritmetik işlemleri gerçekleştirin.

İşiniz bittiğinde, sınav aşağıdaki resim gibi dışında sayıların farklı görünecektir:

![Dört Sorulu matematik sınavı](../ide/media/express_finishedquiz.png)

## <a name="tutorial-links"></a>Öğretici bağlantıları

Sınavın tamamlanmış bir sürümünü indirmek için bkz [tam matematik sınavı öğretici örneği](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).

> [!NOTE]
> Bu öğreticide hem Visual C# ve Visual Basic ele alınmaktadır; bu nedenle kullandığınız programlama diline özgü bilgilere odaklanın.

## <a name="related-topics"></a>İlgili konular

|Başlık|Açıklama|
|-----------|-----------------|
|[1. adım: Proje oluşturma ve formunuza etiketler ekleme](../ide/step-1-create-a-project-and-add-labels-to-your-form.md)|Başlangıç projesi oluşturma özelliklerini değiştirme ve ekleme `Label` kontrol eder.|
|[2. adım: rasgele bir toplama problemi oluşturma](../ide/step-2-create-a-random-addition-problem.md)|Bir toplama problemi oluşturma ve kullanma `Random` sınıfını kullanarak rastgele sayılar üretin.|
|[3. adım: geri sayım Zamanlayıcısı ekleme](../ide/step-3-add-a-countdown-timer.md)|Sınav zamanlanabilir geri sayım Zamanlayıcısı ekleyin.|
|[4. adım: CheckTheAnswer() yöntemi ekleme](../ide/step-4-add-the-checktheanswer-parens-method.md)|Sınava sorun için doğru yanıtı girilen olup olmadığını denetlemek için bir yöntem ekleyin.|
|[5. adım: NumericUpDown denetimleri için Enter olay işleyicileri ekleme](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md)|Sınav olması daha kolay hale getirmek olay işleyicileri ekleyin.|
|[6. adım: çıkarma problemi ekleme](../ide/step-6-add-a-subtraction-problem.md)|Rastgele sayılar üreten, Zamanlayıcı kullanan ve doğru yanıtları denetleyen bir çıkarma sorusu ekleyin.|
|[7. adım: çarpma ve bölme sorunları ekleme](../ide/step-7-add-multiplication-and-division-problems.md)|Rastgele sayılar üretin, Zamanlayıcı kullanan ve doğru yanıtları denetleyen çarpma ve bölme soruları ekleyin.|
|[8. adım: testi özelleştirme](../ide/step-8-customize-the-quiz.md)|Renkleri değiştirme ve ipucu ekleme gibi diğer özellikleri deneyin.|
