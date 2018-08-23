---
title: '10. adım: Ek düğmeler ve onay kutusu için kod yazma | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 185cf370-ab39-4ac0-b6bc-601d5b95a4a2
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 254c01b6553c8abc647ab9041fdd6fdf5da63a70
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693858"
---
# <a name="step-10-write-code-for-additional-buttons-and-a-check-box"></a>10. Adım: Ek Düğmeler ve Onay Kutusu için Kod Yazma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [adım 10: ek düğmeler ve onay kutusu için kod yazma](https://docs.microsoft.com/visualstudio/ide/step-10-write-code-for-additional-buttons-and-a-check-box).  
  
Diğer dört yöntemi tamamlamaya artık hazırsınız. Bu kodu kopyalayıp, ancak bilgi almak istiyorsanız bu öğreticiden en iyi kodu yazıp IntelliSense kullanın.  
  
 Bu kod, daha önce eklediğiniz düğmelere işlevsellik ekler. Bu kod olmadan düğmeler hiçbir şey yapmaz. Kodda düğmelerini kendi `Click` olayları (ve onay kutusu kullandığı `CheckChanged` olay) denetimleri etkinleştirdiğinizde değişik şeyler yapmak için. Örneğin, `clearButton_Click` seçtiğinizde olayı, **resmi Temizle** düğmesi, ayarlayarak geçerli görüntüyü siler, `Image` özelliğini `null` (veya `nothing`). Her olay, kodun ne yaptığını açıklayan yorumlar içerir.  
  
 ![video bağlantısı](../data-tools/media/playvideo.gif "PlayVideo")bu konunun video sürümü için bkz: [öğretici 1: Visual Basic'te - Video 5 resim görüntüleyici oluşturma](http://go.microsoft.com/fwlink/?LinkId=205216) veya [öğretici 1: Resim Görüntüleyici C# ' - oluşturma Video 5](http://go.microsoft.com/fwlink/?LinkId=205206). Bazı menü komutlarında ve diğer kullanıcı arabirimi öğelerinde küçük farklılıklar olduğundan bu videolarda Visual Studio'nun önceki bir sürümü kullanın. Ancak, kavramlar ve yordamlar benzer şekilde Visual Studio'nun geçerli sürümünde çalışır.  
  
> [!NOTE]
>  En iyi uygulama olarak: her zaman kodunuza yorum yapın. Yorumlar bir kişinin okuması için için bilgilerdir ve kodunuzu anlaşılır hale getirmek için zaman ayırmanız iyidir. Bir yorum satırındaki her şey program tarafından göz ardı edilir. Visual C# içinde bir satır başına iki eğik yazarak yorum (/ /), ve Visual Basic'te, bir satır tek tırnak işaretiyle (') başlatarak yorum yazabilirsiniz.  
  
### <a name="to-write-code-for-additional-buttons-and-a-check-box"></a>Ek düğmeler ve onay kutusu için kod yazma  
  
-   Form1 kod dosyanıza (Form1.cs veya Form1.vb) aşağıdaki kodu ekleyin. Seçin **VB** Visual Basic kodunu görüntülemek için sekmesinde.  
  
     [!code-csharp[VbExpressTutorial1Step9_10#2](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/cs/form1.cs#2)]
     [!code-vb[VbExpressTutorial1Step9_10#2](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial1step9_10/vb/form1.vb#2)]  
  
### <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Sonraki öğretici adımına gitmek için bkz: [11. adım: bilgisayarınızı programı çalıştırın ve diğer özellikleri deneyin](../ide/step-11-run-your-program-and-try-other-features.md).  
  
-   Önceki öğretici adımına dönmek için bkz: [9. adım: gözden geçirme, açıklama ve Test kodunuzu](../ide/step-9-review-comment-and-test-your-code.md).



