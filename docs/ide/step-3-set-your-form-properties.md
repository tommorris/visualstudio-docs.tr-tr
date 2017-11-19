---
title: "3. adım: Form özelliklerinizi ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 634ef037-1525-48c8-ac7f-abf04be69376
caps.latest.revision: "18"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: d83a19e04a2e795005f2e0cdf0fdfe3a30c22c87
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="step-3-set-your-form-properties"></a>3. Adım: Form Özelliklerinizi Ayarlama
Ardından, kullandığınız **özellikleri** formun görünüşünü değiştirme penceresi.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 1 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205209) veya [Eğitmen 1: bir resim görüntüleyici oluşturma C# - Video 1](http://go.microsoft.com/fwlink/?LinkId=205199). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
### <a name="to-set-your-form-properties"></a>Form özelliklerinizi ayarlamak için  
  
1.  Windows Form Tasarımcısı baktığınızdan emin olun. Visual Studio tümleşik geliştirme ortamında (IDE) seçin **Form1.cs [Design]** sekmesinde (veya **Form1.vb [tasarım]** sekmesini Visual Basic'te).  
  
2.  Herhangi bir yere formun içine seçin **Form1** seçin. Bakmak **özellikleri** formun özelliklerini gösteren şimdi penceresi. Forms çeşitli özelliklere sahiptir. Örneğin, ön plan ve arka plan rengi, görünen başlık metni ayarlayabileceğiniz formun üstünde, form ve diğer özellikleri boyutunu.  
  
    > [!NOTE]
    >  Varsa **özellikleri** penceresi görünmüyor, kare seçerek, programı durdurmak **durdurma hata ayıklama** araç çubuğunda düğmesini veya pencereyi kapatmanız yeterlidir. Program durdurulur ve hala görmüyorum **özellikleri** menü çubuğunda, pencere **Görünüm**, **Özellikler penceresini**.  
  
3.  Formun seçtikten sonra bulma **metin** özelliğinde **özellikleri** penceresi. Listenin nasıl sıralanacağını bağlı olarak, aşağı kaydırmanız gerekebilir. Seçin **metin**, türü **resim görüntüleyici**ve ardından ENTER'i seçin.  Formunuz şimdi metin olmalıdır **resim görüntüleyici** kendi başlık çubuğunda ve **özellikleri** penceresi aşağıdaki resme benzer görünmelidir.  
  
     ![Özellikler penceresi](../ide/media/express_edittextproperty.png "Express_EditTextProperty")  
Özellik penceresi  
  
    > [!NOTE]
    >  Özellikler, kategoriler veya alfabetik görünüm tarafından sıralanabilir. Düğmeleri kullanarak bu iki görünüm arasında geçiş yapabilirsiniz **özellikleri** penceresi. Bu öğreticide, alfabetik görünümü aracılığıyla özellikleri bulmak daha kolay olur.  
  
4.  Windows Forms Tasarımcısı için geri dönün. Formun alt sağ küçük beyaz kare ve aşağıdaki gibi görünür formun sağ alt sürükleme tutamacı seçin.  
  
     ![Sürükleme tutamacı](../ide/media/express_bottomrt_drag.png "Express_BottomRT_Drag")  
tutamacını sürükleyin  
  
     Form formun daha geniş ve biraz daha uzun olacak şekilde yeniden boyutlandırmak için tutamacını sürükleyin.  
  
5.  Bakmak **özellikleri** penceresinde ve dikkat **boyutu** özelliği değişti. **Boyutu** özellik değişiklikleri her zaman formun yeniden boyutlandırma. Yaklaşık 550, bir form boyuta yeniden boyutlandırmak için formun tutamacı sürüklemeyi deneyin 350 (tam olması gerekmez), bu proje için de çalışmalıdır. Alternatif olarak, doğrudan değerler girebilirsiniz **boyutu** özelliği ve ardından ENTER tuşuna seçin.  
  
6.  Programı yeniden çalıştırın. Unutmayın, programınızı çalıştırmak için aşağıdaki yöntemlerden herhangi birini kullanabilirsiniz.  
  
    -   Seçin **F5** anahtarı.  
  
    -   Menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
    -   Araç çubuğunda seçin **hata ayıklamayı Başlat** aşağıdaki gibi görünür düğmesi.  
  
         ![Araç çubuğu düğmesi hata ayıklamayı Başlat](../ide/media/express_icondebug.png "Express_IconDebug")  
Hata ayıklama araç çubuğu düğmesi Başlat  
  
     Gibi daha önce IDE oluşturur ve programınızı çalıştırır ve bir pencere görüntülenir.  
  
7.  Sonraki adıma geçmeden önce programı durdurmak, IDE izin vermeyeceğinden çalışırken programınızı değiştirin. Unutmayın, programı durdurmak için aşağıdaki yöntemlerden herhangi birini kullanabilirsiniz.  
  
    -   Araç çubuğunda seçin **durdurma hata ayıklama** düğmesi.  
  
    -   Menü çubuğunda seçin **hata ayıklama**, **durdurma hata ayıklama**.  
  
    -   Üst köşesinde X düğmesini seçin **Form1** penceresi.  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [4. adım: düzenleme çıkışı bilgisayarınızı Form TableLayoutPanel denetimi ile](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [2. adım: bilgisayarınızı Program Çalıştır](../ide/step-2-run-your-program.md).