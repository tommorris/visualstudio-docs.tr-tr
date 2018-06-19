---
title: 'CA2135: Düzey 2 derlemeler LinkDemands içermemelidir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2135
ms.assetid: 7a775285-42d2-4f13-8434-3fdb0deeebe6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c33df3775d0a267c35c80abd73d27a580a586da
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917330"
---
# <a name="ca2135-level-2-assemblies-should-not-contain-linkdemands"></a>CA2135: Düzey 2 derlemeler LinkDemands içermemelidir
|||
|-|-|
|TypeName|SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2135|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir sınıf veya sınıf üyesi kullanarak bir <xref:System.Security.Permissions.SecurityAction> uygulamada Düzey 2 güvenlik kullanıyor.

## <a name="rule-description"></a>Kural Tanımı
 LinkDemands, düzey 2 güvenlik kural kümesinden kaldırılmıştır. Tam zamanında (JIT) derleme zamanında güvenlik zorlamak için LinkDemands kullanmak yerine, yöntemleri, türleri ve alanlarla işaretlemek <xref:System.Security.SecurityCriticalAttribute> özniteliği.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için kaldırmak <xref:System.Security.Permissions.SecurityAction> ve tür veya üye ile işaretle <xref:System.Security.SecurityCriticalAttribute> özniteliği.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, <xref:System.Security.Permissions.SecurityAction> kaldırılmalı ve yöntemi ile işaretlenen <xref:System.Security.SecurityCriticalAttribute> özniteliği.

 [!code-csharp[FxCop.Security.CA2135.SecurityRuleSetLevel2MethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2135-level-2-assemblies-should-not-contain-linkdemands_1.cs)]