---
title: "CA5350: Zayıf şifreleme algoritmalarına kullanmayın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c51bb8a-fcfa-46aa-ab61-634be84c4a7a
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4847cd5a1721376e0ca9222be0390e3c7aad2926
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca5350-do-not-use-weak-cryptographic-algorithms"></a>CA5350: Zayıf şifreleme algoritmalarına kullanmayın
|||  
|-|-|  
|TypeName|DoNotUseWeakCryptographicAlgorithms|  
|CheckId|CA5350|  
|Kategori|Microsoft.Cryptography|  
|Yeni Değişiklik|Olmayan sonu|  
  
> [!NOTE]
>  Bu uyarı, Kasım 2015 tarihinde güncelleştirildiği.  
  
## <a name="cause"></a>Sebep  
 Şifreleme algoritmaları gibi <xref:System.Security.Cryptography.TripleDES> ve algoritmalar gibi karma <xref:System.Security.Cryptography.SHA1> ve <xref:System.Security.Cryptography.RIPEMD160> zayıf olduğu kabul edilir.  
  
 Bu şifreleme algoritmaları kadar güvenlik güvencesi daha modern ortaklarınıza olarak sağlamaz. Şifreleme algoritmaları karma <xref:System.Security.Cryptography.SHA1> ve <xref:System.Security.Cryptography.RIPEMD160> daha modern karma algoritmaları daha az çakışma dayanıklılığı sağlar. Şifreleme algoritması <xref:System.Security.Cryptography.TripleDES> daha az güvenlik bitten daha modern şifreleme algoritmaları sağlar.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Zayıf şifreleme algoritmalarını ve karma İşlevler, birçok nedenden dolayı bugün kullanılır, ancak bunlar korudukları verilerin gizliliği güvence altına almak için kullanılmamalıdır.  
  
 Kural tetikler, 3DES, SHA1 veya RIPEMD160 algoritmaları atar ve kod içinde bulduğunda kullanıcıya bir uyarı.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Şifreleme açısından güçlü seçenekleri kullanın:  
  
-   TripleDES şifreleme için kullanın <xref:System.Security.Cryptography.Aes> şifreleme.  
  
-   SHA1 veya RIPEMD160 karma işlevleri için olanları içinde kullanmak [SHA-2](https://msdn.microsoft.com/en-us/library/windows/desktop/aa382459.aspx) ailesi (örneğin <xref:System.Security.Cryptography.SHA512>, <xref:System.Security.Cryptography.SHA384>, <xref:System.Security.Cryptography.SHA256>).  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan verileri için gereken koruma düzeyini güvenlik garantisi gerekmediğinde engelleyin.  
  
## <a name="pseudo-code-example"></a>Sözde kod örneği  
 Bu yazma zamanı sürümünden itibaren bu kural tarafından algılanan desen aşağıdaki sözde kod örneği gösterilmektedir.  
  
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