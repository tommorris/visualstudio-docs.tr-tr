---
title: 'CA1713: Olaylarda önce veya sonra önek olmamalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- EventsShouldNotHaveBeforeOrAfterPrefix
- CA1713
helpviewer_keywords:
- CA1713
- EventsShouldNotHaveBeforeOrAfterPrefix
ms.assetid: 855772a4-aa9e-410b-88c1-c5fba1ca63da
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 66e3d513188093a29aa9f7bb1c9f83b9c70e54d3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915319"
---
# <a name="ca1713-events-should-not-have-before-or-after-prefix"></a>CA1713: Olaylarda önce veya sonra önek olmamalıdır
|||
|-|-|
|TypeName|EventsShouldNotHaveBeforeOrAfterPrefix|
|CheckId|CA1713|
|Kategori|Microsoft.Naming|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir olayın adı 'Before' veya 'After' başlar.

## <a name="rule-description"></a>Kural Tanımı
 Olay adları olayı oluşturan eylem açıklamalıdır. Belirli bir sırayla ilgili olayları adlandırmak için şimdiki veya geçmiş zamanı göreceli konumun sıralı eylemlerini belirtmek için kullanın. Olayları çifti adlandırma kaynak kapatılırken hata oluştuğunda, örneğin, örneğin 'Kapatma' ve 'Kapalı' yerine 'BeforeClose' ve 'AfterClose' adı.

 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır öğrenme eğrisini azaltır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Olay adı öneki kaldırın ve yoksa veya geçmiş zamanın bir Fiilin kullanılacak adını değiştirmeyi göz önünde bulundurun.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.