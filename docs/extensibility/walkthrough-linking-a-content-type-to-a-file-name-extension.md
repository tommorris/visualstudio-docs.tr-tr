---
title: 'İzlenecek yol: bir dosya adı uzantısı için bir içerik türü bağlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - link content type to file name extension
ms.assetid: 21ee64ce-9afe-4b08-94a0-8389cc4dc67c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: cca12f7c04b51bcf2b695e00d9305a7feb72ebc4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144901"
---
# <a name="walkthrough-linking-a-content-type-to-a-file-name-extension"></a>İzlenecek yol: bir içerik türü için bir dosya adı uzantısı bağlama
Düzenleyici Yönetilen Genişletilebilirlik Çerçevesi (MEF) uzantıları kullanarak bir dosya adı uzantısı bağlantısına ve kendi içerik türünü tanımlayın. Bazı durumlarda, dosya adı uzantısı zaten bir dil hizmeti tarafından tanımlanmış; Bununla birlikte, MEF ile kullanmak için hala bir içerik türüyle Bağla gerekir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Bir MEF projesi oluşturma  
  
1.  Bir C# VSIX projesi oluşturun. (İçinde **yeni proje** iletişim kutusunda **Visual C# / genişletilebilirlik**, ardından **VSIX proje**.) Çözüm adı `ContentTypeTest`.  
  
2.  İçinde **source.extension.vsixmanifest** dosya, Git **varlıklar** sekmesini tıklatın ve ayarlama **türü** alanı **Microsoft.VisualStudio.MefComponent**, **kaynak** alanı **geçerli çözümdeki bir proje ile**ve **proje** projesinin adı alanı.  
  
## <a name="defining-the-content-type"></a>İçerik türü tanımlama  
  
1.  Bir sınıf dosyası ekleyin ve adını `FileAndContentTypes`.  
  
2.  Aşağıdaki derlemelere başvurular ekleyin:  
  
    1.  System.ComponentModel.Composition  
  
    2.  Microsoft.VisualStudio.Text.Logic  
  
    3.  Microsoft.VisualStudio.CoreUtility  
  
3.  Aşağıdakileri ekleyin `using` yönergeleri.  
  
    ```csharp  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text.Classification;  
    using Microsoft.VisualStudio.Utilities;  
  
    ```  
  
4.  Tanımları içeren bir statik sınıf bildirin.  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {. . .}  
    ```  
  
5.  Bu sınıf, verme bir <xref:Microsoft.VisualStudio.Utilities.ContentTypeDefinition> "HID" adlı ve temel tanımına "metin" olarak bildirin.  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {  
        [Export]  
        [Name("hid")]  
        [BaseDefinition("text")]  
        internal static ContentTypeDefinition hidingContentTypeDefinition;  
    }  
    ```  
  
## <a name="linking-a-file-name-extension-to-a-content-type"></a>Bir içerik türü için bir dosya adı uzantısı bağlama  
  
-   Bu içerik türü için bir dosya adı uzantısı eşlemek için dışarı aktarma bir <xref:Microsoft.VisualStudio.Utilities.FileExtensionToContentTypeDefinition> ".hid" uzantısına sahip ve "içerik türü HID".  
  
    ```csharp  
    internal static class FileAndContentTypeDefinitions  
    {  
         [Export]  
         [Name("hid")]  
         [BaseDefinition("text")]  
        internal static ContentTypeDefinition hidingContentTypeDefinition;  
  
         [Export]  
         [FileExtension(".hid")]  
         [ContentType("hid")]  
        internal static FileExtensionToContentTypeDefinition hiddenFileExtensionDefinition;  
    }  
    ```  
  
## <a name="adding-the-content-type-to-an-editor-export"></a>İçerik türü Düzenleyicisi verme ekleme  
  
1.  Bir düzenleyici uzantısı oluşturun. Örneğin, açıklanan kenar karakter uzantısı kullanabileceğiniz [izlenecek yol: bir kenar karakter oluşturma](../extensibility/walkthrough-creating-a-margin-glyph.md).  
  
2.  Bu yordamda tanımlanan sınıf ekleyin.  
  
3.  Extension sınıfının dışa aktardığınızda, ekleme bir <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> "kendisine HID" türü.  
  
    ```csharp  
    [Export]  
    [ContentType("hid")]  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dil Hizmeti ve Düzenleyici Uzantı Noktaları](../extensibility/language-service-and-editor-extension-points.md)