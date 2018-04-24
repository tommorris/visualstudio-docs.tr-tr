---
title: Geçmiş hata ayıklama ile uygulamanızı inceleyin. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 629b5d93-39b2-430a-b8ba-d2a47fdf2584
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d6a8e4ec27c73516d2eb4ea79ee8beee91dfd19c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="inspect-your-app-with-intellitrace-historical-debugging-in-visual-studio"></a>Visual Studio'da hata ayıklamayı geçmiş IntelliTrace ile uygulamanızı inceleyin.
Kullanabileceğiniz [geçmiş hata ayıklama](../debugger/historical-debugging.md) geri taşımak ve uygulamanızı yürütme iletmek ve durumunu incelemek için.  
  
Visual Studio Enterprise edition ancak değil Professional veya topluluk sürümleri IntelliTrace kullanabilirsiniz.  
  
## <a name="navigate-your-code-with-historical-debugging"></a>Geçmiş hata ayıklama ile kodunuzu gidin  
 Bir hata bulunmaktadır için basit bir program başlayalım. Bir C# konsol uygulamasında, aşağıdaki kodu ekleyin:  
  
```csharp  
static void Main(string[] args)  
{  
    int testInt = 0;  
    int resultInt = AddAll(testInt);  
    Console.WriteLine(resultInt);  
}  
private static int AddAll(int j)  
{  
    for (int i = 0; i < 20; i++)  
    {  
        j = AddInt(j);  
    }  
    return j;  
}  
  
private static int AddInt(int add)  
{  
    if (add == 10)  
    {  
        return add += 25;  
    }  
    return ++add;  
}  
```  
  
 Varsayıyoruz beklenen değeri `resultInt` çağırdıktan sonra `AddAll()` 20'dir (artırma sonucunu `testInt` 20 kez). (Ayrıca hatayı göremez varsayıyoruz `AddInt()`). Ancak gerçekten 44 sonucudur. Nasıl biz bulabilir hatayı aracılığıyla atlamadan `AddAll()` 10 kez? Hatanın daha hızlı ve kolay bulmak için şu geçmiş hata ayıklama'ı kullanabilirsiniz. İşte nasıl:  
  
1.  İçinde **Araçlar > Seçenekler > IntelliTrace > Genel**, IntelliTrace etkin olduğundan emin olun ve seçin **IntelliTrace olayları ve arama bilgileri**. Bu seçeneği belirlemezseniz (aşağıda açıklandığı gibi) gezinti kanalı görmeye olmaz.  
  
2.  Bir kesme noktası ayarlayın `Console.WriteLine(resultInt);` satır.  
  
3.  Hata ayıklama başlatılamıyor. Kesme noktasına kodu yürütür. İçinde **Yereller** penceresinde görebilirsiniz değerini `resultInt` 44 değil.  
  
4.  Açık **tanılama araçları** penceresi (**hata ayıklama > tanılama araçları Göster**). Kod penceresi aşağıdaki gibi görünmelidir:  
  
     ![Kesme noktası kod penceresine](../debugger/media/historicaldebuggingbreakpoint.png "HistoricalDebuggingBreakpoint")  
  
5.  Kesme noktası hemen üstünde sol kenar boşluğu yanındaki çift ok görmeniz gerekir. Bu alan gezinti kanalı olarak adlandırılır ve geçmiş hata ayıklama için kullanılır. Oka tıklayın.  
  
     Kod penceresinde, görmelisiniz önceki kod satırı ile (`int resultInt = AddIterative(testInt);`) Pembe renkli. Pencerenin şimdi Geçmiş hata ayıklama olan bir ileti görürsünüz.  
  
     Kod penceresi şimdi şöyle görünür:  
  
     ![Geçmiş hata ayıklama modunda kod penceresi](../debugger/media/historicaldebuggingback.png "HistoricalDebuggingBack")  
  
6.  İçine adım artık `AddAll()` yöntemi (**F11**, veya **Step Into** Gezinti kanalı düğmesini. Adım ileri (**F10**, veya **sonraki çağrı Git** Gezinti kanalı içinde. Açıktır şimdi Pembe çizgi `j = AddInt(j);` satır. **F10** bu durumda kod bir sonraki satıra adım değil. Bunun yerine, sonraki işlev çağrısı için adımlar. Geçmiş hata ayıklama çağrısı çağrı gider ve işlev çağrısı içermeyen kod satırlarını atlar.  
  
7.  Şimdi adımla `AddInt()` yöntemi. Bu kod hatada hemen görmeniz gerekir.  

## <a name="next-steps"></a>Sonraki adımlar

Bu yordam yalnızca geçmiş hata ayıklama ile neler yapabileceğinizi yüzeyine disk bozulmuş.

- Hata ayıklama sırasında anlık görüntüleri görüntülemek için bkz: [görüntülemek IntelliTrace adım geri kullanarak anlık görüntüyü](../debugger/how-to-use-intellitrace-step-back.md).
- Farklı ayarlar ve gezinti kanalı farklı düğmeleri etkilerini hakkında daha fazla bilgi için bkz: [IntelliTrace özellikleri](../debugger/intellitrace-features.md).