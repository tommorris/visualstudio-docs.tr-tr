---
title: '10. adım: ek düğmeler ve onay kutusu için kod yazma'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e7194c4b52978ec4294d3b3597989725f32bbdf3
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>10. adım: ek düğmeler ve onay kutusu için kod yazma
Artık bir dört yöntem tamamlamak hazırsınız. Kopyalayın ve bu kodu yapıştırın, ancak bilgi edinmek istiyorsanız bu öğreticiden en kodu yazın ve IntelliSense kullanın.  
  
 Bu kod, daha önce eklediğiniz düğmeleri için işlevsellik ekler. Bu kodu olmadan düğmeleri hiçbir şey yapmayın. Kodda düğmeleri kullanın kendi <xref:System.Windows.Forms.Control.Click> olayları (ve onay kutusu kullandığı <xref:System.Windows.Forms.CheckBox.CheckedChanged> olay) denetimleri etkinleştirdiğinizde farklı işlemler yapmak için. Örneğin, `clearButton_Click` seçtiğinizde etkinleşir olayı, **resmi temizleyin** düğmesini tıklatın, geçerli görüntü ayarlayarak sildiği kendi **görüntü** özelliğine **null**(veya **hiçbir şey**). Her olay kodda kodun ne yaptığını açıklayan açıklamaları içerir.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 5 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205216) veya [Öğreticisi 1: Resim Görüntüleyici C# ' - oluşturma Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
> [!NOTE]
>  En iyi uygulama olarak: kodunuzun her zaman açıklama. Bilgi okumak bir kişi için açıklamalardır ve kodunuzu anlaşılır hale getirmek için zamanı. Her şeyi kısa bir açıklama satırı program tarafından göz ardı edilir. Visual C# ', satır başında iki eğik yazarak Açıklama (/ /), ve Visual Basic'te bir satır tek tırnak işareti (') ile başlatarak açıklama.  

## <a name="to-write-code-for-additional-buttons-and-a-check-box"></a>Ek düğmeler ve onay kutusu için kod yazma  
  
-   Aşağıdaki kodu ekleyin, **Form1** kod dosyasının (*Form1.cs* veya *Form1.vb*). Seçin **VB** Visual Basic kodu görüntülemek için.  
  
     [!code-vb[VbExpressTutorial1Step9_10#2](../ide/codesnippet/VisualBasic/step-10-write-code-for-additional-buttons-and-a-check-box_1.vb)]
     [!code-csharp[VbExpressTutorial1Step9_10#2](../ide/codesnippet/CSharp/step-10-write-code-for-additional-buttons-and-a-check-box_1.cs)]  

## <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [11. adım: programınızı çalıştırma ve diğer özellikleri deneme](../ide/step-11-run-your-program-and-try-other-features.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [adım 9: gözden geçirme, açıklama ve kodunuzu test](../ide/step-9-review-comment-and-test-your-code.md).
