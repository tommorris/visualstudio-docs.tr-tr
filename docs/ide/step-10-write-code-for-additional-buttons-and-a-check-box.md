---
title: "10. adım: Ek düğmeler ve onay kutusu için kod yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
caps.latest.revision: "21"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 797b01016cb82aeb3d6ecfa1d11fa79df0085ee1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>10. Adım: Ek Düğmeler ve Onay Kutusu için Kod Yazma
Artık bir dört yöntem tamamlamak hazırsınız. Kopyalayın ve bu kodu yapıştırın, ancak bilgi edinmek istiyorsanız bu öğreticiden en kodu yazın ve IntelliSense kullanın.  
  
 Bu kod, daha önce eklediğiniz düğmeleri için işlevsellik ekler. Bu kodu olmadan düğmeleri hiçbir şey yapmayın. Kodda düğmeleri kullanın kendi `Click` olayları (ve onay kutusu kullandığı `CheckChanged` olay) denetimleri etkinleştirdiğinizde farklı işlemler yapmak için. Örneğin, `clearButton_Click` seçtiğinizde etkinleşir olayı, **resmi temizleyin** düğmesini tıklatın, geçerli görüntü ayarlayarak sildiği kendi `Image` özelliğine `null` (veya `nothing`). Her olay kodda kodun ne yaptığını açıklayan açıklamaları içerir.  
  
 ![video bağlantı](../data-tools/media/playvideo.gif "PlayVideo")bu konuda video sürümü için bkz: [Eğitmen 1: Visual Basic'te - Video 5 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205216) veya [Eğitmen 1: bir resim görüntüleyici oluşturma C# - Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Bazı menü komutları ve diğer kullanıcı arabirimi öğeleri küçük farklar olduklarından bu videolar Visual Studio'nun önceki bir sürümünü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde geçerli sürümünde Visual Studio çalışır.  
  
> [!NOTE]
>  En iyi uygulama olarak: kodunuzun her zaman açıklama. Bilgi okumak bir kişi için açıklamalardır ve kodunuzu anlaşılır hale getirmek için zamanı. Her şeyi kısa bir açıklama satırı program tarafından göz ardı edilir. Visual C# ', satır başında iki eğik yazarak Açıklama (/ /), ve Visual Basic'te bir satır tek tırnak işareti (') ile başlatarak açıklama.  
  
### <a name="to-write-code-for-additional-buttons-and-a-check-box"></a>Ek düğmeler ve onay kutusu için kod yazma  
  
-   Aşağıdaki kod, Form1 kod dosyasına (Form1.cs ya da Form1.vb) ekleyin. Seçin **VB** Visual Basic kodu görüntülemek için.  
  
     [!code-vb[VbExpressTutorial1Step9_10#2](../ide/codesnippet/VisualBasic/step-10-write-code-for-additional-buttons-and-a-check-box_1.vb)]
     [!code-csharp[VbExpressTutorial1Step9_10#2](../ide/codesnippet/CSharp/step-10-write-code-for-additional-buttons-and-a-check-box_1.cs)]  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Öğretici bir sonraki adıma dönmek için bkz: [11. adım: bilgisayarınızı programın çalıştırılması ve diğer özellikleri deneyin](../ide/step-11-run-your-program-and-try-other-features.md).  
  
-   Eğitmen önceki adıma dönmek için bkz: [adım 9: gözden geçirme, açıklama ve Test kodunuzu](../ide/step-9-review-comment-and-test-your-code.md).