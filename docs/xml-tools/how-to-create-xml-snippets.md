---
title: "Nasıl yapılır: XML parçacıkları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8556dd7-1382-4af7-ba80-3e873c9416be
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 05962d6806631bdfa9b873038ec85cdf9969d55c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-xml-snippets"></a>Nasıl yapılır: XML parçacıkları oluşturma
XML Düzenleyicisi'ni yeni XML parçacıkları oluşturmak için kullanılabilir. Düzenleyici "Parçacığı" adlı bir XML parçacığını içerir yeni XML parçacıkları oluşturmak için diğer bir deyişle bir Demirbaş kod parçacığında.  
  
## <a name="to-create-a-new-xml-snippet"></a>Yeni bir XML parçacığını oluşturmak için  
 Yeni bir XML kodu oluşturmak için kod parçacığında yeni bir XML dosyası oluşturun ve kullanın **Ekle parçacığı** özelliği.  
  
1.  Üzerinde **dosya** menüsünde tıklatın **yeni** ve ardından **dosya**.  
  
2.  Tıklatın **XML dosyası** ve ardından **açık**.  
  
3.  Düzenleyici Bölmesi'nde sağ tıklatıp **Ekle parçacığı**.  
  
4.  Seçin **parçacığı** listesi ve ENTER tuşuna basın.  
  
5.  Yeni kod parçacığını tüm değişiklikleri yapın.  
  
6.  Gelen **dosya** menüsünü seçin **kaydetmek XMLFile.xml**.  
  
     **Dosyasını Farklı Kaydet** iletişim kutusu görüntülenir.  
  
7.  Yeni kod parçacığını için ad girin ve **parçacık dosyaları** gelen **farklı türde Kaydet** açılır penceresi.  
  
8.  Kullanım **kaydetmek** My Documents\Visual Studio 2005\Code Snippets\XML\My XML parçacıkları klasörüne dosyasının konumunu değiştirmek ve ENTER tuşuna basın, aşağı açılan liste **kaydetmek**.  
  
## <a name="snippet-description"></a>Kod parçacığında açıklaması  
 Bu bölümde bazı Demirbaş kod parçacığını anahtar öğeleri açıklanmaktadır. XML parçacıkları tarafından kullanılan şema öğeleri hakkında daha fazla bilgi için bkz: [kod parçacıkları şema başvurusu](../ide/code-snippets-schema-reference.md).  
  
### <a name="snippettype-element"></a>SnippetType Öğesi  
 Düzenleyici iki parçacığı türlerini destekler:  
  
```xml
<SnippetTypes>  
  <SnippetType>SurroundsWith</SnippetType>  
  <SnippetType>Expansion</SnippetType>  
</SnippetTypes>  
```  
  
 `Expansion` Türü belirler çağırdığınızda, kod parçacığında görünüp görünmeyeceğini **Ekle parçacığı** komutu. `SurroundsWith` Türü belirler çağırdığınızda, kod parçacığında görünüp görünmeyeceğini **Surrounds ile** komutu.  
  
### <a name="code-element"></a>Code Öğesi  
 `Code` Öğesi kod parçacığını çağrıldığında eklenir XML metni tanımlar.  
  
> [!NOTE]
>  XML parçacığını metni içinde alınmalıdır bir `<![CDATA[...]]>` bölümü.  
  
 Aşağıdaki `Code` Demirbaş kod parçacığını tarafından oluşturulan öğesi.  
  
```xml
<Code Language="XML">  
  <![CDATA[<test>  
  <name>$name$</name>  
  $selected$ $end$</test>]]>  
</Code>  
```  
  
 `Code` Öğesi üç değişkenleri içerir.  
  
-   Kullanıcı tanımlı değişken $name$ değildir. Oluşturduğu bir `name` "name" varsayılan olarak düzenlenebilir bir değere sahip öğe. Kullanıcı tanımlı değişkenleri kullanılarak tanımlanır `Literal` öğesi.  
  
-   Seçili $$ önceden tanımlanmış bir değişkendir. XML Düzenleyicisi'nde kod parçacığını çağırmadan önce seçilmedi metni temsil eder. Seçili metni, seçimi çevreleyen kod parçacığında göründüğü Bu değişken yerleşimini belirler.  
  
-   $end$ önceden tanımlanmış bir değişkendir. Kullanıcı kod parçacığını alanları düzenleme bitirmek için ENTER tuşuna bastığında, bu değişken şapka (^) burada taşınır belirler.  
  
 Yukarıdaki `Code` öğesi aşağıdaki XML metni ekler:  
  
```xml
<test>  
  <name>name</name>  
</test>  
```  
  
 Name öğesi değerini düzenlenebilir bölgeyi işaretlenir.  
  
### <a name="literal-element"></a>Literal Öğesi  
 `Literal` Öğe dosyasına eklendikten sonra özelleştirilebilir değiştirme metnini tanımlamak için kullanılır. Örneğin, değişmez değer dizeleri, sayısal değerler ve bazı değişken adları değişmez değerler bildirilebilir. Kod parçacığını içinde birden çok kez den başvurabilir ve XML parçacığında herhangi bir sayıda değişmez değerleri tanımlayabilirsiniz. Aşağıdaki örneğidir bir `Literal` varsayılan değeri olan "ad" $name$ değişkeni öğesi  
  
```xml
<Literal>  
  <ID>name</ID>  
  <Default>name</Default>  
</Literal  
```  
  
 Değişmez değerler işlevler de başvurabilir. XML Düzenleyicisi adlı bir işlev içerir **LookupPrefix**. **LookupPrefix** işlevi bu parçacığı öğesinden çağrılır ve varsa bu ad alanı için tanımlanan ad alanı öneki döndürür ve iki nokta (:) içerir XML belgesindeki bir konumdan verilen ad alanı URI arar Bu adı. Aşağıdaki örneğidir bir `Literal` kullanan öğesi **LookupPrefix** işlevi.  
  
```xml
<Literal Editable="false">  
   <ID>prefix</ID>  
   <Function>LookupPrefix("namespaceURI")</Function>  
</Literal>  
```  
  
 $Prefix$ değişkeni XML parçacığında sonra bir başka bir yerde kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML parçacıkları](../xml-tools/xml-snippets.md)   
 [Nasıl yapılır: XML parçacıklarını kullanma](../xml-tools/how-to-use-xml-snippets.md)   
 [Nasıl Yapılır: XML Şemasından XML Kod Parçacığı Oluşturma](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)