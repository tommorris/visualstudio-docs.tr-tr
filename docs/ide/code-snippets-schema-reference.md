---
title: "Kod parçacıkları şema başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema reference [Visual Studio]
- snippets [Visual Studio], schema reference
- code snippets [Visual Studio], schema reference
- IntelliSense Code Snippets, XML Schema
ms.assetid: 58a60621-725f-4763-93b7-62ea5424ef88
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b3fdf8728e5afd839718e31e4eb6b113b8f9cde2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="code-snippets-schema-reference"></a>Kod Parçacıkları Şema Başvurusu
IntelliSense kod parçacıkları ile uygulamanıza eklenmeye hazır önceden yazılmış kod parçalarını olan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Yinelenen kodları yazmak veya örnekleri aramak için harcanan süreyi kısaltan kod parçacıkları sağlayarak üretkenliği artırabilirsiniz. IntelliSense kod parçacığı XML Şeması kendi kod parçacıkları oluşturmak ve bunları kod parçacıkları eklemek için kullanabileceğiniz, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zaten içerir.  
  
## <a name="intellisense-code-snippets-schema-elements"></a>IntelliSense Kod Parçacıkları Şeması Öğeleri  
  
||||  
|-|-|-|  
|[Assembly öğesi](../ide/code-snippets-schema-reference.md#assembly)|[HelpUrl öğesi](../ide/code-snippets-schema-reference.md#helpurl)|[References öğesi](../ide/code-snippets-schema-reference.md#references)|  
|[Yazar öğesi](../ide/code-snippets-schema-reference.md#author)|[ID öğesi](../ide/code-snippets-schema-reference.md#id)|[Kısayol öğesi](../ide/code-snippets-schema-reference.md#shortcut)|  
|[Kod öğesi](../ide/code-snippets-schema-reference.md#code)|[İçeri aktarma öğesi](../ide/code-snippets-schema-reference.md#import)|[Kod parçacığında öğesi](../ide/code-snippets-schema-reference.md#snippet)|  
|[CodeSnippet öğesi](../ide/code-snippets-schema-reference.md#codesnippet)|[İçeri aktarmalar öğesi](../ide/code-snippets-schema-reference.md#imports)|[SnippetType öğesi](../ide/code-snippets-schema-reference.md#snippettype)|  
|[CodeSnippets öğesi](../ide/code-snippets-schema-reference.md#codesnippets)|[Keyword öğesinde](../ide/code-snippets-schema-reference.md#keyword)|[SnippetTypes öğesi](../ide/code-snippets-schema-reference.md#snippettypes)|  
|[Bildirimleri öğesi](../ide/code-snippets-schema-reference.md#declarations)|[Anahtar sözcükler öğesi](../ide/code-snippets-schema-reference.md#keywords)|[Title öğesi](../ide/code-snippets-schema-reference.md#title)|  
|[Varsayılan öğesi](../ide/code-snippets-schema-reference.md#default)|[Değişmez değer öğesi](../ide/code-snippets-schema-reference.md#literal)|[Araç İpucu öğesi](../ide/code-snippets-schema-reference.md#tooltip)|  
|[Description öğesi](../ide/code-snippets-schema-reference.md#description)|[Namespace öğesi](../ide/code-snippets-schema-reference.md#namespace)|[Type öğesi](../ide/code-snippets-schema-reference.md#type)|  
|[İşlev öğesi](../ide/code-snippets-schema-reference.md#function)|[Object öğesi](../ide/code-snippets-schema-reference.md#object)|[URL öğesi](../ide/code-snippets-schema-reference.md#url)|  
|[Üstbilgi öğesi](../ide/code-snippets-schema-reference.md#header)|[Reference öğesi](../ide/code-snippets-schema-reference.md#reference)||  
  
##  <a name="assembly"></a>Assembly öğesi  
 Kod parçacığının başvurduğu derlemenin adını belirtir.
  
 Metin değerini **derleme** öğesidir derleme kolay metin adı gibi `System.dll`, ya da kendi güçlü ad gibi `System,Version=1.0.0.1,Culture=neutral,PublicKeyToken=9b35aa323c18d4fb1`.  
  
```xml  
<Assembly>  
    AssemblyName  
</Assembly>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Reference öğesi](../ide/code-snippets-schema-reference.md#reference)|Kod parçacığının gerek duyduğu derleme başvuruları hakkındaki bilgileri içerir.|  
  
 Bir metin değeri gereklidir. Bu metin, kod parçacığının başvurduğu derlemeyi belirtir.  
  
##  <a name="author"></a>Yazar öğesi  
 Kod parçacığı yazarının adını belirtir. **Kod parçacıkları Yöneticisi** depolanan adını görüntüler `Author` kod parçacığında öğesidir.  
  
```xml  
<Author>  
   Code Snippet Author  
</Author>    
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Üstbilgi öğesi](../ide/code-snippets-schema-reference.md#header)|Kod parçacığı hakkında genel bilgiler içerir.|  
  
 Bir metin değeri gereklidir. Bu metin kod parçacığının yazarını belirtir.  
  
## <a name="a-namecode--code-element"></a><a name="code" />Kod öğesi  
Kısa kod blokları için bir kapsayıcı sağlar.  
  
### <a name="keywords"></a>Anahtar Sözcükler
İki ayrılmış sözcükler metninde kullanıma `Code` öğesi: `$end$` ve `$selected$`. `$end$`kod parçacığı eklendikten sonra imleci yerleştirmek için konumun işaretler. `$selected$`metin çalıştırıldığında kod parçacığını eklenecek belgede seçili temsil eder. Örneğin, içeren parçacık verilen:  
  
```  
$selected$ is a great color.  
```  
  
Kullanıcı şablonu çalıştırdığında "Mavi" word seçtiyseniz oluşur:  
  
```  
Blue is a great color.  
```  
  
Ya da kullanamazsınız `$end$` veya `$selected$` kod parçacığında bulunan bir kereden fazla. Bunu yaparsanız, yalnızca ikinci örneği tanınır. İçeren parçacık verilen:  
  
```  
$selected$ is a great color. I love $selected$.  
```  
  
"Mavi" word seçtiyseniz oluşur:  
  
```  
 is a great color. I love Blue.  
```  
  
İlk alanı arasında bir boşluk olduğundan görünür `$selected$` ve `is`.  
  
Diğer tüm `$` anahtar sözcükleri tanımlanmış dinamik olarak `<Literal>` ve `<Object>` etiketler.  

Kod öğesi yapısını aşağıdadır:
  
```xml  
<Code Language="Language"  
    Kind="method body/method decl/type decl/page/file/any"  
    Delimiter="Delimiter">  
    Code to insert  
</Code>  
```

Bir metin değeri gereklidir. Bu metin değişmez değerleri ve bu kod parçacığını bir kod dosyaya eklendiğinde, kullanabileceğiniz nesneleri ile birlikte kod belirtir.  

### <a name="attributes"></a>Öznitelikler
Kod öğesi için kullanılabilen üç özniteliği vardır:

- **Dil** - _gerekli_ kod parçacığında dil belirten özniteliği. Değerin aşağıdakilerden biri olabilir:

   |Değer|Açıklama|  
   |-----|-----------|  
   |`VB`|Bir Visual Basic kod parçacığını tanımlar.|  
   |`CSharp`|Bir C# kod parçacığını tanımlar.|  
   |`CPP`|Bir C++ kod parçacığını tanımlar.|  
   |`XML`|Bir XML kod parçacığını tanımlar.|  
   |`JavaScript`|Bir JavaScript kod parçacığını tanımlar.|  
   |`SQL`|Bir SQL kod parçacığını tanımlar.|  
   |`HTML`|Bir HTML kod parçacığını tanımlar.|
 
- **Tür** - _isteğe bağlı_ parçacığı içeren kodu ve hangi kod parçacığı girilmelidir kod parçacığını derlemek konum türünü belirten özniteliği. Değerin aşağıdakilerden biri olabilir:

   |Değer|Açıklama|  
   |-----|-----------|  
   |`method body`|Kod parçacığının bir yöntem gövdesi olduğunu ve bu nedenle, bir yöntem bildiriminin içine eklenmesi gerektiğini belirtir.|  
   |`method decl`|Kod parçacığının bir yöntem olduğunu ve bu nedenle, bir sınıf veya modül içine eklenmesi gerektiğini belirtir.|  
   |`type decl`|Kod parçacığının bir tür olduğunu ve bu nedenle, bir sınıf, modül veya ad alanı içine eklenmesi gerektiğini belirtir.|  
   |`file`|Kod parçacığının eksiksiz bir kod dosyası olduğunu belirtir. Bu kod parçacıkları tek başına bir kod dosyasının içine veya bir ad alanının içine eklenebilir.|  
   |`any`|Kod parçacığının istenen yere eklenebileceğini belirtir. Bu etiket, açıklamalar gibi içeriğe bağımlı kod parçacıkları için kullanılır.|

- **Sınırlayıcı** - _isteğe bağlı_ değişmez değerleri ve kod nesneleri tanımlamak için kullanılan sınırlayıcıyı belirten özniteliği. Varsayılan olarak sınırlayıcı olan `$`.

### <a name="parent-element"></a>Üst öğesi
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Kod parçacığında öğesi](../ide/code-snippets-schema-reference.md#snippet)|Kod parçacığı için başvuruları, içeri aktarımları, bildirimleri ve kodu içerir.|
  
##  <a name="codesnippet"></a>CodeSnippet öğesi  
 Visual Studio kod dosyalarına ekleyebileceğiniz bir başlık ve birden fazla IntelliSense Kod Parçacığı belirtmenizi sağlar.  
  
```xml  
<CodeSnippet Format="x.x.x">  
    <Header>... </Header>  
    <Snippet>... </Snippet>  
</CodeSnippet>  
```  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Format`|Gerekli öznitelik. Kod parçacığının şema sürümünü belirtir. Format özniteliği, her "x"in sürüm numarasına ait sayısal bir değeri temsil ettiği x.x.x sözdiziminde bir dize olmalıdır. Visual Studio ile kod parçacıkları yoksayar `Format` anlamadığı öznitelikleri.|  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Üstbilgi öğesi](../ide/code-snippets-schema-reference.md#header)|Gerekli öğe. Kod parçacığı hakkında genel bilgiler içerir. Koyulmalıdır tam olarak bir `Header` bir kod parçacığı öğesinde.|  
|[Kod parçacığında öğesi](../ide/code-snippets-schema-reference.md#snippet)|Gerekli öğe. Visual Studio tarafından eklenecek kodu içerir. Koyulmalıdır tam olarak bir `Snippet` bir kod parçacığı öğesinde.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[CodeSnippets öğesi](../ide/code-snippets-schema-reference.md#codesnippets)|Kod parçacığı XML şemasının kök öğesi.|  
  
##  <a name="codesnippets"></a>CodeSnippets öğesi  
 Grupları [CodeSnippet öğesi](../ide/code-snippets-schema-reference.md#codesnippet)öğeleri. `CodeSnippets` Kod parçacığını XML şeması kök öğesinin bir öğedir.  
  
```xml  
<CodeSnippets>  
    <CodeSnippet>... </CodeSnippet>  
</CodeSnippets>  
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[CodeSnippet öğesi](../ide/code-snippets-schema-reference.md#codesnippet)|İsteğe bağlı öğe. Tüm kod parçacığı verisi için üst öğe. Sıfır veya daha fazla olabilir `CodeSnippet` öğelerinde bir `CodeSnippets` öğesi.|  
  
##  <a name="declarations"></a>Bildirimleri öğesi  
 Bir kod parçacığının düzenleyebileceğiniz bölümlerini oluşturan değişmez değerleri ve nesneleri belirtir.  
  
```xml  
<Declarations>  
    <Literal>... </Literal>  
    <Object>... </Object>  
</Declarations>  
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Değişmez değer öğesi](../ide/code-snippets-schema-reference.md#literal)|İsteğe bağlı öğe. Kod parçacığının düzenleme yapabileceğiniz değişmez değerlerini tanımlar. Sıfır veya daha fazla olabilir `Literal` öğelerinde bir `Declarations` öğesi.|  
|[Object öğesi](../ide/code-snippets-schema-reference.md#object)|İsteğe bağlı öğe. Kod parçacığının düzenleme yapabileceğiniz nesnelerini tanımlar. Sıfır veya daha fazla olabilir `Object` öğelerinde bir `Declarations` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Kod parçacığında öğesi](../ide/code-snippets-schema-reference.md#snippet)|Kod parçacığı için başvuruları, içeri aktarımları, bildirimleri ve kodu içerir.|  
  
##  <a name="default"></a>Varsayılan öğesi  
 Bir IntelliSense Kod Parçacığı için değişmez değerin veya nesnenin varsayılan değerini belirtir.  
  
```xml  
<Default>  
    Default value  
</Default>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Değişmez değer öğesi](../ide/code-snippets-schema-reference.md#literal)|Kod parçacığının düzenleme yapabileceğiniz değişmez değer alanlarını tanımlar.|  
|[Object öğesi](../ide/code-snippets-schema-reference.md#object)|Kod parçacığının düzenleme yapabileceğiniz nesne alanlarını tanımlar.|  
  
 Bir metin değeri gereklidir. Bu metin, düzenleyebileceğiniz kod parçacığı alanlarını dolduran değişmez değerin veya nesnenin varsayılan değerini belirtir.  
  
##  <a name="description"></a>Description öğesi  
 Bir IntelliSense Kod Parçacığı'nın içeriği hakkında açıklayıcı bilgileri belirtir.  
  
```xml  
<Description>  
    Code Snippet Description  
</Description>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Üstbilgi öğesi](../ide/code-snippets-schema-reference.md#header)|Kod parçacığı hakkında genel bilgiler içerir.|  
  
 Bir metin değeri gereklidir. Bu metin kod parçacığını tanımlar.  
  
##  <a name="function"></a>İşlev öğesi  
 Değişmez değer veya nesne Visual Studio'da odağa geldiğinde yürütülecek bir işlevi belirtir.  
  
> [!NOTE]
>  `Function` Öğesi yalnızca Visual C# kod parçacıkları içinde desteklenir.  
  
```xml  
<Function>  
    FunctionName  
</Function>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Değişmez değer öğesi](../ide/code-snippets-schema-reference.md#literal)|Kod parçacığının düzenleme yapabileceğiniz değişmez değer alanlarını tanımlar.|  
|[Object öğesi](../ide/code-snippets-schema-reference.md#object)|Kod parçacığının düzenleme yapabileceğiniz nesne alanlarını tanımlar.|  
  
 Bir metin değeri gereklidir. Bu metin, değişmez değer veya nesne alanı Visual Studio'da odağa geldiğinde yürütülecek bir işlevi belirtir.  
  
##  <a name="header"></a>Üstbilgi öğesi  
 IntelliSense Kod Parçacığı hakkında genel bilgileri belirtir.  
  
```xml  
<Header>  
    <Title>... </Title>  
    <Author>... </Author>  
    <Description>... </Description>  
    <HelpUrl>... </HelpUrl>  
    <SnippetTypes>... </SnippetTypes>  
    <Keywords>... </Keywords>  
    <Shortcut>... </Shortcut>  
</Header>  
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Yazar öğesi](../ide/code-snippets-schema-reference.md#author)|İsteğe bağlı öğe. Kod parçacığını yazan kişinin veya şirketin adı. Sıfır veya bir olabilir `Author` öğelerinde bir `Header` öğesi.|  
|[Description öğesi](../ide/code-snippets-schema-reference.md#description)|İsteğe bağlı öğe. Kod parçacığının açıklaması. Sıfır veya bir olabilir `Description` öğelerinde bir `Header` öğesi.|  
|[HelpUrl öğesi](../ide/code-snippets-schema-reference.md#helpurl)|İsteğe bağlı öğe. Kod parçacığı hakkında daha fazla bilgi içeren URL. Sıfır veya bir olabilir `HelpURL` üstbilgi öğesi öğeler. **Not:** Visual Studio kullanmaz `HelpUrl` öğesi. Öğe, IntelliSense Kod Parçacığı XML şemasının bir parçasıdır ve öğeyi içeren her kod parçacığı doğrulanacaktır, ancak öğenin değeri hiçbir zaman kullanılmaz.|  
|[Anahtar sözcükler öğesi](../ide/code-snippets-schema-reference.md#keywords)|İsteğe bağlı öğe. Grupları `Keyword` öğeleri. Sıfır veya bir olabilir `Keywords` öğelerinde bir `Header` öğesi.|  
|[Kısayol öğesi](../ide/code-snippets-schema-reference.md#shortcut)|İsteğe bağlı öğe. Kod parçacığını eklemek için kullanılabilecek kısayol metnini belirtir. Sıfır veya bir olabilir `Shortcut` öğelerinde bir `Header` öğesi.|  
|[SnippetTypes öğesi](../ide/code-snippets-schema-reference.md#snippettypes)|İsteğe bağlı öğe. Grupları `SnippetType` öğeleri. Sıfır veya bir olabilir `SnippetTypes` öğelerinde bir `Header` öğesi. Varsa hiçbir `SnippetTypes` öğeleri, kod parçacığında her zaman geçerli.|  
|[Title öğesi](../ide/code-snippets-schema-reference.md#title)|Gerekli öğe. Kod parçacığının kolay adı. Koyulmalıdır tam olarak bir `Title` öğesinde bir `Header` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[CodeSnippet öğesi](../ide/code-snippets-schema-reference.md#codesnippet)|Tüm kod parçacığı verisi için üst öğe.|  
  
##  <a name="helpurl"></a>HelpUrl öğesi  
 Bir kod parçacığı hakkında daha fazla bilgi sağlayan URL'yi belirtir.  
  
> [!NOTE]
>  Visual Studio kullanmaz `HelpUrl` öğesi. Öğe, IntelliSense Kod Parçacığı XML şemasının bir parçasıdır ve öğeyi içeren her kod parçacığı doğrulanacaktır, ancak öğenin değeri hiçbir zaman kullanılmaz.  
  
```xml  
<HelpUrl>  
    www.microsoft.com  
</HelpUrl>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Üstbilgi öğesi](../ide/code-snippets-schema-reference.md#header)|Kod parçacığı hakkında genel bilgiler içerir.|  
  
 Metin değeri isteğe bağlıdır. Bu metin, kod parçacığı hakkında daha fazla bilgi için ziyaret edilmesi gereken URL'yi belirtir.  
  
##  <a name="id"></a>ID öğesi  
 İçin benzersiz bir tanımlayıcı belirtir bir `Literal` veya `Object` öğesi. Aynı metin değerine sahip iki değişmez değerleri ya da aynı kod parçacığında bulunan nesneleri kendi `ID` öğeleri. Değişmez değerler ve nesneleri içeremez bir `ID` bitiş değerini öğesi. Değer `$end$` ayrılmıştır ve kod parçacığında eklendikten sonra imleci yerleştirmek için konumun işaretlemek için kullanılır.  
  
```xml  
<ID>  
    Unique Identifier  
</ID>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Değişmez değer öğesi](../ide/code-snippets-schema-reference.md#literal)|Kod parçacığının düzenleme yapabileceğiniz değişmez değer alanlarını tanımlar.|  
|[Object öğesi](../ide/code-snippets-schema-reference.md#object)|Kod parçacığının düzenleme yapabileceğiniz nesne alanlarını tanımlar.|  
  
 Bir metin değeri gereklidir. Bu metin, nesne veya değişmez değer için benzersiz tanımlayıcıyı belirtir.  
  
##  <a name="import"></a>İçeri aktarma öğesi  
 Bir IntelliSense Kod Parçacığı tarafından kullanılan içeri aktarılan ad alanlarını belirtir.  
  
> [!NOTE]
>  `Import` Öğesi yalnızca Visual Basic projeleri için desteklenir.  
  
```xml  
<Import>  
    <Namespace>... </Namespace>  
</Import>  
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Namespace öğesi](../ide/code-snippets-schema-reference.md#namespace)|Gerekli öğe. Kod parçacığı tarafından kullanılan ad alanını belirtir. Koyulmalıdır tam olarak bir `Namespace` öğesinde bir `Import` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[İçeri aktarmalar öğesi](../ide/code-snippets-schema-reference.md#imports)|Grouping öğesi için **alma** öğeleri.|  
  
##  <a name="imports"></a>İçeri aktarmalar öğesi  
 Gruplar tek tek `Import` öğeleri.  
  
> [!NOTE]
>  `Imports` Öğesi yalnızca Visual Basic projeleri için desteklenir.  
  
```xml  
<Imports>  
    <Import>... </Import>  
<Imports>  
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[İçeri aktarma öğesi](../ide/code-snippets-schema-reference.md#import)|İsteğe bağlı öğe. Kod parçacığı için içeri aktarılan ad alanlarını içerir. Sıfır veya daha fazla olabilir **alma** öğelerinde bir `Imports` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Kod parçacığında öğesi](../ide/code-snippets-schema-reference.md#snippet)|Kod parçacığı için başvuruları, içeri aktarımları, bildirimleri ve kodu içerir.|  
  
##  <a name="keyword"></a>Keyword öğesinde  
 Kod parçacığı için özel bir anahtar sözcük belirtir. Kod parçacığı anahtar sözcükleri Visual Studio tarafından kullanılır ve çevrimiçi içerik sağlayıcılarının aramaya veya kategorilere ayırmaya yönelik özel anahtar sözcükler eklemek için kullandıkları standart bir yöntemi temsil eder.  
  
```xml  
<Keyword>  
    Code Snippet Keyword  
</Keyword>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Anahtar sözcükler öğesi](../ide/code-snippets-schema-reference.md#keywords)|Gruplar tek tek `Keyword` öğeleri.|  
  
 Bir metin değeri gereklidir. Kod parçacığı için anahtar sözcük.  
  
##  <a name="keywords"></a>Anahtar sözcükler öğesi  
 Gruplar tek tek `Keyword` öğeleri. Kod parçacığı anahtar sözcükleri Visual Studio tarafından kullanılır ve çevrimiçi içerik sağlayıcılarının aramaya veya kategorilere ayırmaya yönelik özel anahtar sözcükler eklemek için kullandıkları standart bir yöntemi temsil eder  
  
```xml  
<Keywords>  
    <Keyword>... </Keyword>  
    <Keyword>... </Keyword>  
<Keywords>  
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Keyword öğesinde](../ide/code-snippets-schema-reference.md#keyword)|İsteğe bağlı öğe. Kod parçacığı için tek tek anahtar sözcükleri içerir. Sıfır veya daha fazla olabilir `Keyword` öğelerinde bir `Keywords` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Üstbilgi öğesi](../ide/code-snippets-schema-reference.md#header)|Kod parçacığı hakkında genel bilgiler içerir.|  
  
##  <a name="literal"></a>Değişmez değer öğesi  
 Kod parçacığının düzenleme yapabileceğiniz değişmez değerlerini tanımlar. `Literal` Öğe koda eklendikten sonra paylaştırılabilen bir kod parçacığı ancak büyük olasılıkla içinde tamamen bulunan özelleştirilmesi için değiştirme tanımlamak için kullanılır. Örneğin, değişmez değer dizeleri, sayısal değerler ve bazı değişken adları değişmez değer olarak bildirilmelidir.  
  
 Değişmez değerler ve nesneleri içeremez bir **kimliği** değerini öğesi seçili veya bitemez. Değer `$selected$` çalıştırıldığında kod parçacığını eklenecek belgede seçili metin temsil eder. `$end$`kod parçacığı eklendikten sonra imleci yerleştirmek için konumun işaretler.  
  
```xml  
<Literal Editable="true/false">  
   <ID>... </ID>  
   <ToolTip>... </ToolTip>  
   <Default>... </Default>  
   <Function>... </Function>  
</Literal>  
```  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Editable`|İsteğe bağlı `Boolean` özniteliği. Kod parçacığı eklendikten sonra değişmez değerde düzenleme yapıp yapamayacağınızı belirtir. Bu özniteliğin varsayılan değer `true`.|  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Varsayılan öğesi](../ide/code-snippets-schema-reference.md#default)|Gerekli öğe. Kod parçacığını eklediğinizde değişmez değerin alacağı varsayılan değeri belirtir. Koyulmalıdır tam olarak bir `Default` öğesinde bir `Literal` öğesi.|  
|[İşlev öğesi](../ide/code-snippets-schema-reference.md#function)|İsteğe bağlı öğe. Değişmez değer Visual Studio'da odağa geldiğinde yürütülecek bir işlevi belirtir. Sıfır veya bir olabilir `Function` öğelerinde bir `Literal` öğesi.|  
|[ID öğesi](../ide/code-snippets-schema-reference.md#id)|Gerekli öğe. Değişmez değer için benzersiz bir tanımlayıcı belirtir. Koyulmalıdır tam olarak bir `ID` öğesinde bir `Literal` öğesi.|  
|[Araç İpucu öğesi](../ide/code-snippets-schema-reference.md#tooltip)|İsteğe bağlı öğe. Değişmez değerin beklenen değerini ve kullanımını açıklar. Sıfır veya bir olabilir **araç ipucu** öğelerinde bir `Literal` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Bildirimleri öğesi](../ide/code-snippets-schema-reference.md#declarations)|Kod parçacığının düzenleme yapabileceğiniz değişmez değerlerini ve nesnelerini içerir.|  
  
##  <a name="namespace"></a>Namespace öğesi  
 Kod parçacığının derlenip çalışması için içeri aktarılması gereken ad alanını belirtir. Belirtilen ad alanı `Namespace` öğesi otomatik olarak eklenir bir `Imports` zaten yoksa, kodunun başında deyimi.  
  
> [!NOTE]
>  `Namespace` Öğesi yalnızca Visual Basic projeleri için desteklenir.  
  
```xml  
<Namespace>  
    Namespace  
</Namespace>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[İçeri aktarma öğesi](../ide/code-snippets-schema-reference.md#import)|Belirtilen ad alanını içeri aktarır.|  
  
 Bir metin değeri gereklidir. Bu metin, kod parçacığının içeri aktarıldığını varsaydığı bir ad alanını belirtir.  
  
##  <a name="object"></a>Object öğesi  
 Kod parçacığının düzenleme yapabileceğiniz nesnelerini tanımlar. `Object` Öğesi tarafından kod parçacığını gereklidir ancak parçacığı dışında tanımlanmış olması olası bir öğeyi tanımlamak için kullanılır. Örneğin, Windows Forms denetimleri, ASP.NET denetimleri, nesne örnekleri ve tür örnekleri nesne olarak bildirilmelidir. Nesne bildirimleri gerektiren bir türü belirtilmesini ile yapılan `Type` öğesi.  
  
```xml  
<Object Editable="true/false">  
    <ID>... </ID>  
    <Type>... </Type>  
    <ToolTip>... </ToolTip>  
    <Default>... </Default>  
    <Function>... </Function>  
</Object>  
```  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Editable`|İsteğe bağlı `Boolean` özniteliği. Kod parçacığı eklendikten sonra değişmez değerde düzenleme yapıp yapamayacağınızı belirtir. Bu özniteliğin varsayılan değer `true`.|  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Varsayılan öğesi](../ide/code-snippets-schema-reference.md#default)|Gerekli öğe. Kod parçacığını eklediğinizde değişmez değerin alacağı varsayılan değeri belirtir. Koyulmalıdır tam olarak bir `Default` öğesinde bir `Literal` öğesi.|  
|[İşlev öğesi](../ide/code-snippets-schema-reference.md#function)|İsteğe bağlı öğe. Değişmez değer Visual Studio'da odağa geldiğinde yürütülecek bir işlevi belirtir. Sıfır veya bir olabilir `Function` öğelerinde bir `Literal` öğesi.|  
|[ID öğesi](../ide/code-snippets-schema-reference.md#id)|Gerekli öğe. Değişmez değer için benzersiz bir tanımlayıcı belirtir. Koyulmalıdır tam olarak bir `ID` öğesinde bir `Literal` öğesi.|  
|[Araç İpucu öğesi](../ide/code-snippets-schema-reference.md#tooltip)|İsteğe bağlı öğe. Değişmez değerin beklenen değerini ve kullanımını açıklar. Sıfır veya bir olabilir **araç ipucu** öğelerinde bir `Literal` öğesi.|  
|[Type öğesi](../ide/code-snippets-schema-reference.md#type)|Gerekli öğe. Nesnenin türünü belirtir. Koyulmalıdır tam olarak bir `Type` öğesinde bir `Object` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Bildirimleri öğesi](../ide/code-snippets-schema-reference.md#declarations)|Kod parçacığının düzenleme yapabileceğiniz değişmez değerlerini ve nesnelerini içerir.|  
  
##  <a name="reference"></a>Reference öğesi  
 Kod parçacığının gerek duyduğu derleme başvuruları hakkındaki bilgileri belirtir. 
  
```xml  
<Reference>  
    <Assembly>... </Assembly>  
    <Url>... </Url>  
</Reference>  
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Assembly öğesi](../ide/code-snippets-schema-reference.md#assembly)|Gerekli öğe. Kod parçacığının başvurduğu derlemenin adını içerir. Koyulmalıdır tam olarak bir `Assembly` öğesinde bir `Reference` öğesi.|  
|[URL öğesi](../ide/code-snippets-schema-reference.md#url)|İsteğe bağlı öğe. Başvurulan derleme hakkında daha fazla bilgi sağlayan bir URL içerir. Sıfır veya bir olabilir `Url` öğelerinde bir `Reference` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[References öğesi](../ide/code-snippets-schema-reference.md#references)|Grouping öğesi için `Reference` öğeleri.|  
  
##  <a name="references"></a>References öğesi  
 Gruplar tek tek `Reference` öğeleri.  
  
```xml  
<References>  
    <Reference>... </Reference>  
</References>  
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Reference öğesi](../ide/code-snippets-schema-reference.md#reference)|İsteğe bağlı öğe. Kod parçacığı için derleme başvuruları hakkındaki bilgileri içerir. Sıfır veya daha fazla olabilir `Reference` öğelerinde bir `References` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Kod parçacığında öğesi](../ide/code-snippets-schema-reference.md#snippet)|Kod parçacığı için başvuruları, içeri aktarımları, bildirimleri ve kodu içerir.|  
  
##  <a name="shortcut"></a>Kısayol öğesi  
 Kod parçacığını eklemek için kullanılan kısayol metnini belirtir. Metin değeri bir `Shortcut` öğesi yalnızca alfasayısal karakterler içeren tireler (-) ve alt çizgi (_).  
  
> [!CAUTION]
>  _ ve - C++ kod parçacığında kısayolları desteklenen karakter değildir.  
  
```xml  
<Shortcut>  
    Shortcut Text  
</Shortcut>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Üstbilgi öğesi](../ide/code-snippets-schema-reference.md#header)|Kod parçacığı hakkında genel bilgiler içerir.|  
  
 Metin değeri isteğe bağlıdır. Bu metin, kod parçacığını eklemek için bir kısayol olarak kullanılır.  
  
##  <a name="snippet"></a>Kod parçacığında öğesi  
 Kod parçacığı için başvuruları, içeri aktarımları, bildirimleri ve kodu belirtir.  
  
```xml  
<Snippet>  
    <References>... </References>  
    <Imports>... </Imports>  
    <Declarations>... </Declarations>  
    <Code>... </Code>  
</Snippet>    
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[Kod öğesi](../ide/code-snippets-schema-reference.md#code)|Gerekli öğe. Bir belge dosyasına eklemek istediğiniz kodu belirtir. Koyulmalıdır tam olarak bir `Code` öğesinde bir `Snippet` öğesi.|  
|[Bildirimleri öğesi](../ide/code-snippets-schema-reference.md#declarations)|İsteğe bağlı öğe. Bir kod parçacığının düzenleyebileceğiniz bölümlerini oluşturan değişmez değerleri ve nesneleri belirtir. Sıfır veya bir olabilir `Declarations` öğelerinde bir `Snippet` öğesi.|  
|[İçeri aktarmalar öğesi](../ide/code-snippets-schema-reference.md#imports)|İsteğe bağlı öğe. Gruplar tek tek `Import` öğeleri. Sıfır veya bir olabilir `Imports` öğelerinde bir `Snippet` öğesi.|  
||İsteğe bağlı öğe. Gruplar tek tek `Reference` öğeleri. Sıfır veya bir olabilir `References` öğelerinde bir `Snippet` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[CodeSnippet öğesi](../ide/code-snippets-schema-reference.md#codesnippet)|Visual Studio kod dosyalarına ekleyebileceğiniz bir başlık ve birden fazla IntelliSense Kod Parçacığı belirtmenizi sağlar.|  
  
##  <a name="snippettype"></a>SnippetType öğesi  
 Visual Studio'nun kod parçacığını nasıl eklediğini belirtir.  
  
```xml  
<SnippetType>  
    SurroundsWith/Expansion  
<SnippetType>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[SnippetTypes öğesi](../ide/code-snippets-schema-reference.md#snippettypes)|Grupları `SnippetType` öğeleri.|  
  
 Metin değeri şu değerlerden biri olmalıdır:  
  
-   `SurroundsWith`: seçilen paylaştırılabilen bir kod yerleştirilecek kod parçacığını sağlar.  
  
-   `Expansion`: kod parçacığı imlecin eklenmesini sağlar.  
  
-   `Refactoring`: kod parçacığı Visual C# yeniden düzenleme sırasında kullanıldığını belirtir. `Refactoring`özel kod parçacıkları kullanılamaz.  
  
##  <a name="snippettypes"></a>SnippetTypes öğesi  
 Gruplar tek tek `SnippetType` öğeleri. Varsa `SnippetTypes` öğesi mevcut değil, kod parçacığında kodda yere eklenebilir.  
  
```xml  
<SnippetTypes>  
    <SnippetType>... </SnippetType>  
    <SnippetType>... </SnippetType>  
<SnippetTypes>  
```  
  
|Alt Öğe|Açıklama|  
|-------------------|-----------------|  
|[SnippetType öğesi](../ide/code-snippets-schema-reference.md#snippettype)|İsteğe bağlı öğe. Visual Studio'nun kod parçacığını kodun içine nasıl eklediğini belirtir. Sıfır veya daha fazla olabilir `SnippetType` öğelerinde bir `SnippetTypes` öğesi.|  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Üstbilgi öğesi](../ide/code-snippets-schema-reference.md#header)|Kod parçacığı hakkında genel bilgiler belirtir.|  
  
##  <a name="title"></a>Title öğesi  
 Kod parçacığı için başlığı belirtir. Başlık depolanan `Title` kod parçacığında öğesi görünür **kod parçacığı Seçici** ve kod parçacığında 's açıklamasında **kod parçacıkları Yöneticisi**.  
  
```xml  
<Title>  
    Code Snippet Title  
<Title>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Üstbilgi öğesi](../ide/code-snippets-schema-reference.md#header)|Kod parçacığı hakkında genel bilgiler belirtir.|  
  
 Bir metin değeri gereklidir. Bu metin kod parçacığının başlığını belirtir.  
  
##  <a name="tooltip"></a>Araç İpucu öğesi  
 Kod parçacığındaki bir değişmez değerin veya nesnenin beklenen değerini ve kullanımını açıklar; Visual Studio, kod parçacığını bir projeye eklerken ToolTip öğesinde bunu görüntüler. ToolTip metni, kod parçacığı eklendikten sonra değişmez değerin veya nesnenin üzerine fare geldiğinde görüntülenir.  
  
```xml  
<ToolTip>  
    ToolTip description  
</ToolTip>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Değişmez değer öğesi](../ide/code-snippets-schema-reference.md#literal)|Kod parçacığının düzenleme yapabileceğiniz değişmez değer alanlarını tanımlar.|  
|[Object öğesi](../ide/code-snippets-schema-reference.md#object)|Kod parçacığının düzenleme yapabileceğiniz nesne alanlarını tanımlar.|  
  
 Bir metin değeri gereklidir. Bu metin, kod parçacığındaki nesne veya değişmez değer ile ilişkilendirilecek ToolTip açıklamasını belirtir.  
  
##  <a name="type"></a>Type öğesi  
 Nesnenin türünü belirtir. `Object` Öğesi tarafından kod parçacığını gereklidir ancak parçacığı dışında tanımlanmış olması olası bir öğeyi tanımlamak için kullanılır. Örneğin, Windows Forms denetimleri, ASP.NET denetimleri, nesne örnekleri ve tür örnekleri nesne olarak bildirilmelidir. Nesne bildirimleri gerektiren bir türü belirtilmesini ile yapılan `Type` öğesi.  
  
```xml  
<Type>  
    Type  
</Type>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Object öğesi](../ide/code-snippets-schema-reference.md#object)|Kod parçacığının düzenleme yapabileceğiniz nesne alanlarını tanımlar.|  
  
 Bir metin değeri gereklidir. Bu metin nesnenin türünü belirtir.  
  
##  <a name="url"></a>URL öğesi  
 Başvurulan derleme hakkında daha fazla bilgi sağlayan bir URL'yi belirtir.  
  
> [!NOTE]
>  `Url` Öğesi yalnızca Visual Basic projeleri için desteklenir.  
  
```xml  
<Url>  
    www.microsoft.com  
</Url>  
```  
  
|Üst Öğe|Açıklama|  
|--------------------|-----------------|  
|[Reference öğesi](../ide/code-snippets-schema-reference.md#reference)|Kod parçacığının gerek duyduğu derleme başvurularını belirtir.|  
  
 Bir metin değeri gereklidir. Bu metin, başvurulan derleme hakkında daha fazla bilgi içeren bir URL'yi belirtir. Bu URL, başvuru projeye eklenemediğinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod parçacıkları](../ide/code-snippets.md)   
 [İzlenecek Yol: Kod Parçacığı Oluşturma](../ide/walkthrough-creating-a-code-snippet.md)