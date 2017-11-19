---
title: "CA1709: Tanımlayıcılar doğru ortası | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IdentifiersShouldBeCasedCorrectly
- CA1709
helpviewer_keywords:
- CA1709
- IdentifiersShouldBeCasedCorrectly
ms.assetid: f633d1a7-4ca4-40ae-b207-ec571c5fb083
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d9332359228d657e9155996443822a5d1c11ad01
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1709-identifiers-should-be-cased-correctly"></a>CA1709: Tanımlayıcıların büyük/küçük harfleri doğru yazılmalıdır
|||  
|-|-|  
|TypeName|IdentifiersShouldBeCasedCorrectly|  
|CheckId|CA1709|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|-Derlemeler, ad alanlarını, türleri, üyeleri ve parametreleri oluştuğunda kesiliyor.<br /><br /> Genel tür parametreleri harekete zaman bölünemez -.|  
  
## <a name="cause"></a>Sebep  
 Tanımlayıcı adı ortası doğru değil.  
  
 \-veya -  
  
 İkinci harf küçük harf ve iki harfli kısaltma bir tanımlayıcı adını içerir.  
  
 \-veya -  
  
 Tanımlayıcı adı bir kısaltma üç veya daha fazla büyük harflerin içeriyor.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Adlandırma kuralları hedefleyen ortak dil çalışma zamanı kitaplıkları için genel bir bakış sağlar. Bu, yeni yazılım kitaplıkları için gereklidir ve kitaplık geliştirme yönetilen kodda uzmanlığa sahip olan kişi tarafından geliştirilmiştir müşteri güvenini artırır öğrenme eğrisini azaltır.  
  
 Kurala göre parametre adlarını ortası büyük/küçük harf kullanın; ad alanı, tür ve üye adları kullanın Pascal büyük/küçük harf. Bir başlamalıdır adı ilk harfi küçük harf ve adında kalan tüm sözcükleri ilk harfini büyük olduğu. "PacketSniffer", "ioFile" ve "fatalErrorCode" başlamalıdır adları örnekleridir. Bir Pascal ortası adı ilk harfini büyük harf ve adında kalan tüm sözcükleri ilk harfini büyük olduğu. "PacketSniffer", "IOFile" ve "FatalErrorCode" Pascal ortası adları örnekleridir.  
  
 Bu kural adı büyük/küçük harf üzerinde dayalı sözcükler ayıran ve iki harfli sözcüklere "İçinde" gibi sık kullanılan iki harfli sözcükleri veya "Benim" listesini karşı denetler. Bir eşleşme bulunmazsa, word bir kısaltma olduğu varsayılır. Ayrıca, bu kural adı bir satır dört büyük harflerle ya da bir satırda adının sonuna üç büyük harflerle içerdiğinde bir kısaltma bulduğu varsayar.  
  
 Kurala göre iki harfli kısaltmalar tümüyle büyük harfe kullanıyorsanız ve üç veya daha fazla karakterden oluşan kısaltmalar Pascal büyük/küçük harf. Aşağıdaki örnekler bu adlandırma kuralını kullanın: 'DB', 'CR', 'Cpa' ve 'Ecma'. Aşağıdaki örnekler kuralı ihlal eden: 'GÇ', 'XML' ve 'Savunma Bakanlığı' nonparameter adları, 'xp' ve 'cpl'.  
  
 'ID' özel-ortası bu kural ihlal neden olacak. 'Id' bir kısaltma değil, ancak 'Kimliği' ifadesinin kısaltmasıdır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Böylece doğru ortası adını değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu Adlandırma kurallarınızı varsa veya düzgün bir ad, örneğin, bir şirket veya bir teknoloji adı tanımlayıcısını temsil ediyorsa gizlemek güvenlidir.  
  
 Ayrıca belirli terimleri, kısaltmalar ve kısaltmalar ekleyebilirsiniz, kod çözümleme özel sözlüğe. Bu kural ihlalleri özel sözlükte belirtilen koşulları neden olmaz. Daha fazla bilgi için bkz: [nasıl yapılır: Kod Analizi dizinini özelleştirme](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)