---
title: "CA2232: İşareti Windows Forms giriş noktalarını STAThread ile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MarkWindowsFormsEntryPointsWithStaThread
- CA2232
helpviewer_keywords:
- CA2232
- MarkWindowsFormsEntryPointsWithStaThread
ms.assetid: a3c95130-8e7f-4419-9fcd-b67d077e8efb
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fe12ce5947a22414aaf07c59945fd667b106101f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2232-mark-windows-forms-entry-points-with-stathread"></a>CA2232: Windows Forms giriş noktalarını STAThread ile işaretleyin
|||  
|-|-|  
|TypeName|MarkWindowsFormsEntryPointsWithStaThread|  
|CheckId|CA2232|  
|Kategori|Microsoft.Usage|  
|Yeni Değişiklik|Olmayan sonu|  
  
## <a name="cause"></a>Sebep  
 Bir derlemeye başvurur <xref:System.Windows.Forms> ad alanı ve kendi giriş noktası işaretlenmemiş ile <xref:System.STAThreadAttribute?displayProperty=fullName> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.STAThreadAttribute>iş parçacığı modeli uygulama için COM tek iş parçacıklı olduğunu gösterir. Bu öznitelik Windows Forms kullanan herhangi bir uygulamanın girişinde sunulur; atlanırsa, Windows bileşenleri doğru çalışmayabilir. Öznitelik yoksa, uygulama Windows Forms için desteklenmeyen birden çok iş parçacıklı apartman modeli kullanır.  
  
> [!NOTE]
>  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]Uygulama Çerçevesi kullanan projelerin işaretlemek gerekmez **ana** STAThread ile yöntemi. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Derleyici yapar, otomatik olarak.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için add <xref:System.STAThreadAttribute> özniteliği için giriş noktası. Varsa <xref:System.MTAThreadAttribute?displayProperty=fullName> özniteliği varsa, bunu kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 .NET Compact Framework, kendisi için geliştiriyorsanız, bu kural bir uyarıdan gizlemek güvenlidir <xref:System.STAThreadAttribute> özniteliktir gereksiz ve desteklenmiyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler doğru kullanımını göstermek <xref:System.STAThreadAttribute>.  
  
 [!code-csharp[FxCop.Usage.StaThread#1](../code-quality/codesnippet/CSharp/ca2232-mark-windows-forms-entry-points-with-stathread_1.cs)]
 [!code-vb[FxCop.Usage.StaThread#1](../code-quality/codesnippet/VisualBasic/ca2232-mark-windows-forms-entry-points-with-stathread_1.vb)]