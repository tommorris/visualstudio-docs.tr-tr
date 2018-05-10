---
title: 'İzlenecek yol: bir kısayol tuşu Düzenleyicisi uzantısı ile kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - link keystrokes to commands
ms.assetid: cf6cc6c6-5a65-4f90-8f14-663decf74672
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f8f8a310832f0691b4bc4056baddeb1fbbad78f8
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-using-a-shortcut-key-with-an-editor-extension"></a>İzlenecek yol: bir kısayol tuşu Düzenleyicisi uzantısı ile kullanma
Kısayol tuşları Düzenleyicisi uzantısı'nda yanıt verebilir. Aşağıdaki örneklerde, bir kısayol tuşunu kullanarak bir görünüm adornment bir metin görünümüne eklemek gösterilmiştir. Bu kılavuz Görünüm penceresi adornment Düzenleyicisi şablona dayalı ve kullanarak adornment eklemenize olanak sağlayan + karakter.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-managed-extensibility-framework-mef-project"></a>Yönetilen Genişletilebilirlik Çerçevesi (MEF) proje oluşturma  
  
1.  Bir C# VSIX projesi oluşturun. (İçinde **yeni proje** iletişim kutusunda **Visual C# / genişletilebilirlik**, ardından **VSIX proje**.) Çözüm adı `KeyBindingTest`.  
  
2.  Bir düzenleyici metin Adornment öğe şablonu projeye ekleyin ve adını `KeyBindingTest`. Daha fazla bilgi için bkz: [bir düzenleyici öğesi şablonuyla bir uzantısı oluşturma](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Aşağıdaki başvurular ekleyin ve ayarlayın **CopyLocal** için `false`:  
  
     Microsoft.VisualStudio.Editor  
  
     Microsoft.VisualStudio.OLE.Interop  
  
     Microsoft.VisualStudio.Shell.14.0  
  
     Microsoft.VisualStudio.TextManager.Interop  
  
 KeyBindingTest sınıf dosyasında, sınıf adı için PurpleCornerBox değiştirin. Görüntülenen ampul sol kenar boşluğunda uygun bir değişiklik yapmak için kullanın. Oluşturucu içinde adornment katmandan adını değiştirmek **KeyBindingTest** için **PurpleCornerBox**:  
  
```csharp  
this.layer = view.GetAdornmentLayer("PurpleCornerBox");  
```  

KeyBindingTestTextViewCreationListener.cs sınıf dosyasında AdornmentLayer adını değiştirmek **KeyBindingTest** için **PurpleCornerBox**:
  
    ```csharp  
    [Export(typeof(AdornmentLayerDefinition))]  
    [Name("PurpleCornerBox")]  
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]  
    public AdornmentLayerDefinition editorAdornmentLayer;  
    ```  

## <a name="handling-typechar-command"></a>TYPECHAR komutu işleme
Visual Studio 2017 sürümü bir düzenleyici uzantısını komutları işlemek için tek yolu uygulama 15,6 önce bir <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> komutu filtresini tabanlı. Visual Studio 2017 sürüm 15,6 Düzenleyicisi komut işleyicileri dayalı modern basitleştirilmiş bir yaklaşım sunmuştur. Sonraki iki bölümde hem eski ve modern bir yaklaşım kullanarak bir komut nasıl ele alınacağını göstermektedir.

## <a name="defining-the-command-filter-prior-to-visual-studio-2017-version-156"></a>(Önce Visual Studio 2017 sürüm 15,6) komutu filtresini tanımlama

 Komut filtresi uygulamasıdır <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>, hangi işleme komutu adornment oluşturarak.  
  
1.  Bir sınıf dosyası ekleyin ve adını `KeyBindingCommandFilter`.  
  
2.  Aşağıdaki using deyimlerini.  
  
    ```csharp  
    using System;  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Text.Editor;  
  
    ```  
  
3.  KeyBindingCommandFilter adlı sınıf alması gerektiğini <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>.  
  
    ```csharp  
    internal class KeyBindingCommandFilter : IOleCommandTarget  
    ```  
  
4.  Metin görünümü için özel alanlar, sonraki komut komut zinciri ve komut filtresi zaten eklenmiş olup olmadığını göstermek için bir bayrak ekleyin.  
  
    ```csharp  
    private IWpfTextView m_textView;  
    internal IOleCommandTarget m_nextTarget;  
    internal bool m_added;  
    internal bool m_adorned;  
    ```  
  
5.  Metin görünümü ayarlar bir oluşturucu ekleyin.  
  
    ```csharp  
    public KeyBindingCommandFilter(IWpfTextView textView)  
    {  
        m_textView = textView;  
        m_adorned = false;  
    }  
    ```  
  
6.  Uygulama `QueryStatus()` yöntemini aşağıdaki şekilde.  
  
    ```csharp  
    int IOleCommandTarget.QueryStatus(ref Guid pguidCmdGroup, uint cCmds, OLECMD[] prgCmds, IntPtr pCmdText)  
    {  
        return m_nextTarget.QueryStatus(ref pguidCmdGroup, cCmds, prgCmds, pCmdText);  
    }  
    ```  
  
7.  Uygulama `Exec()` onun mor kutusunu görünümüne ekler şekilde yöntemi bir + karakter türü.  
  
    ```csharp  
    int IOleCommandTarget.Exec(ref Guid pguidCmdGroup, uint nCmdID, uint nCmdexecopt, IntPtr pvaIn, IntPtr pvaOut)  
    {  
        if (m_adorned == false)  
        {  
            char typedChar = char.MinValue;  
  
            if (pguidCmdGroup == VSConstants.VSStd2K && nCmdID == (uint)VSConstants.VSStd2KCmdID.TYPECHAR)  
            {  
                typedChar = (char)(ushort)Marshal.GetObjectForNativeVariant(pvaIn);  
                if (typedChar.Equals('+'))  
                {  
                    new PurpleCornerBox(m_textView);  
                    m_adorned = true;  
                }  
            }  
        }  
        return m_nextTarget.Exec(ref pguidCmdGroup, nCmdID, nCmdexecopt, pvaIn, pvaOut);  
    }  
  
    ```  
  
## <a name="adding-the-command-filter-prior-to-visual-studio-2017-version-156"></a>(Önce Visual Studio 2017 sürüm 15,6) komut filtresi ekleme
 Adornment sağlayıcısı komut filtresi metni görünümüne eklemeniz gerekir. Bu örnekte, sağlayıcı uygulayan <xref:Microsoft.VisualStudio.Editor.IVsTextViewCreationListener> metin görünüm oluşturma olayları dinleyecek şekilde. Bu adornment sağlayıcısı ayrıca adornment Z-sıralamasını tanımlar adornment katmanı dışa aktarır.  
  
1.  Aşağıdaki KeyBindingTestTextViewCreationListener dosyasına ekleyin using deyimleri:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio.Utilities;  
    using Microsoft.VisualStudio.Editor;  
    using Microsoft.VisualStudio.Text.Editor;  
    using Microsoft.VisualStudio.TextManager.Interop;  
  
    ```  
  
2.  Metin görünümü bağdaştırıcısı almak için içeri aktarmanız gerekir <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService>.  
  
    ```csharp  
    [Import(typeof(IVsEditorAdaptersFactoryService))]  
    internal IVsEditorAdaptersFactoryService editorFactory = null;  
  
    ```  
  
3.  Değişiklik <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> olan ekler için yöntemi `KeyBindingCommandFilter`.  
  
    ```csharp  
    public void TextViewCreated(IWpfTextView textView)  
    {  
        AddCommandFilter(textView, new KeyBindingCommandFilter(textView));  
    }  
    ```  
  
4.  `AddCommandFilter` İşleyicisi metin görünümü bağdaştırıcısı alır ve komut filtre ekler.  
  
    ```csharp  
    void AddCommandFilter(IWpfTextView textView, KeyBindingCommandFilter commandFilter)  
    {  
        if (commandFilter.m_added == false)  
        {  
            //get the view adapter from the editor factory  
            IOleCommandTarget next;   
            IVsTextView view = editorFactory.GetViewAdapter(textView);  
  
            int hr = view.AddCommandFilter(commandFilter, out next);  
  
            if (hr == VSConstants.S_OK)  
            {      
                commandFilter.m_added = true;  
                 //you'll need the next target for Exec and QueryStatus   
                if (next != null)  
                commandFilter.m_nextTarget = next;  
            }  
        }  
    }  
    ```  

## <a name="implement-a-command-handler-starting-in-visual-studio-2017-version-156"></a>(Visual Studio 2017 sürüm 15,6 başlayarak) bir komut işleyici uygulama

İlk olarak, en son Düzenleyicisi API başvuru için projenin Nuget başvurularını güncelleştirme:

1. Sağ tıklatın ve proje **Nuget paketlerini Yönet**.

2. İçinde **Nuget Paket Yöneticisi**seçin **güncelleştirmeleri** sekmesine **tüm paketleri seçmek** onay kutusunu ve ardından **güncelleştirme**.

Bir komut işleyici uygulamasıdır <xref:Microsoft.VisualStudio.Commanding.ICommandHandler%601>, hangi işleme komutu adornment oluşturarak.  
  
1.  Bir sınıf dosyası ekleyin ve adını `KeyBindingCommandHandler`.  
  
2.  Aşağıdaki using deyimlerini.  
  
    ```csharp  
    using Microsoft.VisualStudio.Commanding;
    using Microsoft.VisualStudio.Text.Editor;
    using Microsoft.VisualStudio.Text.Editor.Commanding.Commands;
    using Microsoft.VisualStudio.Utilities;
    using System.ComponentModel.Composition;   
    ```  
  
3.  KeyBindingCommandHandler adlı sınıf alması gerektiğini `ICommandHandler<TypeCharCommandArgs>`ve olarak dışarı aktarma <xref:Microsoft.VisualStudio.Commanding.ICommandHandler>:
  
    ```csharp  
    [Export(typeof(ICommandHandler))]
    [ContentType("text")]
    [Name("KeyBindingTest")]
    internal class KeyBindingCommandHandler : ICommandHandler<TypeCharCommandArgs>  
    ```  
  
4.  Komut işleyici görünen adını ekleyin:  
  
    ```csharp  
    public string DisplayName => "KeyBindingTest";
    ```  
    
5.  Uygulama `GetCommandState()` yöntemini aşağıdaki şekilde. Bu komut işleyici çekirdek Düzenleyici TYPECHAR komutu işlemesi nedeniyle çekirdek Düzenleyici komutuna etkinleştirme devredebilirsiniz.
  
    ```csharp  
    public CommandState GetCommandState(TypeCharCommandArgs args)
    {
        return CommandState.Unspecified;
    } 
    ```  
  
6.  Uygulama `ExecuteCommand()` onun mor kutusunu görünümüne ekler şekilde yöntemi bir + karakter türü. 
  
    ```csharp  
    public bool ExecuteCommand(TypeCharCommandArgs args, CommandExecutionContext executionContext)
    {
        if (args.TypedChar == '+')
        {
            bool alreadyAdorned = args.TextView.Properties.TryGetProperty(
                "KeyBindingTextAdorned", out bool adorned) && adorned;
            if (!alreadyAdorned)
            {
                new PurpleCornerBox((IWpfTextView)args.TextView);
                args.TextView.Properties.AddProperty("KeyBindingTextAdorned", true);
            }
        }

        return false;
    }
    ```  
 7. Adornment katman tanımı KeyBindingTestTextViewCreationListener.cs dosyasından KeyBindingCommandHandler.cs kopyalayın ve sonra KeyBindingTestTextViewCreationListener.cs dosyasını silin:
 
    ```csharp  
    /// <summary>
    /// Defines the adornment layer for the adornment. This layer is ordered
    /// after the selection layer in the Z-order.
    /// </summary>
    [Export(typeof(AdornmentLayerDefinition))]
    [Name("PurpleCornerBox")]
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]
    private AdornmentLayerDefinition editorAdornmentLayer;    
    ```  

## <a name="making-the-adornment-appear-on-every-line"></a>Adornment yapmadan her satırda görünür  

Her karakteri özgün adornment görünen bir metin dosyasındaki ' bir'. Biz adornment yanıt '+' karakter olarak eklemek için kodu değişti, yalnızca satırda adornment ekler burada '+' yazılır. Böylece adornment kez daha görünür adornment kodunu değiştirmek her 'bir'.  
  
KeyBindingTest.cs dosyasında 'bir' karakteri tasarlamanız görünümdeki tüm satırları yinelemek için CreateVisuals() yöntemini değiştirin.  
  
```csharp  
private void CreateVisuals(ITextViewLine line)  
{  
    IWpfTextViewLineCollection textViewLines = this.view.TextViewLines;  
  
    foreach (ITextViewLine textViewLine in textViewLines)  
    {  
        if (textViewLine.ToString().Contains("a"))  
        {  
            // Loop through each character, and place a box around any 'a'   
            for (int charIndex = textViewLine.Start; charIndex < textViewLine.End; charIndex++)  
            {  
                if (this.view.TextSnapshot[charIndex] == 'a')  
                {  
                    SnapshotSpan span = new SnapshotSpan(this.view.TextSnapshot, Span.FromBounds(charIndex, charIndex + 1));  
                    Geometry geometry = textViewLines.GetMarkerGeometry(span);  
                    if (geometry != null)  
                    {  
                        var drawing = new GeometryDrawing(this.brush, this.pen, geometry);  
                        drawing.Freeze();  
  
                        var drawingImage = new DrawingImage(drawing);  
                        drawingImage.Freeze();  
  
                        var image = new Image  
                        {  
                            Source = drawingImage,  
                        };  
  
                        // Align the image with the top of the bounds of the text geometry  
                        Canvas.SetLeft(image, geometry.Bounds.Left);  
                        Canvas.SetTop(image, geometry.Bounds.Top);  
  
                        this.layer.AddAdornment(AdornmentPositioningBehavior.TextRelative, span, null, image, null);  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="building-and-testing-the-code"></a>Derleme ve kodu test etme  
  
1.  KeyBindingTest çözümü oluşturmak ve deneysel örneğinde çalıştırın.  
  
2.  Oluşturun veya bir metin dosyasını açın. Karakter içeren bazı sözcükleri yazın 'bir' ve ardından + metin görünümü başka bir yerindeki.  
  
     Mor kare dosyasındaki 'bir' her bir karakteri görüntülenmesi gerekir.
