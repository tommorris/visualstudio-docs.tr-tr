---
title: "CA1901: P-Invoke bildirimleri taşınabilir olmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
helpviewer_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
ms.assetid: 90361812-55ca-47f7-bce9-b8775d3b8803
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6e0d3ce3d0130b0a2cf40f6d4f1716c32ae7c40e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1901-pinvoke-declarations-should-be-portable"></a>CA1901: P/Invoke bildirimleri taşınabilir olmalıdır
|||  
|-|-|  
|TypeName|PInvokeDeclarationsShouldBePortable|  
|CheckId|CA1901|  
|Kategori|Microsoft.Portability|  
|Yeni Değişiklik|P/Invoke derlemenin dışından görünür durumdaysa - kesiliyor. P/Invoke derlemenin dışından görünür değilse olmayan sonu -.|  
  
## <a name="cause"></a>Sebep  
 Bu kural her parametre boyutunu ve P/Invoke dönüş değerini değerlendirir ve 32-bit ve 64 bit platformlarda yönetilmeyen kod için sıralanmış zaman boyutlarına doğru olduğunu doğrular. Bu kural en yaygın ihlalinden, bir platforma bağımlı, işaretçi ölçekli değişkeni gerekli olduğu bir sabit boyutlu tamsayı geçirmektir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural aşağıdaki senaryolardan biri ihlal oluşur:  
  
-   Olarak yazılmalıdır, parametre ve dönüş değeri bir sabit boyutlu tamsayı olarak yazılan bir `IntPtr`.  
  
-   Dönüş değeri veya parametre olarak yazılan bir `IntPtr` zaman yazdığınız sabit boyutlu tamsayı olarak.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Kullanarak bu ihlali düzeltebilirsiniz `IntPtr` veya `UIntPtr` yerine tanıtıcıları temsil etmek için `Int32` veya `UInt32`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu uyarı engelleme.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal gösterir.  
  
```csharp  
internal class NativeMethods  
{  
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]  
    internal static extern IntPtr ExtractIcon(IntPtr hInst,   
        string lpszExeFileName, IntPtr nIconIndex);  
}  
```  
  
 Bu örnekte, `nIconIndex` parametre olarak bildirilen bir `IntPtr`, 32-bit platformu ve 8 bayt bir 64-bit platformda geniş geniş 4 bayt olduğu. Aşağıdaki yönetilmeyen bildiriminde görebilirsiniz `nIconIndex` tüm platformlarda 4-bayt işaretsiz tamsayı değil.  
  
```csharp  
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,   
    UINT nIconIndex);  
```  
  
## <a name="example"></a>Örnek  
 İhlali düzeltmek için bildirimi aşağıdaki gibi değiştirin:  
  
```csharp  
internal class NativeMethods{  
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]   
    internal static extern IntPtr ExtractIcon(IntPtr hInst,   
        string lpszExeFileName, uint nIconIndex);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşınabilirlik Uyarıları](../code-quality/portability-warnings.md)