---
title: '1. adım: bir Windows Forms uygulaması projesi oluşturma'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 16ac2422-e720-4e3a-b511-bc2a54201a86
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 133166ad19b438f3da43f9c3b600c6cb67ce4827
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="step-1-create-a-windows-forms-application-project"></a>1. adım: bir Windows Forms uygulaması projesi oluşturma
Bir resim görüntüleyici oluşturduğunuzda, ilk adım bir Windows Forms uygulaması projesi oluşturmaktır.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 1 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205209) veya [Öğreticisi 1: Resim Görüntüleyici C# ' - oluşturma Video 1](http://go.microsoft.com/fwlink/?LinkId=205199). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
## <a name="to-create-a-windows-forms-application-project"></a>Bir Windows Forms uygulaması projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya** > **yeni** > **proje**. İletişim kutusu aşağıdaki gibi görünmelidir.  
  
     ![Yeni Proje iletişim kutusu](../ide/media/newprojectdialogcallouts.png "NewProjectDialogCallouts")  
**Yeni proje** iletişim kutusu  
  
2.  Ya da seçin **Visual C#** veya **Visual Basic** içinde **yüklü şablonlar** listesi.  

3.  Şablonları listesinden seçin **Windows Forms uygulaması** simgesi. Yeni formun adı **PictureViewer**ve ardından **Tamam** düğmesi.  

     Visual Studio, program için bir çözüm oluşturur. Bir çözüm, tüm projeleri ve programınız tarafından gerekli dosyalar için bir kapsayıcı görevi görür. Bu koşulları, bu öğreticinin ilerleyen bölümlerinde daha ayrıntılı olarak açıklanacaktır.  

4.  Aşağıdaki çizimde, ne Visual Studio arabiriminde görmelisiniz gösterir.  

    > [!NOTE]
    >  Pencere düzeninizi tam olarak bu çizim gibi görünmeyebilir. Tam pencere düzenini Visual Studio, kullanmakta olduğunuz programlama dili ve diğer etkenlere bağlı sürümüne bağlıdır. Ancak, tüm üç windows görünür olduğunu doğrulamanız gerekir.  

     ![IDE penceresi](../ide/media/express_ideoverview_visio.png "Express_IDEOverview_Visio")  
**IDE** penceresi  
  
     Üç windows arabirimi içerir: ana penceresinde, **Çözüm Gezgini**ve **özellikleri** penceresi.  
  
     Bu windows eksik olan çubuğu, seçme menüsünde, varsayılan pencere düzenini geri **penceresi** > **pencere düzenini Sıfırla**. Windows menü komutlarını kullanarak da görüntüleyebilirsiniz. Menü çubuğunda seçin **Görünüm** > **Özellikler penceresini** veya **Çözüm Gezgini**. Diğer windows açıksa, bunları seçerek kapatın **kapatmak** (x), sağ üst köşesinde düğmesini.  
  
5.  Çizim (sol üst köşeden yönünde gitme) aşağıdaki windows göstermektedir:  
  
    -   **Ana penceresi** Bu pencerede, formları ile çalışma ve kod düzenleme gibi çalışmanızı çoğunu gerçekleştirirsiniz. Çizimde, bir formda pencereyi gösterir **Form Düzenleyicisi**. Pencerenin üstündeki **başlangıç sayfası** sekmesi ve **Form1.cs [Design]** sekmesinde görünür. (Visual Basic'te sekme adı ile biter. *.vb* yerine *.cs*.)  
  
    -   **Çözüm Gezgini penceresi** Bu pencerede, görüntülemek ve çözümünüzdeki tüm öğelerine gidin. Bir dosya içeriğini seçerseniz **özellikleri** penceresi değişiklikleri. Bir kod dosyası açarsanız (sona erdiği içinde *.cs* Visual C# ve *.vb* Visual Basic'te), kod dosyası veya kod dosyası için bir tasarımcı görüntülenir. Bir Tasarımcısı düğmeleri ve listeler gibi denetimleri ekleyebilirsiniz visual yüzey olur. Visual Studio formlar için tasarımcı adlı **Windows Form Tasarımcısı**.  
  
    -   **Özellikler penceresi** Bu pencerede, diğer windows seçtiğiniz öğelerinin özelliklerini değiştirebilirsiniz. Form1 seçerseniz, örneğin, başlığını ayarlayarak değiştirebileceğiniz **metin** özelliği ve değiştirebilir arka plan rengini ayarlayarak **Backcolor** özelliği.  
  
    > [!NOTE]
    >  Üst satır **Çözüm Gezgini** gösterir **çözüm 'PictureViewer' (1 proje)**, Visual Studio bir çözüm için oluşturduğunuz anlamına gelir. Bir çözüm birden çok proje içerebilir, ancak şu an için yalnızca bir projede çözümleriyle karşılaşmayacağınızı.  
  
6.  Menü çubuğunda seçin **dosya** > **Tümünü Kaydet**.  
  
     Alternatif olarak, seçin **Tümünü Kaydet** aşağıda gösterilmiştir araç çubuğunda.  

     ![Kaydet tüm araç çubuğu düğmesi](../ide/media/express_iconsaveall.png "Express_IconSaveAll")  
**Tümünü Kaydet** araç çubuğu düğmesi  
  
     Visual Studio klasör adı ve proje adı otomatik olarak doldurur ve sonra projeyi projeleri klasörünüzde kaydeder.  

## <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [2. adım: programınızı çalıştırma](../ide/step-2-run-your-program.md).  
  
-   Genel Bakış konuya geri dönmek için bkz: [Eğitmen 1: Resim Görüntüleyici oluşturma](../ide/tutorial-1-create-a-picture-viewer.md).
