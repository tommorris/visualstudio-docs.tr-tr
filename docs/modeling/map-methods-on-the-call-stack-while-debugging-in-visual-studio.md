---
title: "Visual Studio'da hata ayıklarken çağrı yığınında yöntemler eşleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: get-started-article
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4b29267f46495378d0bf6ae53e991372509d7543
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="map-methods-on-the-call-stack-while-debugging-in-visual-studio"></a>Visual Studio'da hata ayıklarken çağrı yığınında eşleştirme yöntemleri
Hatalarını ayıkladığınız sırada görsel olarak çağrı yığınını izleme için bir kod Haritası oluşturun. Hataları bulmaya odaklanabilmeniz amacıyla kodun ne yaptığını izlemek için harita üzerine not alabilirsiniz.  
  
 ![Çağrı yığınları kod haritalarını üzerinde ile hata ayıklama](../debugger/media/debuggermap_overview.png "DebuggerMap_Overview")  
  
 İhtiyacınız vardır:  
  
-   [Visual Studio Enterprise](https://www.visualstudio.com/downloads/download-visual-studio-vs)  
  
-   Visual C#, Visual Basic, C++, JavaScript veya X ++ gibi ayıklayabilirsiniz kodu  
  
 Bkz.  
  
-   [Video: kod Haritası hata ayıklayıcı tümleştirme (Channel 9) görsel olarak hata ayıklama](http://go.microsoft.com/fwlink/?LinkId=293418)
  
-   [Çağrı yığınını eşleme](#MapStack)
  
-   [Kod ile ilgili notlar olun](#MakeNotes)
  
-   [Güncelleştirme eşlemesi sonraki çağrı yığını ile](#UpdateMap)
  
-   [Eşleme için ilgili kod ekleme](#AddRelatedCode)
  
-   [Haritanın kullanarak hataları bulma](#FindBugs)
  
-   [SORU- CEVAP](#QA)  
  
 Kullanabileceğiniz kod haritalarını ile çalışırken, eylemleri ve komutları ayrıntıları için bkz: [göz atın ve haritalar kod sıralama](../modeling/browse-and-rearrange-code-maps.md).  
  
##  <a name="MapStack"></a>Çağrı yığınını eşleme  
  
1.  Hata ayıklama başlatılamıyor. (Klavye: **F5**)  
  
2.  Uygulamanızı Kesme moduna girer ya da bir işlevdeki adım sonra tercih **kod Haritası**. (Klavye: **Ctrl** + **Shift** + **`**)  
  
     ![Eşleme çağrı yığını başlatmak için kod Haritası seçin](../debugger/media/debuggermap_choosecodemap.png "DebuggerMap_ChooseCodeMap")  
  
     Geçerli çağrı yığını yeni bir kod haritası üzerinde turuncu renkte görüntülenir:  
  
     ![Bkz: kod Haritası çağrı yığınındaki](../debugger/media/debuggermap_seeundocallstack.png "DebuggerMap_SeeUndoCallStack")  
  
     Hata ayıklama devam ederken harita otomatik olarak güncelleştirir. Bkz: [harita sonraki çağrı yığını ile güncelleştirme](#UpdateMap).  
  
##  <a name="MakeNotes"></a>Kod ile ilgili notlar olun  
 Kod içinde neler olduğunu izlemek için açıklamalar ekleyin. Yeni bir satır bir yorum eklemek için basın **Shift + dönmek**.  
  
 ![Kod haritasında çağrı yığını açıklama eklemek](../debugger/media/debuggermap_addcomment.png "DebuggerMap_AddComment")  
  
##  <a name="UpdateMap"></a>Güncelleştirme eşlemesi sonraki çağrı yığını ile  
 Uygulamanızı sonraki kesme noktasına kadar çalıştırın veya bir işleve adımlayın. Eşleme yeni bir çağrı yığını ekler.  
  
 ![Sonraki çağrı yığınına sahip güncelleştirme kod Haritası](../debugger/media/debuggermap_addclearcallstack.png "DebuggerMap_AddClearCallStack")  
  
##  <a name="AddRelatedCode"></a>Eşleme için ilgili kod ekleme  
 Şimdi, bir harita - ne sonraki var? C# veya Visual Basic ile çalışıyorsanız, alanları, özellikleri ve kodda neler olduğunu izlemek için diğer yöntemleri gibi öğeleri ekleyin.  
  
 Kod tanımı görmek için bir yöntem çift tıklatın veya yöntemi için kısayol menüsünü kullanın. (Klavye: basın ve harita yöntemi seçin **F12**)  
  
 ![Kod tanımı kod Haritası bir yöntem için Git](../debugger/media/debuggermap_gotocodedefinition.png "DebuggerMap_GoToCodeDefinition")  
  
 Haritada izlemek istediğiniz öğeleri ekleyin.  
  
 ![Çağrı yığını kod Haritası bir yöntem alanları gösterin](../debugger/media/debuggermap_showfields.png "DebuggerMap_ShowFields")  
  
> [!NOTE]
>  Varsayılan olarak, öğeleri eşlemeye ekleme sınıfı, ad alanı ve derleme gibi üst grubu düğümler ekler. Bu yararlı olsa da, eşleme özelliğini kullanarak bu devre dışı bırakarak basit tutabildiğiniz **dahil üst** düğmesine basarak veya map araç çubuğunda **CTRL** öğeleri eklediğinizde.  
  
 ![İlişkili alanları bir çağrı yığını kod Haritası yöntemi](../debugger/media/debuggermap_showedfields.png "DebuggerMap_ShowedFields")  
  
 Hangi yöntemlerin aynı alanları kullandığını kolayca görebilirsiniz. En son eklenen öğeler yeşil görünür.  
  
 Daha fazla kod görmek için haritayı oluşturmaya devam edin.  
  
 ![Bir alan kullanan yöntemleri bkz: çağrı yığını kod Haritası](../debugger/media/debuggermap_findallreferences.png "DebuggerMap_FindAllReferences")  
  
 ![Çağrı yığını kod haritasında bir alan kullanan yöntemleri](../debugger/media/debuggermap_foundallreferences.png "DebuggerMap_FoundAllReferences")  
  
##  <a name="FindBugs"></a>Haritanın kullanarak hataları bulma  
 Kodunuzu görselleştirmeniz, hataları daha hızlı şekilde bulmanıza yardımcı olabilir. Örneğin, bir çizim programı hatada çalışıyoruz varsayalım. Bir çizgi çizip geri almayı denediğinizde, başka bir çizgi çizinceye kadar hiçbir şey olmaz.  
  
 Kesme noktalarını ayarlayın şekilde `clear`, `undo`, ve `Repaint` yöntemleri, hata ayıklamayı Başlat ve bunun gibi bir harita oluşturur:  
  
 ![Başka bir çağrı yığını için kod Eşlemesi Ekle](../debugger/media/debuggermap_addpaintobjectcallstack.png "DebuggerMap_AddPaintObjectCallStack")  
  
 Tüm kullanıcı eşlemesi çağrıda hareketleri fark `Repaint`, dışında `undo`. Bu nedenle açıklayabilir `undo` hemen çalışmıyor.  
  
 Hatayı düzeltin ve program çalıştırmaya devam sonra yeni çağrısından harita ekler `undo` için `Repaint`:  
  
 ![Kod haritasında yeni yöntem çağrısı için çağrı yığını eklemek](../debugger/media/debuggermap_addnewcallforrepaint.png "DebuggerMap_AddNewCallForRepaint")  
  
##  <a name="QA"></a>SORU- CEVAP  
  
-   **Tüm çağrıları harita üzerinde görünür. Neden?**  
  
     Varsayılan olarak, yalnızca kendi kodunuzu harita üzerinde görünür. Dış kodu görmek için de açmak **çağrı yığını** penceresi:  
  
     ![Çağrı yığını penceresini kullanarak harici kod görüntülemek](../debugger/media/debuggermap_callstackmenu.png "DebuggerMap_CallStackMenu")  
  
     veya kapatılabilir **sadece kendi kodumu etkinleştir** Visual Studio hata ayıklama seçenekleri:  
  
     ![Seçenekler iletişim kutusu kullanılarak harici kod Göster](../debugger/media/debuggermap_debugoptions.png "DebuggerMap_DebugOptions")  
  
-   **Harita değiştirme kodu etkiliyor mu?**  
  
     Harita değiştirme herhangi bir yolla kod etkilemez. Haritadaki herhangi bir şeyi rahatça yeniden adlandırabilir, taşıyabilir veya kaldırabilirsiniz.  
  
-   **Bu ileti ne anlama gelir: "diyagram kodu daha eski bir sürümü temel alıyor olabilir"?**  
  
     Kod, haritayı son güncelleştirmenizden sonra değişmiş olabilir. Örneğin, harita üzerindeki bir çağrı artık kodda bulunmayabilir. İletiyi kapatın ve haritayı yeniden güncelleştirmeden önce çözümü yeniden oluşturmayı deneyin.  
  
-   **Haritanın düzeni nasıl denetlerim?**  
  
     Açık **düzeni** map araç çubuğundaki menüsü:  
  
    -   Ekran düzenini değiştirin.  
  
    -   Harita otomatik olarak yeniden düzenleme durdurmak için kapatmak **otomatik olarak hata ayıklama sırasında düzeni**.  
  
    -   Öğeleri eklediğinizde, mümkün olduğunca az harita yeniden düzenlemek için kapatmak **artan düzen**.  
  
-   **I harita başkalarıyla paylaşabilirsiniz?**  
  
     Haritayı dışarı aktarabilir, Microsoft Outlook'unuz varsa başkalarına gönderebilir veya çözümünüze kaydedebilir, böylece Team Foundation sürüm denetimine iade edebilirsiniz.  
  
     ![Paylaşım çağrı yığını kod Haritası başkalarıyla](../debugger/media/debuggermap_sharewithothers.png "DebuggerMap_ShareWithOthers")  
  
-   **Yeni çağrı yığınları otomatik olarak eklemeden harita nasıl Durdur?**  
  
     Seçin ![düğmesi &#45; Çağrı yığını otomatik olarak kod haritasında Göster](../debugger/media/debuggermap_automaticupdateicon.gif "DebuggerMap_AutomaticUpdateIcon") map araç. Geçerli çağrı yığını eşlemesine el ile eklemek için basın **Ctrl** + **Shift** + **`**.  
  
     Harita, hatalarını ayıkladığınız sırada mevcut çağrı yığınları harita üzerinde vurgulama devam eder.  
  
-   **Öğesi simgelerinin ve okları anlamı nedir?**  
  
     Bir öğe hakkında daha fazla bilgi almak için fare işaretçisini üzerine getirin ve öğenin araç ipucu bakın. Ayrıca bakabilir **gösterge** her simge anlamı öğrenin.  
  
     ![Çağrı yığını kod Haritası simgeleri ne anlama geliyor? ] (../debugger/media/debuggermap_showlegend.png "DebuggerMap_ShowLegend")  
  
 Bkz.  
  
-   [Çağrı yığınını eşleme](#MapStack)
  
-   [Kod ile ilgili notlar olun](#MakeNotes)
  
-   [Güncelleştirme eşlemesi sonraki çağrı yığını ile](#UpdateMap)
  
-   [Eşleme için ilgili kod ekleme](#AddRelatedCode)
  
-   [Haritanın kullanarak hataları bulma](#FindBugs)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çözümlerinizdeki bağımlılıkları eşleme](../modeling/map-dependencies-across-your-solutions.md)   
 [Uygulamalarınızda hata ayıklamak için kod haritalarını kullanma](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Kod Haritası çözümleyicilerini kullanarak olası sorunları bulma](../modeling/find-potential-problems-using-code-map-analyzers.md)   
 [Kod haritalarına göz atma ve bunları yeniden düzenleme](../modeling/browse-and-rearrange-code-maps.md)