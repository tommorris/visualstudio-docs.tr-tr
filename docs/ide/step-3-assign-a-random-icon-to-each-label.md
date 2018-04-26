---
title: '3. Adım: Her Etikete Rasgele Simge Atama'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 0ba5ed7a-9aaa-41f4-95d2-e3c2d567bc79
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 293548d1fcb1e06391d052aefa64b19065ba1372
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="step-3-assign-a-random-icon-to-each-label"></a>3. Adım: Her Etikete Rasgele Simge Atama
Simgeler her oyunda aynı hücrelerde gösterilirse, oyun pek de zorlu olmaz. Bu durumu önlemek için simgeler rastgele formunuzda etiket denetimleri kullanarak atamak bir `AssignIconsToSquares()` yöntemi.  

### <a name="to-assign-a-random-icon-to-each-label"></a>Her etikete rasgele bir simge atamak için  

1.  Aşağıdaki kodu eklemeden önce yöntemin nasıl çalıştığını düşünün. Yeni bir anahtar sözcük vardır: `foreach` Visual C# ve `For Each` Visual Basic'te. (Satırlardan biri bilerek derleme dışı bırakılmıştır; bunun nedeni bu yordamın sonunda açıklanmaktadır.)  

     [!code-csharp[VbExpressTutorial4Step2_3_4#2](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_1.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#2](../ide/codesnippet/VisualBasic/step-3-assign-a-random-icon-to-each-label_1.vb)]  

2.  Ekleme `AssignIconsToSquares()` önceki adımda gösterildiği gibi yöntemi. Yalnızca eklediğiniz kod aşağıda put [2. adım: rasgele nesne ve, bir liste simgeler ekleme](../ide/step-2-add-a-random-object-and-a-list-of-icons.md).  

     Daha önce belirtildiği gibi bazı sorunlar var. yeni, `AssignIconsToSquares()` yöntemi: bir `foreach` döngü Visual C# ve `For Each` Visual Basic'te. Kullanabileceğiniz bir `For Each` döngü birden çok kez aynı işlemi yapmak için istediğiniz zaman. Bu durumda, aşağıdaki kod ile açıklandığı gibi, TableLayoutPanel denetiminizdeki her öğe için aynı deyimleri yürütmek istiyorsunuz. İlk satırı adlı bir değişken oluşturur `control` , her denetim birer birer sırasında denetim üzerinde yürütülen Döngüdeki deyimleri olduğunu depolar.  

     [!code-csharp[VbExpressTutorial4Step2_3_4#14](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_2.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#14](../ide/codesnippet/VisualBasic/step-3-assign-a-random-icon-to-each-label_2.vb)]  

    > [!NOTE]
    >  "iconLabel" (simge etiketi) ve "control" (denetim) kullanılmasının nedeni bu adların açıklayıcı olmasıdır. Bu adların yerine istediğiniz adları kullanabilirsiniz; ilgili adı döngüdeki her bir deyimde de değiştirdiğiniz sürece kod tamamen aynı şekilde çalışacaktır.  

     `AssignIconsToSquares()` Yöntemi her etiket TableLayoutPanel denetiminde dolaşır ve bunların her biri için aynı ifadeleri çalıştırır. Bu deyimler eklediğiniz listeden rasgele simge çekme [2. adım: rasgele nesne ve, bir liste simgeler ekleme](../ide/step-2-add-a-random-object-and-a-list-of-icons.md). (Listeye her simgeden iki tane eklemenizin nedeni budur; böylece rasgele etiket denetimlerine atanmış bir çift simge olur.)  

     Bakabilir daha yakından içinde çalışan bir kod `foreach` veya `For Each` döngü. Bu kod burada tekrar üretilmektedir.  

     [!code-csharp[VbExpressTutorial4Step2_3_4#16](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_3.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#16](../ide/codesnippet/VisualBasic/step-3-assign-a-random-icon-to-each-label_3.vb)]  

     İlk satırı dönüştürür `control` adlı bir etiket için değişken `iconLabel`. Bu sonraki satır bir `if` dönüştürme emin olmak için denetler deyimi çalışmıştır. Dönüştürme çalışıyorsanız, deyimleri `if` deyimini çalıştırın. (Önceki öğreticileri Hatırlayacağınız `if` deyimi belirttiğiniz ne olursa olsun bir koşulu değerlendirmek için kullanılır.) İlk satırı `if` deyimi adlı bir değişken oluşturur `randomNumber` simgeleri listedeki öğeler birine karşılık gelen rastgele bir sayıyı içerir. Bunu yapmak için onu kullanır `Next` yöntemi `Random` daha önce oluşturduğunuz nesne. `Next` Yöntemi rastgele bir sayıyı döndürür. Bu satırı de kullanır `Count` özelliği `icons` listesi rastgele sayı seçmek üzere aralığını belirler. Sonraki satıra simgesi birini liste öğelerine atar `Text` etiket özelliği. Derleme dışı bırakılan satır bu konunun sonunda açıklanmaktadır. Son olarak, son satırında `if` deyimi forma eklenen simgesi listeden kaldırır.  

     Kodun belirli bir bölümünün ne işe yaradığından emin olamadığınızda, fare işaretçisini kod öğesinin üzerine getirip ortaya çıkan araç ipucunu gözden geçirebileceğinizi unutmayın. Ayrıca, Visual Studio hata ayıklayıcısını kullanarak, program çalışırken kodun her satırını adım adım geçebilirsiniz. Bkz: [nasıl yapmak I: adımıyla Visual Studio hata ayıklayıcısı?](http://msdn.microsoft.com/vstudio/ee672313.aspx) veya [hata ayıklayıcısı ile kodlarda gezinme](../debugger/navigating-through-code-with-the-debugger.md) daha fazla bilgi için.  

3.  Oyun tahtası simgelerle doldurmak için çağırması gerekir `AssignIconsToSquares()` program başlar başlamaz yöntemi. Visual C# kullanıyorsanız çağrısı hemen altındaki bir deyim ekleyin `InitializeComponent()` yönteminde `Form1` *Oluşturucusu*, formunuz, gösterilen önce kendisini ayarlamak için yeni yöntemini çağırır. Oluşturucular, sınıf veya yapı gibi yeni bir nesne oluşturduğunuzda çağrılır. Bkz: [oluşturucular (C# programlama Kılavuzu)](http://msdn.microsoft.com/library/ace5hbzh.aspx) veya [kullanarak Kurucular ve Yıkıcılar](http://msdn.microsoft.com/library/2z08e49e.aspx) daha fazla bilgi için Visual Basic'te.  

     [!code-csharp[VbExpressTutorial4Step2_3_4#13](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_4.cs)]  

     Visual Basic for eklemek `AssignIconsToSquares()` yöntemi çağrısına `Form1_Load` yöntemi böylece kodu aşağıdaki gibi görünür.  

    ```vb  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AssignIconsToSquares()  
    End Sub  
    ```  

4.  Programınızı kaydedip çalıştırın. Her etikete rasgele simgelerin atandığı bir form gösterilmesi gerekir.  

5.  Programınızı kapatın ve yeniden çalıştırın. Aşağıdaki resimde gösterildiği gibi, her etikete farklı simgeler atandığına dikkat edin.  

     ![Oyun rasgele simge ile eşleşen](../ide/media/express_tut4step3.png "Express_Tut4Step3")  
Rasgele simgeleri içeren eşleştirme oyunu  

     Henüz gizlemediğiniz için simgeler şimdilik görünmektedir. Player'gizlemek için her etiketin ayarlayabilirsiniz `Forecolor` aynı renkte özelliğine kendi `BackColor` özelliği.  

    > [!TIP]
    >  Etiketler gibi denetimlerini gizlemek için başka bir şekilde ayarlamaktır kendi **görünür** özelliğine `False`.  

6.  Simgeleri gizlemek için program ve yorum işaretler içinde kod açıklamalı satırı Kaldır Durdur `For Each` döngü.  

     [!code-csharp[VbExpressTutorial4Step2_3_4#15](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_5.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#15](../ide/codesnippet/VisualBasic/step-3-assign-a-random-icon-to-each-label_5.vb)]  

7.  Menü çubuğunda seçin **Tümünü Kaydet** programınızı kaydetmek için düğmesine tıklayın ve ardından çalıştırın. Simgelerin kaybolduğu görülür ve yalnızca mavi bir arka plan görüntülenir. Bununla birlikte simgeler rasgele atanırlar ve halen oradadırlar. Simgeler arka plan ile aynı renkte olduğundan, oyuncudan gizlenmiş olurlar. Sonuçta, oyuncu simgelerin tümünü doğrudan görebilseydi hiç de zorlayıcı bir oyun olmazdı!  

### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  

-   Öğretici bir sonraki adıma dönmek için bkz: [4. adım: her etikete bir tıklatın olay işleyicisi ekleyin](../ide/step-4-add-a-click-event-handler-to-each-label.md).  

-   Eğitmen önceki adıma dönmek için bkz: [2. adım: rasgele nesne ve, bir liste simgeler ekleme](../ide/step-2-add-a-random-object-and-a-list-of-icons.md).
