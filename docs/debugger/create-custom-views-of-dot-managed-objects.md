---
title: "Yönetilen nesnelerin özel görünümlerini oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data types [C#], custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
caps.latest.revision: "34"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 329e7fae6a2a8682c23417f88e59700b7caffd53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="create-custom-views-of-managed-objects"></a>Yönetilen nesnelerin özel görünümlerini oluşturma
Visual Studio veri türleri hata ayıklayıcı değişken pencerelerini görüntüler şekilde özelleştirebilirsiniz.  
  
## <a name="attributes"></a>Öznitelikler  
 C# ve Visual Basic özel veri kullanma genişletmeleri ekleyebilirsiniz <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, ve <xref:System.Diagnostics.DebuggerBrowsableAttribute>.  
  
 İçinde [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] kod, Visual Basic DebuggerBrowsable özniteliğini desteklemiyor. Bu sınırlama .NET Framework'ün daha yeni sürümlerinde kaldırılmıştır.  
  
## <a name="visualizers"></a>Görselleştiriciler  
 Herhangi bir yönetilen veri türü görüntülenecek Görselleştirici yazabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Görselleştirici yazma](../debugger/how-to-write-a-visualizer.md).  
  
## <a name="native-code"></a>Yerel kod  
 Yerel kod için Program Files\Microsoft Visual Studio 11.0\Common7\Packages\Debugger dizininde bulunan dosya autoexp.dat özel veri türü genişletmeleri ekleyebilirsiniz. Yazma yönergeler `autoexp` kuralları dosyasında bulunur.  
  
> [!CAUTION]
>  Bu dosya yapısını ve sözdizimi autoexp kuralları, Visual Studio, bir sürümünden sonraki değişebilir.  
  
 Yerel tür görünümleri bir ifade değerlendiricisi eklenti yazarak da özelleştirilebilir. Daha fazla bilgi için bkz: [EEAddIn örnek: hata ayıklama ifade değerlendiricisi eklenti](http://msdn.microsoft.com/en-us/d4f6b068-c812-45bc-9ec0-7e0363c4bb9e).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DebuggerTypeProxy özniteliğini kullanma](../debugger/using-debuggertypeproxy-attribute.md)   
 [DebuggerDisplay özniteliğini kullanma](../debugger/using-the-debuggerdisplay-attribute.md)   
 [İzleme ve QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)   
 [Hata Ayıklayıcı Görüntü Öznitelikleriyle Hata Ayıklamayı Geliştirme](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)