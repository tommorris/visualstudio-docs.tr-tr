---
title: 'CA1301: Yinelenen hızlandırıcılardan kaçının'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1301
- AvoidDuplicateAccelerators
helpviewer_keywords:
- CA1301
- AvoidDuplicateAccelerators
ms.assetid: 20570a00-864b-459c-a1fa-a6e9db5f1001
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9d402bec5bf9c79b845f3bfa643c65fc07359a09
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900125"
---
# <a name="ca1301-avoid-duplicate-accelerators"></a>CA1301: Yinelenen hızlandırıcılardan kaçının
|||
|-|-|
|TypeName|AvoidDuplicateAccelerators|
|CheckId|CA1301|
|Kategori|Microsoft.Globalization|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Bir tür genişletir <xref:System.Windows.Forms.Control?displayProperty=fullName> ve kaynak dosyasında depolanır aynı erişim anahtarlara sahip iki veya daha fazla en üst düzey denetimleri içerir.

## <a name="rule-description"></a>Kural Tanımı
 Giriş anahtarı, bir hızlandırıcı olarak da bilinir, ALT anahtarını kullanarak klavye giriş denetimini sağlar. Birden çok denetimin yinelenen erişim tuşları varsa, erişim tuşunun davranışı iyi tanımlı değildir. Kullanıcı erişim tuşunu kullanarak erişim hedeflenen denetimi mümkün olmayabilir ve bir denetim kullanılmaya farklı etkinleştirilmemiş olabilir.

 Bu kuralın geçerli uygulama menüsü öğeleri yok sayar. Ancak, aynı alt menü öğeleri aynı erişim anahtarları yok.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için tüm denetimler için benzersiz erişim anahtarları tanımlayın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, aynı erişim anahtarlara sahip iki denetimleri içeren en az bir form gösterilmektedir. Anahtarları gösterilmiyor bir kaynak dosyasında depolanır; Ancak, bunların değerleri açıklanmış görünür çıkışı `checkBox.Text` satırları. Yinelenen hızlandırıcılardan davranışını değiştirerek incelenebilir `checkBox.Text` çıkışı açıklamalı dekiler satırıyla. Ancak, bu durumda, örnek bir uyarı kuralından oluşturmaz.

 [!code-csharp[FxCop.Globalization.AvoidDuplicateAccels#1](../code-quality/codesnippet/CSharp/ca1301-avoid-duplicate-accelerators_1.cs)]

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Resources.ResourceManager?displayProperty=fullName> [Masaüstü uygulamalarındaki kaynaklar](/dotnet/framework/resources/index)