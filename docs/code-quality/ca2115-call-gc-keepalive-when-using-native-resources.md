---
title: "CA2115: Yerel kaynaklar kullanırken GC.KeepAlive'ı çağırın"
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CallGCKeepAliveWhenUsingNativeResources
- CA2115
helpviewer_keywords:
- CA2115
- CallGCKeepAliveWhenUsingNativeResources
ms.assetid: f00a59a7-2c6a-4bbe-a1b3-7bf77d366f34
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 66621bec3316dfcee92a1e5b1d1d1a8d97ae5c54
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca2115-call-gckeepalive-when-using-native-resources"></a>CA2115: Yerel kaynaklar kullanırken GC.KeepAlive'ı çağırın
|||
|-|-|
|TypeName|CallGCKeepAliveWhenUsingNativeResources|
|CheckId|CA2115|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Bir yöntem bir sonlandırıcı türüyle içinde bildirilen başvuruda bulunan bir <xref:System.IntPtr?displayProperty=fullName> veya <xref:System.UIntPtr?displayProperty=fullName> alan, ancak çağrılmayan <xref:System.GC.KeepAlive%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Kural Tanımı
 Yönetilen kodda, daha fazla başvuru varsa çöp toplama bir nesne sonlandırır. Nesnelere yönetilmeyen başvurular çöp toplama engellemez. Bu kural, yönetimsiz kod içinde kullanıldığı sırada yönetilmeyen kaynağın sonlandırılması nedeniyle oluşabilecek hataları algılar.

 Bu kural varsayar <xref:System.IntPtr> ve <xref:System.UIntPtr> alanları yönetilmeyen kaynakları işaretçiler depolar. Bir sonlandırıcı amacı yönetilmeyen kaynakları serbest olduğundan, kuralın sonlandırıcıyı işaretçi alanları tarafından işaret yönetilmeyen kaynak boşaltır varsayar. Bu kural, ayrıca yöntemi yönetilmeyen kaynak yönetilmeyen koda geçirmek için imleç alanı başvurulduğu varsayar.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için bir çağrı ekleyin <xref:System.GC.KeepAlive%2A> yöntemi için geçerli örneğini geçirme (`this` C# ve C++) için bağımsız değişken olarak. Çağrı nereye nesne çöp koleksiyonundan korumalı olması gereken kodu son satırından sonra yerleştirin. Çağrısından sonra hemen <xref:System.GC.KeepAlive%2A>, yönetilen hiçbir başvuruları var olduğu varsayımıyla nesne yeniden atık toplama için hazır olarak kabul edilir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural için hatalı pozitif sonuç yol açabilecek bazı varsayımlarda bulunur. Bu kural bir uyarıdan, güvenli bir şekilde gizleyebilirsiniz:

-   Sonlandırıcıyı içeriğini boş değil <xref:System.IntPtr> veya <xref:System.UIntPtr> yöntemi tarafından başvurulan alan.

-   Yöntem geçemezse <xref:System.IntPtr> veya <xref:System.UIntPtr> yönetilmeyen kod alanı.

 Hariç önce diğer iletileri dikkatle gözden geçirin. Bu kural yeniden oluşturun ve hata ayıklama zor olan hataları algılar.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, `BadMethod` yapılan bir çağrı içermez `GC.KeepAlive` ve bu nedenle kural ihlal ediyor. `GoodMethod` Düzeltilmiş kodunu içerir.

> [!NOTE]
>  Kod derlenir ve çalışır ancak bu örnek sahte kodu, bir yönetilmeyen kaynak oluşturulan veya serbest olmadığından uyarı tetiklenir değil.

 [!code-csharp[FxCop.Security.IntptrAndFinalize#1](../code-quality/codesnippet/CSharp/ca2115-call-gc-keepalive-when-using-native-resources_1.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.GC.KeepAlive%2A?displayProperty=fullName> <xref:System.IntPtr?displayProperty=fullName> <xref:System.Object.Finalize%2A?displayProperty=fullName> <xref:System.UIntPtr?displayProperty=fullName> [Desen dispose](/dotnet/standard/design-guidelines/dispose-pattern)