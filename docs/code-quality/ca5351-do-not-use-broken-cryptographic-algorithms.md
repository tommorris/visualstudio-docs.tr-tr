---
title: CA5351 Bozuk şifreleme algoritmaları kullanmayın
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 483f51b3-e186-4433-b48e-5ca24a9a9c94
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3aa720459fff6cc67080fd3368cda6ed3a82bfda
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca5351-do-not-use-broken-cryptographic-algorithms"></a>CA5351 Bozuk şifreleme algoritmaları kullanmayın
|||
|-|-|
|TypeName|DoNotUseBrokenCryptographicAlgorithms|
|CheckId|CA5351|
|Kategori|Microsoft.Cryptography|
|Yeni Değişiklik|Olmayan sonu|

> [!NOTE]
>  Bu uyarı, Kasım 2015 tarihinde güncelleştirildiği.

## <a name="cause"></a>Sebep
 İşlevleri gibi karma <xref:System.Security.Cryptography.MD5> ve şifreleme algoritmaları gibi <xref:System.Security.Cryptography.DES> ve <xref:System.Security.Cryptography.RC2> önemli riski getirebilir ve deneme yanılma saldırıları gibi Önemsiz saldırı teknikleri aracılığıyla gizli bilgilerin ortaya çıkarılmasına neden olabilir ve karma çakışmaları.

 Bilinen şifreleme saldırılarına maruz aşağıdaki şifreleme algoritmaları listede var. Şifreleme karma algoritması <xref:System.Security.Cryptography.MD5> karma çakışma saldırılarına maruz değil.  Kullanımınıza bağlı olarak, bir karma çakışma kimliğe bürünme, değişiklik yapmayı veya diğer tür saldırılar, karma işlevi şifreleme benzersiz çıktısını kullanan sistemler neden olabilir. Şifreleme algoritmaları <xref:System.Security.Cryptography.DES> ve <xref:System.Security.Cryptography.RC2> istenmeyen şifrelenmiş verilerin açığa çıkmasına neden şifreleme saldırılara maruz şunlardır.

## <a name="rule-description"></a>Kural Tanımı
 Şifreleme bozuk algoritmaları güvenli kabul edilmez ve bunların kullanılması önerilmez. Belirli güvenlik açığı kullanım bağlamında göre değişir ancak MD5 karma algoritması bilinen çakışma saldırılara açıktır.  (Örneğin, dosya imzası veya dijital sertifika) veri bütünlüğünü sağlamak için kullanılan karma algoritmaları özellikle etkilenir.  Zararsız veri kötü amaçlı veriler ile karma değeri değiştirme veya ilişkili bir dijital imza geçersiz kılmalarını yerine kullanılabilecek şekilde bu bağlamda iki ayrı veri parçaları, saldırganlar oluşturabilir.

 Şifreleme algoritmaları için:

-   <xref:System.Security.Cryptography.DES> Şifreleme değerinden bir gün içinde deneme yanılma yoluyla yapılan zorla olabilir küçük bir anahtar boyutu içerir.

-   <xref:System.Security.Cryptography.RC2> Şifreleme yere saldırgan tüm anahtar değerlerin arasındaki matematiksel ilişkileri bulur ilgili anahtar saldırılarına karşı açıktır.

 Yukarıdaki şifreleme işlevlerini hiçbirini kaynak kodunda bulur ve kullanıcı için bir uyarı oluşturur, bu kural tetikler.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Şifreleme açısından güçlü seçenekleri kullanın:

-   MD5 için karmaları içinde kullanmak [SHA-2](https://msdn.microsoft.com/library/windows/desktop/aa382459.aspx) ailesi (örneğin <xref:System.Security.Cryptography.SHA512>, <xref:System.Security.Cryptography.SHA384>, <xref:System.Security.Cryptography.SHA256>).

-   DES ve RC2 için kullanmak <xref:System.Security.Cryptography.Aes> şifreleme.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu şifreleme uzmanı tarafından gözden sürece bu kuraldan bir uyarı bastırma değil.

## <a name="pseudo-code-example"></a>Sözde kod örneği
 Bu kural ve olası alternatifler tarafından algılanan desen aşağıdaki sözde kod örneği gösterilmektedir.

### <a name="md5-hashing-violation"></a>MD5 Karma ihlali

```
using System.Security.Cryptography;
...
var hashAlg = MD5.Create();

```

### <a name="solution"></a>Çözüm

```
using System.Security.Cryptography;
...
var hashAlg = SHA256.Create();

```

### <a name="rc2-encryption-violation"></a>RC2 Şifreleme ihlali

```
using System.Security.Cryptography;
...
RC2 encAlg = RC2.Create();

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

### <a name="des-br-br-encryption-violation"></a>DES <br /><br />Şifreleme ihlali

```
using System.Security.Cryptography;
...
DES encAlg = DES.Create();

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