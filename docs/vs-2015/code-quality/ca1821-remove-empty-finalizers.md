---
title: 'CA1821: Boş Sonlandırıcıları kaldırın | Microsoft Docs'
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
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: efd7a2675326780c8e66daf49390587a7f85db3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689267"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: Boş sonlandırıcıları kaldırın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1821: boş Sonlandırıcıları kaldırın](https://docs.microsoft.com/visualstudio/code-quality/ca1821-remove-empty-finalizers).  
  
TypeName | RemoveEmptyFinalizers |  
| Checkıd | CA1821 |  
| Kategori | Microsoft.Performance|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Bir tür boş, yalnızca temel tür Sonlandırıcı çağırır veya yöntemleri koşullu olarak yayınlanan yalnızca çağıran sonlandırıcıyı uygular.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Güncelleştirirken, nesne kullanım süresini izleme söz konusu olduğunda ek performans yükü nedeniyle sonlandırıcılardan kaçının. Nesne topladığı önce çöp toplayıcının sonlandırıcıyı çalışacak. Başka bir deyişle, iki koleksiyon nesnesi toplamak için gerekli olacaktır. Boş Sonlandırıcı eklenen yükü hiçbir avantajı bu artmasına neden olur.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Boş Sonlandırıcı kaldırın. Bir sonlandırıcı hata ayıklama için gereklidir, içindeki tüm Sonlandırıcı içine `#if DEBUG / #endif` yönergeleri.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir iletiden bastırmayın. Sonlandırma bastırmak için hata performansınızın ve hiçbir avantaj sağlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kaldırılacak boş Sonlandırıcı, içinde içine alınması bir sonlandırıcıyı gösterir `#if DEBUG / #endif` yönergeleriyle birlikte kullanan bir sonlandırıcı `#if DEBUG / #endif` yönergeleri doğru.  
  
 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.RemoveEmptyFinalizers/cs/FxCop.Performance.RemoveEmptyFinalizers.cs#1)]



