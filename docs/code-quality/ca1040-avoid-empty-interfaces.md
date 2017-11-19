---
title: "CA1040: boş arabirimlerden kaçının | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7e086ffc1b0166ec17954323b8cf7871fd758ea0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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