---
title: "Visual Studio'da değişkenleri bir izleme ayarlama | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 04/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.watch
helpviewer_keywords:
- debugging [Visual Studio], Watch window
- expressions [debugger], evaluating
- variables [debugger], evaluating
- expression evaluation
- registers, evaluating
- debugging [Visual Studio], expression evaluation
ms.assetid: d5c18377-2a0e-4819-a645-407e24ccc58c
caps.latest.revision: "45"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8792c9ed175d2ced5d9c10cc19b2d222f4d839a8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="set-a-watch-on-variables-using-the-watch-and-quickwatch-windows-in-visual-studio"></a>Bir izleme izleme ve QuickWatch Windows Visual Studio kullanarak değişkenleri ayarlayın
Hata ayıklarken, kullanabileceğiniz **izleme** (**hata ayıklama > Windows > İzleme > İzle (1, 2, 3, 4)**) ve **QuickWatch** (değişkeni sağ /  **Hata ayıklama > QuickWatch**) değişkenleri ve ifadeler izlemek için windows.  Aralarındaki fark **izleme** penceresi birkaç değişkenleri görüntüleyebilir sırada **QuickWatch** penceresi, aynı anda tek bir değişken görüntüler.

Windows, yalnızca hata ayıklama oturumu sırasında kullanılabilir. 
  
## <a name="observing-a-single-variable-with-quickwatch"></a>QuickWatch ile tek bir değişken Gözlemleme  
 Kullanabileceğiniz **QuickWatch** tek bir değişken izlemek için penceresi. Örneğin, aşağıdaki kodu varsa:  
  
```CSharp
static void Main(string[] args)  
{  
    int a, b;  
    a = 1;  
    b = 2;  
    for (int i = 0; i < 10; i++)  
    {  
        a = a + b;  
    }   
}  
```  
  
 Bir değişken QuickWatch penceresinde aşağıdaki gibi görebilirsiniz:  
  
1.  Bir kesme noktası ayarlayın `a = a + b;` satır.  
  
2.  Hata ayıklama başlatılamıyor. Yürütme kesme noktasında durur.  
  
3.  Açık **QuickWatch** penceresi (sağ tıklayın ardından **QuickWatch**, veya **SHIFT + F9**).

    Bir değişkende görmelisiniz **değerleri** penceresinde, 1 değerine sahip.

    ![QuickWatch ifade](../debugger/media/watchexpression.png "QuickWatchExpression")  

    Değişkeni kullanan bir ifade değerlendirmek istiyorsanız, bir ifade gibi eklemek `a + b` için **ifade** penceresini açın ve **yeniden**. 
  
4.  Değişkeni eklemek **izleme** penceresinden **QuickWatch** tıklayarak **Gözcü Ekle**. 

    > [!NOTE]
    > **QuickWatch** penceredir bir modal iletişim kutusu penceresinin böylece açık olduğu sürece hata ayıklama devam edemiyor.  
  
5.  Kapat **QuickWatch** penceresi. Değer gözlemleyin sırada hata ayıklama devam artık **izleme** penceresi.  
  
## <a name="observing-variables-with-the-watch-window"></a>Gözlemci değişkenlerle Gözcü penceresi  
 Birden çok değişkenlerle gözleyebilirsiniz **izleme** penceresi. Örneğin, aşağıdaki kodu varsa:  
  
```C++  
int main()
{
    int a, b, c;
    a = 1;
    b = 2;
    c = 0;

    for (int i = 0; i < 10; i++)
    {
        a++;
        b *= 2;
        c = a + b;
    }

    return 0;
}
  
```  
  
 Üç değişkenlerin değerleri Gözcü penceresi aşağıdaki şekilde ekleyin:  
  
1.  Bir kesme noktası ayarlayın `c = a + b;` satır.  
  
2.  Hata Ayıklamayı Başlat (**F5**). Yürütme kesme noktasında durur.  
  
3.  Gözcü penceresi açın (**hata ayıklama > Windows > İzleme > İzleme 1**, veya **CTRL + ALT + W, 1**).  
  
4.  Ekleme `a` ilk satırına değişken `b` ikinci satır değişken ve `c` değişken üçüncü satır.

    Boş bir satırı tıklatarak ve değişken adını yazarak değişkenleri ekleyebilirsiniz.
  
5.  Hata ayıklama devam (basın **F11** hata ayıklayıcı ilerletmek için).  
  
 Değişken değerleri üzerinden yineleme olarak değiştirme görmelisiniz `for` döngü.  
  
 Yerel kodda programlama, bazen bir değişken adı veya bir değişken adı içeren bir ifade bağlamında nitelemek gerekebilir. İşlev, kaynak dosyası ve bir değişkeni bulunduğu modülü bağlamdır. Bağlam nitelemek varsa, bağlam işleci sözdizimini kullanabilirsiniz. Daha fazla bilgi için bkz: [bağlamı işleci (C++)](../debugger/context-operator-cpp.md).  
  
## <a name="observing-expressions-with-the-watch-window"></a>Gözlemci ifadelerle Gözcü penceresi  
 Şimdi bir ifade kullanmayı deneyelim. Hata ayıklayıcı tarafından tanınan geçerli bir ifade ekleyebilirsiniz.  
  
 Örneğin, önceki bölümde listelenen kodu varsa, bu gibi üç değerlerin ortalamasını elde edebilirsiniz:  
  
 ![Gözcü deyimi](../debugger/media/watchexpression.png "WatchExpression")  
  
 Genel olarak, ifadelerinde değerlendirmek için kuralları **izleme** penceresinde kodlama dilinizi ifadelerinde değerlendirmek için kurallar aynı bulunur. İfadeniz bir sözdizimi hatası varsa, Kod düzenleyicisinde görür aynı derleyici hatası bekleyebilirsiniz. Örnek buradadır:  
  
 ![İfade hata izleme](../debugger/media/watchexpressionerror.png "WatchExpressionError")  
  
##  <a name="bkmk_refreshWatch"></a>Eski Gözcü değerlerini yenileme  
 Bazı durumlarda bir yenileme simgesi (döngüsel bir ok) görebilirsiniz ne zaman bir ifadenin değerlendirileceği içinde **izleme** penceresi.  Özellik değerlendirmesi kapalı varsa, örneğin, (**Araçlar > Seçenekler > hata ayıklama > özellik değerlendirmesi ve diğer dolaylı işlev çağrılarını etkinleştirme**), ve aşağıdaki kodu sahip:  
  
```CSharp  
static void Main(string[] args)  
{  
    List<string> list = new List<string>();  
    list.Add("hello");  
    list.Add("goodbye");  
}  
  
```  
  
 Bir izleme ayarlarsanız `Count` özellik listesi, aşağıdakine benzer görmeniz gerekir:  
  
 ![RefreshWatch](../debugger/media/refreshwatch.png "RefreshWatch")  
  
 Önceki çizimde, bir hata veya eski bir değer gösterir. Simgesine tıklayarak değeri genellikle yenileyebilirsiniz, ancak bazı durumlarda yenilemeniz değil tercih edebilirsiniz. İlk neden değeri değil değerlendirildiğinde bilmeniz gerekir.  
  
 Simgenin üzerine kullanıyorsanız, bir araç ipucu neden ifade değil Hesaplandı hakkında bilgi sağlar.  Circling okları görünüyorsa, ifade aşağıdaki nedenlerden birinden dolayı Hesaplandı değil:  
  
-   İfade Hesaplandı gibi bir hata oluştu. Örneğin, bir zaman aşımı oluşmuş olabilir veya bir değişken kapsamı dışında silinmiş olabilir.  
  
-   İfade bir yan etkisi uygulamadaki tetikleyebilir bir işlev çağrısı içeriyor (bkz [yan etkiler ve ifadeler](#bkmk_sideEffects)).  
  
-   Özellikleri ve hata ayıklayıcısı tarafından dolaylı işlev çağrıları otomatik değerlendirme kapalı (**Araçlar > Seçenekler > hata ayıklama > özellik değerlendirmesi ve diğer dolaylı işlev çağrılarını etkinleştirme**), ve ardından ifade olamaz otomatik olarak değerlendirilir.  
  
 Değer yenilemek için Yenile simgesine tıklayın veya Ara çubuğu tuşlarına basın. Hata ayıklayıcı ifade yeniden dener. Özellikleri ve diğer dolaylı işlev çağrıları otomatik değerlendirme kapatıldığı için yenileme simgesi görüntüleniyorsa, ifade değerlendirilebilir.  
  
 İş parçacığı benzer iki dalgalı çizgiler ile bir daire simge görürseniz, potansiyel iş parçacıkları arası bağımlılık nedeniyle ifade Hesaplandı değil. Diğer bir deyişle, kodu değerlendirme, geçici olarak çalıştırmak için uygulamanızda başka bir iş parçacığı gerektirir. Kesme modunda olduğunda, uygulamanızdaki tüm iş parçacıklarının genellikle durdurulur. Geçici olarak çalıştırmak başka bir iş parçacığı izin vererek olabilir beklenmeyen etkiler, programın durumunu ve olayları kesme noktaları ve bu iş parçacıklarında oluşturulan özel durumları gibi yoksaymak hata ayıklayıcı neden olur.  
  
##  <a name="bkmk_sideEffects"></a>Yan etkiler ve ifadeler  
 Bazı ifadeleri değerlendirme bir değişkenin değerini değiştirebilir veya aksi halde, programın durumunu etkiler. Örneğin, aşağıdaki ifade değerlendirme değerini değiştirir `var1`:  
  
```  
var1 = var2  
```  
  
 Bu kodu neden olabilir bir [yan etkisi](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\)). Yan etkiler hata ayıklama daha zor programınız çalışır değiştirerek yapabilirsiniz.  
  
 Yalnızca ilk onu girdiğinizde sonra yan etkisi bilinen bir ifade değerlendirilir. Sonraki değerlendirme devre dışı bırakılır. El ile yanındaki değerinin göründüğü güncelleştirme simgeye tıklayarak bu davranışı geçersiz kılabilirsiniz.  
  
 Tüm yan etkileri önlemek için bir yol olduğundan otomatik İşlev değerlendirmesi devre dışı bırakma (**Araçlar > Seçenekler > hata ayıklama > özellik değerlendirmesi ve diğer dolaylı işlev çağrılarını etkinleştirme**).  
  
 Değerlendirme özellikleri ya da dolaylı işlev çağrıları devre dışı bırakıldığında kullanarak değerlendirme zorlayabilirsiniz **ac** biçimi değiştiricisi (C# için yalnızca). Bkz: [biçim belirticileri C#](../debugger/format-specifiers-in-csharp.md).  
  
## <a name="bkmk_objectIds"></a>Gözcü penceresi (C# ve Visual Basic) içinde nesne kimlikleri kullanma  

 Belirli bir nesnenin davranışını gözlemlemek istediğiniz zaman zamanlar vardır. Örneğin, bu değişken fazlası kapsam dışında sonra yerel bir değişkeni tarafından başvurulan nesne izlemek isteyebilirsiniz. C# ve Visual Basic nesne başvuru türleri belirli örnekleri için kimlikleri oluşturabilir ve bunları Gözcü penceresi ve kesme noktası koşulları kullanın. Nesne Kimliği hizmetlerinde hata ayıklama ortak dil çalışma zamanı tarafından (CLR) oluşturulur ve nesneyle ilişkilendirilmiş.  
  
> [!NOTE]
>  Nesne kimlikleri zayıf başvurular oluşturun ve nesneyi toplanacak engelleyen değil. Bunlar, yalnızca geçerli hata ayıklama oturumu için geçerli olur.  
  
 Aşağıdaki kodda bir yöntem oluşturur bir `Person` yerel bir değişken, ancak kullanarak istediğiniz ne yaptığını öğrenmek `Person`ait farklı bir yöntem adıdır:  
  
```CSharp  
class Person  
{  
    public Person(string name)  
    {  
        Name = name;  
    }  
    public string Name { get; set; }  
}  
  
public class Program  
{  
    List<Person> _people = new List<Person>();  
    public static void Main(string[] args)  
    {  
        MakePerson();  
        DoSomething();  
    }  
  
    private static void MakePerson()  
    {  
        var p = new Person("Bob");  
        _people.Add(p);  
    }  
  
    private static void DoSomething()  
    {  
        // more processing  
         Console.WriteLine("done");  
    }  
}  
  
```  
  
 Bir başvuru ekleyebilir `Person` nesnesinde **izleme** penceresi şekilde:  
  
1.  Bir kesme noktası, nesne oluşturulduktan sonra biraz zaman kodda ayarlayın.  
  
2.  Hata ayıklama başlatın ve yürütme kesme durduğunda değişken bulun **Yereller** penceresinin sağ tıklatın ve seçin **olun nesne kimliği**.  
  
3.  Görmeniz gerekir bir  **$**  bir süre içinde artı **Yereller** nesne kimliği temsil eden penceresi  
  
4.  Nesne Kimliği Gözcü penceresi ekleyin.  
  
5.  Nesne davranışını izlemek istediğiniz bir kesme noktası ayarlayın.  Önceki kodda, olacaktır `DoSomething()` yöntemi.  
  
6.  Hata ayıklama devam etmek ve yürütme durduğunda `DoSomething()` yöntemi, **izleme** penceresinde `Person` nesnesi.  
  
> [!NOTE]
>  Nesnenin özelliklerini gibi görmek istediğinizde `Person.Name` yukarıdaki örnekte, özellik değerlendirmesi etkinleştirmiş olmanız gerekir.  
  
## <a name="using-registers-in-the-watch-window-c-only"></a>Gözcü penceresi (yalnızca C++) kayıtları kullanma  
 Yerel kodda hata ayıklama, değişken adları kullanarak yanı sıra yazmaç adları ekleyebilirsiniz  **$ \<adını kaydetmek >** veya  **@ \<adını kaydetmek >**.  Daha fazla bilgi için bkz: [sözde değişkenler](../debugger/pseudovariables.md).  
  
## <a name="dynamic-view-and-the-watch-window"></a>Dinamik Görünüm ve Gözcü penceresi  
 Bazı komut dosyası dilleri (örneğin, JavaScript veya Python) dinamik kullanın veya [yazarak duck](https://en.wikipedia.org/wiki/Duck_typing), ve .NET dillerinde (sürüm 4.0 ve üstü) olduğundan normal hata ayıklama pencerelerini kullanarak gözlemlemek zor olan nesneler destek bunlar çalışma zamanı özellikleri ve görüntülenemiyor yöntemleri olabilir.  
  
 Gözcü penceresi uygulayan bir türden oluşturulan bir nesne görüntülendiğinde [IDynamicMetaObjectProvider arabirimi](https://docs.microsoft.com/en-us/dotnet/api/system.dynamic.idynamicmetaobjectprovider?view=netframework-4.7), özel bir hata ayıklayıcı ekler **dinamik Görünüm** düğüme **otomatik değişkenler**  görüntüler. Bu düğüm dinamik Nesne dinamik üyeleri gösterir, ancak üye değerlerinin düzenlenmesine izin vermiyor.  
  
 Tüm alt sağ tıklattığınızda, bir **dinamik Görünüm** ve **Gözcü Ekle**, bir dinamik Nesne nesneye çevirir yeni bir izleme değişkeni hata ayıklayıcı ekler. Diğer bir deyişle, **nesne adı** olur (**(dinamik) nesne). Ad**.  
  
 Üyelerini değerlendiren bir **dinamik Görünüm** yan etkileri olabilir. Yan etkileri nelerdir açıklama için bkz: [yan etkiler ve ifadeler](#bkmk_sideEffects). C# ' ta hata ayıklayıcı otomatik olarak gösterilen değerleri yeniden değil **dinamik Görünüm** adım zaman yeni kod satırına. Visual Basic for aracılığıyla ifadeleri eklenen **dinamik Görünüm** otomatik olarak yenilenir.  
  
 Dinamik görünüm değerlerini yenileme hakkında yönergeler için bkz: [güncel yenileme Gözcü değerlerini](#bkmk_refreshWatch).  
  
 Yalnızca görüntülemek istiyorsanız, **dinamik Görünüm** bir nesne için kullandığınız **dinamik** belirticisi Biçimlendir:  
  
-   C# ' ta: **ObjectName, dinamik**  
  
-   Visual Basic:: **$dynamic, ObjectName**  
  
 **Dinamik Görünüm** de COM nesneleri için hata ayıklama deneyimini geliştirir. Hata ayıklayıcı sarmalanmış bir COM nesnesi karşılaştığında **System.__ComObject**, onu ekler bir **dinamik Görünüm** düğüm nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows hata ayıklayıcı](../debugger/debugger-windows.md)
