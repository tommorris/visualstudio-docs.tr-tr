---
title: "11. adım: Programınızı çalıştırma ve diğer özellikleri deneme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
caps.latest.revision: "12"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c53c542741cc64c0d60a94116acf7de4ff7f61ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="step-11-run-your-program-and-try-other-features"></a>11. adım: Programınızı çalıştırma ve diğer özellikleri deneme
Programınızı tamamlandı ve çalıştırılmaya hazır. Programınızı çalıştırma ve PictureBox arka plan rengini ayarlayın. Daha fazla bilgi için program formun rengini değiştirmek, düğmeler ve onay kutusu özelleştirme ve form özelliklerini değiştirme artırmak için deneyin.  
  
 Tamamlanmış bir örnek sürümünü indirmek için bkz: [tam resim görüntüleyici öğretici örnek](http://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8).  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 5 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205216) veya [Eğitmen 1: bir resim görüntüleyici oluşturma C# - Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
### <a name="to-run-your-program-and-set-the-background-color"></a>Programınızı çalıştırma ve arka plan rengini ayarlamak için  
  
1.  F5 seçin veya menü çubuğunda seçin **hata ayıklama**, **hata ayıklamayı Başlat**.  
  
2.  Bir resim açmadan önce seçin **arka plan rengini ayarlama** düğmesi. **Renk** iletişim kutusu açılır.  
  
     ![Renk iletişim kutusu](../ide/media/express_colordialog.png "Express_ColorDialog")  
Renk iletişim kutusu  
  
3.  PictureBox arka plan rengini ayarlamak için renk seçin. Yakından bakmak `backgroundButton_Click()` nasıl çalıştığını anlamak için yöntem.  
  
    > [!NOTE]
    >  Kendi URL'ye yapıştırılarak Internet'ten resim yükleyebilir **Dosya Aç** iletişim kutusu. Arka plan rengini gösterecek şekilde saydam arka plan görüntüyle bulmaya çalışın.  
  
4.  Seçin **resmi temizleyin** düğmesi temizlenmeden emin olun. Ardından, seçerek programdan çıkmak **Kapat** düğmesi.  
  
### <a name="to-try-other-features"></a>Diğer özellikleri denemek için  
  
-   Form ve düğmeleri kullanarak rengini **BackColor** özelliği.  
  
-   Düğmeler ve onay kutusunu kullanarak özelleştirme **yazı tipi** ve **ForeColor** özellikleri.  
  
-   Formun değiştirme **FormBorderStyle** ve **ControlBox** özellikleri.  
  
-   Formun kullanmak **AcceptButton** ve **CancelButton** bu düğmeleri otomatik olarak seçilen şekilde olduğunda kullanıcı ENTER veya ESC tuşuna seçer özellikleri. Program açık olun **Dosya Aç** kullanıcı girin ve kullanıcının ESC seçtiğinde kutusunu kapatmak seçtiğinde iletişim kutusu.  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Visual Studio'da programlama hakkında daha fazla bilgi için bkz: [programlama kavramları](http://msdn.microsoft.com/Library/65c12cca-af4f-4017-886e-2dbc00a189d6).  
  
-   Visual Basic hakkında daha fazla bilgi için bkz: [Visual Basic ile uygulama geliştirme](/dotnet/visual-basic/developing-apps/index).  
  
-   Visual C# hakkında bilgi edinmek için bkz: [C# dili ve .NET Framework Giriş](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework).  
  
-   Sonraki öğretici gitmek için bkz: [Eğitmen 2: bir zaman aşımına matematik test oluşturma](../ide/tutorial-2-create-a-timed-math-quiz.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [adım 10: ek düğmeler ve onay kutusu için kod yazma](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).