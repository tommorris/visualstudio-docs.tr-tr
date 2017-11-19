---
title: "CA1704: Tanımlayıcılar doğru yazılmalıdır | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e43e3340cdbc05ec00c909542e201692199ccfef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704: Tanımlayıcılar doğru yazılmalıdır
|||  
|-|-|  
|TypeName|IdentifiersShouldBeSpelledCorrectly|  
|CheckId|CA1704|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 Tanımlayıcı adı Microsoft Yazım kitaplığı tarafından tanınmayan bir veya daha fazla sözcükler içeriyor. Bu kural değil oluşturucular veya özel adlı üyeleri get gibi denetleyin ve özellik erişimcisi ayarlayın.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural tanımlayıcısını belirteçlere ayrıştırır ve her belirteç yazımını denetler. Ayrıştırma algoritması şu dönüşümleri gerçekleştirir:  
  
-   Büyük harfler, yeni bir belirteç başlatın. Örneğin, MyNameIsJoe "Benim", "Ad", "", "Can" için tokenizes.  
  
-   Birden çok büyük harfler için yeni bir belirteç son büyük harf başlatır. Örneğin, "GUI", "Düzenleyicisi" GUIEditor tokenizes.  
  
-   Baştaki ve sondaki kesme kaldırılır. Örneğin, "gönderene" 'sender' tokenizes.  
  
-   Alt çizgi, bir belirteç sonu belirtmek ve kaldırılır. Örneğin, "Hello", Hello_world tokenizes "world".  
  
-   Katıştırılmış ve işaretlerini kaldırılır. Örneğin, & mat tokenizes "biçimlendirmek için".  
  
 Varsayılan olarak, yazım İngilizce (TR) sürümü kullanılır. Diğer bir dil sözlükleri şu anda kullanılabilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için Word yazımı düzeltin veya word CustomDictionary.xml adlı özel bir sözlüğe ekleyin. Proje dizininin aracı yükleme dizini veya kullanıcı profili altındaki aracı ile ilişkili dizinde sözlük yerleştirin (%USERPROFILE%\Application veri\\...). Bir projeye özel sözlük ekleme konusunda bilgi almak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], bkz: [nasıl yapılır: Kod Analizi dizinini özelleştirme](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
  
-   Sözcükler/sözlük/Recognized yolunda bir ihlali oluşmamalıdır sözcükleri ekleyin.  
  
-   Sözcükler/sözlük/tanınmayan yolunda ihlaline neden sözcükleri ekleyin.  
  
-   Sözlük/sözcükler/kullanım dışı yolunda artık kullanılmayan olarak işaretlenen sözcükleri ekleyin. İlgili kural konusuna [CA1726: tercih edilen terimleri kullanın](../code-quality/ca1726-use-preferred-terms.md) daha fazla bilgi için.  
  
-   Özel durumlar kısaltma büyük/küçük harf kuralları kısaltmalar/sözlük/CasingExceptions yoluna ekleyin.  
  
 Özel sözlük dosyası yapısının bir örnek verilmiştir.  
  
```  
<Dictionary>  
   <Words>  
      <Unrecognized>  
         <Word>cb</Word>  
      </Unrecognized>  
      <Recognized>  
         <Word>stylesheet</Word>  
         <Word>GotDotNet</Word>  
      </Recognized>  
      <Deprecated>  
         <Term PreferredAlternate="EnterpriseServices">ComPlus</Term>  
      </Deprecated>  
   </Words>  
   <Acronyms>  
      <CasingExceptions>  
         <Acronym>CJK</Acronym>  
         <Acronym>Pi</Acronym>  
      </CasingExceptions>  
   </Acronyms>  
</Dictionary>  
```  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural bir uyarıdan yalnızca word bilerek yanlış yazılmış ise ve sınırlı sayıda kitaplığı için Word'ün uyguladığı engelleyin. Doğru yazılmış kelimeler için yeni yazılım kitaplıklar gereklidir öğrenme eğrisini düşürebilir.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2204: Değişmez değerler doğru yazılmalıdır](../code-quality/ca2204-literals-should-be-spelled-correctly.md)  
  
 [CA1703: Kaynak dizeler doğru yazılmalıdır](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
 [CA1709: Tanımlayıcılar doğru ortası](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Tanımlayıcılar örnekten daha fazla farklı olmalıdır](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: Tanımlayıcılar alt çizgi içermemelidir](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1726: tercih edilen kullanım koşulları](../code-quality/ca1726-use-preferred-terms.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Kod Analizi dizinini özelleştirme](../code-quality/how-to-customize-the-code-analysis-dictionary.md)
