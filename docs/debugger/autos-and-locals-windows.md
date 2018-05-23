---
title: Otomatik değişkenler ve yerel Windows değişkenler inceleyin. | Microsoft Docs
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
ms.openlocfilehash: d3b19e8bd55320a9fbd5d8af037a9577db42a2fa
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="inspect-variables-in-the-autos-and-locals-windows-in-visual-studio"></a>Otomatik değişkenler değişkenleri ve Visual Studio Yereller Windows inceleyin.
**Otomobiller** penceresi (hata ayıklama, **CTRL + ALT + V, A**, veya **hata ayıklama > Windows > otomobiller**) ve **Yereller** (hata ayıklama penceresi **CTRL + ALT + V, L**, veya **hata ayıklama > Windows > Yereller**) hata ayıklarken değişken değerleri görmek istediğinizde oldukça faydalıdır. **Yereller** penceresi, işlev veya şu anda yürütülmekte olan yöntem genellikle olan yerel kapsamda tanımlanan değişkenler görüntüler. **Otomobiller** penceresi geçerli satırında (hata ayıklayıcı durduğu koyun) kullanılan değişkenler görüntüler. Tam olarak hangi değişkenleri Bu pencerede görüntüler farklı dillerde farklıdır. Bkz: [değişkenleri otomobiller penceresinde görüntülenecek?](#bkmk_whatvariables) aşağıda.  
  
Temel hata ayıklama hakkında daha fazla bilgiye ihtiyacınız varsa bkz [hata ayıklayıcısı ile çalışmaya başlama](../debugger/getting-started-with-the-debugger.md).  
  
## <a name="looking-at-objects-in-the-autos-and-locals-windows"></a>Otomatik değişkenler ve yerel Windows nesneleri bakarak  
Diziler ve nesneleri otomatik değişkenler ve Yereller pencerelerinde ağaç denetimleri görüntülenir. Alanları ve özellikleri göstermek için Görünümü genişletmek için değişken adının solundaki oka tıklayın. Bir örneği burada verilmiştir bir [FILESTREAM](/dotnet/api/system.io.filestream) nesnesinde **Yereller** penceresi:  
  
![Yerel öğeler&#45;FILESTREAM](../debugger/media/locals-filestream.png "Yereller FILESTREAM")  
  
## <a name="bkmk_whatvariables"></a> Otomatik değişkenler penceresi değişkenleri görüntülenecek?  
 Kullanabileceğiniz **otomobiller** C#, Visual Basic ve C++ kodu penceresinde. **Otomobiller** JavaScript veya F # penceresi desteklemez.  
  
 C# ve Visual Basic **otomobiller** geçerli veya önceki satıra kullanılan herhangi bir değişken penceresinde görüntülenir. Örneğin, dört değişkenleri bildirin ve aşağıdaki gibi ayarlayın:

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

 Satırında bir kesme noktası ayarlarsanız `c = 3`; çalıştırıp yürütme durduğunda hata ayıklayıcı **otomobiller** penceresi şöyle görünür:  

 ![Otomatik değişkenler&#45;CSharp](../debugger/media/autos-csharp.png "otomobiller CSharp")  

 Unutmayın değerini `c` 0, çünkü satır `c = 3` henüz yürütülmedi.  

 C++'ta **otomobiller** penceresinde değişkenleri kullanılan en az üç satır geçerli satır önce (yürütme durdurulduğunda satır). Altı Değişkenler bildirirseniz:

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

 Satırında bir kesme noktası ayarlarsanız `e = 5;` çalıştırıp yürütme durduğunda hata ayıklayıcı **otomobiller** penceresi şöyle görünür:  
  
 ![Otomatik değişkenler&#45;Cplus](../debugger/media/autos-cplus.png "otomobiller Cplus")  
  
 Değişken e başlatılmamış olduğundan Not kod satırında `e = 5;` henüz yürütülmedi.  
  
 Dönüş değerleri işlevler ve bazı durumlarda yöntemler de görebilirsiniz. Bkz: [yöntem çağrılarının döndürülen değerlerini görüntüleme](#bkmk_returnValue) aşağıda.  
  
##  <a name="bkmk_returnValue"></a> Yöntem çağrılarının döndürülen değerlerini görüntüleme  
 .NET ve C++ kodu içinde veya dışında bir yöntem çağrısı adımı dönüş değerleri inceleyebilirsiniz. Bu işlevsellik, yöntem çağrısının sonucunu bir yöntemi, bir parametre veya başka bir yöntem dönüş değeri olarak kullanıldığında, örneğin bir yerel değişken depolanmaz yararlıdır.  
  
 Aşağıdaki C# kod iki işlevlerin dönüş değerlerini ekler:  

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

 Bir kesme noktası ayarlayın `int x = sumVars(a, b) + subtractVars(c, d);` satır.  
  
 Hata ayıklama başlatın ve yürütme ilk kesme noktasında böldüğünde basın **F10 (Step Over)**. Aşağıda, görmelisiniz **otomobiller** penceresi:  
  
 ![AutosReturnValueCSharp2](../debugger/media/autosreturnvaluecsharp2.png "AutosReturnValueCSharp2")  
  
## <a name="why-are-variable-values-sometimes-red-in-locals-and-autos-windows"></a>Neden değişken değerleri, yerel ve otomatik değişkenler windows kırmızıyla misiniz?  
Bir değişkenin değerini bazen de kırmızı olduğunu fark edebilirsiniz **Yereller** ve **otomobiller** windows. Bunlar son değerlendirme bu yana değişmiş olan değişken değerlerdir. Değişiklik önceki hata ayıklama oturumundan olabilir veya değer penceresinde değiştiğinden.  
  
## <a name="changing-the-numeric-format-of-a-variable-window"></a>Bir değişken penceresinde sayısal biçimini değiştirme  
Varsayılan sayısal biçim ondalık ancak onaltılı olarak değiştirebilirsiniz. İçinde sağ bir **Yereller** veya **otomobiller** penceresini açın ve seçin **onaltılı görüntü**. Değişiklik tüm hata ayıklayıcı pencerelerinin etkiler.  
  
## <a name="editing-a-value-in-a-variable-window"></a>Bir değişken penceresinde değer düzenleme  
Görünen çoğu değişkenlerin değerleri düzenleyebilirsiniz **otomobiller**, **Yereller**, **izleme**, ve **QuickWatch** windows. Hakkında bilgi için **izleme** ve **QuickWatch** windows için bkz: [izleme ve QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md). Yalnızca, değiştirmek ve yeni değer eklemek istediğiniz değeri çift tıklatın.  
  
Örneğin bir ifadenin bir değer girebilirsiniz `a + b`. Hata ayıklayıcı en geçerli dili ifadeleri kabul eder.  
  
Yerel C++ kodda bir değişken adı bağlamında nitelemek gerekebilir. Daha fazla bilgi için bkz: [bağlamı işleci (C++)](../debugger/context-operator-cpp.md).  
 
Ancak, değerlerini değiştirirken dikkatli olmanız gerekir. Olası bazı sorunlar şunlardır:  
  
-   Bazı ifadeleri değerlendirme bir değişkenin değerini değiştirebilir veya aksi halde, programın durumunu etkiler. Örneğin, değerlendirme `var1 = ++var2` değerini değiştirir `var1` ve `var2`.  
  
     Verileri değiştirme ifadeler için denirse [yan etkileri](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\)), hangi beklenmeyen sonuçlar verebilir, bunları kullanan değilseniz. Bunu yapmadan önce bu tür bir değişiklik sonuçlarını anladığınızdan emin olun.  
  
-   Kayan nokta değerlerini düzenlemek, kesirli bileşenlerin ondalıktan ikiliye dönüştürülmesi nedeniyle küçük yanlışlıklara neden olabilir. Zararsız görünen bir düzenleme bile, kayan nokta değişkenindeki en az önemli bitlerin bazılarının değişmesine neden olabilir.  
  
## <a name="changing-the-window-context"></a>Pencere bağlamını değiştirme  
Kullanabileceğiniz **hata ayıklama konumu** istenen işlevi, iş parçacığı veya değişken windows bağlamının değişiklikleri işlem seçmek için araç. Bir kesme noktası ayarlayın ve hata ayıklamayı Başlat. (Bu araç görmüyorsanız, bu araç çubuğu alanı boş bir parçası tıklayarak etkinleştirebilirsiniz. Araç çubukları listesini görmeniz gerekir; seçin **hata ayıklama konumu**). Kesme noktası isabet, yürütme durur ve aşağıdaki çizimde en alttaki hata ayıklama konumu araç görebilirsiniz.
  
![DebugLocationToolbar](../debugger/media/debuglocationtoolbar.png "DebugLocationToolbar")   
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows hata ayıklayıcı](../debugger/debugger-windows.md)
