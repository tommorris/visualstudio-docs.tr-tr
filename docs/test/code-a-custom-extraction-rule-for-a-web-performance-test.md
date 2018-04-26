---
title: Visual Studio'da web performans testi için özel ayıklama kuralı kodlama
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- extraction rules
- Web performance tests, creating custom extraction rules
- extraction rules, creating custom
ms.assetid: 6bcc5712-6cc6-4f59-8933-6e8078318c45
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 02fd481455c5198a1d8ae0828072f8085d1d027a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="coding-a-custom-extraction-rule-for-a-web-performance-test"></a>Web performans testi için özel bir ayıklama kuralı kodlama

Ayıklama kuralları oluşturabilirsiniz. Bunu yapmak için kendi kurallarınızı bir ayıklama kuralı sınıfından türetilir. Ayıklama kuralları türetilen <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule> temel sınıfı.

> [!NOTE]
> Özel doğrulama kuralları da oluşturabilirsiniz. Daha fazla bilgi için bkz: [özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md).

## <a name="to-create-a-custom-extraction-rule"></a>Özel bir ayıklama kuralı oluşturmak için

1.  Bir Test içeren bir Web performans testi projesi açın.

2.  (İsteğe bağlı) Ayıklama kuralı depolanacağı ayrı bir sınıf kitaplığı projesi oluşturun.

    > [!IMPORTANT]
    > Testlerinizi bulunan aynı projede sınıfı oluşturabilirsiniz. Bununla birlikte, kural yeniden kullanmak istiyorsanız, kuralınız depolanacağı ayrı bir sınıf kitaplığı projesi oluşturmak en iyisidir. Ayrı bir projesi oluşturursanız, bu yordamdaki isteğe bağlı adımları tamamlamanız gerekir.

3.  (İsteğe bağlı) Sınıf kitaplığı projesinde Microsoft.VisualStudio.QualityTools.WebTestFramework dll için bir başvuru ekleyin.

4.  Türeyen bir sınıf oluşturun <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule> sınıfı. Uygulama <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule.Extract*> ve <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule.RuleName*> üyeleri.

5.  (İsteğe bağlı) Yeni bir sınıf kitaplığı projesi oluşturun.

6.  (İsteğe bağlı) Test projesinde özel ayıklama kuralı içeren sınıf kitaplığı projesine bir başvuru ekleyin.

7.  Bir Web performans testinde Test projesinde açın **Web Performans Testi Düzenleyicisi**.

8.  Özel ayıklama kuralı eklemek için bir Web performans testi isteği sağ tıklatın ve seçin **Ayıklama Kuralı Ekle**.

     **Ayıklama Kuralı Ekle** iletişim kutusu görüntülenir. Özel doğrulama kuralınızı görürsünüz **bir kural seçin** önceden tanımlanmış doğrulama kuralları ile birlikte listesi. Özel ayıklama kuralı seçin ve ardından **Tamam**.

9. Web performans testi çalıştırın.

## <a name="example"></a>Örnek

Aşağıdaki kod, özel bir ayıklama kuralı uygulaması gösterir. Bu ayıklama kuralı değeri belirtilen giriş alandan ayıklar. Bu örnek için kendi özel ayıklama kuralları bir başlangıç noktası olarak kullanın.

```csharp
using System;
using System.Collections.Generic;
using Microsoft.VisualStudio.TestTools.WebTesting;
using System.Globalization;

namespace ClassLibrary2
{
    //-------------------------------------------------------------------------
    // This class creates a custom extraction rule named "Custom Extract Input"
    // The user of the rule specifies the name of an input field, and the
    // rule attempts to extract the value of that input field.
    //-------------------------------------------------------------------------
    public class CustomExtractInput : ExtractionRule
    {
        /// Specify a name for use in the user interface.
        /// The user sees this name in the Add Extraction dialog box.
        //---------------------------------------------------------------------
        public override string RuleName
        {
            get { return "Custom Extract Input"; }
        }

        /// Specify a description for use in the user interface.
        /// The user sees this description in the Add Extraction dialog box.
        //---------------------------------------------------------------------
        public override string RuleDescription
        {
            get { return "Extracts the value from a specified input field"; }
        }

        // The name of the desired input field
        private string NameValue;
        public string Name
        {
            get { return NameValue; }
            set { NameValue = value; }
        }

        // The Extract method.  The parameter e contains the web performance test context.
        //---------------------------------------------------------------------
        public override void Extract(object sender, ExtractionEventArgs e)
        {
            if (e.Response.HtmlDocument != null)
            {
                foreach (HtmlTag tag in e.Response.HtmlDocument.GetFilteredHtmlTags(new string[] { "input" }))
                {
                    if (String.Equals(tag.GetAttributeValueAsString("name"), Name, StringComparison.InvariantCultureIgnoreCase))
                    {
                        string formFieldValue = tag.GetAttributeValueAsString("value");
                        if (formFieldValue == null)
                        {
                            formFieldValue = String.Empty;
                        }

                        // add the extracted value to the web performance test context
                        e.WebTest.Context.Add(this.ContextParameterName, formFieldValue);
                        e.Success = true;
                        return;
                    }
                }
            }
            // If the extraction fails, set the error text that the user sees
            e.Success = false;
            e.Message = String.Format(CultureInfo.CurrentCulture, "Not Found: {0}", Name);
        }
    }
}
```

```vb
Imports System
Imports System.Collections.Generic
Imports Microsoft.VisualStudio.TestTools.WebTesting
Imports System.Globalization

Namespace ClassLibrary2

    '-------------------------------------------------------------------------
    ' This class creates a custom extraction rule named "Custom Extract Input"
    ' The user of the rule specifies the name of an input field, and the
    ' rule attempts to extract the value of that input field.
    '-------------------------------------------------------------------------
    Public Class CustomExtractInput
        Inherits ExtractionRule

        ' Specify a name for use in the user interface.
        ' The user sees this name in the Add Extraction dialog box.
        '---------------------------------------------------------------------
        Public Overrides ReadOnly Property RuleName() As String
            Get
                Return "Custom Extract Input"
            End Get
        End Property

        ' Specify a description for use in the user interface.
        ' The user sees this description in the Add Extraction dialog box.
        '---------------------------------------------------------------------
        Public Overrides ReadOnly Property RuleDescription() As String
            Get
                Return "Extracts the value from a specified input field"
            End Get
        End Property

        ' The name of the desired input field
        Private NameValue As String
        Public Property Name() As String
            Get
                Return NameValue
            End Get
            Set(ByVal value As String)
                NameValue = value
            End Set
        End Property

        ' The Extract method.  The parameter e contains the web performance test context.
        '---------------------------------------------------------------------
        Public Overrides Sub Extract(ByVal sender As Object, ByVal e As ExtractionEventArgs)

            If Not e.Response.HtmlDocument Is Nothing Then

                For Each tag As HtmlTag In e.Response.HtmlDocument.GetFilteredHtmlTags(New String() {"input"})

                    If String.Equals(tag.GetAttributeValueAsString("name"), Name, StringComparison.InvariantCultureIgnoreCase) Then

                        Dim formFieldValue As String = tag.GetAttributeValueAsString("value")
                        If formFieldValue Is Nothing Then

                            formFieldValue = String.Empty
                        End If

                        ' add the extracted value to the web performance test context
                        e.WebTest.Context.Add(Me.ContextParameterName, formFieldValue)
                        e.Success = True
                        Return
                    End If
                Next
            End If
            ' If the extraction fails, set the error text that the user sees
            e.Success = False
            e.Message = String.Format(CultureInfo.CurrentCulture, "Not Found: {0}", Name)
        End Sub
    End Class
End Namespace
```

<xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule.Extract*> Yöntemi bir ayıklama kuralı çekirdek işlevselliğini içerir. <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule.Extract*> Yöntemi önceki örnekte geçen bir <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionEventArgs> bu ayıklama kuralı kapsayan istek tarafından üretilen yanıt sağlar. Yanıtı içeren bir <xref:Microsoft.VisualStudio.TestTools.WebTesting.HtmlDocument> yanıt tüm etiketler içerir. Giriş etiketleri dışı filtrelenir <xref:Microsoft.VisualStudio.TestTools.WebTesting.HtmlDocument>. Her giriş etiketi adlı bir öznitelik için incelenir `name` sağlanan değeri, kullanıcı değeri eşittir `Name` özelliği. Bu eşleştirme özniteliğini içeren bir etiket bulunursa, bir tarafından yer alan bir değer ayıklamak için girişimde `value` öznitelik değeri öznitelik varsa. Varsa, ad ve değer etiketinin ayıklanır ve web performans testi içeriğine eklenir. Ayıklama kuralı geçirir.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.WebTesting.ExtractionRule>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractAttributeValue>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractFormField>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractHttpHeader>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractRegularExpression>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractText>
- <xref:Microsoft.VisualStudio.TestTools.WebTesting.Rules.ExtractHiddenFields>
- [Web performans testi için özel doğrulama kuralı kodlama](../test/code-a-custom-validation-rule-for-a-web-performance-test.md)