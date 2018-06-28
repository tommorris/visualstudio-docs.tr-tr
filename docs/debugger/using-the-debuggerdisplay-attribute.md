---
title: DebuggerDisplay özniteliğini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 08/09/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- attributes [C#], debugger
- DebuggerDisplay attribute
- DebuggerDisplayAttribute class
ms.assetid: f4eb7c76-af4e-493b-9ab6-9cb05949d9b3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8da672193dcbe12581122a48559c9027f01e77c9
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057592"
---
# <a name="using-the-debuggerdisplay-attribute"></a>DebuggerDisplay özniteliğini kullanma
[DebuggerDisplayAttribute sınıfı](/dotnet/api/system.diagnostics.debuggerdisplayattribute) bir nesne, özelliği veya alanı hata ayıklayıcı değişken pencerelerini de nasıl görüntüleneceğini denetler. Bu öznitelik türlerini, temsilciler, özellikleri, alanları ve derlemeler için uygulanabilir.  
  
 `DebuggerDisplay` Özniteliğine sahip bir dize değeri sütununda görüntülenecek olan tek bir değişken türü örnekleri. Bu dize köşeli parantez içerebilir (`{` ve `}`). Bir çift köşeli parantez içinde metin alanı, özellik veya yöntem değerlendirilir.  
  
 Bir sınıf bir geçersiz kılınan varsa `ToString()` yöntemi, hata ayıklayıcı kullanan geçersiz kılınan yöntemi yerine varsayılan `{<typeName>}`. Bu nedenle, siz kıldıysanız `ToString()` yöntemi, hata ayıklayıcı yerine varsayılan geçersiz kılınan yöntemi kullanan`{<typeName>}`, ve kullanmak zorunda değil `DebuggerDisplay`. Her ikisini de kullanırsanız, `DebuggerDisplay` özniteliği önceliklidir geçersiz kılınan `ToString()` yöntemi.  
  
 Hata ayıklayıcı olup bu örtük değerlendirir `ToString()` çağrısı bağlı olan bir kullanıcı ayarı, **Araçlar / Seçenekler / hata ayıklama** iletişim kutusu. Visual Basic bu örtük uygulamıyor `ToString()` değerlendirme.  
  
> [!IMPORTANT]
>  Varsa **nesnelerin ham yapısı değişkenleri windows Göster** onay kutusu seçildiğinde, **Araçlar/Seçenekler / hata ayıklama** iletişim kutusu, sonra `DebuggerDisplay` özniteliği göz ardı edilir.  
  
 Aşağıdaki tabloda bazı olası kullanımları gösterilmektedir `DebuggerDisplay` özniteliği ve örnek çıkarır.  
  
|Öznitelik|Değer sütununda görünen çıktı|  
|---------------|------------------------------------------------|  
|`[DebuggerDisplay("x = {x} y = {y}")]`<br /><br /> Alanları türüyle kullanılan `x` ve `y`.|`x = 5 y = 18`|  
|`[DebuggerDisplay("String value is {getString()}")]`Parametre söz dizimi diller arasında farklılık gösterebilir. Bu nedenle dikkatli kullanın.|`String value is [5, 6, 6]`|  
  
 `DebuggerDisplay` Ayrıca adlandırılmış parametreleri kabul edebilir.  
  
|Parametreler|Amaç|  
|----------------|-------------|  
|`Name`, `Type`|Bu parametreler etkileyen **adı** ve **türü** değişken windows sütunlarının. (Bunlar Oluşturucusu aynı sözdizimini kullanarak dizeleri için ayarlanmış olabilir.) Bu parametreler overusing veya yanlış kullanarak kafa karıştırıcı çıkış neden olabilir.|  
|`Target`, `TargetTypeName`|Öznitelik derleme düzeyinde kullanıldığında, hedef türü belirtir.|  
  
 Autoexp.cs dosyanın derleme düzeyinde DebuggerDisplay özniteliğini kullanır. Autoexp.cs dosyası, Visual Studio .NET nesneleri için kullandığı varsayılan genişletmeler belirler. DebuggerDisplay özniteliğini kullanma örnekleri için autoexp.cs dosyasını inceleyin veya değiştirin ve varsayılan genişletmeler değiştirmek için autoexp.cs dosyasını derleyin. Değiştirmeden önce autoexp.cs dosyasını yedeklemek emin olun.  
  
 Autoexp.cs oluşturmak için VS2015 için geliştirici komut istemi yukarı açın ve aşağıdaki komutları çalıştırın  
  
```cmd
cd <directory containing autoexp.cs>  
csc /t:library autoexp.cs  
```  
  
 Sonraki hata ayıklama oturumunda autoexp.dll değişiklikleri çekilmesi.  
  
## <a name="using-expressions-in-debuggerdisplay"></a>DebuggerDisplay içinde ifadeler kullanma  
 DebuggerDisplay özniteliği ayraçlar arasında genel bir ifade kullanabilmenize karşın, bu yöntem önerilmez.  
  
 DebuggerDisplay genel bir ifadede örtük erişimi `this` hedef türü yalnızca geçerli örneği için bir işaretçi. İfade hiçbir diğer adlar, yerel veya işaretçileri erişebilir. İfade özellikleri başvuruyorsa, bu özellikleri özniteliklerinde işlenmez. Örneğin, C# kodu `[DebuggerDisplay("Object {count - 2}")]` görüntüleyecektir `Object 6` , alan `count` 8 oluştu.  
  
 DebuggerDisplay içinde ifadeler kullanarak aşağıdaki sorunlarına yol açabilir:  
  
-   İfadeleri değerlendirme en pahalı hata ayıklayıcı bir işlemdir ve görüntüleneceğini her zaman bir ifadenin. Kod üzerinden atlama bu performans sorunlarına neden olabilir. Örneğin, öğelerin sayısı büyük olduğunda bir koleksiyon ya da liste değerlerini görüntülemek için kullanılan karmaşık bir ifade çok yavaş olabilir.  
  
-   İfadeleri, geçerli yığın çerçevesini dilinin ifade değerlendiricisi tarafından ve ifade yazıldığı dil değerlendiricisi tarafından değerlendirilir. Dilleri farklı olduğunda bu öngörülemeyen sonuçlara neden olabilir.  
  
-   Bir ifade değerlendirme uygulama durumunu değiştirebilirsiniz. Örneğin, bir özelliğin değerini ayarlar bir ifade yürütme kodu özellik değeri değiştirdiği.  
  
 İfade değerlendirme olası sorunları azaltmak için bir işlemi gerçekleştiren ve bir dize döndürür özel bir özellik oluşturarak yoludur. DebuggerDisplay özniteliğini daha sonra bu özel özellik değerini görüntüleyebilirsiniz. Aşağıdaki örnekte bu deseni uygular:  
  
```csharp  
[DebuggerDisplay("{DebuggerDisplay,nq}")]  
public sealed class MyClass   
{      
    public int count { get; set; }      
    public bool flag { get; set; }      
    private string DebuggerDisplay  
   {         
        get  
        {  
             return string.Format("Object {0}", count - 2);  
        }      
    }  
}  
```  
", Nq" soneki belirten son değer görüntülenirken tırnak işaretleri kaldırmak için ifade değerlendiricisi (nq = tırnak işareti gerekmez). 
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir `DebuggerDisplay`, birlikte `DebuggerBrowseable` ve `DebuggerTypeProxy`. Bir hata ayıklayıcı değişken penceresinde gibi görüntülendiğinde **izleme** penceresinde şuna benzer bir genişletme üretir:  
  
|**Ad**|**Değer**|**Türü**|  
|--------------|---------------|--------------|  
|Anahtar|"üç"|{dize} nesnesi|  
|Değer|3|Nesne {int}|  
  
```csharp  
[DebuggerDisplay("{value}", Name = "{key}")]  
internal class KeyValuePairs  
{  
    private IDictionary dictionary;  
    private object key;  
    private object value;  
    public KeyValuePairs(IDictionary dictionary, object key, object value)  
    {  
        this.value = value;  
        this.key = key;  
        this.dictionary = dictionary;  
    }  
  
    public object Key  
    {  
        get { return key; }  
        set  
        {  
            object tempValue = dictionary[key];  
            dictionary.Remove(key);  
            key = value;  
            dictionary.Add(key, tempValue);  
        }  
    }  
  
    public object Value  
    {  
        get { return this.value; }  
        set  
        {  
            this.value = value;  
            dictionary[key] = this.value;  
        }  
    }  
}  
  
[DebuggerDisplay("{DebuggerDisplay,nq}")]  
[DebuggerTypeProxy(typeof(HashtableDebugView))]  
class MyHashtable  
{  
    public Hashtable hashtable;  
  
    public MyHashtable()  
    {  
        hashtable = new Hashtable();    
    }
    
    private string DebuggerDisplay    {        get { return "Count = " + hashtable.Count); }    }  
  
    private class HashtableDebugView  
    {  
        private MyHashtable myhashtable;  
        public HashtableDebugView(MyHashtable myhashtable)  
        {  
            this.myhashtable = myhashtable;  
        }  
  
        [DebuggerBrowsable(DebuggerBrowsableState.RootHidden)]  
        public KeyValuePairs[] Keys  
        {  
            get  
            {  
                KeyValuePairs[] keys = new KeyValuePairs[myhashtable.hashtable.Count];  
  
                int i = 0;  
                foreach (object key in myhashtable.hashtable.Keys)  
                {  
                    keys[i] = new KeyValuePairs(myhashtable.hashtable, key, myhashtable.hashtable[key]);  
                    i++;  
                }  
                return keys;  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DebuggerTypeProxy özniteliğini kullanma](../debugger/using-debuggertypeproxy-attribute.md)   
 [Yönetilen nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-dot-managed-objects.md)   
 [C# içindeki Biçim belirticileri](../debugger/format-specifiers-in-csharp.md)   
 [Hata Ayıklayıcı Görüntü Öznitelikleriyle Hata Ayıklamayı Geliştirme](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)
