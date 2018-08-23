---
title: 'CA1901: P-Invoke bildirimleri taşınabilir olmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
helpviewer_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
ms.assetid: 90361812-55ca-47f7-bce9-b8775d3b8803
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 685d576594a442f4cac510b5e29000ca0b6d3eb3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691363"
---
# <a name="ca1901-pinvoke-declarations-should-be-portable"></a>CA1901: P/Invoke bildirimleri taşınabilir olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1901: P-Invoke bildirimleri taşınabilir](https://docs.microsoft.com/visualstudio/code-quality/ca1901-p-invoke-declarations-should-be-portable).  
  
TypeName | PInvokeDeclarationsShouldBePortable |  
| Checkıd | CA1901 |  
| Kategori | Microsoft.Portability|  
| Yeni değişiklik | P/Invoke derlemenin dışında görünür olup olmadığını - kesiliyor. Olmayan son - P/Invoke derlemenin dışında görünür değilse. |  
  
## <a name="cause"></a>Sebep  
 Bu kural her parametresinin boyutu ve P/Invoke dönüş değeri değerlendirir ve bunların boyutu, 32-bit ve 64-bit platformlarda, yönetilmeyen kod sıralandığı zaman doğru olduğunu doğrular. Bu kural ihlalini en yaygın bir platforma bağımlı, işaretçi boyutlu değişken gerekli olduğu sabit boyutlu bir tamsayı geçirmektir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kuralı ihlal aşağıdaki senaryolardan biri gerçekleşir:  
  
-   Olarak yazılmalıdır, parametre ve dönüş değeri bir sabit boyutlu tamsayı olarak yazılan bir `IntPtr`.  
  
-   Parametre ve dönüş değeri olarak yazılmış bir `IntPtr` zaman yazdığınız sabit boyutlu bir tamsayı olarak.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Kullanarak, bu ihlali düzeltebilirsiniz `IntPtr` veya `UIntPtr` yerine tanıtıcılarını temsil etmek için `Int32` veya `UInt32`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu uyarı göndermeme değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlalini gösterir.  
  
```csharp  
internal class NativeMethods  
{  
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]  
    internal static extern IntPtr ExtractIcon(IntPtr hInst,   
        string lpszExeFileName, IntPtr nIconIndex);  
}  
```  
  
 Bu örnekte, `nIconIndex` parametresi olarak bildirilmiş bir `IntPtr`, 4 bayt genişliğinde 32-bit bir platforma ve 8 baytlık bir 64-bit platformda geniş olduğu. Görürsünüz izleyen yönetilmeyen bildiriminde `nIconIndex` tüm platformlarda bir 4-bayt işaretsiz tamsayı.  
  
```csharp  
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,   
    UINT nIconIndex);  
```  
  
## <a name="example"></a>Örnek  
 İhlali gidermek için bildirimi aşağıdaki gibi değiştirin:  
  
```csharp  
internal class NativeMethods{  
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]   
    internal static extern IntPtr ExtractIcon(IntPtr hInst,   
        string lpszExeFileName, uint nIconIndex);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşınabilirlik Uyarıları](../code-quality/portability-warnings.md)



