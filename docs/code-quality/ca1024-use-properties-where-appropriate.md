---
title: "CA1024: uygun yerlerde özellikler kullan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UsePropertiesWhereAppropriate
- CA1024
helpviewer_keywords:
- CA1024
- UsePropertiesWhereAppropriate
ms.assetid: 3a04f765-af7c-4872-87ad-9cc29e8e657f
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 42fb569dbf469ed91f96b25818b717353d53bf0b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1024-use-properties-where-appropriate"></a>CA1024: Uygun yerlerde özellikler kullan
|||  
|-|-|  
|TypeName|UsePropertiesWhereAppropriate|  
|CheckId|CA1024|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bir ortak veya korumalı yöntemi ile başlayan bir ada sahip `Get`parametre almayan ve dizisi olmayan bir değer döndürür.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Çoğu durumda, Özellikler verilerini temsil eden ve yöntemleri eylemleri gerçekleştirebilirsiniz. Özellikleri kullanmak kolaylaştırır alanları gibi erişilir. Bir yöntemi, aşağıdaki durumlardan birinde varsa, bir özellik olacak şekilde iyi bir adaydır:  
  
-   Bağımsız değişken almayan ve bir nesne durumu bilgilerini döndürür.  
  
-   Bir nesnenin durumu kısmı ayarlamak için tek bir bağımsız değişken kabul eder.  
  
 Alanları ise gibi özellikleri hareket etmesi gerektiğini; yöntem ayarlanmamışsa, bir özelliğe değiştirilmemelidir. Aşağıdaki durumlarda özellikleri daha iyi yöntemler şunlardır:  
  
-   Yöntemi, bir uzun süren işlem gerçekleştirir. Yöntemi, perceivably ayarlayın veya bir alanın değerini almak için gereken süreden daha yavaştır.  
  
-   Yöntemi, bir dönüştürme gerçekleştirir. Bir alan erişme depoladığı verilerin dönüştürülmüş bir sürümünü döndürmez.  
  
-   Get yöntemini gözlemlenebilir bir yan etkisi yoktur. Bir alanın değerini alma herhangi yan etkileri üretmez.  
  
-   Yürütme sırası önemlidir. Diğer işlemlerin tekrarlamasını üzerinde bir alanın değerini ayarlama bağlı değildir.  
  
-   Art arda iki kez yöntemi çağırma farklı sonuçlar oluşturur.  
  
-   Yöntem statik ancak çağıran tarafından değiştirilebilir. bir nesne döndürür. Bir alanın değerini alma alanı tarafından depolanan verileri değiştirmek arayan izin vermiyor.  
  
-   Yöntemi, bir dizi döndürür.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için bir özelliğe yöntemini değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan yöntemi en az bir daha önce listelenen ölçütlerini karşılıyorsa engelleyin.  
  
## <a name="controlling-property-expansion-in-the-debugger"></a>Hata ayıklayıcı denetleme özelliği genişletme  
 Otomatik-genişletmek için hata ayıklayıcı istemediğiniz programcıları özelliği kullanmaktan kaçının bir nedenidir. Örneğin, özelliği büyük nesne ayırma ya da P/Invoke çağırma gerektirebilir, ancak hiçbir observable yan etkileri gerçekte olmayabilir.  
  
 Hata ayıklayıcı otomatik-aşmasını önlemek uygulayarak özellikleri <xref:System.Diagnostics.DebuggerBrowsableAttribute?displayProperty=fullName>. Aşağıdaki örnekte bu öznitelik bir örnek özelliği için uygulanan gösterir.  
  
```vb  
Imports System   
Imports System.Diagnostics   
  
Namespace Microsoft.Samples   
  
    Public Class TestClass   
  
        ' [...]   
  
        <DebuggerBrowsable(DebuggerBrowsableState.Never)> _   
        Public ReadOnly Property LargeObject() As LargeObject   
            Get   
                ' Allocate large object   
                ' [...]   
            End Get   
        End Property   
  
    End Class   
  
End Namespace  
```  
  
```csharp  
  
      using System;   
using System.Diagnostics;   
  
namespace Microsoft.Samples   
{   
    publicclass TestClass   
    {   
        // [...]   
  
        [DebuggerBrowsable(DebuggerBrowsableState.Never)]   
        public LargeObject LargeObject   
        {   
            get   
            {   
                // Allocate large object   
                // [...]   
  
        }  
    }  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, özelliklerine dönüştürüleceğini ve olmayan alanlar gibi davranırlar değil çünkü, birkaç gereken birkaç yöntem içerir.  
  
 [!code-csharp[FxCop.Design.MethodsProperties#1](../code-quality/codesnippet/CSharp/ca1024-use-properties-where-appropriate_1.cs)]