---
title: "CA2141: saydam yöntemler linkdemands'i karşılamamalıdır | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2141
ms.assetid: 2957f5f7-c511-4180-ba80-752034f10a77
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 90b1873a13f6e60863a99492c353d2270fdea5e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2141transparent-methods-must-not-satisfy-linkdemands"></a>CA2141:Transparent yöntemleri LinkDemands'i karşılamamalıdır
|||  
|-|-|  
|TypeName|TransparentMethodsMustNotSatisfyLinkDemands|  
|CheckId|CA2141|  
|Kategori|Microsoft.Security|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Güvenliği saydam yöntemi derlemedeki ile işaretli olmayan bir yöntemi çağırır <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) özniteliği veya bir güvenlik saydam yöntemi karşılayan bir <xref:System.Security.Permissions.SecurityAction> `.LinkDemand` bir türü ya da bir yöntem.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir LinkDemand çağıran istenmeyen ayrıcalık yükselmesine neden bir güvenlik hassas bir işlemdir. Güvenliği saydam kod LinkDemands, getirmelidir güvenlik açısından kritik kodu aynı güvenlik denetim gereksinimlerini tabi olduğundan değil. Güvenlik kuralı kümesi düzey 1 derlemelerde saydam yöntemler, bunlar, performans sorunlarına neden olabilir çalışma zamanında tam taleplerini dönüştürülecek karşılayan tüm LinkDemands neden olur. Güvenlik kuralı kümesi Düzey 2 derlemeler içinde bir LinkDemand karşılamak çalışırsanız tam zamanında (JIT) derleyicide derlemek saydam yöntemler başarısız olur.  
  
 Bu usee Düzey 2 güvenlik, bir LinkDemand karşılamak veya APTCA olmayan bütünleştirilmiş kodunda bir yöntemi çağırmak için bir güvenlik saydam yöntemi tarafından denemeleri derlemelerde başlatır bir <xref:System.MethodAccessException>; düzey 1 derlemelerde LinkDemand tam isteğe bağlı olur.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için erişimi yöntemiyle işaretlemek <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği veya LinkDemand erişilen yönteminden kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, saydam bir yöntemi, bir LinkDemand sahip bir yöntemi çağırmak çalışır. Bu kural, bu kodu ateşlenir.  
  
 [!code-csharp[FxCop.Security.CA2141.TransparentMethodsMustNotSatisfyLinkDemands#1](../code-quality/codesnippet/CSharp/ca2141-transparent-methods-must-not-satisfy-linkdemands_1.cs)]