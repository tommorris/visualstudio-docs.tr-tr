---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: kesme iş akışları (eski)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- breakpoints, setting in workflows
- debugging, setting breakpoints in workflows
- debugging workflows, setting breakpoints
- workflows, setting breakpoints
ms.assetid: 78e0be39-3e99-487c-bfef-19db0daf6f42
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c0c70b630404830fa8c733a7310e4700da8f08b3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-breakpoints-in-workflows-legacy"></a>Nasıl yapılır: kesme iş akışları (eski)

Bu konu, Windows Workflow Foundation (eski Windows iş akışı Tasarımcısı'nı kullanarak uygulamaları derleme WF içinde) kesme noktalarını ayarlayın açıklar. Windows Workflow Foundation uygulamanız .NET Framework sürüm 3.5 veya WinFX hedef gerektiğinde eski iş akışı Tasarımcısı kullanın.

 Bir Windows Workflow Foundation uygulaması oluşturmak için Visual Studio 2010'da eski iş akışı Tasarımcısı kullandığınızda, Visual Studio'da yaptığınız gibi kesme noktaları C# ve Visual Basic kodu ayarlayabilirsiniz. Beklendiği gibi iş akışı yürütme ayarladığınız her kesme noktasında durur.

 Üç durumlu bir kesme noktası vardır: *bekleyen*, *bağlı*, ve *hata*. Bir kesme noktası ayarladığınızda, bekleyen ve boş bir kırmızı simgesiyle gösterilir. Çalışma zamanı iş akışı türü yüklendiğinde bağlı olur ve düz kırmızı bir simge ile temsil edilir. Biçimi yanlış kesme noktası için geçerli olmayan bir etkinlik adı olarak belirtirseniz, bir hata penceresi görünür. Kesme noktası hala kesme noktası penceresine eklenen ancak küçük "x" ile işaretlenmiş.

 Aşağıdaki yollarla bir etkinlikte iş akışı tasarım yüzeyine kesme noktaları ayarlayabilirsiniz:

-   Etkinliği sağ tıklatın ve seçin **kesme noktası \ kesme noktası Ekle**.

-   Etkinliği seçin ve F9 tuşuna basın.

-   Seçin **yeni kesme noktası** gelen **hata ayıklama** menüsü.

     Hata ayıklayıcı kesme noktasında durduğunda, hata ayıklama sırasında yeni bir kesme noktası ayarlamak için bu seçeneği de kullanabilirsiniz.

    > [!NOTE]
    > Çağrılan iş akışlarında kesme noktalarını ayarlama desteklenmez.

### <a name="to-set-a-breakpoint-using-the-new-breakpoint-option-on-the-debug-menu"></a>Hata Ayıklama menüsünde Yeni kesme noktası seçeneğini kullanarak bir kesme noktası ayarlamak için

1.  Üzerinde **hata ayıklama** menüsünde, select **yeni kesme noktası**.

2.  Tıklatın **bölün konumundaki işlev**.

     **Yeni kesme noktası** iletişim kutusu açılır.

3.  Bir etkinliğin adını belirtin **işlevi** bu söz dizimini kullanarak metin kutusuna: `QualifiedActivityId[:[FullClassName][:InstanceId]]`.

    > [!NOTE]
    > Etkinlik adı yerine isteğe bağlı olarak, **işlevi** metin kutusunda, iş akışı etkinliğini mutlak yolu belirterek bir kesme noktası ayarlayabilirsiniz. Örneğin, adlandırılmış bir iş akışı çözümü olduğunu varsayalım **WorkflowConsoleApplication1** ve bir iş akışında adlı çözüm **Workflow1** adlı bir etkinlik kullanan **Delay1**. Etkinlik adı kullanabilirsiniz **Delay1** veya yolu olarak belirtebilirsiniz **Delay1:WorkflowConsoleApplication1.Workflow1** veya **Delay1:WorkflowConsoleApplication1.Workflow1: { 6614886A-608E-412B-BF98-99FF1559DDDF}**.

4.  Seçin **kullanım IntelliSense** onay kutusunu işlevi adını doğrulayın.

     Bu onay kutusu seçili değilse, hiçbir kesme noktası adı doğrulaması gerçekleştirilir.

5.  Seçin **iş akışı** gelen **dil** listesi.

6.  **Tamam**'ı tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

- [Eski İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-legacy-workflows.md)
- [Windows Workflow Foundation için Visual Studio Hata Ayıklayıcısını Çağırma (Eski)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)