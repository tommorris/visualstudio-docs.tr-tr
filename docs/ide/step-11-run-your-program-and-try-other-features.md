---
title: '11. adım: programınızı çalıştırma ve diğer özellikleri deneme'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: feee6c95852e90fef5f3fcacf47dfb67d48255b7
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747648"
---
# <a name="step-11-run-your-program-and-try-other-features"></a>11. adım: programınızı çalıştırma ve diğer özellikleri deneme
Programınızı tamamlandı ve çalıştırılmaya hazır. Programınızı çalıştırma ve arka plan rengini ayarlama <xref:System.Windows.Forms.PictureBox>. Daha fazla bilgi için program formun rengini değiştirmek, düğmeler ve onay kutusu özelleştirme ve form özelliklerini değiştirme artırmak için deneyin.

 Tamamlanmış bir örnek sürümünü indirmek için bkz: [tam resim görüntüleyici öğretici örnek](http://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8).

 ![video bağlantı](../data-tools/media/playvideo.gif)bu konuda video sürümü için bkz: [Öğreticisi 1: Visual Basic'te - Video 5 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205216) veya [Eğitmen 1: Resim Görüntüleyici C# ' - Video 5 oluşturma](http://go.microsoft.com/fwlink/?LinkId=205206). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.

## <a name="to-run-your-program-and-set-the-background-color"></a>Programınızı çalıştırma ve arka plan rengini ayarlamak için

1.  Seçin **F5**, veya menü çubuğunda seçin **hata ayıklama** > **hata ayıklamayı Başlat**.

2.  Bir resim açmadan önce seçin **arka plan rengini ayarlama** düğmesi. **Renk** iletişim kutusu açılır.

     ![Renk iletişim kutusu](../ide/media/express_colordialog.png)
**renk** iletişim kutusu

3.  PictureBox arka plan rengini ayarlamak için renk seçin. Yakından bakmak `backgroundButton_Click()` nasıl çalıştığını anlamak için yöntem.

    > [!NOTE]
    >  Kendi URL'ye yapıştırılarak Internet'ten resim yükleyebilir **Dosya Aç** iletişim kutusu. Arka plan rengini gösterecek şekilde saydam arka plan görüntüyle bulmaya çalışın.

4.  Seçin **resmi temizleyin** düğmesi temizlenmeden emin olun. Ardından, seçerek programdan çıkmak **Kapat** düğmesi.

## <a name="to-try-other-features"></a>Diğer özellikleri denemek için

-   Form ve düğmeleri kullanarak rengini **BackColor** özelliği.

-   Düğmeler ve onay kutusunu kullanarak özelleştirme **yazı tipi** ve **ForeColor** özellikleri.

-   Formun değiştirme **FormBorderStyle** ve **ControlBox** özellikleri.

-   Formun kullanmak **AcceptButton** ve **CancelButton** bu düğmeleri otomatik olarak seçilen şekilde zaman kullanıcının seçtiği özellikleri **Enter** veya **Esc** anahtarı. Program açık olun **Dosya Aç** kullanıcı seçtiğinde iletişim kutusu **Enter** ve kullanıcı seçtiğinde kutusunu kapatmak **Esc**.

## <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için

-   Visual Studio'da programlama hakkında daha fazla bilgi için bkz: [programlama kavramları](http://msdn.microsoft.com/Library/65c12cca-af4f-4017-886e-2dbc00a189d6).

-   Visual Basic hakkında daha fazla bilgi için bkz: [Visual Basic ile uygulama geliştirme](/dotnet/visual-basic/developing-apps/index).

-   Visual C# hakkında bilgi edinmek için bkz: [C# dili ve .NET Framework Giriş](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework).

-   Sonraki öğretici gitmek için bkz: [Eğitmen 2: zamanlı matematik testi oluşturma](../ide/tutorial-2-create-a-timed-math-quiz.md).

-   Eğitmen önceki adıma dönmek için bkz: [adım 10: ek düğmeler ve onay kutusu için kod yazma](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).
