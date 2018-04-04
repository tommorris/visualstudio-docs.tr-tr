---
title: 'CA1703: Kaynak dizeler doğru yazılmalıdır | Microsoft Docs'
ms.date: 03/28/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1227849992cf91a208563020583b19af48b13d42
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="ca1703-resource-strings-should-be-spelled-correctly"></a>CA1703: Kaynak dizeler doğru yazılmalıdır

|||
|-|-|
|TypeName|ResourceStringsShouldBeSpelledCorrectly|
|CheckId|CA1703|
|Kategori|Microsoft.Naming|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep

Kaynak dizesi, Microsoft Yazım kitaplığı tarafından tanınmayan bir veya birkaç sözcük içerir.

## <a name="rule-description"></a>Kural açıklaması

Bu kural kaynak dizesi (bileşik sözcüklerin belirtece dönüştürmek) sözcüklere ayrıştırır ve her word/token yazımını denetler. Ayrıştırma algoritması hakkında daha fazla bilgi için bkz: [CA1704: tanımlayıcılar yazıldığından](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

## <a name="how-to-fix-violations"></a>İhlallerini düzeltmek nasıl

Bu kural ihlal düzeltmek için doğru yazıldığından veya özel bir sözlüğe sözcükler ekleme tam sözcükler kullanın. Özel sözlük kullanma hakkında daha fazla bilgi için bkz: [CA1704: tanımlayıcılar yazıldığından](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

## <a name="change-the-dictionary-language"></a>Sözlük dilini değiştirme

Varsayılan olarak, yazım İngilizce (TR) sürümü kullanılır. Yazım denetimi dilini değiştirmek istiyorsanız, ekleyerek aşağıdakilerden birini özniteliklerini şekilde bunu yapabilirsiniz, *AssemblyInfo.cs* veya *AssemblyInfo.vb* dosyası:

- Kullanım <xref:System.Reflection.AssemblyCultureAttribute> kültürü kaynaklarınızı uydu derlemesi içinde olup olmadığını belirtmek için.
- Kullanım <xref:System.Resources.NeutralResourcesLanguageAttribute> belirtmek için *bağımsız kültür* kodunuzu aynı bütünleştirilmiş kaynaklarınız varsa, derleme.

> [!IMPORTANT]
> Bir İngilizce tabanlı kültürü dışında her şey için kültürü ayarlama, bu kod analizi kural sessiz bir şekilde devre dışı bırakılır.

## <a name="when-to-suppress-warnings"></a>Ne zaman uyarıları bastırma

Bu kuraldan uyarıyı bastırmayın. Doğru yazılmış kelimeler yeni yazılım kitaplıkları öğrenmek için gereken süreyi azaltmak.

## <a name="related-rules"></a>İlgili kuralları

- [CA1701: Kaynak dize bileşik sözcüklerinin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA2204: Değişmez değerler doğru yazılmalıdır](../code-quality/ca2204-literals-should-be-spelled-correctly.md)