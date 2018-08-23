---
title: 'CA2200: yığın ayrıntılarını korumak için yeniden | Microsoft Docs'
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
- RethrowToPreserveStackDetails
- CA2200
helpviewer_keywords:
- CA2200
- RethrowToPreserveStackDetails
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b6be88ae7a4413ee62e39d22eddb55166e5b5075
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687120"
---
# <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200: Yığın ayrıntılarını korumak için yeniden fırlatma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2200: yığın ayrıntılarını korumak için yeniden fırlatma](https://docs.microsoft.com/visualstudio/code-quality/ca2200-rethrow-to-preserve-stack-details).  
  
TypeName | RethrowToPreserveStackDetails |  
| Checkıd | CA2200 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Bir özel durum yeniden ve özel durum açıkça belirtilen `throw` deyimi.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir özel durum sonra bunu izleme bilgileri parçası yığın izlemesi aşağıdadır. Yığın izlemesi, özel durum oluşturur ve özel durumu yakalar yöntemi ile biten yöntem ile başlayan yöntemi çağrı hiyerarşisini listesidir. Özel durum belirterek yeniden durum varsa `throw` deyimi, yığın izlemesi geçerli bir yöntem yeniden başlatılır ve özel durum döndüren özgün yöntem ile geçerli yöntemi arasındaki yöntem çağrılarını listesini kaybolur. Özel durum ile özgün yığın izleme bilgileri tutmak için kullanın `throw` özel durum belirtmeden deyimi.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için özel durum açıkça belirtmeden bir özel durum yeniden oluşturun.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir yöntemi gösterir `CatchAndRethrowExplicitly`, kural ve bir yöntem ihlal `CatchAndRethrowImplicitly`, kural karşılar.  
  
 [!code-csharp[FxCop.Usage.Rethrow#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.Rethrow/cs/FxCop.Usage.Rethrow.cs#1)]
 [!code-vb[FxCop.Usage.Rethrow#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.Rethrow/vb/FxCop.Usage.Rethrow.vb#1)]



