---
title: 'CA2232: İşareti Windows Forms giriş noktalarını STAThread ile işaretleyin | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MarkWindowsFormsEntryPointsWithStaThread
- CA2232
helpviewer_keywords:
- CA2232
- MarkWindowsFormsEntryPointsWithStaThread
ms.assetid: a3c95130-8e7f-4419-9fcd-b67d077e8efb
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5b7c479856ceddbf6785833d207984c9d01343e5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628533"
---
# <a name="ca2232-mark-windows-forms-entry-points-with-stathread"></a>CA2232: Windows Forms giriş noktalarını STAThread ile işaretleyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2232: işareti Windows Forms giriş noktalarını STAThread](https://docs.microsoft.com/visualstudio/code-quality/ca2232-mark-windows-forms-entry-points-with-stathread).  
  
TypeName | MarkWindowsFormsEntryPointsWithStaThread |  
| Checkıd | CA2232 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Bir derlemeye başvuran <xref:System.Windows.Forms> ad alanı ve kendi giriş noktası olarak işaretlenmemiş ile <xref:System.STAThreadAttribute?displayProperty=fullName> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 <xref:System.STAThreadAttribute> iş parçacığı modeli uygulama için COM tek iş parçacıklı grup olduğunu gösterir. Bu öznitelik Windows Forms kullanan herhangi bir uygulamanın girişinde sunulur; atlanırsa, Windows bileşenleri doğru çalışmayabilir. Öznitelik mevcut değilse, uygulamanın Windows Forms için desteklenmiyor çok iş parçacıklı grubun modeli kullanır.  
  
> [!NOTE]
>  [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] Uygulama Çerçevesi kullanan projeler işaretlemek gerekmez **ana** yöntemi STAThread ile işaretleyin. [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] Derleyici her şeyi otomatik olarak.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için ekleme <xref:System.STAThreadAttribute> özniteliği giriş noktası. Varsa <xref:System.MTAThreadAttribute?displayProperty=fullName> özniteliği varsa, bunu kaldırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 .NET Compact Framework için kendisi için geliştiriyorsanız, bu kuraldan bir uyarıyı bastırmak güvenlidir <xref:System.STAThreadAttribute> özniteliktir gereksiz ve desteklenmiyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler doğru kullanımını gösterir <xref:System.STAThreadAttribute>.  
  
 [!code-csharp[FxCop.Usage.StaThread#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.StaThread/cs/FxCop.Usage.StaThread.cs#1)]
 [!code-vb[FxCop.Usage.StaThread#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.StaThread/vb/FxCop.Usage.StaThread.vb#1)]



