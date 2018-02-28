---
title: "Öznitelik sözlüğü | Microsoft Intellitest Geliştirici Test aracı | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliTest, Attribute glossary
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 0eab751276537de30de095d200fc0f0ffcb4ad43
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="attribute-glossary"></a>Öznitelik sözlüğü

## <a name="attributes-by-namespace"></a>Ad alanı göre öznitelikler

* **Microsoft.Pex.Framework**
  * [PexAssumeNotNull](#pexassumenotnull)
  * [PexClass](#pexclass)
  * [PexGenericArguments](#pexgenericarguments)
  * [PexMethod](#pexmethod)
     - [PexExplorationAttributeBase](#pexexplorationattributebase)<p />

* **Microsoft.Pex.Framework.Settings**
  * [PexAssemblySettings](#pexassemblysettings)<p />

* **Microsoft.Pex.Framework.Instrumentation**
  * [PexAssemblyUnderTest](#pexassemblyundertest)
  * [PexInstrumentAssembly](#pexinstrumentassemblyattribute)<p />

* **Microsoft.Pex.Framework.Using**
  * [PexUseType](#pexusetype)<p />

* **Microsoft.Pex.Framework.Validation**
  * [PexAllowedException](#pexallowedexception)
  * [PexAllowedExceptionFromAssembly](#pexallowedexceptionfromassembly)
  * [PexAllowedExceptionFromType](#pexallowedexceptionfromtype)
  * [PexAllowedExceptionFromTypeUnderTest](#pexallowedexceptionfromtypeundertest)

<a name="pexassumenotnull"></a>
## <a name="pexassumenotnull"></a>PexAssumeNotNull

Bu öznitelik governed değeri olamaz onaylar **null**. İçin eklenebilir:

* bir **parametresi** parametreli test yöntemi

  ```
  // assume foo is not null
  [PexMethod]
  public void SomeTest([PexAssumeNotNull]IFoo foo, ...) {}
  ```

* bir **alan**

  ```
  public class Foo {
     // this field should not be null
     [PexAssumeNotNull]
     public object Bar;
  }
  ```

* bir **türü**

  ```
  // never consider null for Foo types
  [PexAssumeNotNull]
  public class Foo {}
  ```

Ayrıca test derleme, test donanımı veya test yöntemi eklenebilecek; Bu durumda ilk bağımsız değişken hangi alan veya türü varsayımlar uygulamak belirtmeniz gerekir. Öznitelik türü için geçerlidir, bu biçimsel türündeki tüm alanlar için geçerlidir.

<a name="pexclass"></a>
## <a name="pexclass"></a>PexClass

Bu öznitelik içeren bir sınıf işaretler *explorations*. Mstest'i eşdeğerdir **TestClassAttribute** (veya NUnit **TestFixtureAttribute**). Bu öznitelik isteğe bağlıdır.

Sınıflar ile işaretli [PexClass](#pexclass) olmalıdır *varsayılan oluşturulabilir*:

* Genel olarak dışarı aktarılan türü
* varsayılan oluşturucu
* soyut değil

Sınıfı bu gereksinimlerini karşılamıyorsa, bir hata bildirilir ve araştırması başarısız olur.

Bu sınıfları oluşturmak için de önemle önerilir **kısmi** Intellitest bölümü sınıfının ancak ayrı bir dosyada yeni testleri oluşturabilmesi. Bu yaklaşım nedeniyle birçok sorunu çözer [görünürlük](input-generation.md#visibility) ve C# tipik bir tekniktir.

**Ek paketi ve kategorileri**:

```
[TestClass] // MSTest test fixture attribute
[PexClass(Suite = "checkin")] // fixture attribute
public partial class MyTests { ... }
```

**Test altındaki türünü belirtme**:

```
[PexClass(typeof(Foo))] // this is a test for Foo
public partial class FooTest { ... }
```

Sınıfı yöntemleri ile Açıklama içerebilir [PexMethod](#pexmethod). Intellitest de anlar [ayarlama ve aşağı kesmeden](test-generation.md#setup-teardown).

<a name="pexgenericarguments"></a>
## <a name="pexgenericarguments"></a>PexGenericArguments

Bu öznitelik türü tanımlama grubu oluşturmak için sağlar bir [genel parametreli birim testi](test-generation.md#generic-parameterized).

<a name="pexmethod"></a>
## <a name="pexmethod"></a>PexMethod

Bu öznitelik bir yöntem olarak işaretler bir [parametreli birim testi](test-generation.md#parameterized-unit-testing).
Yöntem ile işaretli bir sınıf içinde bulunmalıdır [PexClass](#pexclass) özniteliği.

Intellitest çağrısı, Geleneksel, parametresiz testleri oluşturacağını [parametreli birim testi](test-generation.md#parameterized-unit-testing) farklı parametrelere sahip.

Parametreli birim testi:

* Örnek yöntemi olmalıdır
* olmalıdır [görünür](input-generation.md#visibility) içine oluşturulan testleri yerleştirilir göre test sınıfına [ayarları Waterfall](settings-waterfall.md)
* herhangi bir sayıda parametre sürebilir
* Genel olabilir

**Örnek**

```
[PexClass]
public partial class MyTests {
     [PexMethod]
     public void MyTest(int i)
     { ... }
}
```

<a name="pexexplorationattributebase"></a>
## <a name="pexexplorationattributebase"></a>PexExplorationAttributeBase

[Daha fazla bilgi](https://msdn.microsoft.com/library/microsoft.pex.framework.pexexplorationattributebase.aspx)

<a name="pexassemblysettings"></a>
## <a name="pexassemblysettings"></a>PexAssemblySettings

Bu öznitelik, tüm explorations için varsayılan ayar değerleri geçersiz kılmak için derleme düzeyinde ayarlanabilir.

```
using Microsoft.Pex.Framework;
// overriding the test framework selection
[assembly: PexAssemblySettings(TestFramework = "Naked")]
```

<a name="pexassemblyundertest"></a>
## <a name="pexassemblyundertest"></a>PexAssemblyUnderTest

Bu öznitelik geçerli test projesi tarafından test edilmekte olan derleme belirtir. 

```
[assembly: PexAssemblyUnderTest("MyAssembly")]
```

<a name="pexinstrumentassemblyattribute"></a>
## <a name="pexinstrumentassemblyattribute"></a>PexInstrumentAssemblyAttribute

Bu öznitelik izlenmiş için bir derlemeyi belirtmek için kullanılır.

**Örnek**

```
using Microsoft.Pex.Framework;

// the assembly containing ATypeFromTheAssemblyToInstrument should be instrumented
[assembly: PexInstrumentAssembly(typeof(ATypeFromTheAssemblyToInstrument))]

// the assembly name can be used as well
[assembly: PexInstrumentAssembly("MyAssemblyName")]
```

<a name="pexusetype"></a>
## <a name="pexusetype"></a>PexUseType

Bu öznitelik, belirli bir tür (soyut) temel türleri veya arabirimlerini örneği oluşturmak için kullanabileceğiniz Intellitest söyler.

**Örnek**

```
[PexMethod]
[PexUseType(typeof(A))]
[PexUseType(typeof(B))]
public void MyTest(object testParameter)
{
     ... // IntelliTest will consider types A and B to instantiate 'testParameter'
}
```

<a name="pexallowedexception"></a>
## <a name="pexallowedexception"></a>PexAllowedException

Bu öznitelik için bağlıysa bir [PexMethod](#pexmethod) (veya bir [PexClass](#pexclass), testler başarısız olduğunda gösterir varsayılan Intellitest mantığı değiştirir. Belirtilen özel durum oluşturursa bile test başarısız olarak kabul edilmez.

**Örnek**

Aşağıdaki sınama belirleyen oluşturucusunun **yığın** atabilir bir **ArgumentOutOfRangeException**:

```
class Stack {
  int[] _elements;
  int _count;
  public Stack(int capacity) {
    if (capacity<0) throw new ArgumentOutOfRangeException();
    _elements = new int[capacity];
    _count = 0;
  }
  ...
}
```

Filtre için donanımı (Bu da derleme veya test düzeyinde tanımlanabilir) aşağıdaki gibi eklenir:

```
[PexMethod]
[PexAllowedException(typeof(ArgumentOutOfRangeException))]
class CtorTest(int capacity) {
  Stack s = new Stack(capacity); // may throw ArgumentOutOfRangeException
}
```

<a name="pexallowedexceptionfromassembly"></a>
## <a name="pexallowedexceptionfromassembly"></a>PexAllowedExceptionFromAssembly

[Daha fazla bilgi](https://msdn.microsoft.com/library/microsoft.pex.framework.validation.pexallowedexceptionfromassemblyattribute.aspx)

<a name="pexallowedexceptionfromtype"></a>
## <a name="pexallowedexceptionfromtype"></a>PexAllowedExceptionFromType

[Daha fazla bilgi](https://msdn.microsoft.com/library/microsoft.pex.framework.validation.pexallowedexceptionfromtypeattribute.aspx)

<a name="pexallowedexceptionfromtypeundertest"></a>
## <a name="pexallowedexceptionfromtypeundertest"></a>PexAllowedExceptionFromTypeUnderTest

[Daha fazla bilgi](https://msdn.microsoft.com/library/microsoft.pex.framework.validation.pexallowedexceptionfromtypeundertestattribute.aspx)

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi sonrası ve özellik istekleri  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
