---
title: "CA2220: Sonlandırıcılar taban sınıf çağırmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: aa5ed3329d4168a0781243a4faf021de3488e77c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220: Sonlandırıcılar taban tür sonlandırıcıları çağırmalıdır
|||  
|-|-|  
|TypeName|FinalizersShouldCallBaseClassFinalizer|  
|CheckId|CA2220|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Geçersiz kılan bir türü <xref:System.Object.Finalize%2A?displayProperty=fullName> çağrılmayan <xref:System.Object.Finalize%2A> devralınabilir. taban sınıf yöntemi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Sonlandırılma, devralma hiyerarşisi aracılığıyla gönderilmelidir. Bu emin olmak için türleri bir temel sınıf'i çağırın <xref:System.Object.Finalize%2A> yönteminden kendi içinde <xref:System.Object.Finalize%2A> yöntemi. C# derleyici temel sınıf sonlandırıcıyı çağrısı otomatik olarak ekler.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için temel türün çağrısı <xref:System.Object.Finalize%2A> yönteminden, <xref:System.Object.Finalize%2A> yöntemi.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Ortak dil çalışma zamanı hedef bazı derleyicileri Microsoft Ara dile (MSIL) temel türün sonlandırıcıyı yapılan bir çağrı ekleyin. Bu kural bir uyarıdan bildirilirse, derleyici çağrı eklemez ve kodunuzu eklemeniz gerekir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki Visual Basic örnek bir türü gösterir `TypeB` doğru çağırır <xref:System.Object.Finalize%2A> devralınabilir. taban sınıf yöntemi.  
  
 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2220-finalizers-should-call-base-class-finalizer_1.vb)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Desen dispose](/dotnet/standard/design-guidelines/dispose-pattern)