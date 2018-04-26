---
title: Visual Studio'da Test birim için uygulamanızın yalıtmak üzere dolgular kullanma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 55b31661120c5224d12485764328007dc8445a8e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="use-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing"></a>Uygulamanızı birim testi için diğer derlemelerden yalıtmak üzere dolgular kullanma

**Dolguya türleri** izin verecek şekilde Microsoft Fakes Framework kullanan iki teknolojilerden birine kolayca yalıtmak altında test ortamı'ndan bileşenleridir. Dolgular belirli yöntemler testinizi bir parçası olarak yazma koda çağrı yönlendir. Birçok yöntem farklı sonuçlar dış koşullar bağımlı döndürebilir ancak bir dolgu testinizi denetimi altındadır ve her çağrısında tutarlı sonuçlar döndürebilir. Bu testleri yazmak çok daha kolay hale getirir.

 Kodunuzu çözümünüzü parçası olmayan derlemelerden yalıtmak üzere dolgular kullanın. Bileşenleri çözümünüzün birbirinden yalıtmak üzere saplamalar kullanmanızı öneririz.

 Genel bir bakış ve hızlı başlangıç kılavuzu için bkz: [yalıtma kodu altında Microsoft Fakes ile Test](../test/isolating-code-under-test-with-microsoft-fakes.md)

 **Gereksinimler**

-   Visual Studio Enterprise
-   Bir .NET Framework projesi

> [!NOTE]
> .NET standart projeleri desteklenmez.

## <a name="example-the-y2k-bug"></a>Örnek: Y2K hata

Şimdi, 1 Ocak 2000'in üzerinde aykırı bir yöntem göz önünde bulundurun:

```csharp
// code under test
public static class Y2KChecker {
    public static void Check() {
        if (DateTime.Now == new DateTime(2000, 1, 1))
            throw new ApplicationException("y2kbug!");
    }
}
```

 Bu yöntem test sorunlu programa bağımlı olduğundan dolayı `DateTime.Now`, bilgisayara bağlı bir yöntem kullanıcının saat, bir ortam bağımlı, belirleyici olmayan yöntemi. Ayrıca, `DateTime.Now` bir saplama türü burada kullanılamaz statik bir özelliktir. Bu sorunu birim testi yalıtım sorunun belirtisi: veritabanı API'leri, çağrısına iletişim doğrudan web hizmetleri ve benzeri birimine sabit programların test kendi mantığı ortamda bağımlı olduğundan.

 Dolgu türleri kullanıldığı budur. Dolgu türü kullanıcı tanımlı bir temsilci için herhangi bir .NET yöntemi saptıran için bir mekanizma sağlar. Kod-Fakes oluşturma tarafından oluşturulan dolgusu türleri ve dolgusu türleri diyoruz, temsilciler yeni yöntem uygulamalarını belirtmek için kullandıkları.

 Aşağıdaki sınama Dolgu türü kullanmayı gösterir `ShimDateTime`, DateTime.Now, özel bir uygulama sunmak amacıyla:

```csharp
//unit test code
// create a ShimsContext cleans up shims
using (ShimsContext.Create()
    // hook delegate to the shim method to redirect DateTime.Now
    // to return January 1st of 2000
    ShimDateTime.NowGet = () => new DateTime(2000, 1, 1);
    Y2KChecker.Check();
}

```

##  <a name="BKMK_Fakes_requirements"></a> Dolgular kullanma

###  <a name="AddFakes"></a> Fakes derlemelerini ekleyin

1.  Çözüm Gezgini'nde, birim testi projenizin genişletin **başvurular**.

    -   Visual Basic'te çalışıyorsanız, seçmelisiniz **tüm dosyaları göster** başvuruları listesini görmek için Çözüm Gezgini araç çubuğunda.

2.  Dolgular oluşturmak istediğiniz sınıfları tanımları içeren derlemenin seçin. DateTime dolguya istiyorsanız, örneğin, System.dll seçin

3.  Kısayol menüsünden seçin **Fakes derleme Ekle**.

###  <a name="ShimsContext"></a> ShimsContext kullanın
 Dolgu türleri bir birim test çerçevesi kullanırken, test kodda kaydırma bir `ShimsContext` , dolgular ömrünü denetlemek için. Biz bu kaydetmedi gerekiyorsa, dolgular AppDomain kapatma kadar en son. Oluşturmanın en kolay yolu bir `ShimsContext` statik kullanarak `Create()` yöntemini aşağıdaki kodda gösterildiği gibi değiştirin:

```csharp
//unit test code
[Test]
public void Y2kCheckerTest() {
  using(ShimsContext.Create()) {
    ...
  } // clear all shims
}

```

 Her dolgusu bağlamı düzgün bir şekilde silmek için önemlidir. Altın kural, her zaman çağrısı `ShimsContext.Create` içine bir `using` kayıtlı dolgular, uygun temizleme emin olmak için deyimi. Örneğin, bir dolgu yerini alan bir test yöntemi için kayıt `DateTime.Now` yöntemi her zaman döndüren bir temsilci ile ilk Ocak, 2000. Test yöntemi kayıtlı dolgusunu temizlemek unutursanız, test çalışması kalan her zaman döndürecektir DateTime.Now olarak ilk, Ocak 2000 değeri. Bu, şaşırtıcı ve kafa karıştırıcı olabilir.

###  <a name="WriteShims"></a> Bir test dolgular ile yazma
 Test kodunuzda bir *detour* taklit etmek istediğiniz yöntemi. Örneğin:

```csharp
[TestClass]
public class TestClass1
{
        [TestMethod]
        public void TestCurrentYear()
        {
            int fixedYear = 2000;

            using (ShimsContext.Create())
            {
              // Arrange:
                // Detour DateTime.Now to return a fixed date:
                System.Fakes.ShimDateTime.NowGet =
                () =>
                { return new DateTime(fixedYear, 1, 1); };

                // Instantiate the component under test:
                var componentUnderTest = new MyComponent();

              // Act:
                int year = componentUnderTest.GetTheCurrentYear();

              // Assert:
                // This will always be true if the component is working:
                Assert.AreEqual(fixedYear, year);
            }
        }
}

```

```vb
<TestClass()> _
Public Class TestClass1
    <TestMethod()> _
    Public Sub TestCurrentYear()
        Using s = Microsoft.QualityTools.Testing.Fakes.ShimsContext.Create()
            Dim fixedYear As Integer = 2000
            ' Arrange:
            ' Detour DateTime.Now to return a fixed date:
            System.Fakes.ShimDateTime.NowGet = _
                Function() As DateTime
                    Return New DateTime(fixedYear, 1, 1)
                End Function

            ' Instantiate the component under test:
            Dim componentUnderTest = New MyComponent()
            ' Act:
            Dim year As Integer = componentUnderTest.GetTheCurrentYear
            ' Assert:
            ' This will always be true if the component is working:
            Assert.AreEqual(fixedYear, year)
        End Using
    End Sub
End Class
```

 Dolgu sınıf adları yapılma ekleyerek `Fakes.Shim` özgün türü adı.

 Dolgular iş ekleyerek *detours* test altındaki uygulama koduna. Özgün yöntemine bir çağrı oluşur olduğunda, Fakes sistem gerçek yöntemi çağırmak yerine, dolgu kodunuzu adlı bir detour gerçekleştirir.

 Detours oluşturulur ve çalışma zamanında silinmiş dikkat edin. Her zaman bir detour ömrü içinde oluşturmalısınız bir `ShimsContext`. Silindiğinde, etkin olduğu sırada oluşturduğunuz dolgular kaldırılır. Bunu yapmak için en iyi yolu içindedir bir `using` deyimi.

 Fakes ad alanı mevcut olmadığını belirten bir yapı hata görebilirsiniz. Bu hata, bazen diğer derleme hataları olmadığında görüntülenir. Diğer hataları giderin ve kaybolur.

##  <a name="BKMK_Shim_basics"></a> Dolgular için çeşitli yöntemler
 Dolgu türü, statik yöntemler veya kendi temsilciler ile sanal olmayan yöntemler de dahil olmak üzere, herhangi bir .NET yöntemini değiştirmek izin verir.

###  <a name="BKMK_Static_methods"></a> Statik yöntemler
 Dolgular statik yöntem eklemek için özellikler bir dolgu türü yerleştirilir. Her bir özellik için hedef yöntemin bir temsilciyi bağlamak için kullanılan bir ayarlayıcı vardır. Örneğin, bir sınıf verilen `MyClass` bir statik yöntem `MyMethod`:

```csharp
//code under test
public static class MyClass {
    public static int MyMethod() {
        ...
    }
}
```

 Bir dolgu ekleyebilir miyim `MyMethod` , her zaman 5 döndürür:

```csharp
// unit test code
ShimMyClass.MyMethod = () =>5;
```

###  <a name="BKMK_Instance_methods__for_all_instances_"></a> Örnek yöntemleri (için tüm örnekleri)
 Benzer şekilde statik yöntemler için örnek yöntemleri tüm örnekler için shimmed. Bu dolgular eklemek için özellikler Karışıklığı önlemek için de AllInstances adlı bir iç içe geçmiş tür yerleştirilir. Örneğin, bir sınıf verilen `MyClass` örnek yöntemi ile `MyMethod`:

```csharp
// code under test
public class MyClass {
    public int MyMethod() {
        ...
    }
}
```

 Bir dolgu iliştirebilirsiniz `MyMethod` , 5, örnek bakılmaksızın her zaman döndürür:

```csharp
// unit test code
ShimMyClass.AllInstances.MyMethod = () => 5;
```

 ShimMyClass oluşturulan tür yapısını aşağıdaki kod gibi görünür:

```csharp
// Fakes generated code
public class ShimMyClass : ShimBase<MyClass> {
    public static class AllInstances {
        public static Func<MyClass, int>MyMethod {
            set {
                ...
            }
        }
    }
}
```

 Fakes dikkat edin, çalışma zamanı örneği bu durumda temsilci ilk bağımsız değişken olarak geçirir.

###  <a name="BKMK_Instance_methods__for_one_instance_"></a> Örnek yöntemleri (örneğin bir çalışma zamanı)
 Örnek yöntemleri çağrı alıcı üzerinde göre farklı temsilcileri tarafından da shimmed. Bu türün örneğini başına farklı davranışlar sağlamak aynı örnek yöntemi sağlar. Bu dolgular ayarlanacak özellikler Dolgu türü örneği yöntemleridir. Her örneklenen Dolgu türü de shimmed türünde ham bir örneği ile ilişkilidir.

 Örneğin, bir sınıf verilen `MyClass` örnek yöntemi ile `MyMethod`:

```csharp
// code under test
public class MyClass {
    public int MyMethod() {
        ...
    }
}
```

 İki dolgusu tür MyMethod ilk 5 her zaman döndürür ve 10 saniye her zaman döndürür şekilde ayarlayabilirsiniz:

```csharp
// unit test code
var myClass1 = new ShimMyClass()
{
    MyMethod = () => 5
};
var myClass2 = new ShimMyClass { MyMethod = () => 10 };
```

 ShimMyClass oluşturulan tür yapısını aşağıdaki kod gibi görünür:

```csharp
// Fakes generated code
public class ShimMyClass : ShimBase<MyClass> {
    public Func<int> MyMethod {
        set {
            ...
        }
    }
    public MyClass Instance {
        get {
            ...
        }
    }
}
```

 Gerçek shimmed türü örneği örnek özelliği üzerinden erişilebilir:

```csharp
// unit test code
var shim = new ShimMyClass();
var instance = shim.Instance;
```

 Genellikle yalnızca Dolgu türü olarak kullanabilmek için Dolgu türü ayrıca shimmed türüne örtük bir dönüştürme vardır:

```csharp
// unit test code
var shim = new ShimMyClass();
MyClass instance = shim; // implicit cast retrieves the runtime
                         // instance
```

###  <a name="BKMK_Constructors"></a> Oluşturucular
 Oluşturucular dolgusu türleri gelecek nesnelere iliştirmek için de shimmed. Her Oluşturucusu dolgusu türündeki bir statik yöntem oluşturucusu olarak sunulur. Örneğin, bir sınıf verilen `MyClass` tamsayı alan bir oluşturucuya sahip:

```csharp
// code under test
public class MyClass {
    public MyClass(int value) {
        this.Value = value;
    }
    ...
}
```

 Değer alıcı çağrıldığında değeri oluşturucusundaki bağımsız olarak her gelecekteki örneğini -5 döndürür. böylece biz Oluşturucusu Dolgu türü ayarlayın:

```csharp
// unit test code
ShimMyClass.ConstructorInt32 = (@this, value) => {
    var shim = new ShimMyClass(@this) {
        ValueGet = () => -5
    };
};
```

 Her Dolgu türü iki oluşturucular kullanıma sunar. Varsayılan Oluşturucu, yeni bir örneği, yalnızca Oluşturucusu dolgular bağımsız değişkeni kullanılmalıdır gibi bir shimmed örneği alan oluşturucu çalışırken gerekli olduğunda kullanılmalıdır:

```csharp
// unit test code
public ShimMyClass() { }
public ShimMyClass(MyClass instance) : base(instance) { }
```

 Aşağıdaki kod ShimMyClass oluşturulan tür yapısına benzer:

```csharp
// Fakes generated code
public class ShimMyClass : ShimBase<MyClass>
{
    public static Action<MyClass, int> ConstructorInt32 {
        set {
            ...
        }
    }

    public ShimMyClass() { }
    public ShimMyClass(MyClass instance) : base(instance) { }
    ...
}
```

###  <a name="BKMK_Base_members"></a> Temel üyeler
 Temel üyeler dolgusu özelliklerini temel türü için bir dolgu oluşturarak ve alt örneği parametre olarak temel dolgusu sınıfı oluşturucusuna geçirerek erişilebilir.

 Örneğin, bir sınıf verilen `MyBase` örnek yöntemi ile `MyMethod` ve alt `MyChild`:

```csharp
public abstract class MyBase {
    public int MyMethod() {
        ...
    }
}

public class MyChild : MyBase {
}

```

 Bir dolgu ayarlarız `MyBase` yeni oluşturarak `ShimMyBase` dolgusu:

```csharp
// unit test code
var child = new ShimMyChild();
new ShimMyBase(child) { MyMethod = () => 5 };
```

 Alt Dolgu türü parametre olarak temel dolgusu oluşturucuya geçirilen alt örneğine örtük olarak dönüştürülür unutmayın.

 Aşağıdaki kod ShimMyChild ve ShimMyBase oluşturulan tür yapısını benzer:

```csharp
// Fakes generated code
public class ShimMyChild : ShimBase<MyChild> {
    public ShimMyChild() { }
    public ShimMyChild(Child child)
        : base(child) { }
}
public class ShimMyBase : ShimBase<MyBase> {
    public ShimMyBase(Base target) { }
    public Func<int> MyMethod
    { set { ... } }
}
```

###  <a name="BKMK_Static_constructors"></a> Statik oluşturucular
 Dolgu türleri kullanıma sunmak için bir statik yöntem `StaticConstructor` türü statik Oluşturucusu dolguya yeniden. Statik oluşturucular çalıştırıldığından emin olmak gereken yalnızca bir kez Dolgu türü herhangi bir üyenin erişmeden önce yapılandırılır.

###  <a name="BKMK_Finalizers"></a> Sonlandırıcılar
 Sonlandırıcılar Fakes içinde desteklenmez.

###  <a name="BKMK_Private_methods"></a> Özel yöntemler
 Fakes Kod Oluşturucu yalnızca görünür türlerine imzada, yani sahip özel yöntemler, parametre türleri ve dönüş türü dolgusu özelliklerini görünür oluşturur.

###  <a name="BKMK_Binding_interfaces"></a> Bağlama arabirimleri
 Kod oluşturucunun shimmed türü bir arabirimini uygulayan, tüm üyeleri bu arabirimden aynı anda bağlamak izin veren bir yöntem yayar.

 Örneğin, bir sınıf verilen `MyClass` uygulayan `IEnumerable<int>`:

```csharp
public class MyClass : IEnumerable<int> {
    public IEnumerator<int> GetEnumerator() {
        ...
    }
    ...
}

```

 Biz uygulamaları dolguya `IEnumerable<int>` bağlama yöntemini çağırarak MyClass içinde:

```csharp
// unit test code
var shimMyClass = new ShimMyClass();
shimMyClass.Bind(new List<int> { 1, 2, 3 });

```

 Aşağıdaki kod ShimMyClass oluşturulan tür yapısına benzer:

```csharp
// Fakes generated code
public class ShimMyClass : ShimBase<MyClass> {
    public ShimMyClass Bind(IEnumerable<int> target) {
        ...
    }
}

```

##  <a name="BKMK_Changing_the_default_behavior"></a> Varsayılan davranışı değiştirme
 Her oluşturulan Dolgu türü örneğini tutan `IShimBehavior` arabirimi aracılığıyla `ShimBase<T>.InstanceBehavior` özelliği. Bir istemci değil açıkça shimmed bir örnek üyesine çağırdığında davranışı kullanılır.

 Davranış açıkça ayarlı değil, statik tarafından döndürülen örnek kullanan `ShimsBehaviors.Current` özelliği. Varsayılan olarak, bu özellik oluşturur bir davranış döndürür bir `NotImplementedException` özel durum.

 Bu davranış ayarlayarak herhangi bir zamanda değiştirilebilir `InstanceBehavior` herhangi bir dolgu örneği özelliği. Örneğin, aşağıdaki kod parçacığında dolgu hiçbir şey yapmaz veya dönüş türü varsayılan değerini döndüren bir davranış değişiklikleri — diğer bir deyişle, default(T):

```csharp
// unit test code
var shim = new ShimMyClass();
//return default(T) or do nothing
shim.InstanceBehavior = ShimsBehaviors.DefaultValue;

```

 Davranış da genel shimmed tüm örnekler için değiştirilebilir `InstanceBehavior` özelliği açıkça ayarlanmamış statik ayarlayarak `ShimsBehaviors.Current` özelliği:

```csharp
// unit test code
// change default shim for all shim instances
// where the behavior has not been set
ShimsBehaviors.Current =
    ShimsBehaviors.DefaultValue;

```

##  <a name="BKMK_Detecting_environment_accesses"></a> Algılama ortamı erişir
 Belirli bir türdeki atayarak statik yöntemler de dahil olmak üzere tüm üyeleri için bir davranış eklemek mümkündür `ShimsBehaviors.NotImplemented` statik özelliğe davranışı `Behavior` karşılık gelen Dolgu türü:

```csharp
// unit test code
// assigning the not implemented behavior
ShimMyClass.Behavior = ShimsBehaviors.NotImplemented;
// shorthand
ShimMyClass.BehaveAsNotImplemented();

```

##  <a name="BKMK_Concurrency"></a> Eşzamanlılık
 Dolgu türleri AppDomain içindeki tüm iş parçacıklarının uygulamak ve iş parçacığı benzeşimini yok. Eşzamanlılık destekleyen bir test Çalıştırıcısı kullanmayı planlıyorsanız, önemli bir olgu budur: dolgusu türleriyle ilgili testleri aynı anda çalıştırılamaz. Bu özellik Fakes çalışma zamanı tarafından zorlanmaz.

##  <a name="BKMK_Calling_the_original_method_from_the_shim_method"></a> Dolgu yönteminden özgün yöntemi çağırma
 Biz gerçekte yönteme geçirilen dosya adı doğrulanırken sonra metin dosya sistemine yazma istediğinizi düşünelim. Bu durumda, biz dolgusu yöntemi ortasında özgün yöntemini çağırmak istersiniz.

 Bu sorunu çözmek için ilk bir temsilci kullanarak özgün yöntemine bir çağrı sarmalamak için yaklaşımdır ve `ShimsContext.ExecuteWithoutShims()` aşağıdaki kodu olduğu gibi:

```csharp
// unit test code
ShimFile.WriteAllTextStringString = (fileName, content) => {
  ShimsContext.ExecuteWithoutShims(() => {

      Console.WriteLine("enter");
      File.WriteAllText(fileName, content);
      Console.WriteLine("leave");
  });
};

```

 Başka bir yaklaşım, null, özgün yöntemini çağırın ve dolgu geri dolgu ayarlamaktır.

```csharp
// unit test code
ShimsDelegates.Action<string, string> shim = null;
shim = (fileName, content) => {
  try {
    Console.WriteLine("enter");
    // remove shim in order to call original method
    ShimFile.WriteAllTextStringString = null;
    File.WriteAllText(fileName, content);
  }
  finally
  {
    // restore shim
    ShimFile.WriteAllTextStringString = shim;
    Console.WriteLine("leave");
  }
};
// initialize the shim
ShimFile.WriteAllTextStringString = shim;
```

##  <a name="BKMK_Limitations"></a> Sınırlamaları
 Dolgular, .NET temel sınıf kitaplığı'ndan tüm türler kullanılamaz **mscorlib** ve **sistem**.

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Fakes ile Test Edilen Kodu Yalıtma](../test/isolating-code-under-test-with-microsoft-fakes.md)
- [Peter Provost'ın blogu: Visual Studio 2012 dolgular](http://www.peterprovost.org/blog/2012/04/25/visual-studio-11-fakes-part-2)
- [Video (1-h 16): Visual Studio 2012'de Untestable kodu Fakes ile test etme](http://go.microsoft.com/fwlink/?LinkId=261837)
