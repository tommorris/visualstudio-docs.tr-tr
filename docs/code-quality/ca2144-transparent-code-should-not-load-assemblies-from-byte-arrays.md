---
title: 'CA2144: Saydam kod derlemeleri bayt dizilerinden yüklememelidir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6b0357d6fc0c0cbfdd59c7718d58181e4d58b3a3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917767"
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144: Saydam kod derlemeleri bayt dizilerinden yüklememelidir
|||
|-|-|
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|
|CheckId|CA2144|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Saydam bir yöntemi, aşağıdaki yöntemlerden birini kullanarak bir bayt dizisinden bir derleme yükler:

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

## <a name="rule-description"></a>Kural Tanımı
 Saydam kod için güvenlik incelemesi kritik kod için güvenlik incelemesi kadar kapsamlı değildir, çünkü saydam kod güvenlik duyarlı eylemleri gerçekleştiremez. Bir bayt dizisinden yüklenen derlemeler saydam kodda fark edilmeyebilir ve o bayt dizisi denetlenmesi gereken kritik ya da daha da önemlisi güvenli kritik kod içerebilir. Bu nedenle, saydam kod derlemeleri bayt dizisinden yüklenmemelidir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için derleme yükleme yöntemini işaretlemek <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Saydam yöntemi bir bayt dizisinden bir derlemeyi yüklediğinden kural aşağıdaki kod ateşlenir.

 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../code-quality/codesnippet/CSharp/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays_1.cs)]