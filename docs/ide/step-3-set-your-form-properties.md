---
title: '3. adım: form özelliklerinizi ayarlama'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 634ef037-1525-48c8-ac7f-abf04be69376
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3005dfc81de43aa6c31f38d1985b10f3ed62c816
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="step-3-set-your-form-properties"></a>3. adım: form özelliklerinizi ayarlama
Ardından, kullandığınız **özellikleri** formun görünüşünü değiştirme penceresi.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 1 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205209) veya [Öğreticisi 1: Resim Görüntüleyici C# ' - oluşturma Video 1](http://go.microsoft.com/fwlink/?LinkId=205199). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
## <a name="to-set-your-form-properties"></a>Form özelliklerinizi ayarlamak için  
  
1.  Konumundaki arayan emin olun **Windows Form Tasarımcısı**. Visual Studio tümleşik geliştirme ortamında (IDE) seçin **Form1.cs [Design]** sekmesinde (veya **Form1.vb [tasarım]** sekmesini Visual Basic'te).  
  
2.  Herhangi bir yere formun içine seçin **Form1** seçin. Bakmak **özellikleri** formun özelliklerini gösteren şimdi penceresi. Forms çeşitli özelliklere sahiptir. Örneğin, ön plan ve arka plan rengi, görünen başlık metni ayarlayabileceğiniz formun üstünde, form ve diğer özellikleri boyutunu.  

    > [!NOTE]
    >  Varsa **özellikleri** penceresi görünmüyor, kare seçerek, programı durdurmak **durdurma hata ayıklama** araç çubuğunda düğmesini veya pencereyi kapatmanız yeterlidir. Program durdurulur ve hala görmüyorum **özellikleri** menü çubuğunda, pencere **Görünüm** > **Özellikler penceresini**.  
  
3.  Formun seçtikten sonra bulma **metin** özelliğinde **özellikleri** penceresi. Listenin nasıl sıralanacağını bağlı olarak, aşağı kaydırmanız gerekebilir. Seçin **metin**, türü **resim görüntüleyici**ve ardından **Enter**.  Formunuz şimdi metin olmalıdır **resim görüntüleyici** kendi başlık çubuğunda ve **özellikleri** penceresi aşağıdaki resme benzer görünmelidir.  
  
     ![Özellikler penceresi](../ide/media/express_edittextproperty.png "Express_EditTextProperty")  
**Özellikler** penceresi  
  
    > [!NOTE]
    >  Özellikler göre sıralayarak bir **kategoriler** veya **alfabetik** görünümü. Düğmeleri kullanarak bu iki görünüm arasında geçiş yapabilirsiniz **özellikleri** penceresi. Bu öğreticide, özelliklerinden daha kolay **alfabetik** görünümü.  
  
4.  Geri dönerek **Windows Form Tasarımcısı**. Formun alt sağ küçük beyaz kare ve aşağıdaki gibi görünür formun sağ alt sürükleme tutamacı seçin.  
  
     ![Sürükleme tutamacı](../ide/media/express_bottomrt_drag.png "Express_BottomRT_Drag")  
tutamacını sürükleyin  

     Form formun daha geniş ve biraz daha uzun olacak şekilde yeniden boyutlandırmak için tutamacını sürükleyin.  
  
5.  Bakmak **özellikleri** penceresinde ve dikkat **boyutu** özelliği değişti. **Boyutu** özellik değişiklikleri her zaman formun yeniden boyutlandırma. Bir form boyutuna yaklaşık yeniden boyutlandırmak için formun tutamacı sürüklemeyi deneyin **550, 350** (tam olması gerekmez), bu proje için de çalışmalıdır. Alternatif olarak, doğrudan değerler girebilirsiniz **boyutu** özelliği ve ardından **Enter** anahtarı.  
  
6.  Programı yeniden çalıştırın. Unutmayın, programınızı çalıştırmak için aşağıdaki yöntemlerden herhangi birini kullanabilirsiniz.  

    -   Seçin **F5** anahtarı.  
  
    -   Menü çubuğunda seçin **hata ayıklama** > **hata ayıklamayı Başlat**.  
  
    -   Araç çubuğunda seçin **hata ayıklamayı Başlat** aşağıdaki gibi görünür düğmesi.  

         ![Araç çubuğu düğmesi hata ayıklamayı Başlat](../ide/media/express_icondebug.png "Express_IconDebug")  
**Hata ayıklama Başlat** araç çubuğu düğmesi  
  
     Gibi daha önce IDE oluşturur ve programınızı çalıştırır ve bir pencere görüntülenir.  

7.  Sonraki adıma geçmeden önce programı durdurmak, IDE izin vermeyeceğinden çalışırken programınızı değiştirin. Unutmayın, programı durdurmak için aşağıdaki yöntemlerden herhangi birini kullanabilirsiniz.  

    -   Araç çubuğunda seçin **durdurma hata ayıklama** düğmesi.  
  
    -   Menü çubuğunda seçin **hata ayıklama** > **durdurma hata ayıklama**.  
  
    -   Seçin **X** üst köşesindeki düğmesini **Form1** penceresi.  
  
## <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [4. adım: bir TableLayoutPanel denetimi ile formunuzu düzenleme](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [2. adım: programınızı çalıştırma](../ide/step-2-run-your-program.md).
