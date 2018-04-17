---
title: 'CA1040: boş arabirimlerden kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 26ba25038baf0d54c1705d4f4dd6c9b0cca9f856
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: Boş arabirimlerden kaçının
|||  
|-|-|  
|TypeName|AvoidEmptyInterfaces|  
|CheckId|CA1040|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Arabirim tüm üyeleri bildirme ya da iki veya daha fazla diğer arabirimlerini.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Arayüzler bir davranış veya kullanım sözleşmesi sağlayan üyeleri tanımlar. Arabirim tarafından tanımlanan fonksiyonellik herhangi bir tür tarafından türün kalıtım hiyerarşisinde nerede belirdiği önemsenmeksizin devralınabilir. Tür arabirimin üyeleri için uygulamaları sağlayarak bir arayüz uygular. Boş bir arabirim üye tanımlamıyor. Bu nedenle, uygulanabilir bir sözleşme tanımlamıyor.  
  
 Tasarımınızın boş içeriyorsa türleri arabirimleri uygulamak için beklenen, büyük olasılıkla bir işaretçi veya türleri grubu belirlemenin bir yolu bir arabirim kullanıyor. Bu kimliği çalışma zamanında meydana gelir, bunu gerçekleştirmek için doğru bir şekilde özel bir öznitelik kullanmaktır. Varlık veya öznitelik olmaması ya da öznitelik özelliklerini hedef türlerini tanımlamak için kullanın. Ardından kimliği derleme zamanında gerçekleşmesi gerekir, boş bir arabirim kullanmak için kabul edilebilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Arabirimi kaldırmak veya üyeleri ekleyin. Boş arabirimi türleri kümesi etiketlemek için kullanılıyorsa, arabirim ile özel bir öznitelik değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan arabirimi derleme zamanında türleri kümesini tanımlamak için kullanıldığında gizlemek güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, boş bir arabirimi gösterir.  
  
 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]