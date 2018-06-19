---
title: 'CA2106: Bildirimlerin güvenliğini sağlayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5863f4d8ca4db47f7e537f0b1abc5eb280434c80
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31916805"
---
# <a name="ca2106-secure-asserts"></a>CA2106: Bildirimlerin güvenliğini sağlayın
|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir yöntem izin ileri sürer ve güvenlik önlemi olmayan çağrı üzerinde gerçekleşir.

## <a name="rule-description"></a>Kural Tanımı
 Güvenlik denetimleri yapmadan herhangi bir güvenlik izni ileri sürmek, kodunuzdaki güvenlik zayıflıklarını yararlanılabilir bırakır. Bir güvenlik izni uygulanan güvenlik yığın ilerlemesi durdurur. Arayan üzerinde herhangi bir denetim yapmadan izin assert, çağıran dolaylı olarak kod izinlerinizi kullanarak yürütebilir. Yalnızca assert zararlı bir biçimde kullanıldığından emin olduğunuzda verilebilir güvenlik denetimlerini olmadan onaylar. Assert çağırmanız kodu zararsız ise zararsız veya kullanıcılar, çağıran kodu rasgele bilgi geçiremezsiniz.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için güvenlik talebi yöntemi veya bildiri türü ekleyin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural bir uyarıdan dikkatli güvenlik incelemesi sonra yalnızca engelleyin.

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> [Güvenli kodlama yönergeleri](/dotnet/standard/security/secure-coding-guidelines)