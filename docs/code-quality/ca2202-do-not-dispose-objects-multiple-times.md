---
title: 'CA2202: nesneleri birden çok kez atmayın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2202
- Do not dispose objects multiple times
- DoNotDisposeObjectsMultipleTimes
helpviewer_keywords:
- CA2202
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e8d7132f9f4ac935b49ad61a7b3e4df307395e73
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2202-do-not-dispose-objects-multiple-times"></a>CA2202: Nesneleri birden çok kez atmayın
|||  
|-|-|  
|TypeName|DoNotDisposeObjectsMultipleTimes|  
|CheckId|CA2202|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Yöntem uygulaması için birden fazla çağrı neden olabilecek kod yolları içeren <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> veya çağrısının yöntemi aynı nesne üzerinde bazı türleri gibi bir Dispose eşdeğer.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Doğru bir şekilde A <xref:System.IDisposable.Dispose%2A> yöntemi çağrılabilir birden çok kez bir özel durum oluşturmadan. Ancak, bu garanti edilmez ve oluşturulmasını engellemek için bir <xref:System.ObjectDisposedException?displayProperty=fullName> değil çağırmalıdır <xref:System.IDisposable.Dispose%2A> bir nesne üzerinde birden fazla kez.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2000: Kapsamı kaybetmeden önce verileri atın](../code-quality/ca2000-dispose-objects-before-losing-scope.md)  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltin, kod yolu, bu nedenle bu bakılmaksızın uygulama değiştirmek için <xref:System.IDisposable.Dispose%2A> nesne için yalnızca bir kez çağrılır.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Olsa bile <xref:System.IDisposable.Dispose%2A> nesne birden çok kez güvenli bir şekilde çağrılabilir olduğu bilinen için uygulama gelecekte değişebilir.  
  
## <a name="example"></a>Örnek  
 İç içe geçmiş `using` deyimleri (`Using` Visual Basic'te) CA2202 uyarı ihlalleri neden olabilir. İç içe geçmiş iç IDisposable kaynak `using` deyimi içeren kaynak dış `using` deyimi, `Dispose` iç içe kaynak yöntemi içerilen kaynağın serbest bırakır. Bu durum oluştuğunda `Dispose` yöntemi dış `using` deyimi için ikinci kez kaynağı dispose dener.  
  
 Aşağıdaki örnekte, bir <xref:System.IO.Stream> bir dış oluşturulan nesne deyimiyle deyimi içinde Dispose yöntemini kullanarak iç sonunda yayımlanır <xref:System.IO.StreamWriter> içeren nesne `stream` nesne. Dış sonunda `using` deyimi, `stream` nesne ikinci kez yayımlanır. CA2202 ihlal ikinci sürümüdür.  
  
```  
using (Stream stream = new FileStream("file.txt", FileMode.OpenOrCreate))  
{  
    using (StreamWriter writer = new StreamWriter(stream))  
    {  
        // Use the writer object...  
    }  
}  
  
```  
  
## <a name="example"></a>Örnek  
 Bu sorunu gidermek için bir `try` / `finally` dış yerine blok `using` deyimi. İçinde `finally` engellemek, olduğundan emin olun `stream` kaynağı null değil.  
  
```  
Stream stream = null;  
try  
{  
    stream = new FileStream("file.txt", FileMode.OpenOrCreate);  
    using (StreamWriter writer = new StreamWriter(stream))  
    {  
        stream = null;  
        // Use the writer object...  
    }  
}  
finally  
{  
    if(stream != null)  
        stream.Dispose();  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IDisposable?displayProperty=fullName>   
 [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)