---
title: 'CA2200: Yığın ayrıntılarını korumak için yeniden fırlatma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RethrowToPreserveStackDetails
- CA2200
helpviewer_keywords:
- CA2200
- RethrowToPreserveStackDetails
ms.assetid: 046e1b98-c4dc-4515-874f-9c0de2285621
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 688c10802b144c619b22b06309cec6dee5efc52e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31919782"
---
# <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200: Yığın ayrıntılarını korumak için yeniden fırlatma
|||
|-|-|
|TypeName|RethrowToPreserveStackDetails|
|CheckId|CA2200|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Olmayan sonu|

## <a name="cause"></a>Sebep
 Bir özel durum yeniden oluşturulur ve özel durum açıkça belirtilen `throw` deyimi.

## <a name="rule-description"></a>Kural Tanımı
 Bir özel durum oluşturulduktan sonra bunu izleme bilgileri yığın izlemesi parçasıdır. Yığın izlemesi, özel durum oluşturur ve özel durum yakalar yöntemi ile biten yöntemi ile başlayan yöntemi çağrı hiyerarşisi listesidir. Özel durum belirterek yeniden özel durum, `throw` deyimi, yığın izlemesi geçerli bir yöntem yeniden başlatılıp başlatılmayacağını ve özel durum oluşturdu özgün yöntemi ve geçerli yöntemi arasındaki yöntem çağrılarını listesi kaybolur. Özel özgün yığın izleme bilgileri korumak için kullanın `throw` özel belirtmeden deyimi.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için özel durum açıkça belirtmeden özel durum yeniden oluşturun.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir yöntemi gösterir `CatchAndRethrowExplicitly`, kural ve bir yöntem ihlal `CatchAndRethrowImplicitly`, kural karşılar.

 [!code-csharp[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/CSharp/ca2200-rethrow-to-preserve-stack-details_1.cs)]
 [!code-vb[FxCop.Usage.Rethrow#1](../code-quality/codesnippet/VisualBasic/ca2200-rethrow-to-preserve-stack-details_1.vb)]