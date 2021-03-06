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
ms.openlocfilehash: 5dc83fc859e99a86b1057a02b7cfb9ff2e1232af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42635531"
---
# <a name="using-the-debuggerdisplay-attribute"></a>DebuggerDisplay özniteliğini kullanma
<xref:System.Diagnostics.DebuggerDisplayAttribute> Hata ayıklayıcı değişken pencerelerinde bir nesne, özelliği veya alanı nasıl görüntüleneceğini denetler. Bu öznitelik türleri, temsilciler, özellikleri, alanları ve derlemeler için uygulanabilir.  
  
 `DebuggerDisplay` Özniteliğine sahip bir dize değeri sütununda görüntülenecek olan tek bir bağımsız değişken, tür örnekleri. Bu dize, küme ayraçları içerebilir (`{` ve `}`). Metin çifti küme ayraçlarının içinde bir alan, özelliği veya yöntemi değerlendirilir.  
  
 Bir sınıfın bir geçersiz kılınan varsa `ToString()` yöntemi, hata ayıklayıcı yerine varsayılan geçersiz kılınan yöntemi kullanan `{<typeName>}`. Bu nedenle, siz kıldıysanız `ToString()` yöntemi, hata ayıklayıcı yerine varsayılan geçersiz kılınan yöntemi kullanan`{<typeName>}`, ve kullanmak zorunda değil `DebuggerDisplay`. Her ikisi de kullanırsanız `DebuggerDisplay` özniteliği önceliklidir geçersiz kılınan `ToString()` yöntemi.  
  
 Hata ayıklayıcı bu örtük değerlendirir `ToString()` çağrı bir kullanıcı ayarı bağlıdır **Araçlar / Seçenekler / hata ayıklama** iletişim kutusu. Visual Basic bu örtük uygulamıyor `ToString()` değerlendirme.  
  
> [!IMPORTANT]
>  Varsa **nesnelerin ham yapısını değişkenler pencerelerinde Göster** onay kutusu seçiliyse **Araçlar/Seçenekler / hata ayıklama** iletişim kutusu, ardından `DebuggerDisplay` özniteliği göz ardı edilir.  
  
 Aşağıdaki tablo olası bazı kullanımlarını gösterir `DebuggerDisplay` özniteliği ve örnek çıktı.  
  
|Öznitelik|Değer sütununda görünen çıkış|  
|---------------|------------------------------------------------|  
|`[DebuggerDisplay("x = {x} y = {y}")]`<br /><br /> Bir türü alanları ile kullanılan `x` ve `y`.|`x = 5 y = 18`|  
|`[DebuggerDisplay("String value is {getString()}")]`Parametresi söz dizimi diller arasında değişebilir. Bu nedenle dikkatli kullanın.|`String value is [5, 6, 6]`|  
  
 `DebuggerDisplay` Ayrıca, adlandırılmış parametreleri kabul edebilir.  
  
|Parametreler|Amaç|  
|----------------|-------------|  
|`Name`, `Type`|Bu parametreleri etkileyen **adı** ve **türü** değişken pencerelerini sütunlarının. (Bunlar dizelere Oluşturucu olarak aynı sözdizimini kullanılarak ayarlanabilir.) Bu parametreleri aşırı kullanımı ya da yanlış kullanarak karmaşık çıkış neden olabilir.|  
|`Target`, `TargetTypeName`|Özniteliği derleme düzeyinde kullanıldığında hedef türünü belirtir.|  
  
 Autoexp.cs dosya DebuggerDisplay özniteliği derleme düzeyinde kullanır. Visual Studio .NET nesneleri için kullandığı varsayılan genişletmeleri autoexp.cs dosyayı belirler. DebuggerDisplay özniteliğini kullanma örnekleri için autoexp.cs dosyayı inceleyebilirsiniz veya değiştirebilir ve varsayılan genişletmeleri değiştirmek için autoexp.cs dosyasını derleyin. Değiştirmeden önce autoexp.cs dosyasını yedekleyin emin olun.  
  
 Autoexp.cs oluşturmak için VS2015 için geliştirici komut istemi ayarlama açın ve aşağıdaki komutları çalıştırın  
  
```cmd
cd <directory containing autoexp.cs>  
csc /t:library autoexp.cs  
```  
  
 Sonraki hata ayıklama oturumunda autoexp.dll değişiklikler seçilir.  
  
## <a name="using-expressions-in-debuggerdisplay"></a>DebuggerDisplay içinde ifadeler kullanma  
 Bu yöntem, bir DebuggerDisplay özniteliği ayraçlar arasındaki genel bir ifade kullanabilirsiniz, ancak önerilmez.  
  
 Genel bir DebuggerDisplay ifadesinde örtük erişimi `this` yalnızca hedef türü geçerli örneği için işaretçi. İfade, diğer adlar, yerel öğeler veya işaretçiler erişim yok. İfade özellikleri başvuruyorsa, bu özellikleri özniteliklerinde işlenmez. Örneğin, C# kodu `[DebuggerDisplay("Object {count - 2}")]` görüntüler `Object 6` , alanın `count` 8 oluştu.  
  
 DebuggerDisplay içinde ifadeleri kullanarak aşağıdaki sorunlarına yol açabilir:  
  
-   İfadeleri değerlendirme en pahalı işleminde hata ayıklayıcı ve ifade, görüntülenen her zaman değerlendirilir. Bu kod içerisinde ilerlemeye performans sorunlarına neden olabilir. Örneğin, bir koleksiyon veya listedeki değerleri görüntülemek için kullanılan karmaşık bir ifade öğe sayısı büyük olduğunda çok yavaş olabilir.  
  
-   İfadeler, geçerli yığın çerçevesi dilinin ifade değerlendiricisi tarafından ve değerlendirme ifadesi yazıldığı dili tarafından değerlendirilir. Dilleri farklı olduğunda bu öngörülemeyen sonuçlara neden olabilir.  
  
-   Bir ifadenin değerlendirilmesi, uygulama durumunu değiştirebilirsiniz. Örneğin, bir özelliğinin değerini ayarlayan bir ifade kodu yürütürken özellik değeri değiştirdiği.  
  
 İfade değerlendirmesinin olası sorunları azaltmak yollarından biri, işlemi gerçekleştiren ve bir dize döndürür bir özel özellik oluşturmaktır. DebuggerDisplay özniteliği, bu özel özellik değerini daha sonra görüntüleyebilirsiniz. Aşağıdaki örnek bu düzeni uygular:  
  
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
", Nq" soneki belirten ifade değerlendiricisi, son değer görüntülenirken tırnak işaretlerini (nq = tırnak işareti gerekmez). 
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği kullanma işlemini gösterir `DebuggerDisplay`birlikte `DebuggerBrowseable` ve `DebuggerTypeProxy`. Bir hata ayıklayıcı değişken penceresinde gibi görüntülendiğinde **Watch** penceresinde şuna benzer bir genişletme üretir:  
  
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
