---
title: "CA1031: genel özel durum türleri catch değil | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
helpviewer_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
ms.assetid: cbc283ae-2a46-4ec0-940e-85aa189b118f
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d1b11db50a4e6104c09a65ebe9e7616d223ef3ee
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031: Genel özel durum türlerini yakalamayın
|||  
|-|-|  
|TypeName|DoNotCatchGeneralExceptionTypes|  
|CheckId|CA1031|  
|Kategori|Microsoft.Design|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Genel bir özel durum gibi <xref:System.Exception?displayProperty=fullName> veya <xref:System.SystemException?displayProperty=fullName> , yakalanan bir `catch` deyimi ya da bir genel catch yan tümcesi gibi `catch()` kullanılır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Genel özel durum yakalanmamalı.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için daha belirgin bir özel durum catch veya son ifade olarak genel özel durum yeniden oluşturulması `catch` bloğu.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Genel özel durum türleri yakalama çalışma zamanı kitaplığı kullanıcı sorunlarında gizleyebilirsiniz ve hata ayıklama daha zor hale getirebilir.  
  
> [!NOTE]
>  İle başlayarak [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)], ortak dil çalışma zamanı (CLR) artık işletim sistemi ve erişim ihlali gibi yönetilen kod oluşan bozuk durumda özel durumlarını teslim [!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)], yönetilen kod tarafından işlenecek. Uygulamayı derlemek isterseniz [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] veya sonraki sürümleri ve bakımını bozuk durumda özel durumları işleme, uygulayabilirsiniz <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> özniteliği bozuk durumda özel durumu işler yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal eden bir tür ve doğru şekilde uygulayan bir tür gösterir `catch` bloğu.  
  
 [!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CPP/ca1031-do-not-catch-general-exception-types_1.cpp)]
 [!code-vb[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/VisualBasic/ca1031-do-not-catch-general-exception-types_1.vb)]
 [!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CSharp/ca1031-do-not-catch-general-exception-types_1.cs)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2200: Yığın ayrıntılarını korumak için yeniden fırlatma](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)