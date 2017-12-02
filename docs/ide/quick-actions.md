---
title: "Hızlı Eylemler | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 22a6c84608f8955e3a751af4ee2b9fb113645590
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2017
---
# <a name="quick-actions"></a>Hızlı Eylemler

[Hızlı Eylemler](refactoring-code-generation-quick-actions.md#quick-actions) düzenleme kolayca izin oluşturmak ya da aksi durumda tek bir eylemle kodu değiştirin. Hızlı Eylemler C# ' ta kullanılabilir [C++](/cpp/ide/writing-and-refactoring-code-cpp)ve Visual Basic kod dosyaları. Bazı eylemler için bir dil özeldir ve diğer tüm diller için geçerlidir. Ampul simgesini kullanarak hızlı Eylemler uygulanabilir ![küçük ampul simge](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall"), basarak veya **Ctrl** + **.** İmleci kod uygun satırında olduğunda.

Bir kırmızı dalgalı ve Visual Studio ise ampul sorunu gidermeye yönelik bir öneri sahip görürsünüz. Örneği için kırmızı dalgalı tarafından belirtilen bir hata varsa, düzeltmeleri bu hata için kullanılabilir durumda olduğunda bir ampul görünür. Herhangi bir dil için üçüncü tarafların özel tanılama ve öneriler, örneğin bir SDK'ın bir parçası olarak sağlayabilir ve Visual Studio ampuller bu kurallara göre yanar.

## <a name="to-see-a-light-bulb"></a>Bir ampul görmek için

1. Çoğu durumda, içinde bir hata var. bir satır halinde şapka taşıdığınızda, fare bir hata noktasında veya düzenleyicinin sol kenar boşluğunda geldiğinizde ampuller kendiliğinden görünür. Kırmızı dalgalı gördüğünüzde, bunun üzerine ampul görüntülenecek gelebilirsiniz. Ayrıca, herhangi bir yere satırda sorunun nerede oluştuğunu gitmek için klavye ve fare kullandığınızda görüntülemek bir ampul neden olabilir.

1. Tuşuna **Ctrl** + **.** Ampul çağırma ve olası listesine doğrudan gitmek için bir satır üzerinde herhangi bir yere giderir.

   ![Ampul fare bekleyerek ile](../ide/media/vs2015_lightbulb_hover.png "VS2017_LightBulb_Hover")

## <a name="to-see-potential-fixes"></a>Olası düzeltmeleri görmek için

Ya da aşağı oka veya olası ampul için uygulayabileceğiniz hızlı eylemlerin bir listesini görüntülemek için bağlantıyı düzeltmeleri Göster'i tıklatın.

![Genişletilmiş ampul](../ide/media/vs2015_lightbulb_hover_expanded.png "VS2017_LightBulb_hover_expanded")

## <a name="common-quick-actions"></a>Genel Hızlı eylemleri

Genel Hızlı hem C# ve Visual Basic kodu için geçerli olan eylemleri bazıları aşağıda verilmiştir.
- [Hataları düzeltin Eylemler](#fix)
- [Gereksiz kod kaldırma eylemleri](#remove)
- [Eksik kod ekleme Eylemler](#add)
- [Kod dönüşümleri](#transform)

### <a id="fix"></a>Hataları düzeltin Eylemler

#### <a name="correct-misspelled-type"></a>Doğru yazılmış türü
|  Hata Kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| CS0103, BC30002 | C# ve Visual Basic | Visual Studio 2015 Güncelleştirme 2 |

Visual Studio'da bir türü yanlışlıkla yazıyorsanız, hızlı Bu eylem otomatik olarak onu sizin için düzeltebilirsiniz.  Bu öğeler ampul menüde görürsünüz  **"değişiklik '*yanlış yazılmış türü*'to'*düzeltmek türü*' **.  Örneğin:

```csharp
// Before
private viod MyMethod()
{
}

// Change 'viod' to 'void'

// After
private void MyMethod()
{
}
```

```vb
' Before
Function MyFunction as Intger
End Function

' Change 'Intger' to 'Integer'

' After
Function MyFunction as Integer
End Function
```

#### <a name="resolve-git-merge-conflict"></a>Git merge çakışmayı
|  Hata Kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| CS8300, BC37284  | C# ve Visual Basic | Visual Studio 2017 sürüm 15.3 |

Bu hızlı Eylemler git birleştirme çakışmaları sağlayan göre "alma bir değişiklik", çakışan kod ve işaretçiler kaldırır.  

```csharp
// Before     
private void MyMethod()
{
<<<<<<< HEAD
    if (true)
    {

    }
=======
    if (false)
    {

    }
>>>>>>> upstream
}

// Take changes from 'HEAD'

// After 
private void MyMethod()
{
    if (true)
    {

    }
}
```

#### <a name="make-method-synchronous"></a>Zaman uyumlu hale yöntemi
|  Hata Kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| CS1998, BC42356 | C# ve Visual Basic | Visual Studio 2015 Güncelleştirme 2 |

Kullanırken `async` / `Async` olmasından anahtar sözcüğü bir yöntemi, bu yöntem içinde herhangi bir yerde beklenen `await` / `Await` anahtar sözcüğü de kullanılır.  Bu durum böyle değilse, ancak, hızlı bir eylem, görünür yöntemi zaman uyumlu kaldırarak olmanızı sağlayacak `async` / `Async` anahtar sözcüğü ve dönüş türü değiştirme.  Kullanım **yöntemi zaman uyumlu hale getirin** hızlı Eylemler menüsünden seçeneği.

```csharp
// Before
async Task<int> MyAsyncMethod()
{
    return 3;
}

// Make method synchronous

// After
int MyAsyncMethod()
{
    return 3;
}
```

```vb
' Before
Async Function MyAsyncMethod() As Task(Of Integer)
    Return 3
End Function

' Make method synchronous

' After
Function MyAsyncMethod() As Integer
    Return 3
End Function
```

#### <a name="make-method-asynchronous"></a>Zaman uyumsuz hale yöntemi
|  Hata Kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| CS4032, BC37057 | C# ve Visual Basic | Visual Studio 2017 |

Kullanırken `await` / `Await` anahtar sözcüğü bir yöntem içinde yöntemi ile işaretlenmiş görünür duruma beklenir `async` / `Async` anahtar sözcüğü.  Bu durum böyle değilse, ancak, hızlı bir eylem, görünür yöntemi zaman uyumsuz yapmanıza izin verir.  Kullanım **yöntemi ya da işlevin zaman uyumsuz hale getirin** hızlı Eylemler menüsünden seçeneği.

```csharp
// Before
int MyAsyncMethod()
{
    return await Task.Run(...);
}

// Make method asynchronous

// After
async Task<int> MyAsyncMethod()
{
    return await Task.Run(...);
}
```

```vb
' Before
Function MyAsyncMethod() as Integer
    Return  Await Task.Run(...)
End Function

' Make method asynchronous

' After
Async Function MyAsyncMethod() As Task(Of Integer)
    Return Await Task.Run(...)
End Function
```

### <a id="remove"></a>Gereksiz kod kaldırma eylemleri

#### <a name="remove-unnecesary-usingsimports"></a>Gereksiz kullanımları/Imports Kaldır

|  Geçerli diller |  Desteklenen sürüm |
|  -------------------- | ----------------  |
|  C# ve Visual Basic | Visual Studio 2015 RTW |

**Kaldırmak gereksiz kullanımları/Imports** hızlı eylem daha kullanılmayan kaldırılır `using` ve `Import` deyimleri geçerli dosyası için.  Bu öğe seçtiğinizde, kullanılmayan ad alanı içe aktarımlarını hemen kaldırılır.

#### <a name="remove-unnecessary-cast"></a>Gereksiz atamayı kaldırma
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0004 | C# ve Visual Basic | Visual Studio 2015 RTW |

Bir cast gerektirmeyen başka bir tür türe varsa **gereksiz atamayı kaldırmak** hızlı eylem öğesi kodunuzdan cast kaldırılır.

```csharp
// before
int number = (int)3;

// Remove Unnecessary Cast

// after
int number = 3;
```
```vb
' Before
Dim number as Integer = CType(3, Integer)

' Remove Unnecessary Cast

' After
Dim number as Integer = 3
```

#### <a name="remove-unused-variables"></a>Kullanılmayan değişkenleri kaldırma
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| CS0219, BC42024 | C# ve Visual Basic | Visual Studio 2017 sürüm 15.3 |

Bu hızlı eylem bildirildi, ancak hiç kullanılmadı değişkenleri kodunuzda kaldırmanıza olanak sağlar.

```csharp
// Before
public MyMethod()
{
    var unused = 8;
    var used = 1;
    return DoStuff(used);
}

// Remove unused variables

// After
public MyMethod()
{
    var used = 1;
    return DoStuff(used);
}
```

#### <a name="remove-type-from-default-value-expression"></a>Türünden kaldırmak **varsayılan** değer ifadesi
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0034 | C# ' TA 7.1 + | Visual Studio 2017 sürüm 15.3 |

Bu hızlı eylem değer türü bir varsayılan değer ifadesinden kaldırır ve kullandığı [ `default` değişmez değer](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference) zaman derleyici Infer ifade türü.

```csharp 
// Before
void DoWork(CancellationToken cancellationToken = default(CancellationToken)) { ... }

// Simplify default expression

// After
void DoWork(CancellationToken cancellationToken = default) { ... }

```

### <a id="add"></a>Eksik kod ekleme Eylemler

#### <a name="add-usingsimports-for-types-in-reference-assemblies-nuget-packages-or-other-types-in-your-solution"></a>Başvuru derlemeleri, NuGet paketlerini veya diğer türleri çözümünüzdeki kullanımları/Imports türleri ekleme
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| CS0103, BC30451 | C# ve Visual Basic| Visual Studio 2015 Güncelleştirme 2 |

Diğer projeler çözümünüzdeki bulunan türlerini kullanarak görüntüler hızlı eylemi otomatik olarak diğer gelen etkinleştirilmesi gereken ancak **Araçlar > Seçenekler > C#** veya **temel > Gelişmiş** sekmesi:  

* Başvuru derlemeleri türlerinde kullanımları/Imports önerisi
* NuGet paketlerini türlerinde kullanımları/Imports önerisi

Şu anda içeri aktarılmış durumda, ancak bir referans derlemesini veya NuGet paketi mevcut bir ad alanındaki bir türünü kullanırsanız, etkinleştirildiğinde, kullanarak içe deyimi oluşturulur.

```csharp
// Before
Debug.WriteLine("Hello");

// using System.Diagnostics;

// After
using System.Diagnostics;

Debug.WriteLine("Hello");
```

```vb
' Before
Debug.WriteLine("Hello")

' Imports System.Diagnostics

// After
Imports System.Diagnostics

Debug.WriteLine("Hello")
```

#### <a name="add-missing-casesdefault-caseboth"></a>Eksik durumlarda/varsayılan durumda veya her iki ekleme
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0010 | C# ve Visual Basic| Visual Studio 2017 sürüm 15.3 |

Oluştururken bir `switch` C# ' ta, deyimi veya `Select Case` deyimi Visual Basic'te ise maddeler, varsayılan case deyimi ya da her ikisini de otomatik olarak eklemek için bir kod eylemi kullanabilirsiniz.  İçin boş bir deyimi aşağıdaki gibi:

```csharp
enum MyEnum
{
    Item1,
    Item2,
    Item3
}

...

MyEnum myEnum = MyEnum.Item1;

switch(myEnum)
{
}
```

```vb
Enum MyEnum
    Item1
    Item2
    Item3
End Enum

...

Dim myEnum as MyEnum = MyEnum.Item1

Select Case myEnum
End Select
```

Kullanarak **her ikisi de eklemek** eksik durumları ve varsayılan durumda doldurmanız hızlı eylem aşağıdaki oluşturur:

```csharp
switch(myEnum)
{
    case MyEnum.Item1:
        break;
    case MyEnum.Item2:
        break;
    case MyEnum.Item3:
        break;
    default:
        break;
}
```
```vb
Select Case myEnum
    Case MyEnum.Item1
        Exit Select
    Case MyEnum.Item2
        Exit Select
    Case Else
        Exit Select
End Select
```

#### <a name="add-null-checks-for-parameters"></a>Parametre için null denetimlerinin ekleme
| Geçerli diller |  Desteklenen sürüm |
| -------------------- | ----------------  |
| C# ve Visual Basic| Visual Studio 2017 sürüm 15.3 |

Bu hızlı eylem kodunuzu bir parametre null olup olmadığını bildirmek için bir onay eklemenize olanak sağlar.

```csharp
// Before
class MyClass
{
    public string MyProperty { get; set; }

    public MyClass(string myProperty) // cursor inside myProperty
    {
        MyProperty = myProperty;
    }
}

// Add null check

// After
class MyClass
{
    public string MyProperty { get; set; }

    public MyClass(string myProperty)
    {
        MyProperty = myProperty ?? throw new ArgumentNullException(nameof(myProperty));
    }
}
```

#### <a name="add-argument-name"></a>Bağımsız değişken adı ekleyin
| Geçerli diller |  Desteklenen sürüm |
| -------------------- | ----------------  |
| C# ve Visual Basic| Visual Studio 2017 sürüm 15.3 |

```csharp
// Before
var date = new DateTime(1997, 7, 8);

// Include argument name 'year' (include trailing arguments)

// After
var date = new DateTime(year: 1997, month: 7, day: 8);
```

#### <a name="add-braces"></a>Küme parantezleri Ekle
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0011 | C# | Visual Studio 2017 RTW |

Hızlı Eylem Ekle kaşlı ayraçlar tek satırlı geçici sarmalar `if` deyimleri.

```csharp
// Before
if (true)
    return "hello,world";

// Add braces

// After
if (true) 
{
    return "hello,world";
}
```

#### <a name="add-and-order-modifiers"></a>Ekleme ve değiştiricileri sipariş
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0036 | C# ve Visual Basic| Visual Studio 2017 sürüm 15,5 |
| IDE0040 | C# ve Visual Basic| Visual Studio 2017 sürüm 15,5 |

Bu hızlı eylemler varolan sıralamak ve eksik erişilebilirlik değiştiricileri eklemek sağlayarak değiştiricileri düzenlemeye yardımcı.

```csharp
// Before
enum Color
{
    Red, White, Blue
}

// Add accessibility modifiers

// After
internal enum Color
{
    Red, White, Blue
}
```
```csharp
// Before
static private int thisFieldIsPublic;

// Order modifiers

// After
private static int thisFieldIsPublic;

```

### <a id="transform"></a>Kod dönüşümleri

#### <a name="convert-if-construct-to-switch"></a>Dönüştürme **varsa** için oluşturmak **geçiş**
| Geçerli diller |  Desteklenen sürüm |
| -------------------- | ----------------  |
| C# ve Visual Basic| Visual Studio 2017 sürüm 15.3 |

Hızlı Bu eylem dönüştürmenize olanak sağlayan bir **IF-then-else** oluşturmak için bir **geçiş** oluşturun.

```csharp
// Before
if (obj is string s)
{
  Console.WriteLine("obj is a string: " + s);
}

else if (obj is int i && i > 10)
{
  Console.WriteLine("obj is an int greater than 10");
}

// Convert to switch

// After
switch (obj)
{
  case string s:
    Console.WriteLine("Obj is a string: " + s);
    break;
  case int i when i > 10:
    Console.WriteLine("obj is an int greater than 10");
    break;
}
```

```vb
' Before
If TypeOf obj Is String s Then
    Console.WriteLine("obj is a string: " + s)
Else If TypeOf obj Is Integer i And i > 10 Then
    Console.WriteLine("obj is an int greater than 10")
End If

' Convert to switch

' After
Select Case obj
  Case String s
    Console.WriteLine("Obj is a string: " + s)
    Exit Sub
  Case Integer i when i > 10
    Console.WriteLine("obj is an int greater than 10")
    Exit Sub
End Select
```

#### <a name="convert-to-interpolated-string"></a>Ara değerli dizeye dönüştürme
| Geçerli diller |  Desteklenen sürüm |
| -------------------- | ----------------  |
| C# ' ta 6.0 + ve Visual Basic 14 + | Visual Studio 2017 RTW |

[Ara değerli dizeler](/dotnet/csharp/language-reference/keywords/interpolated-strings) katıştırılmış değişkenleri, benzer dizelerle ifade etmek için kolay bir yoludur  **[String.Format](https://msdn.microsoft.com/library/system.string.format.aspx)**  yöntemi.  Bu hızlı eylem birleştirilmiş veya kullanarak dizeleri olduğu durumlarda tanıdığı **String.Format**ve kullanım Ara değerli bir dize olarak değiştirir.

```csharp
// Before
int num = 3;
string s = string.Format("My string with {0} in the middle", num);

// Convert to interpolated string

// After
int num = 3;
string s = $"My string with {num} in the middle";
```
```vb
' Before
Dim num as Integer = 3
Dim s as String = String.Format("My string with {0} in the middle", num)

' Convert to interpolated string

' After
Dim num as Integer = 3
Dim s As String = $"My string with {num} in the middle"
```

#### <a name="use-object-initializers"></a>Nesne başlatıcıları kullanın
| Tanılama kimliği | Geçerli diller | Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0017 | C# ve Visual Basic | Visual Studio 2017 RTW |

Bu hızlı eylem kullanmanıza olanak tanır [nesne başlatıcıları](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) tne oluşturucusu ve sahip ek satırları atama deyimleri çağırma yerine.

```csharp
// Before
var c = new Customer();
c.Age = 21;

// Object initialization can be simplified

// After
var c = new Customer() { Age = 21 };
```
```vb
' Before
Dim c = New Customer()
c.Age = 21

' Object initialization can be simplified

' After
Dim c = New Customer() With {.Age = 21}
```

#### <a name="use-collection-initializers"></a>Koleksiyon başlatıcıları kullanın
| Tanılama kimliği | Geçerli diller | Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0028 | C# ve Visual Basic | Visual Studio 2017 RTW |

Bu hızlı eylem kullanmanıza olanak sağlayan [koleksiyon başlatıcıları](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) birden fazla çağrı yerine `Add` sınıfınızın yöntemi.

```csharp
// Before
var list = new List<int>();
list.Add(1);
list.Add(2);
list.Add(3);

// Collection initialization can be simplified

// After
var list = new List<int> { 1, 2, 3 };
```
```vb
' Before
Dim list = New List(Of Integer)
list.Add(1)
list.Add(2)
list.Add(3)

' Collection initialization can be simplified

' After
Dim list = New List(Of Integer) From {1, 2, 3}

```  

#### <a name="convert-auto-property-to-full-property"></a>Tam özelliğine otomatik özelliği Dönüştür
|  Geçerli diller |  Desteklenen sürüm |
|  -------------------- | ----------------  |
| C# ve Visual Basic | Visual Studio 2017 sürüm 15,5 |

Bu hızlı eylem tam bir özellik için bir otomatik özelliği dönüştürmenize olanak sağlar ve bunun tam tersi.

```csharp
// Before
private int MyProperty { get; set; }

// Convert to full property

// After
private int MyProperty
{
    get { return _myProperty; }
    set { _myProperty = value; } 
}
```
```vb
' Before
Public Property Name As String

' Convert to full property

' After
Private _Name As String

Public Property Name As String
    Get
        Return _Name
    End Get
    Set
        _Name = Value
    End Set
End Property

```

#### <a name="convert-block-body-to-expression-bodied-member"></a>Blok gövde ifade bodied üyesine Dönüştür
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0021 27 | C# ' TA 6.0 + | Visual Studio 2017 RTW |

Bu hızlı eylemi ifade bodied üyeleri yöntemleri, Oluşturucular, işleçleri, özellikleri, dizin oluşturucular ve erişimcileri bloğu gövdeleri dönüştürmek sağlar.

```csharp
//Before
class MyClass4
{
    private int _myProperty;

    public int MyProperty
    {
        get { return _myProperty; }
        set
        {
            _myProperty = value;
        }
    }

    public MyClass4(int myProperty)
    {
        MyProperty = myProperty;
    }

    public void PrintProperty()
    {
        Console.WriteLine(MyProperty);
    }
}

// Use expression body for accessors/constructors/methods

// After
class MyClass4
{
    private int _myProperty;

    public int MyProperty
    {
        get => _myProperty;
        set => _myProperty = value;
    }

    public MyClass4(int myProperty) => MyProperty = myProperty;

    public void PrintProperty() => Console.WriteLine(MyProperty);
}
```

#### <a name="convert-anonymous-function-to-local-function"></a>Yerel işleve Çevir anonim işlevi
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0039 | C# ' TA 7.0 + | Visual Studio 2017 sürüm 15,5 |

Bu hızlı eylem yerel işlevlerini anonim işlevler dönüştürür.

```csharp 
// Before
Func<int, int> fibonacci = null;
fibonacci = (int n) =>
{
    return n <= 1 ? 1 : fibonacci(n - 1) + fibonacci(n - 2);
};

// Use local function

// After
int fibonacci(int n)
{
    return n <= 1 ? 1 : fibonacci(n-1) + fibonacci(n-2);
}

```

#### <a name="convert-referenceequals-to-is-null"></a>Dönüştürme `ReferenceEquals` için`is null`
|  Tanılama kimliği | Geçerli diller |  Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0041 | C# ' TA 7.0 + | Visual Studio 2017 sürüm 15,5 |

Bu hızlı eylemi kullanımını öneren [desen eşleştirme](/dotnet/csharp/pattern-matching) yerine ```ReferenceEquals``` kodlama düzenini, mümkün olduğunda.

```csharp
// Before
var value = "someString";
if (object.ReferenceEquals(value, null))
{
    return;
}

// Use 'is null' check

// After
var value = "someString";
if (value is null)
{
    return;
}
```

#### <a name="introduce-pattern-matching"></a>Desen eşleştirme tanıtır
| Tanılama kimliği | Geçerli diller | Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0020 | C# ' TA 7.0 + | Visual Studio 2017 RTW |
| IDE0019 | C# ' TA 7.0 + | Visual Studio 2017 RTW |

Bu hızlı eylemi kullanımını öneren [desen eşleştirme](/dotnet/csharp/pattern-matching) atamalar ve null denetimlerinin C# ile.   

```csharp
// Before
if (o is int) 
{
    var i = (int)o; 
    ... 
}

// Use pattern matching

// After
if (o is int i) 
{
    ...
}

```
```csharp
// Before
var s = o as string;
if (s != null) 
{
    ...
}

// Use pattern matching

// After
if (o is string s) 
{
    ...
}
```

#### <a name="change-base-for-numeric-literals"></a>Sayısal değişmez değerlerini değiştirme temeli
| Geçerli diller | Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| C# ' ta 7.0 + ve Visual Basic 14 + | Visual Studio 2017 sürüm 15.3 |

Bu hızlı eylem tamsayısal bir hazır değer bir temel sayısal sistemden dönüştürmenize olanak sağlar. Örneğin, bir sayı onaltılık veya ikili biçime değiştirebilirsiniz. 

```csharp
// Before
int countdown = 2097152;

// Convert to hex

// After
int countdown = 0x200000;
```
```vb
' Before
Dim countdown As Integer = 2097152

' Convert to hex

' After
Dim countdown As Integer = &H200000
```

#### <a name="insert-digit-separators-into-literals"></a>Değişmez değerler basamak ayırıcıları Ekle
| Geçerli diller | Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| C# ' ta 7.0 + ve Visual Basic 14 + | Visual Studio 2017 sürüm 15.3 |

Bu hızlı eylem ayırıcı karakterleri değişmez değerler eklemenize olanak sağlar.  

```csharp
// Before
int countdown = 1000000;

// Separate thousands

// After
int countdown = 1_000_000;
```
```vb
' Before
Dim countdown As Integer = 1000000

' Separate thousands

' After
Dim countdown As Integer = 1_000_000
```

#### <a name="use-explicit-tuple-names"></a>Açık tanımlama grubu adlarını kullanın
| Tanılama kimliği | Geçerli diller | Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0033 | C# ' ta 7.0 + ve Visual Basic 15 + | Visual Studio 2017 RTW |

Bu hızlı eylem açık tanımlama grubu adı kullanıldığı Item1, Item2 vb. yerine alanları tanımlar.

```csharp
// Before
(string name, int age) customer = GetCustomer();
var name = customer.Item1;

// Use explicit tuple name

// After
(string name, int age) customer = GetCustomer();
var name = customer.name;
```
```vb
' Before
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.Item1

' Use explicit tuple name

' After
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.name
```

#### <a name="use-inferred-names"></a>Adları çıkarımı yapılan kullan
| Tanılama kimliği | Geçerli diller | Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0037 | C# | Visual Studio 2017 v. 15.5 |
| IDE0037 | C# ' TA 7.1 + | Visual Studio 2017 v. 15.5 |

Anonim türler üye adlarında zaman kullanıcılar kullanabilir çıkışı bu hızlı Eylemler noktası yapılandırılacağını veya kullanım C# 7.1'ın tanımlama grubu öğe adları çıkarımı yapılan.

```csharp 
// Before
var anon = new { age = age, name = name };

// Use inferred member name

// After
var anon = new { age, name };
```
```csharp
// Before
var tuple = (age: age, name: name);

// Use inferred tuple element name

// After
var tuple = (age, name);

```

#### <a name="deconstruct-tuple-declaration"></a>Tuple bildirimi deconstruct
| Tanılama kimliği | Geçerli diller | Desteklenen sürüm |
| ------- | -------------------- | ----------------  |
| IDE0042 | C# ' TA 7.0 + | Visual Studio 2017 v. 15.5 |

Bu hızlı eylem tanımlama grubu değişken bildirimleri deconstruct olanak sağlar. 

```csharp 
// Before
var person = GetPersonTuple();
Console.WriteLine($"{person.name} {person.age}");

(int x, int y) point = GetPointTuple();
Console.WriteLine($"{point.x} {point.y}");

//Deconstruct variable declaration

// After
var (name, age) = GetPersonTuple();
Console.WriteLine($"{name} {age}");

(int x, int y) = GetPointTuple();
Console.WriteLine($"{x} {y}");
```

## <a name="see-also"></a>Ayrıca Bkz.
* [Kod stilleri ve hızlı Eylemler](code-styles-and-quick-actions.md)  
* [Yazma ve yeniden düzenleme kod (C++)](/cpp/ide/writing-and-refactoring-code-cpp)
