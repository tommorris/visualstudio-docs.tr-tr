---
title: Otolar ve yerel öğeler Windows değişkenler İnceleme | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 04/17/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.autos
- vs.debug.locals
helpviewer_keywords:
- debugger, variable windows
- debugging [Visual Studio], variable windows
ms.assetid: bb6291e1-596d-4af0-9f22-5fd713d6b84b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 956b3afe1308ee748ee9efa6292834754f7e8124
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42626476"
---
# <a name="inspect-variables-in-the-autos-and-locals-windows-in-visual-studio"></a>Otolar değişkenleri ve Visual Studio'da yerel Windows inceleyin
**Otolar** penceresini (hata ayıklarken, **CTRL + ALT + V, A**, veya **hata ayıklama > Windows > Otolar**) ve **Yereller** (hata ayıklama sırasında penceresi **CTRL + ALT + V, L**, veya **hata ayıklama > Windows > Yereller**) oldukça ayıklarken değişken değerleri görmek istediğinizde yararlıdır. **Yereller** genel işlev veya şu anda yürütülmekte olan bir yöntem olan yerel kapsamda tanımlanan değişkenler penceresinde görüntülenir. **Otolar** penceresi değişkenleri geçerli satırı (hata ayıklayıcı durduğu yeri) geçici olarak kullanılan görüntüler. Tam olarak hangi değişkenlerini Bu pencerede görüntülemek farklı dillerde farklı değildir. Bkz: [değişkenleri Otolar penceresinde görüntülenecek?](#bkmk_whatvariables) aşağıda.  
  
Temel hata ayıklama hakkında daha fazla bilgiye ihtiyacınız varsa bkz [hata ayıklayıcı ile çalışmaya başlama](../debugger/getting-started-with-the-debugger.md).  
  
## <a name="looking-at-objects-in-the-autos-and-locals-windows"></a>Otolar ve yerel öğeler pencerelerinde nesneleri bakarak  
Diziler ve nesneler değişkenler ve yerel öğeler pencerelerinde ağaç denetimleri görüntülenir. Görünümü alanlar ve Özellikler'i gösterecek şekilde genişletmek için değişken adının sol tarafındaki oka tıklayın. İşte bir örnek bir <xref:System.IO.FileStream?displayProperty=fullName> nesnesine **Yereller** penceresi:  
  
![Yerel öğeler&#45;FILESTREAM](../debugger/media/locals-filestream.png "Yereller FILESTREAM")  
  
## <a name="bkmk_whatvariables"></a> Değişkenleri Otolar penceresinde görüntülenecek?  
 Kullanabileceğiniz **Otolar** C#, Visual Basic ve C++ kod penceresinde. **Otolar** penceresi, JavaScript veya F # desteklemez.  
  
 C# ve Visual Basic **Otolar** geçerli ya da önceki satırında kullanılan herhangi bir değişken penceresinde görüntülenir. Örneğin, dört değişkenleri tanımlayın ve bunları aşağıdaki gibi ayarlayın:

```csharp
    public static void Main()
    {
       int a, b, c, d;
       a = 1;
       b = 2;
       c = 3;
       d = 4;
    }
```

 Satırına bir kesme noktası ayarlarsanız `c = 3`; ve hata ayıklayıcı yürütme durdurulduğunda çalıştırma **Otolar** penceresi şu şekilde görünür:  

 ![Otolar&#45;CSharp](../debugger/media/autos-csharp.png "Otolar-CSharp")  

 Unutmayın değerini `c` 0, çünkü satır `c = 3` henüz çalıştırılmadı.  

 C++'ta **Otolar** penceresi değişkenleri kullanılan en az üç satır önce geçerli satırı görüntüler (yürütme durdurulduğunda satır). Altı değişken bildirirseniz:

```C++
    void main() {
        int a, b, c, d, e, f;
        a = 1;
        b = 2;
        c = 3;
        d = 4;
        e = 5;
        f = 6;
    }
```

 Satırına bir kesme noktası ayarlarsanız `e = 5;` ve hata ayıklayıcı yürütme durdurulduğunda çalıştırma **Otolar** penceresi şu şekilde görünür:  
  
 ![Otolar&#45;Cplus](../debugger/media/autos-cplus.png "Otolar Cplus")  
  
 E değişkeni başlatılmamış olduğundan Not kod satırı `e = 5;` henüz çalıştırılmadı.  
  
 İşlevler ve bazı durumlarda yöntemlerinin dönüş değerlerini de görebilirsiniz. Bkz: [yöntem çağrılarının dönüş değerlerini görüntüleme](#bkmk_returnValue) aşağıda.  
  
##  <a name="bkmk_returnValue"></a> Yöntem çağrılarının dönüş değerlerini görüntüleme  
 .NET ve C++ kodunda üzerinden veya bir yöntem çağrısının dışına adımladığınızda dönüş değerlerini inceleyebilirsiniz. Bu işlev, bir yöntem parametresi olarak veya başka bir yöntemin dönüş değeri olarak kullanılır, örneğin bir yerel değişken bir yöntem çağrısının sonucuna depolanmaz yararlıdır.  
  
 Aşağıdaki C# kodu iki işlev dönüş değerlerini ekler:  

```csharp
static void Main(string[] args)  
{  
    int a, b, c, d;  
    a = 1;  
    b = 2;  
    c = 3;  
    d = 4;  
    int x = sumVars(a, b) + subtractVars(c, d);  
}  
  
private static int sumVars(int i, int j)  
{  
    return i + j;  
}  
  
private static int subtractVars(int i, int j)  
{  
    return j - i;  
}  
```

 Bir kesme noktası ayarlamak `int x = sumVars(a, b) + subtractVars(c, d);` satır.  
  
 Hata ayıklamayı başlatmak ve ilk kesme noktasında yürütmeyi keserse basın **F10 (Step Over)**. Aşağıdaki görmelisiniz **Otolar** penceresi:  
  
 ![AutosReturnValueCSharp2](../debugger/media/autosreturnvaluecsharp2.png "AutosReturnValueCSharp2")  
  
## <a name="why-are-variable-values-sometimes-red-in-locals-and-autos-windows"></a>Neden değişken değerleri, Yereller ve Arabalar'da windows kırmızıyla misiniz?  
Bir değişkenin değerini bazen de kırmızı olduğunu fark edebilirsiniz **Yereller** ve **Otolar** windows. Son Değerlendirme bu yana değişmiş olan değişken değerleri şunlardır. Değişiklik, bir önceki hata ayıklama oturumundan olabilir veya pencerede değeri değiştirildi.  
  
## <a name="changing-the-numeric-format-of-a-variable-window"></a>Bir değişken penceresinde sayısal biçimini değiştirme  
Varsayılan sayısal biçimi ondalık ancak onaltılı olarak değiştirebilirsiniz. İçinde sağ bir **Yereller** veya **Otolar** penceresi ve select **onaltılık gösterim**. Bu değişiklik tüm hata ayıklayıcı pencereleri etkiler.  
  
## <a name="editing-a-value-in-a-variable-window"></a>Bir değişken penceresinde değer düzenleme  
Görünen çoğu değişkenlerin değerlerini düzenleyebileceğiniz **Otolar**, **Yereller**, **Watch**, ve **QuickWatch** windows. Hakkında bilgi için **Watch** ve **QuickWatch** windows bkz [izleme ve QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md). Yalnızca değiştirmek ve yeni değer eklemek için istediğiniz değere çift tıklayın.  
  
Örneğin bir değer için bir ifade girin `a + b`. Hata ayıklayıcı en geçerli dili ifadelerini kabul eder.  
  
Yerel C++ kod içinde bir değişken adının bağlamını nitelemeniz gerekebilir. Daha fazla bilgi için [bağlam işleci (C++)](../debugger/context-operator-cpp.md).  
 
Ancak, değerlerini değiştirirken dikkatli olmanız gerekir. Olası bazı sorunlar şunlardır:  
  
-   Bazı ifadelerin değerlendirilmesi bir değişkenin değerini değiştirebilir veya aksi halde, programınızın durumunu etkileyebilir. Örneğin, değerlendirme `var1 = ++var2` değerini değiştirir `var1` ve `var2`.  
  
     Verileri değiştiren ifadelerin söylenebilir sağlamak için [yan etkileri](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\)), hangi beklenmeyen sonuçlar verebilir, bunları farkında değilseniz. Bunu yapmadan önce böyle bir değişiklik sonuçlarını anladığınızdan emin olun.  
  
-   Kayan nokta değerlerini düzenlemek, kesirli bileşenlerin ondalıktan ikiliye dönüştürülmesi nedeniyle küçük yanlışlıklara neden olabilir. Zararsız görünen bir düzenleme bile, kayan nokta değişkenindeki en az önemli bitlerin bazılarının değişmesine neden olabilir.  
  
## <a name="changing-the-window-context"></a>Pencere bağlam değiştirme  
Kullanabileceğiniz **hata ayıklama konumu** araç istenen işlevi, iş parçacığı veya değişken pencerelerini bağlamı değiştiren bir işlem seçin. Bir kesme noktası ayarlayın ve hata ayıklamaya başlayın. (Bu araç görmüyorsanız, araç çubuğu alanında boş bir bölümüne tıklayarak etkinleştirebilirsiniz. Araç çubukları listesini görmeniz gerekir; seçin **hata ayıklama konumu**). Kesme noktası isabet edildiğinde yürütme durur ve aşağıdaki çizimde en alt satırında olan hata ayıklama konumu araç çubuğunda görebilirsiniz.
  
![DebugLocationToolbar](../debugger/media/debuglocationtoolbar.png "DebugLocationToolbar")   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows hata ayıklayıcı](../debugger/debugger-windows.md)
