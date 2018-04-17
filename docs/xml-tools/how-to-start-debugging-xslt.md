---
title: 'Nasıl yapılır: XSLT hata ayıklamayı Başlat | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: f76412ce4dd0f5d443564755c460dfb82c186847
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-start-debugging-xslt"></a>Nasıl yapılır: XSLT hata ayıklamayı Başlat

XSLT hata ayıklayıcı XSLT stil sayfasını veya XSLT uygulamanın hata ayıklamak için kullanılabilir. Hata ayıklama sırasında içine Adımlama, üzerinden atlama veya kodların dışına Adımlama aynı anda bir satır kod yürütebilir. Kod atlama işlevselliği kullanmak için bir Visual Studio için olduğu gibi XSLT hata ayıklayıcı için aynı debuggers komutlardır. Hata ayıklama başladıktan sonra XSLT hata ayıklayıcı giriş belgesi ve XSLT çıkış göstermek için windows açar.

## <a name="xml-editor"></a>XML Düzenleyicisi

Hata ayıklayıcı XML Düzenleyicisi'nden başlatabilirsiniz. Bu, stil sayfası tasarlama gibi ayıklamanızı sağlar.

### <a name="to-start-debugging-from-a-style-sheet"></a>Stil sayfası içinden hata ayıklama başlatılamıyor

1. Stil sayfası XML düzenleyicisinde açın.

1. Seçin **hata ayıklama XSL** gelen **XML** menüsü.

### <a name="to-start-debugging-from-an-xml-input-document"></a>Giriş XML belgesinden hata ayıklamayı başlatmak için

1. XML belgesi XML düzenleyicisinde açın.

1. Seçin **hata ayıklama XSL** gelen **XML** menüsü.

## <a name="xslt-from-other-languages"></a>XSLT diğer dillerdeki

XSLT bir uygulama hata ayıklama sırasında da geçebilirsiniz. F11 bastığınızda bir <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=fullName> çağrısı, hata ayıklayıcı adım XSLT koda.

> [!NOTE]
> XSLT içine Adımlama <xref:System.Xml.Xsl.XslTransform> sınıfı desteklenmiyor. <xref:System.Xml.Xsl.XslCompiledTransform> Hata ayıklama sırasında XSLT Adımlama destekleyen yalnızca XSLT işlemci bir sınıftır.

### <a name="to-start-debugging-an-xslt-application"></a>XSLT uygulama hata ayıklama başlatılamıyor

1. Başlatılırken <xref:System.Xml.Xsl.XslCompiledTransform> nesne, ayarlamak `enableDebug` parametresi `true` kodunuzda.

     Bu kodu derlendiğinde hata ayıklama bilgileri oluşturmak için XSLT işlemci bildirir.

1. XSLT koda adım için F11 tuşuna basın.

     XSLT stil sayfası bir yeni belge penceresinde yüklenir ve XSLT hata ayıklayıcı başlatılır.

     Alternatif olarak, bir kesme noktası stil sayfasına ekleyin ve uygulamanızı çalıştırın.

### <a name="example"></a>Örnek

Bir C# XSLT programının bir örnek verilmiştir. XSLT hata ayıklamayı etkinleştirmek nasıl gösterir.

```csharp
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
  
namespace ConsoleApplication   
{  
  class Program   
  {  
    private const string sourceFile = @"c:\data\xsl_files\books.xml";  
    private const string stylesheet = @"c:\data\xsl_files\belowAvg.xsl";  
    private const string outputFile = @"c:\data\xsl_files\output.xml";  
  
    static void Main(string[] args)  
    {  
      // Enable XSLT debugging.
      XslCompiledTransform xslt = new XslCompiledTransform(true);  
  
      // Compile the style sheet.
      xslt.Load(stylesheet)  
  
      // Execute the XSLT transform.
      FileStream outputStream = new FileStream(outputFile, FileMode.Append);  
      xslt.Transform(sourceFile, null, outputStream);  
    }  
  }  
}  
```

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yol: XSLT Stil Sayfasında Hata Ayıklama](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)  
[Hata ayıklayıcısı temel bilgileri](../debugger/debugger-basics.md)