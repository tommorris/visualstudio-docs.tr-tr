---
title: 'CA1408: AutoDual ClassInterfaceType kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotUseAutoDualClassInterfaceType
- CA1408
helpviewer_keywords:
- CA1408
- DoNotUseAutoDualClassInterfaceType
ms.assetid: 60ca5e02-3c51-42dd-942b-4f950eecfa0f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9ee8c016896381814aa5406b4023e24799f29219
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1408-do-not-use-autodual-classinterfacetype"></a>CA1408: AutoDual ClassInterfaceType kullanma
|||  
|-|-|  
|TypeName|DoNotUseAutoDualClassInterfaceType|  
|CheckId|CA1408|  
|Kategori|Microsoft.Interoperability|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Bileşen Nesne Modeli (COM) görünür türü ile işaretlenmiş <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliğini `AutoDual` değerini <xref:System.Runtime.InteropServices.ClassInterfaceType>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Çift arabirim kullanan türler, belirli bir arabirim düzenine bağlanmak için istemcileri etkinleştirir. Gelecek sürümdeki değişiklikler, türün düzeni veya bazı temel türler, arayüze bağlanan COM istemcilerini kesintiye uğratır. Varsayılan olarak, varsa <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliği belirtilmezse, yalnızca gönderme arabirimi kullanılır.  
  
 Aksi takdirde işaretlenmiş sürece, tüm genel türlere COM görünür; Tüm özel ve genel türleri COM'a görünmez  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için değerini değiştirme <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliğini `None` değerini <xref:System.Runtime.InteropServices.ClassInterfaceType> ve açıkça arabirimi tanımlayın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Türü ve temel türlerinden düzenini sonraki bir sürümde değiştirmez belirli olduğu sürece bu kuraldan bir uyarı bastırma değil.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kural ve açık bir arabirim kullanılacak sınıfı yeniden bildirimi ihlal eden bir sınıfı gösterir.  
  
 [!code-csharp[FxCop.Interoperability.AutoDual#1](../code-quality/codesnippet/CSharp/ca1408-do-not-use-autodual-classinterfacetype_1.cs)]
 [!code-vb[FxCop.Interoperability.AutoDual#1](../code-quality/codesnippet/VisualBasic/ca1408-do-not-use-autodual-classinterfacetype_1.vb)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1403: Otomatik yerleşim türleri COM görünebilir olmamalıdır](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)  
  
 [CA1412: ComSource Arabirimlerini IDispatch olarak işaretleyin](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birlikte çalışma için .NET türlerini niteleme](/dotnet/framework/interop/qualifying-net-types-for-interoperation)   
 [Yönetilmeyen Kod ile Birlikte Çalışma](/dotnet/framework/interop/index)