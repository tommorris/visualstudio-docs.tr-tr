---
title: 'Nasıl yapılır: Kod Çözümleme Dizinini Özelleştirme'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis dictionary
- custom dictionary, code analysis
- dictionary, code analysis
ms.assetid: 667e3b4e-beff-48be-b3d1-376e1716a895
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f1a0ecc19d5648d6ee9454a53c9b0a1ebcb5a2e1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924310"
---
# <a name="how-to-customize-the-code-analysis-dictionary"></a>Nasıl yapılır: Kod Çözümleme Dizinini Özelleştirme
Kod çözümleme tanımlayıcıları kodunuzda yazımı, dilbilgisi çalışması ve diğer adlandırma kurallarına göre hataları denetlemek için yerleşik bir sözlük kullanır [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] yönergeleri. Eklemek, kaldırmak veya koşulları, kısaltmalar ve kısaltmalar yerleşik sözlüğüne değiştirmek için bir özel sözlük Xml dosyası oluşturabilirsiniz.

 Örneğin, kodunuzu bulunan adlı bir sınıf varsayalım **DoorKnokker**. Kod çözümleme iki sözcüklerin bileşik adı tanımlamak: **kapı** ve **knokker**. Daha sonra bir uyarı oluşturacak, **knokker** doğru yazıldığından değil. Yazım tanımak için Kod Analizi zorlamak için terimi ekleyebilirsiniz **knokker** özel sözlüğe.

## <a name="to-create-a-custom-dictionary"></a>Özel sözlük oluşturmak için
 Adlı bir dosya oluşturun **CustomDictionary.xml**.

 Aşağıdaki XML yapısını kullanarak özel sözcüklerinizi tanımlayın:

```
<Dictionary>
      <Words>
         <Unrecognized>
            <Word>knokker</Word>
         </Unrecognized>
         <Recognized>
            <Word></Word>
         </Recognized>
         <Deprecated>
            <Term PreferredAlternate=""></Term>
         </Deprecated>
         <Compound>
            <Term CompoundAlternate=""></Term>
         </Compound>
         <DiscreteExceptions>
            <Term></Term>
         </DiscreteExceptions>
      </Words>
      <Acronyms>
         <CasingExceptions>
            <Acronym></Acronym>
         </CasingExceptions>
      </Acronyms>
   </Dictionary>
```

## <a name="custom-dictionary-elements"></a>Özel sözlük öğeleri
 Özel sözlük aşağıdaki öğeleri iç metin olarak koşulları ekleyerek Kod Analizi sözlüğü davranışını değiştirebilirsiniz:

-   [/ Sözcükler/tanınan/sözcüğü](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsRecognizedWord)

-   [/ Sözcükler/tanınmayan/sözcüğü](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsUnrecognizedWord)

-   [Sözlük/sözcükler/kullanım dışı/terim [@PreferredAlternate]](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsDeprecatedTermPreferredAlternate)

-   [Sözlük/sözcükler/bileşik/terim [@CompoundAlternate]](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsCompoundTermCompoundAlternate)

-   [Sözlük/sözcükler/DiscreteExceptions/terimi](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryWordsDiscreteExceptionsTerm)

-   [Sözlük/kısaltmalar/CasingExceptions/kısaltması](../code-quality/how-to-customize-the-code-analysis-dictionary.md#BKMK_DictionaryAcronymsCasingExceptionsAcronym)

###  <a name="BKMK_DictionaryWordsRecognizedWord"></a> / Sözcükler/tanınan/sözcüğü
 Bir terim olarak doğru yazıldığından Kod Analizi tanımlayan koşulları listesinde dahil etmek için bir sözlük/sözcükler/Recognized/Word öğesinin iç metni terimi ekleyin. Terimleri sözlüğü/sözcükler/Recognized/Word öğelerinde büyük küçük harfe duyarlı değildir.

 **Örnek**

```
<Dictionary>
      <Words>
         <Recognized>
            <Word>knokker</Word>
            ...
         </Recognized>
         ...
      </Words>
      ...
</Dictionary>

```

 Aşağıdaki kod çözümleme kurallarını için sözcükler/sözlük/Recognized düğümleri bağlamında uygulanır:

-   [CA1701: Kaynak dize bileşik sözcüklerinin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)

-   [CA1702: Bileşik sözcüklerin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)

-   [CA1703: Kaynak dizeler doğru yazılmalıdır](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)

-   [CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)

-   [CA1709: Tanımlayıcıların büyük/küçük harfleri doğru yazılmalıdır](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

-   [CA1726: Tercih edilen terimleri kullanın](../code-quality/ca1726-use-preferred-terms.md)

-   [CA2204: Değişmez değerler doğru yazılmalıdır](../code-quality/ca2204-literals-should-be-spelled-correctly.md)

###  <a name="BKMK_DictionaryWordsUnrecognizedWord"></a> / Sözcükler/tanınmayan/sözcüğü
 Bir terim olarak doğru yazıldığından Kod Analizi tanımlayan koşulları listeden dışlamak için bir sözlük/sözcükler/tanınmayan/Word öğesinin iç metni dışlanacak terimi ekleyin. Terimleri sözlüğü/sözcükler/tanınmayan/Word öğelerinde büyük küçük harfe duyarlı değildir.

 **Örnek**

```
<Dictionary>
      <Words>
         <Unrecognized>
            <Word>meth</Word>
            ...
         </Unrecognized>
         ...
      </Words>
      ...
</Dictionary>

```

 Aşağıdaki kod çözümleme kurallarını için koşulları sözcükler/sözlük/tanınmayan düğümünde uygulanır:

-   [CA1701: Kaynak dize bileşik sözcüklerinin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)

-   [CA1702: Bileşik sözcüklerin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)

-   [CA1703: Kaynak dizeler doğru yazılmalıdır](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)

-   [CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)

-   [CA1709: Tanımlayıcıların büyük/küçük harfleri doğru yazılmalıdır](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

-   [CA1726: Tercih edilen terimleri kullanın](../code-quality/ca1726-use-preferred-terms.md)

-   [CA2204: Değişmez değerler doğru yazılmalıdır](../code-quality/ca2204-literals-should-be-spelled-correctly.md)

###  <a name="BKMK_DictionaryWordsDeprecatedTermPreferredAlternate"></a> Sözlük/sözcükler/kullanım dışı/terim [@PreferredAlternate]
 Kod Analizi kullanım dışı tanımlayan koşulları listedeki bir terim içermek üzere bir sözlük/sözcükler/kullanım dışı/terim öğesinin iç metni terimi ekleyin. Doğru yazıldığından, ancak kullanılmaması gereken bir sözcük buna kullanım dışı bir terimdir.

 Uyarıda önerilen bir alternatif terim eklemek için diğer terim öğesinin PreferredAlternate özniteliği belirtin. Alternatif önermek üzere istemiyorsanız, öznitelik değeri boş bırakabilirsiniz.

-   Sözlük/sözcükler kullanım dışı vadede/kullanım dışı/Terim öğesi büyük küçük harfe duyarlı değildir.

-   PreferredAlternate öznitelik değeri büyük/küçük harf duyarlıdır. Pascal çalışması için bileşik alternatifleri kullanın.

 **Örnek**

```
<Dictionary>
      <Words>
         <Deprecated>
            <Term PreferredAlternate="LogOn">login</Term>
            ...
         </Deprecated>
         ...
      </Words>
      ...
</Dictionary>

```

 Aşağıdaki kod çözümleme kurallarını için terimler sözlüğü/sözcükler/kullanım dışı düğümünde uygulanır:

-   [CA1701: Kaynak dize bileşik sözcüklerinin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)

-   [CA1702: Bileşik sözcüklerin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)

-   [CA1703: Kaynak dizeler doğru yazılmalıdır](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)

-   [CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)

-   [CA1726: Tercih edilen terimleri kullanın](../code-quality/ca1726-use-preferred-terms.md)

###  <a name="BKMK_DictionaryWordsCompoundTermCompoundAlternate"></a> Sözlük/sözcükler/bileşik/terim [@CompoundAlternate]
 Yerleşik sözlük bileşik bir terim yerine tek, ayrık koşulları olarak bazı koşulları tanımlar. Kod çözümleme bileşik word olarak tanımlayan koşulları listesi bir terim dahil ve koşulunun doğru büyük/küçük harf belirtmek için terimi sözlük/sözcükler/bileşik/terim öğesinin iç metni ekleyin. Terim öğesinin CompoundAlternate özniteliği bileşik terim (Pascal büyük) ayrı sözcükleri ilk harfini büyük harf yaparak olun ayrı sözcükleri belirtin. İç metni belirtilen terim sözcükler/sözlük/DiscreteExceptions listesine otomatik olarak eklendiğine dikkat edin.

-   Sözlük/sözcükler kullanım dışı vadede/kullanım dışı/Terim öğesi büyük küçük harfe duyarlı değildir.

-   PreferredAlternate öznitelik değeri büyük/küçük harf duyarlıdır. Pascal çalışması için bileşik alternatifleri kullanın.

 **Örnek**

```
<Dictionary>
      <Words>
         <Compound>
            <Term CompoundAlternate="CheckBox">checkbox</Term>
            ...
         </Compound>
         ...
      </Words>
      ...
</Dictionary>

```

 Terimleri sözlüğü/sözcükler/bileşik düğümünde, aşağıdaki kod çözümleme kurallarını için uygulanır:

-   [CA1701: Kaynak dize bileşik sözcüklerinin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)

-   [CA1702: Bileşik sözcüklerin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)

-   [CA1703: Kaynak dizeler doğru yazılmalıdır](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)

-   [CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)

###  <a name="BKMK_DictionaryWordsDiscreteExceptionsTerm"></a> Sözlük/sözcükler/DiscreteExceptions/terimi
 Bileşik sözcüklerin için büyük/küçük harf kurallar tarafından terimi işaretlendiğinde ayrık word bir terim tek bir kod analizi tanımlayan koşulları listesinde dışlamak için bir sözlük/sözcükler/DiscreteExceptions/terim öğesinin iç metni terimi ekleyin. Sözlük/sözcükler/DiscreteExceptions/Terim öğesi vadede büyük küçük harfe duyarlı değildir.

 **Örnek**

```
<Dictionary>
      <Words>
         <DiscreteExceptions>
            <Term>checkbox</Term>
            ...
         </DiscreteExceptions>
         ...
      </Words>
      ...
</Dictionary>

```

 Terimleri sözlüğü/sözcükler/DiscreteExceptions düğümünde, aşağıdaki kod çözümleme kurallarını için uygulanır:

-   [CA1701: Kaynak dize bileşik sözcüklerinin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)

-   [CA1702: Bileşik sözcüklerin küçük/büyük harfleri doğru yazılmalıdır](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)

###  <a name="BKMK_DictionaryAcronymsCasingExceptionsAcronym"></a> Sözlük/kısaltmalar/CasingExceptions/kısaltması
 Kod Analizi doğru yazılmış olarak tanımlayan koşulları listesi bir kısaltma dahil ve terimi büyük/küçük harf olarak işaretlendiğinde kısaltması için bileşik sözcüklerin nasıl kurallar belirtmek için bir sözlük/kısaltmalar/CasingExceptions iç metin olarak terimi ekleyin / Acronym Element öğesi. Sözlük/kısaltmalar/CasingExceptions/acronym Element öğesi kısaltması büyük/küçük harf duyarlıdır.

 **Örnek**

```
<Dictionary>
      <Acronyms>
         <CasingExceptions>
            <Acronym>NESW</Acronym>   <!-- North East South West -->
            ...
         </CasingExceptions>
         ...
      </Acronyms>
      ...
</Dictionary>

```

 Aşağıdaki kod çözümleme kurallarını için terimler sözlüğü/kısaltmalar/CasingExceptions düğümünde uygulanır:

-   [CA1709: Tanımlayıcıların büyük/küçük harfleri doğru yazılmalıdır](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

##  <a name="BKMK_ToApplyACustomDictionaryToAProject"></a> Bir projeye özel sözlük uygulamak için

1.  İçinde **Çözüm Gezgini**, aşağıdaki yordamlardan birini kullanın:

2.  Tek bir projeye bir sözlük eklemek için proje adına sağ tıklayın ve ardından **varolan öğeyi Ekle**. Dosyada belirtin **varolan öğeyi Ekle** iletişim kutusu.

3.  İki veya daha fazla projeler arasında paylaşılan bir sözlük eklemek için de paylaşmak için dosyayı bulun **varolan öğeyi Ekle** iletişim kutusunda, aşağı oka tıklayın **Ekle** düğmesine tıklayın ve ardından **bağlantı olarak Ekle** .

4.  İçinde **Çözüm Gezgini**, sağ **CustomDictionary.xml** dosya adı ve tıklatın **özellikleri**.

5.  Gelen **yapı eylemi** listesinde **CodeAnalysisDictionary**.

6.  Gelen **çıktı dizinine Kopyala** listesinde **kopyalamayın**.