---
title: "CA2115: GC çağırın. Yerel kaynaklar kullanırken KeepAlive | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CallGCKeepAliveWhenUsingNativeResources
- CA2115
helpviewer_keywords:
- CA2115
- CallGCKeepAliveWhenUsingNativeResources
ms.assetid: f00a59a7-2c6a-4bbe-a1b3-7bf77d366f34
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f767c923d319a0accce655eea84a6fff22dc5069
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
 Aşağıdaki örnekte, `BadMethod` yapılan bir çağrı içermez `GC.KeepAlive` ve bu nedenle kural ihlal ediyor. `GoodMethod`Düzeltilmiş kodunu içerir.  
  
> [!NOTE]
>  Kod derlenir ve çalışır ancak bu örnek sahte kodu, bir yönetilmeyen kaynak oluşturulan veya serbest olmadığından uyarı tetiklenir değil.  
  
 [!code-csharp[FxCop.Security.IntptrAndFinalize#1](../code-quality/codesnippet/CSharp/ca2115-call-gc-keepalive-when-using-native-resources_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.GC.KeepAlive%2A?displayProperty=fullName>   
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.Object.Finalize%2A?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>   
 [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)