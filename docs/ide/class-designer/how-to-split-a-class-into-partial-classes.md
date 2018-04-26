---
title: 'Nasıl Yapılır: Sınıfı Kısmi Sınıflara Bölme (Sınıf Tasarımcısı)'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer, partial classes
- partial classes, Class Designer
ms.assetid: 6f6b0b30-3996-4569-9200-20482b3adf90
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3d0aa5b844b3743ab80c11971caa26340effe671
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-split-a-class-into-partial-classes-class-designer"></a>Nasıl yapılır: bir sınıfı kısmi sınıflara (Sınıf Tasarımcısı) bölme

Kullanabileceğiniz `partial` anahtar sözcüğü (`Partial` Visual Basic'te) bir sınıf veya yapı birkaç bildirimler arasında bildirimi bölmek için. İstediğiniz sayıda kısmi bildirimleri kullanabilirsiniz.

Bildirimler, bir veya birden çok kaynak dosyalarında olabilir. Tüm bildirimler aynı bütünleştirilmiş kodda ve aynı ad olmalıdır.

Kısmi sınıflar birkaç durumlarda faydalıdır. Büyük bir proje üzerinde örneğin, bir sınıfın birden çok dosyaya ayırma projede aynı anda çalışması birden fazla Programcı sağlar. Visual Studio'nun oluşturduğu kodu ile çalışırken, kaynak dosyayı yeniden oluşturmak zorunda kalmadan sınıfı değiştirebilirsiniz. (Windows Forms ve Web hizmeti sarmalayıcı kodu Visual Studio'nun oluşturduğu kod örnekleri içerir.) Bu nedenle, Visual Studio oluşturur dosyasını değiştirmek zorunda kalmadan otomatik olarak oluşturulan sınıfları kullanan kodu oluşturabilirsiniz.

Kısmi yöntemler iki tür vardır. C# ' ta bunlar bildirme ve uygulama olarak adlandırılır; Visual Basic'te, bunlar bildirimi ve uygulama adı verilir.

**Sınıf Tasarımcısı** kısmi sınıflar ve yöntemler destekler. Sınıf diyagramında türü şekli parçalı sınıf için bir tek bildirimi konumu ifade eder. Parçalı sınıf içinde birden çok dosya tanımlanmışsa bildirimi konumu belirtebilirsiniz **Sınıf Tasarımcısı** ayarlayarak kullanacağı **yeni üye konumu** özelliğinde **özellikleri**  penceresi. Diğer bir deyişle, bir sınıf şekli çift tıkladığınızda **Sınıf Tasarımcısı** tarafından tanımlanan sınıf bildirimi içeren kaynak dosyasına gider **yeni üye konumu** özelliği. Bir sınıf şekli kısmi yönteminde çift tıkladığınızda **Sınıf Tasarımcısı** kısmi yöntemi bildirimine gider. Ayrıca, **özellikleri** penceresinde **dosya adı** özellik bildirimi konuma başvuruyor. Kısmi sınıflar için **dosya adı** tüm bu sınıf için bildirim ve uygulama kodu içeren dosyaları listeler. Ancak, kısmi yöntemler için **dosya adı** kısmi yöntem bildirimi içeren dosyanın listeler.

Aşağıdaki örnekler sınıfının tanımını bölme `Employee` iki bildirimleri her biri farklı bir yordam tanımlar. İki kısmi tanımları örneklerde, bir kaynak dosyasında veya iki farklı kaynak dosyalar olabilir.

> [!NOTE]
> Visual Basic, Visual Studio ayırmak için kısmi sınıf tanımları kullanır — kullanıcı tarafından yazılan koddan oluşturulan kodda. Kod ayrık kaynak dosyalarıyla ayrılır. Örneğin, **Windows Form Tasarımcısı** denetimleri için kısmi sınıflar gibi tanımlar `Form`. Bu denetimler oluşturulan kodda değiştirmemeniz gerekir.


Visual Basic'te kısmi türler hakkında daha fazla bilgi için bkz: [kısmi](/dotnet/visual-basic/language-reference/modifiers/partial).

## <a name="visual-basic-example"></a>Visual Basic örnek

Visual Basic'te bir sınıf tanımı bölmek için kullanın `Partial` aşağıdaki örnekte gösterildiği gibi anahtar.

```vb
' First part of class definition.
Partial Public Class Employee
    Public Sub CalculateWorkHours()
    End Sub
End Class

' Second part of class definition.
Partial Public Class Employee
    Public Sub CalculateTaxes()
    End Sub
End Class
```

## <a name="c-example"></a>C# örnek

Bir sınıf tanımı C# bölmek için kullanın `partial` aşağıdaki örnekte gösterildiği gibi anahtar.

```csharp
// First part of class definition.
public partial class Employee
{
    public void CalculateWorkHours()
    {
    }
}

// Second part of class definition.
public partial class Employee
{
    public void CalculateTaxes()
    {
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Parçalı Sınıflar ve Yöntemler](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)
- [partial (Tür)](/dotnet/csharp/language-reference/keywords/partial-type)
- [partial (yöntem) (C# Başvurusu)](/dotnet/csharp/language-reference/keywords/partial-method)
- [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)