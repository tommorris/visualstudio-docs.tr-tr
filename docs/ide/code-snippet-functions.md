---
title: Kod Parçacığı İşlevleri
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- code snippets [Visual Studio], functions
- snippets [Visual Studio], functions
- IntelliSense code snippets, functions
ms.assetid: c0a2bf21-8fa5-4457-9281-f599beb53e7d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ead5a3f15f5ba7f586c9dfcec86fb309cbda391f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31917972"
---
# <a name="code-snippet-functions"></a>Kod parçacığı işlevleri

C# kod parçacıkları ile kullanmak kullanılabilen üç işlevleri vardır. İşlevler içinde belirtilen [işlevi](../ide/code-snippets-schema-reference.md#function) kod parçacığında öğesidir. Kod parçacıkları oluşturma hakkında daha fazla bilgi için bkz: [kod parçacıkları](../ide/code-snippets.md).

## <a name="functions"></a>İşlevler

Aşağıdaki tabloda ile kullanmak için kullanılabilir işlevleri açıklanmaktadır `Function` kod parçacıkları öğesinde.

|İşlev|Açıklama|Dil|
|--------------|-----------------|--------------|
|`GenerateSwitchCases(` `EnumerationLiteral` `)`|Switch deyimi ve case deyimleri kümesi tarafından belirtilen numaralandırma üyeleri için oluşturur `EnumerationLiteral` parametresi. `EnumerationLiteral` Parametresi bir numaralandırma sabit değeri bir başvuru ya da bir numaralandırma türü olmalıdır.|[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]|
|`ClassName()`|Eklenen kod parçacığını içeren sınıf adını döndürür.|[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]|
|`SimpleTypeName(` `TypeName` `)`|Azaltır *TypeName* en basit biçimiyle kod parçacığını çağrıldığı bağlam parametresi.|[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]|

## <a name="example"></a>Örnek

Aşağıdaki örnekte nasıl kullanılacağını gösterir `GenerateSwitchCases` işlevi. Ne zaman bu kod parçacığında eklenen ve numaralandırma girilir `$switch_on$` değişmez değeri `$cases$` değişmez değeri oluşturur bir `case` listedeki her bir değer ifadesi.

```xml
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>switch</Title>
            <Shortcut>switch</Shortcut>
            <Description>Code snippet for switch statement</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal>
                    <ID>expression</ID>
                    <ToolTip>Expression to switch on</ToolTip>
                    <Default>switch_on</Default>
                </Literal>
                <Literal Editable="false">
                    <ID>cases</ID>
                    <Function>GenerateSwitchCases($expression$)</Function>
                    <Default>default:</Default>
                </Literal>
            </Declarations>
            <Code Language="csharp">
                <![CDATA[
                    switch ($expression$)
                    {
                        $cases$
                    }
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="example"></a>Örnek

Aşağıdaki örnekte nasıl kullanılacağını gösterir `ClassName` işlevi. Bu kod parçacığında takıldığında `$classname$` değişmez değeri kodu dosyanın bu konumda kapsayan sınıfın adı ile değiştirilir.

```xml
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>Common constructor pattern</Title>
            <Shortcut>ctor</Shortcut>
            <Description>Code Snippet for a constructor</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal>
                    <ID>type</ID>
                    <Default>int</Default>
                </Literal>
                <Literal>
                    <ID>name</ID>
                    <Default>field</Default>
                </Literal>
                <Literal default="true" Editable="false">
                    <ID>classname</ID>
                    <ToolTip>Class name</ToolTip>
                    <Function>ClassName()</Function>
                    <Default>ClassNamePlaceholder</Default>
                </Literal>
            </Declarations>
            <Code Language="csharp" Format="CData">
                <![CDATA[
                    public $classname$ ($type$ $name$)
                    {
                        this._$name$ = $name$;
                    }
                    private $type$ _$name$;
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="example"></a>Örnek

Bu örnek nasıl kullanılacağını gösterir `SimpleTypeName` işlevi. Bu kod parçacığında bir kod dosyaya eklendiğinde, `$SystemConsole$` değişmez değeri ile en basit biçimi değiştirilecek <xref:System.Console> kod parçacığını çağrıldığı bağlam türü.

```xml
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title>Console_WriteLine</Title>
            <Shortcut>cw</Shortcut>
            <Description>Code snippet for Console.WriteLine</Description>
            <Author>Microsoft Corporation</Author>
            <SnippetTypes>
                <SnippetType>Expansion</SnippetType>
            </SnippetTypes>
        </Header>
        <Snippet>
            <Declarations>
                <Literal Editable="false">
                    <ID>SystemConsole</ID>
                    <Function>SimpleTypeName(global::System.Console)</Function>
                </Literal>
            </Declarations>
            <Code Language="csharp">
                <![CDATA[
                    $SystemConsole$.WriteLine();
                ]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="see-also"></a>Ayrıca bkz.

- [İşlev öğesi](../ide/code-snippets-schema-reference.md#function)
- [Kod parçacıkları şema başvurusu](../ide/code-snippets-schema-reference.md)
