---
title: "Özel belge özellikleri eski dil hizmetindeki | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom document properties, language services [managed package framework]
- document properties, custom
- language services [managed package framework], custom document properties
ms.assetid: cc714a67-b33e-4440-9203-3c90f648bd9c
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c82476b9d6fd632ed67acbeeab147743ea16cb40
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="custom-document-properties-in-a-legacy-language-service"></a>Eski dil hizmetinde özel belge özellikleri
Belge özellikleri görüntülenebilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **özellikleri** penceresi. Programlama dilleri, tek tek kaynak dosyalarıyla ilişkili özellikleri genellikle gerekmez. Ancak, XML kodlama, şema ve stil etkileyen belge özelliklerini destekler.  
  
## <a name="discussion"></a>Tartışma  
 Özel belge özelliklerini dilinizi ihtiyaç duyuyorsa öğesinden bir sınıf türetin <xref:Microsoft.VisualStudio.Package.DocumentProperties> sınıf ve türetilen sınıf üzerinde gerekli özellikleri uygulamak.  
  
 Ayrıca, belge özellikleri genellikle kaynak dosyasının kendisini depolanır. Bu özellik bilgilerini görüntülemek için kaynak dosyadan dil hizmeti gerektirir **özellikleri** penceresi ve belge özelliklerinde bir değişiklik yapıldığında kaynak dosyasını güncelleştirmek için  **Özellikler** penceresi.  
  
## <a name="customizing-the-documentproperties-class"></a>DocumentProperties sınıfı özelleştirme  
 Özel belge özelliklerini desteklemek için öğesinden bir sınıf türetin <xref:Microsoft.VisualStudio.Package.DocumentProperties> sınıfı ve gerektiği gibi birçok özellik ekleyin. Bunları düzenlemek için kullanıcı özniteliklerini sağlamanız **özellikleri** penceresini görüntüleme. Yalnızca bir özellik varsa, bir `get` erişimci salt okunur olarak içinde gösterilen **özellikleri** penceresi. Her ikisi de özelliğine sahipse `get` ve `set` erişimciler, özelliği de güncelleştirilebilir içinde **özellikleri** penceresi.  
  
### <a name="example"></a>Örnek  
 Türetilen bir örnek sınıf işte <xref:Microsoft.VisualStudio.Package.DocumentProperties>, iki özellikleri, dosya adını ve açıklamasını gösteren. Bir özelliği güncelleştirildiğinde, özel bir yöntem <xref:Microsoft.VisualStudio.Package.LanguageService> sınıf özelliği kaynak dosyaya yazmak için çağrılır.  
  
```csharp  
using System.ComponentModel;  
using Microsoft.VisualStudio.Package;  
  
namespace TestLanguagePackage  
{  
    class TestDocumentProperties : DocumentProperties  
    {  
        private string m_filename;  
        private string m_description;  
  
        public TestDocumentProperties(CodeWindowManager mgr)  
            : base(mgr)  
        {  
        }  
  
        // Helper function to initialize this property without  
        // going through the FileName property (which does a lot  
        // more than we need when the filename is set).  
        public void SetFileName(string filename)  
        {  
            m_filename = filename;  
        }  
  
        // Helper function to initialize this property without  
        // going through the Description property (which does a lot  
        // more than we need when the description is set).  
        public void SetDescription(string description)  
        {  
            m_description = description;  
        }  
  
        ////////////////////////////////////////////////////////////  
        // The document properties  
  
        [CategoryAttribute("General")]  
        [DescriptionAttribute("Name of the file")]  
        [DisplayNameAttribute("Filename")]  
        public string FileName  
        {  
            get { return m_filename; }  
            set  
            {  
               if (value != m_filename)  
               {  
                    m_filename = value;  
                    SetPropertyValue("Filename", m_filename);  
               }  
            }  
        }  
  
        [CategoryAttribute("General")]  
        [DescriptionAttribute("Description of the file")]  
        [DisplayNameAttribute("Description")]  
        public string Description  
        {  
            get { return m_description; }  
            set  
            {  
                if (value != m_description)  
                {  
                    m_description = value;  
                    SetPropertyValue("Description", m_description);  
                }  
            }  
        }  
  
        ///////////////////////////////////////////////////////////  
        // Private methods.  
  
        private void SetPropertyValue(string propertyName, string propertyValue)  
        {  
            Source src = this.GetSource();  
            if (src != null)  
            {  
                TestLanguageService service = src.LanguageService as TestLanguageService;  
                if (service != null)  
                {  
                    // Set the property in to the source file.  
                    service.SetPropertyValue(src, propertyName, propertyValue);  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="instantiating-the-custom-documentproperties-class"></a>Özel DocumentProperties sınıfı örneği  
 Özel belge özellikleri sınıfının örneği için geçersiz kılmanız gerekir <xref:Microsoft.VisualStudio.Package.LanguageService.CreateDocumentProperties%2A> sürümünüz yönteminde <xref:Microsoft.VisualStudio.Package.LanguageService> tek bir örneğini döndürmek için sınıf, <xref:Microsoft.VisualStudio.Package.DocumentProperties> sınıfı.  
  
### <a name="example"></a>Örnek  
  
```csharp  
using System.ComponentModel;  
using Microsoft.VisualStudio.Package;  
  
namespace TestLanguagePackage  
{  
    class TestLanguageService : LanguageService  
    {  
        private TestDocumentProperties m_documentProperties;  
  
        public override DocumentProperties CreateDocumentProperties(CodeWindowManager mgr)  
        {  
            if (m_documentProperties == null)  
            {  
                m_documentProperties = new TestDocumentProperties(mgr);  
            }  
            return m_documentProperties;  
        }  
    }  
}  
```  
  
## <a name="properties-in-the-source-file"></a>Kaynak dosyanın özelliklerinde  
 Belge özellikleri için kaynak dosyası genellikle belirli olduğundan, değerler kaynak dosyasının kendisini depolanır. Bu dil Ayrıştırıcıyı veya bu özellikleri tanımlamak için tarayıcıdan desteği gerektirir. Örneğin, bir XML belgesi özelliklerini kök düğümde depolanır. Kök düğüm değerlerine ne zaman değiştirildiğinde **özellikleri** pencere değerleri değiştirilirse ve kök düğümü Düzenleyicisi'nde güncelleştirilir.  
  
### <a name="example"></a>Örnek  
 Bu örnekte, "Dosya adı" ve "olarak özel Açıklama üstbilgisinde katıştırılmış açıklamasında" ilk iki satır kaynak dosyasının özelliklerini depolar:  
  
```  
//!Filename = file.testext  
//!Description = A sample file  
```  
  
 Bu örnekte almak ve kullanıcının kaynak dosyasını doğrudan değiştiriyorsa özellikler güncelleştirilir ne de kaynak dosyasının ilk iki satırlarından belge özelliklerini ayarlamak için gereken iki yöntemi gösterilir. `SetPropertyValue` One yöntemi aynı işte gösterilen örnekte adlı `TestDocumentProperties` "DocumentProperties sınıfı özelleştirme" bölümünde gösterildiği gibi sınıfı.  
  
 Bu örnek tarayıcı ilk iki satır belirteçleri türünü belirlemek için kullanır. Bu örnek yalnızca tanım amaçlıdır. Bu durum daha tipik bir yaklaşım ne ayrıştırma ağacı, belirli bir belirteç hakkında bilgi her Ağaç düğümünün içerdiği çağrılır kaynak dosyası ayrıştırılamadı ' dir. Kök düğüm belge özelliklerini içerir.  
  
```csharp  
using System.ComponentModel;  
using Microsoft.VisualStudio.Package;  
  
namespace TestLanguagePackage  
{  
    // TokenType.Comment is the last item in that enumeration.  
    public enum TestTokenTypes  
    {  
        DocPropertyLine = TokenType.Comment + 1,  
        DocPropertyName,  
        DocPropertyAssign,  
        DocPropertyValue  
    }  
  
    class TestLanguageService : LanguageService  
    {  
        // Search this many lines from the beginning for properties.  
        private static int maxLinesToSearch = 2;  
  
        private TestDocumentProperties m_documentProperties;  
  
        // Called whenever a full parsing operation has completed.  
        public override void OnParseComplete(ParseRequest req)  
        {  
            if (m_documentProperties != null)  
            {  
                Source src = GetSource(req.View);  
                if (src != null)  
                {  
                    string value = GetPropertyValue(src, "Filename");  
                    m_documentProperties.SetFileName(value);  
  
                    value = GetPropertyValue(src, "Description");  
                    m_documentProperties.SetDescription(value);  
  
                    // Update the Properties Window.  
                    m_documentProperties.Refresh();  
                }  
            }  
        }  
  
        // Retrieves the specified property value from the given source.  
        public string GetPropertyValue(Source src, string propertyName)  
        {  
            string propertyValue = "";  
  
            if (src != null)  
            {  
                IVsTextColorState colorState = src.ColorState;  
                if (colorState != null)  
                {  
                    string      line;  
                    TokenInfo[] lineInfo = null;  
                    int         i;  
  
                    for (i = 0; i < maxLinesToSearch; i++)  
                    {  
                        line     = src.GetLine(i);  
                        lineInfo = src.GetColorizer().GetLineInfo(  
                                                        src.GetTextLines(),  
                                                        i,  
                                                        colorState);  
                        if (lineInfo == null)  
                        {  
                            continue;  
                        }  
                        if (lineInfo[0].Type != (TokenType)TestTokenTypes.DocPropertyLine)  
                        {  
                            // Not a property line.  
                            continue;  
                        }  
                        TokenInfo valueInfo = new TokenInfo();  
                        int tokenIndex = -1;  
                        for (tokenIndex = 0;  
                             tokenIndex < lineInfo.Length;  
                             tokenIndex++)  
                        {  
                            if (lineInfo[tokenIndex].Type == (TokenType)TestTokenTypes.DocPropertyName)  
                            {  
                                break;  
                            }  
                        }  
                        if (tokenIndex >= lineInfo.Length)  
                        {  
                            // No property name on the line.  
                            continue;  
                        }  
                        string name = src.GetText(i,  
                                                  lineInfo[tokenIndex].StartIndex,  
                                                  i,  
                                                  lineInfo[tokenIndex].EndIndex + 1);  
                        if (name != null)  
                        {  
                            if (String.Compare(name, propertyName, true) == 0)  
                            {  
                                for ( ;  
                                     tokenIndex < lineInfo.Length;  
                                     tokenIndex++)  
                                {  
                                    if (lineInfo[tokenIndex].Type == (TokenType)TestTokenTypes.DocPropertyValue)  
                                    {  
                                        break;  
                                    }  
                                }  
                                if (tokenIndex < lineInfo.Length)  
                                {  
                                    propertyValue = src.GetText(i,  
                                                          lineInfo[tokenIndex].StartIndex,  
                                                          i,  
                                                          lineInfo[tokenIndex].EndIndex + 1);  
                                }  
                                break;  
                            }  
                        }  
                    }  
                }  
            }  
            return propertyValue;  
        }  
  
        // Sets the specified property into the given source file.  
        // Called from the TestDocumentProperties class.  
        public void SetPropertyValue(Source src, string propertyName, string propertyValue)  
        {  
            string newLine;  
  
            if (propertyName == null || propertyName == "")  
            {  
                // No property name, so nothing to do  
                return;  
            }  
            if (propertyValue == null)  
            {  
                propertyValue = "";  
            }  
            // This is the line to be inserted.  
            newLine = String.Format("//!{0} = {1}", propertyName, propertyValue);  
  
            // First, find the line on which the property belongs.  
            // If line is found, replace it.  
            // Otherwise, insert the line at the beginning of the file.  
            if (src != null)  
            {  
                IVsTextColorState colorState = src.ColorState;  
                if (colorState != null)  
                {  
                    int         lineNumber = -1;  
                    string      line;  
                    TokenInfo[] lineInfo   = null;  
                    int         i;  
  
                    for (i = 0; i < maxLinesToSearch; i++)  
                    {  
                        line     = src.GetLine(i);  
                        lineInfo = src.GetColorizer().GetLineInfo(  
                                                        src.GetTextLines(),  
                                                        i,  
                                                        colorState);  
                        if (lineInfo == null)  
                        {  
                            continue;  
                        }  
                        if (lineInfo[0].Type != (TokenType)TestTokenTypes.DocPropertyLine)  
                        {  
                            // Not a property line  
                            continue;  
                        }  
                        TokenInfo valueInfo = new TokenInfo();  
                        int tokenIndex = -1;  
                        for (tokenIndex = 0;  
                             tokenIndex < lineInfo.Length;  
                             tokenIndex++)  
                        {  
                            if (lineInfo[tokenIndex].Type == (TokenType)TestTokenTypes.DocPropertyName)  
                            {  
                                break;  
                            }  
                        }  
                        if (tokenIndex >= lineInfo.Length)  
                        {  
                            // No property name on the line.  
                            continue;  
                        }  
                        string name = src.GetText(i,  
                                                  lineInfo[tokenIndex].StartIndex,  
                                                  i,  
                                                  lineInfo[tokenIndex].EndIndex + 1);  
                        if (name != null)  
                        {  
                            if (String.Compare(name, propertyName, true) == 0)  
                            {  
                                lineNumber = i;  
                                break;  
                            }  
                        }  
                    }  
  
                    // Set up an undo context that also handles the insert/replace.  
                    EditArray editArray = new EditArray(src,  
                                                        true,  
                                                        "Update Property");  
                    if (editArray != null)  
                    {  
                        TextSpan span = new TextSpan();  
                        if (lineNumber != -1)  
                        {  
                            // Replace line.  
                            int lineLength = 0;  
                            src.GetTextLines().GetLengthOfLine(lineNumber,  
                                                               out lineLength);  
                            span.iStartLine  = lineNumber;  
                            span.iStartIndex = 0;  
                            span.iEndLine    = lineNumber;  
                            span.iEndIndex   = lineLength;  
                        }  
                        else  
                        {  
                            // Insert new line.  
                            span.iStartLine  = 0;  
                            span.iStartIndex = 0;  
                            span.iEndLine    = 0;  
                            span.iEndIndex   = 0;  
                            newLine += "\n";  
                        }  
                        editArray.Add(new EditSpan(span, newLine));  
                        editArray.ApplyEdits();  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski dil hizmeti özellikleri](../../extensibility/internals/legacy-language-service-features1.md)