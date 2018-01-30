---
title: "Nasıl yapılır: bir sınıfı kısmi sınıflara (Sınıf Tasarımcısı) bölme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Class Designer, partial classes
- partial classes, Class Designer
ms.assetid: 6f6b0b30-3996-4569-9200-20482b3adf90
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 9e9d1b0dca7c8e9d152a84273410e4bd7d768508
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-split-a-class-into-partial-classes-class-designer"></a>Nasıl Yapılır: Sınıfı Kısmi Sınıflara Bölme (Sınıf Tasarımcısı)
Kullanarak bir sınıf veya yapı birkaç bildirimler arasında bildirimi bölebilirsiniz `Partial` Visual Basic anahtar sözcüğü veya `partial` C# anahtar sözcüğü. İstediğiniz sayıda farklı kaynak dosyaları veya bir kaynak dosyasında istediğiniz sayıda kısmi bildirimleri kullanabilirsiniz. Ancak, tüm bildirimler aynı bütünleştirilmiş kodda ve aynı ad olmalıdır.  
  
Kısmi sınıflar birkaç durumlarda faydalıdır. Örneğin, bir sınıfın birden fazla dosyaya ayırarak büyük projeler üzerinde çalışırken, aynı anda üzerinde çalışması birden fazla Programcı sağlar. Visual Studio'nun oluşturduğu kodu ile çalışırken, kaynak dosyayı yeniden oluşturmak zorunda kalmadan sınıfı değiştirebilirsiniz. (Windows Forms ve Web hizmeti sarmalayıcı kodu Visual Studio'nun oluşturduğu kod örnekleri içerir.) Bu nedenle, Visual Studio oluşturur dosyasını değiştirmek zorunda kalmadan otomatik olarak oluşturulan sınıfları kullanan kodu oluşturabilirsiniz.  
  
Kısmi yöntemler iki tür vardır. C# ' ta bunlar bildirme ve uygulama olarak adlandırılır; Visual Basic'te, bunlar bildirimi ve uygulama adı verilir.  
  
Sınıf Tasarımcısı kısmi sınıflar ve yöntemler destekler. Sınıf diyagramında türü şekli parçalı sınıf için bir tek bildirimi konumu ifade eder. Parçalı sınıf içinde birden çok dosya tanımlanmışsa Sınıf Tasarımcısı ayarlayarak kullanacağınız bildirimi konumu belirtebilirsiniz **yeni üye konumu** özelliğinde **özellikleri** penceresi. Bir sınıf şekli çift tıkladığınızda, diğer bir deyişle, Sınıf Tasarımcısı tarafından tanımlanan sınıf bildirimi içeren kaynak dosyası gider **yeni üye konumu** özelliği. Bir sınıf şekli kısmi yönteminde çift tıkladığınızda, Sınıf Tasarımcısı için kısmi yöntem bildirimi gider. Ayrıca, **özellikleri** penceresinde **dosya adı** özellik bildirimi konuma başvuruyor. Kısmi sınıflar için **dosya adı** tüm bu sınıf için bildirim ve uygulama kodu içeren dosyaları listeler. Ancak, kısmi yöntemler için **dosya adı** kısmi yöntem bildirimi içeren dosyanın listeler.  
  
Aşağıdaki örnekler sınıfının tanımını bölme `Employee` iki bildirimleri her biri farklı bir yordam tanımlar. İki kısmi tanımları örneklerde, bir kaynak dosyasında veya iki farklı kaynak dosyalar olabilir.  
  
> [!NOTE]
>  Visual Basic, Visual Studio ayırmak için kısmi sınıf tanımları kullanır — kullanıcı tarafından yazılan koddan oluşturulan kodda. Kod ayrık kaynak dosyalarıyla ayrılır. Örneğin, **Windows Form Tasarımcısı** denetimleri için kısmi sınıflar gibi tanımlar `Form`. Bu denetimler oluşturulan kodda değiştirmemeniz gerekir.  
  
Visual Basic'te kısmi türler hakkında daha fazla bilgi için bkz: [kısmi](/dotnet/visual-basic/language-reference/modifiers/partial).  
  
## <a name="example"></a>Örnek  
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

## <a name="example"></a>Örnek  
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
[Kısmi sınıflar ve yöntemler](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)   
[partial (tür)](/dotnet/csharp/language-reference/keywords/partial-type)   
[partial (yöntem) (C# Başvurusu)](/dotnet/csharp/language-reference/keywords/partial-method)   
[Partial](/dotnet/visual-basic/language-reference/modifiers/partial)