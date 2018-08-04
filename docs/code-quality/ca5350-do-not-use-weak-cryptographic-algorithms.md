---
title: 'CA5350: Zayıf Şifreleme Algoritmaları Kullanmayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 4c51bb8a-fcfa-46aa-ab61-634be84c4a7a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f97de4818e6be66b4ee23d97d8995dfa30533985
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39510510"
---
# <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a>CA5350: Zayıf Şifreleme Algoritmaları Kullanmayın
|||
|-|-|
|TypeName|DoNotUseWeakCryptographicAlgorithms|
|CheckId|CA5350|
|Kategori|Microsoft.Cryptography|
|Yeni Değişiklik|Bozucu olmayan|

> [!NOTE]
>  Bu uyarı, Kasım 2015 tarihinde güncelleştirildiği.

## <a name="cause"></a>Sebep
 Şifreleme algoritmaları gibi <xref:System.Security.Cryptography.TripleDES> ve karma algoritmaları gibi <xref:System.Security.Cryptography.SHA1> ve <xref:System.Security.Cryptography.RIPEMD160> zayıf olarak değerlendirilir.

 Bu şifreleme algoritmaları kadar güvenlik güvencesi daha modern ortaklarınıza olarak sağlamaz. Şifreleme karma algoritmaları <xref:System.Security.Cryptography.SHA1> ve <xref:System.Security.Cryptography.RIPEMD160> daha modern karma algoritmaları daha az çakışma Direnci sağlayın. Şifreleme algoritması <xref:System.Security.Cryptography.TripleDES> daha az güvenlik bitten daha modern şifreleme algoritmaları sağlar.

## <a name="rule-description"></a>Kural Tanımı
 Zayıf şifreleme algoritmalarını ve karma işlevler bir dizi nedenden ötürü bugün kullanılır, ancak bunlar bunların koruduğu verilerin gizliliği güvence altına almak için kullanılmamalıdır.

 Kural tetikler 3DES, SHA1 veya RIPEMD160 algoritmaları oluşturur ve kod içinde bulduğunda kullanıcıya bir uyarı.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Şifreleme bakımından daha güçlü seçenekleri kullanın:

-   TripleDES şifreleme için <xref:System.Security.Cryptography.Aes> şifreleme.

-   SHA1 veya RIPEMD160 karma işlevler için olanları içinde kullanmak [SHA-2](/windows/desktop/SecCrypto/hash-and-signature-algorithms) ailesi (örneğin <xref:System.Security.Cryptography.SHA512>, <xref:System.Security.Cryptography.SHA384>, <xref:System.Security.Cryptography.SHA256>).

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Verileri için gereken koruma düzeyini güvenlik garantisi gerekmiyorsa, bu kuraldan bir uyarıyı gizler.

## <a name="pseudo-code-example"></a>Sözde kod örneği
 Bu makalenin yazıldığı zaman itibariyle, aşağıdaki sözde kod örneği bu kural tarafından algılanan düzeni göstermektedir.

### <a name="sha-1-hashing-violation"></a>SHA-1 karma ihlali

```
using System.Security.Cryptography;
...
var hashAlg = SHA1.Create();

```

### <a name="solution"></a>Çözüm

```
using System.Security.Cryptography;
...
var hashAlg = SHA256.Create();

```

### <a name="ripemd160-br-br-hashing-violation"></a>RIPEMD160 <br /><br />Karma ihlali

```
using System.Security.Cryptography;
...
var hashAlg = RIPEMD160Managed.Create();

```

### <a name="solution"></a>Çözüm

```
using System.Security.Cryptography;
...
var hashAlg = SHA256.Create();

```

### <a name="tripledes-encryption-violation"></a>TripleDES şifreleme ihlali

```
using System.Security.Cryptography;
...
using (TripleDES encAlg = TripleDES.Create())
{
  ...
}
```

### <a name="solution"></a>Çözüm

```
using System.Security.Cryptography;
...
using (AesManaged encAlg = new AesManaged())
{
  ...
}
```