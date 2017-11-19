---
title: "Hızlı Eylemler | Microsoft Docs"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: e173fb7d-c5bd-4568-ba0f-aa61913b3244
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 1ba45a0ac183c4f2249461048277eda7cffad1e9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="quick-actions"></a>Hızlı Eylemler

[Hızlı Eylemler](refactoring-code-generation-quick-actions.md#quick-actions) düzenleme kolayca izin oluşturmak ya da aksi durumda tek bir eylemle kodu değiştirin.  Pek çok hızlı özellikle C# veya Visual Basic uygulanan eylemler olsa da, ayrıca vardır bazı hem C# ve Visual Basic projeler için geçerlidir.  Bunlar ampul simgesini kullanarak uygulanabilir ![küçük ampul simge](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall"), veya tuşuna basarak **Ctrl +.** İmleci kod uygun satırında olduğunda.

Bir kırmızı dalgalı ve Visual Studio ise ampul sorunu gidermeye yönelik bir öneri sahip görürsünüz. Örneği için kırmızı dalgalı tarafından belirtilen bir hata varsa, düzeltmeleri bu hata için kullanılabilir durumda olduğunda bir ampul görünür. Herhangi bir dil için üçüncü tarafların özel tanılama ve öneriler, örneğin bir SDK'ın bir parçası olarak sağlayabilir ve Visual Studio ampuller bu kurallara göre yanar.  

### <a name="to-see-a-light-bulb"></a>Bir ampul görmek için  

1. Çoğu durumda, içinde bir hata var. bir satır halinde şapka taşıdığınızda, fare bir hata noktasında veya düzenleyicinin sol kenar boşluğunda geldiğinizde ampuller kendiliğinden görünür. Kırmızı dalgalı gördüğünüzde, bunun üzerine ampul görüntülenecek gelebilirsiniz. Ayrıca, herhangi bir yere satırda sorunun nerede oluştuğunu gitmek için klavye ve fare kullandığınızda görüntülemek bir ampul neden olabilir.  

2. Tuşuna **Ctrl +.** Ampul çağırma ve olası listesine doğrudan gitmek için bir satır üzerinde herhangi bir yere giderir.  

   ![Ampul fare bekleyerek ile](../ide/media/vs2015_lightbulb_hover.png "VS2017_LightBulb_Hover")  

### <a name="to-see-potential-fixes"></a>Olası düzeltmeleri görmek için  
Ya da aşağı oka veya olası ampul için uygulayabileceğiniz hızlı eylemlerin bir listesini görüntülemek için bağlantıyı düzeltmeleri Göster'i tıklatın.  

![Genişletilmiş ampul](../ide/media/vs2015_lightbulb_hover_expanded.png "VS2017_LightBulb_hover_expanded")

## <a name="common-quick-actions"></a>Genel Hızlı eylemleri
Genel Hızlı hem C# ve Visual Basic kodu için geçerli olan eylemleri bazıları aşağıda verilmiştir.

### <a name="add-missing-casesdefault-caseboth"></a>Eksik durumlarda/varsayılan durumda veya her iki ekleme
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

### <a name="correct-misspelled-type"></a>Doğru yazılmış türü
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

### <a name="remove-unnecessary-cast"></a>Gereksiz atamayı kaldırma
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

### <a name="replace-method-with-property--replace-property-with-method"></a>Replace yöntemi özelliğiyle / özellik yöntemi ile değiştirin
Bu hızlı Eylemler bir yöntem dönüştürecek bir özelliğe veya tersi.  Aşağıdaki örnek, bir özellik değişikliği bir yöntemi gösterir.  Ters bu durum, yalnızca ters *önce* ve *sonra* bölümler.

```csharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```
```vb
Dim MyValue As Integer

' Before
Function GetMyValue() As Integer
    Return MyValue
End Function

' Replace 'GetMyValue' with property

' After
ReadOnly Property MyValue As Integer
    Get
        Return MyValue
    End Get
End Property
```

### <a name="make-method-synchronous"></a>Zaman uyumlu hale yöntemi
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

### <a name="make-method-asynchronous"></a>Zaman uyumsuz hale yöntemi
Kullanırken `await` / `Await` anahtar sözcüğü bir yöntem içinde yöntemi ile işaretlenmiş görünür duruma beklenir `async` / `Async` anahtar sözcüğü.  Bu durum böyle değilse, ancak, hızlı bir eylem, görünür yöntemi zaman uyumsuz yapmanıza izin verir.  Kullanım **yöntemi ya da işlevin zaman uyumsuz hale getirin** hızlı Eylemler menüsünden seçeneği.

```csharp
// Before
int MyAsyncMethod()
{
    return await Task.Run(...);
}

// Make method synchronous

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

' Make method synchronous

' After
Async Function MyAsyncMethod() As Task(Of Integer)
    Return Await Task.Run(...)
End Function
```

### <a name="remove-unnecesary-usingsimports"></a>Gereksiz kullanımları/Imports Kaldır
**Kaldırmak gereksiz kullanımları/Imports** hızlı eylem daha kullanılmayan kaldırılır `using` ve `Import` deyimleri geçerli dosyası için.  Bu öğe seçtiğinizde, kullanılmayan ad alanı içe aktarımlarını hemen kaldırılır.

### <a name="add-usingsimports-for-types-in-reference-assemblies-nuget-packages-or-other-types-in-your-solution"></a>Başvuru derlemeleri, NuGet paketlerini veya diğer türleri çözümünüzdeki kullanımları/Imports türleri ekleme
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

### <a name="convert-to-interpolated-string"></a>Ara değerli dizeye dönüştürme
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

### <a name="remove-merge-conflict-markers"></a>Merge çakışmayı işaretlerini kaldırın
Bu hızlı Eylemler birleştirme çakışmaları sağlayan göre "alma bir değişiklik", çakışan kod ve işaretçiler kaldırır. (Yalnızca Visual Studio 2017 (sürüm 15.3 - Önizleme) içinde kullanılabilir.)

![Yeniden düzenleme - birleştirme Çakışmaları Çöz](../ide/media/vside-refactoring-merge-conflicts.png)

### <a name="add-null-checks-for-parameters"></a>Parametre için null denetimlerinin ekleme
Bu hızlı eylem kodunuzu bir parametre null olup olmadığını bildirmek için bir onay eklemenize olanak sağlar. (Yalnızca Visual Studio 2017 (sürüm 15.3 - Önizleme) içinde kullanılabilir.)

![Yeniden düzenleme - null denetimi ekleme](../ide/media/vside-refactoring-nullcheck.png)

### <a name="constructor-generator-improvements"></a>Oluşturucu üreteci geliştirmeleri
Bir oluşturucu oluştururken, hızlı Bu eylem özellikleri veya oluşturmak için alanları seçmenize olanak sağlar veya boş bir gövdesinden Oluşturucusu oluşturabilir. Varolan bir oluşturucuya çağrısı sitesinden parametreleri eklemek için de kullanabilirsiniz. (Yalnızca Visual Studio 2017 (sürüm 15.3 - Önizleme) içinde kullanılabilir.)

![Yeniden düzenleme - oluşturucular oluştur](../ide/media/vside-refactoring-constructors.png)

### <a name="remove-unused-variables"></a>Kullanılmayan değişkenleri kaldırma
Bu hızlı eylem bildirildi, ancak hiç kullanılmadı değişkenleri kodunuzda kaldırmanıza olanak sağlar. (Yalnızca Visual Studio 2017 (sürüm 15.3 - Önizleme) içinde kullanılabilir.)

![Yeniden düzenleme - kullanılmayan değişkenleri](../ide/media/vside-refactoring-unusedvars.png)

### <a name="generate-overrides"></a>Geçersiz kılmaları oluştur
Bu hızlı eylem sınıfta veya yapı içinde boş bir satırından bir geçersiz kılma oluşturmanıza olanak sağlar. **Çekme üyeleri** geçersiz kılmak için üyeleri seçin iletişim kutusu sağlar. (Yalnızca Visual Studio 2017 (sürüm 15.3 - Önizleme) içinde kullanılabilir.)

![Yeniden düzenleme - geçersiz kılar](../ide/media/vside-refactoring-overrides.png)

![Geçersiz kılmaları iletişim kutusunu yeniden düzenleme-](../ide/media/vside-refactoring-overrides-dialog.png)

### <a name="change-base-for-numeric-literals"></a>Sayısal değişmez değerlerini değiştirme temeli
Bu hızlı eylem tamsayısal bir hazır değer bir temel sayısal sistemden dönüştürmenize olanak sağlar. Örneğin, bir sayı onaltılık veya ikili biçime değiştirebilirsiniz. (Yalnızca Visual Studio 2017 (sürüm 15.3 - Önizleme) içinde kullanılabilir.)

![Yeniden düzenleme - taban değiştirme](../ide/media/vside-refactoring-changebase1.png)

![Yeniden düzenleme - taban değiştirme](../ide/media/vside-refactoring-changebase2.png)

### <a name="insert-digit-separators-into-literals"></a>Değişmez değerler basamak ayırıcıları Ekle
Bu hızlı eylem ayırıcı karakterleri değişmez değerler eklemenize olanak sağlar. (Yalnızca Visual Studio 2017 (sürüm 15.3 - Önizleme) içinde kullanılabilir.)

![Yeniden düzenleme - değişiklik basamak ayırıcıları](../ide/media/vside-refactoring-separators.png)

### <a name="convert-if-construct-to-switch"></a>Dönüştürme **varsa** için oluşturmak **geçiş**
Hızlı Bu eylem dönüştürmenize olanak sağlayan bir **IF-then-else** oluşturmak için bir **geçiş** oluşturun. (Yalnızca Visual Studio 2017 (sürüm 15.3 - Önizleme) içinde kullanılabilir.)

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

## <a name="see-also"></a>Ayrıca Bkz.
* [Kod stilleri ve hızlı Eylemler](code-styles-and-quick-actions.md)
