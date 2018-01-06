---
title: "CA1062: Genel yöntemlerin bağımsız değişkenlerini doğrulamak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
- Validate arguments of public methods
helpviewer_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
ms.assetid: db1f69ca-68f7-477e-94f3-d135cc5dfcbc
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eb659fa8bfd18d8caf4a7473f6cd53809d0a126b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1062-validate-arguments-of-public-methods"></a>CA1062: Genel yöntemlerin bağımsız değişkenlerini doğrulayın
|||  
|-|-|  
|TypeName|ValidateArgumentsOfPublicMethods|  
|CheckId|CA1062|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünür bir yöntem başvuru değişkenlerinin birini bağımsız olup olmadığını doğrulamadan dereferences `null` (`Nothing` Visual Basic'te).  
  
## <a name="rule-description"></a>Kural Tanımı  
 Dışarıdan görünür yöntemlere iletilen tüm başvuru bağımsız değişkenleri karşı denetlenmesi `null`. Uygunsa, throw bir <xref:System.ArgumentNullException> bağımsız değişkeni olduğunda `null`.  
  
 Genel veya korumalı bildirildiğinden bilinmeyen bir derlemeye ait bir yöntemi çağrılabilir, tüm parametreleri yönteminin doğrulamalıdır. Yöntem yalnızca bilinen derlemeleri tarafından çağrılması için tasarlanmış, yöntemi iç yapmanız ve uygulama gerekir <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> özniteliği yöntemi içeren derleme.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için her başvuru bağımsız değişkeni karşı doğrulama `null`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Dereferenced parametresi işlevinde başka bir yöntem çağrısı tarafından doğrulanan eminseniz bu kural bir uyarıdan gizleyebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kuralını ihlal eden bir yöntem ve kural karşılayan bir yöntemi gösterir.  
  
 ```csharp
 using System;

namespace DesignLibrary
{
    public class Test
    {
        // This method violates the rule.
        public void DoNotValidate(string input)
        {
            if (input.Length != 0)
            {
                Console.WriteLine(input);
            }
        }

        // This method satisfies the rule.
        public void Validate(string input)
        {
            if (input == null)
            {
                throw new ArgumentNullException("input");
            }
            if (input.Length != 0)
            {
                Console.WriteLine(input);
            }
        }
    }
}
```

```vb
Imports System

Namespace DesignLibrary

    Public Class Test

        ' This method violates the rule.
        Sub DoNotValidate(ByVal input As String)

            If input.Length <> 0 Then
                Console.WriteLine(input)
            End If

        End Sub

        ' This method satisfies the rule.
        Sub Validate(ByVal input As String)

            If input Is Nothing Then
                Throw New ArgumentNullException("input")
            End If

            If input.Length <> 0 Then
                Console.WriteLine(input)
            End If

        End Sub

    End Class

End Namespace
```
  
## <a name="example"></a>Örnek  
 İçinde [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)], bu kural parametreleri doğrulama yapan başka bir yönteme geçirilen algılamaz.  

```csharp
public string Method(string value)
{
    EnsureNotNull(value);

    // Fires incorrectly    
    return value.ToString();
}

private void EnsureNotNull(string value)
{
    if (value == null)
        throw new ArgumentNullException("value");
}
```

```vb
Public Function Method(ByVal value As String) As String
    EnsureNotNull(value)

    ' Fires incorrectly    
    Return value.ToString()
End Function

Private Sub EnsureNotNull(ByVal value As String)
    If value Is Nothing Then
        Throw (New ArgumentNullException("value"))
    End If
End Sub
```

## <a name="example"></a>Örnek  
 Alan veya reference nesneleridir özellikleri doldurmak kopya oluşturucuları de CA1062 kuralı ihlal edebilir. Kopya oluşturucuya geçirilen kopyalanan nesne olabileceğinden ihlali oluşuyor `null` (`Nothing` Visual Basic'te). İhlali çözümlemek için kopyalanan nesnesi null olmayan denetlemek için bir statik (Visual Basic'te Shared) yöntemini kullanın.  
  
 Aşağıdaki `Person` sınıfı örneği `other` geçirilir nesne `Person` kopya Oluşturucu olabilir `null`.  
  
```csharp  
public class Person  
{  
    public string Name { get; private set; }  
    public int Age { get; private set; }  
  
    public Person(string name, int age)  
    {  
        Name = name;  
        Age = age;  
    }  
  
    // Copy constructor CA1062 fires because other is dereferenced  
    // without being checked for null  
    public Person(Person other)  
        : this(other.Name, other.Age)  
    {  
    }  
}  
```
  
## <a name="example"></a>Örnek  
 Aşağıdaki düzenlendi `Person` örnek, `other` kopya oluşturucusuna geçirilen nesne için null olarak işaretli ilk `PassThroughNonNull` yöntemi.  
  
```csharp  
public class Person  
{  
    public string Name { get; private set; }  
    public int Age { get; private set; }  
  
    public Person(string name, int age)  
    {  
        Name = name;  
        Age = age;  
    }  
  
    // Copy constructor  
    public Person(Person other)  
        : this(PassThroughNonNull(other).Name,   
          PassThroughNonNull(other).Age)  
    {   
    }  
  
    // Null check method  
    private static Person PassThroughNonNull(Person person)  
    {  
        if (person == null)  
            throw new ArgumentNullException("person");  
        return person;  
    }  
}  
  
```