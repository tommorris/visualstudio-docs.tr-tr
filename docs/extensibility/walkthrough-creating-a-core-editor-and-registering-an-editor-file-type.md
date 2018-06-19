---
title: Bir çekirdek düzenleyici oluşturma ve bir düzenleyici dosya türü kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - walkthrough
ms.assetid: 24d2bffd-a35c-46db-8515-fd60b884b7fb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6bb9b9443a60e54d875d6e3992a18ac1f0691244
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31147415"
---
# <a name="walkthrough-creating-a-core-editor-and-registering-an-editor-file-type"></a>İzlenecek yol: bir çekirdek düzenleyici oluşturma ve bir düzenleyici dosya türü kaydetme
Bu kılavuzda nasıl başlatır VSPackage oluşturulduğunu gösteren [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çekirdek .myext dosya adı uzantısına sahip bir dosya açıldığında düzenleyicisidir yüklü.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda izlemek için Visual Studio SDK'yı yüklemeniz gerekir. Daha fazla bilgi için bkz: [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="locations-for-the-visual-studio-package-project-template"></a>Visual Studio Paketi proje şablonu için konumları  
 Visual Studio Paketi proje şablonu üç farklı konumlarda bulunabilir **yeni proje** iletişim:  
  
1.  Visual Basic genişletilebilirliği altında. Visual Basic projesinin varsayılan dildir.  
  
2.  C# genişletilebilirlik altında. Varsayılan proje C# dilidir.  
  
3.  Diğer proje türleri genişletilebilirlik altında. C++ projesinin varsayılan dildir.  
  
### <a name="to-create-the-vspackage"></a>VSPackage oluşturmak için  
  
-   Başlat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve oluşturma bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] adlı VSPackage `MyPackage`özetlenen gibi [izlenecek yol: menü komutu VSPackage oluşturma](http://msdn.microsoft.com/en-us/d699c149-5d1e-47ff-94c7-e1222af02c32).  
  
### <a name="to-add-the-editor-factory"></a>Düzenleyici üreteci eklemek için  
  
1.  Sağ **MyPackage** proje, fareyle **Ekle** ve ardından **sınıfı**.  
  
2.  İçinde **Yeni Öğe Ekle** iletişim kutusunda, emin olun **sınıfı** Şablon seçildiğinde, türü `EditorFactory.cs` adı ve ardından **Ekle** sınıfı projenize eklemek için.  
  
     EditorFactory.cs dosya otomatik olarak açılması gerekir.  
  
3.  Aşağıdaki derlemeler kodunuzdan başvuru.  
  
    ```vb  
    Imports System.Runtime.InteropServices  
    Imports Microsoft.VisualStudio  
    Imports Microsoft.VisualStudio.Shell  
    Imports Microsoft.VisualStudio.Shell.Interop  
    Imports Microsoft.VisualStudio.OLE.Interop  
    Imports Microsoft.VisualStudio.TextManager.Interop  
    Imports IOleServiceProvider = Microsoft.VisualStudio.OLE.Interop.IServiceProvider  
    ```  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio.TextManager.Interop;  
    using IOleServiceProvider = Microsoft.VisualStudio.OLE.Interop.IServiceProvider;  
  
    ```  
  
4.  Bir GUID olarak ekleme `EditorFactory` ekleyerek sınıfı `Guid` sınıf bildiriminden hemen önce öznitelik.  
  
     Guidgen.exe programı kullanarak yeni bir GUID oluşturabilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] komut isteminden veya tıklayarak **Create GUID** üzerinde **Araçları** menüsü. Burada kullanılan GUID yalnızca bir örnektir; Projenizde kullanmayın.  
  
    ```vb  
    <Guid("0eea3187-c5fa-48d4-aa72-b5eecd3b17b1")> _  
    ```  
  
    ```csharp  
    [Guid("0eea3187-c5fa-48d4-aa72-b5eecd3b17b1")]   
    ```  
  
5.  Sınıf tanımı'nda üst paket ve bir hizmet sağlayıcısı içerecek şekilde iki özel değişkenler ekleyin.  
  
    ```vb  
    Class EditorFactory  
        Private parentPackage As Package  
        Private serviceProvider As IOleServiceProvider  
    ```  
  
    ```csharp  
    class EditorFactory  
    {  
        private Package parentPackage;  
        private IOleServiceProvider serviceProvider;  
    }  
  
    ```  
  
6.  Türünde bir parametre alan bir public sınıf oluşturucu ekleyin <xref:Microsoft.VisualStudio.Shell.Package>:  
  
    ```vb  
    Public Sub New(ByVal parentPackage As Package)  
        Me.parentPackage = parentPackage  
    End Sub  
    ```  
  
    ```csharp  
    public EditorFactory(Package parentPackage)  
    {  
        this.parentPackage = parentPackage;  
    }  
    ```  
  
7.  Değiştirme `EditorFactory` sınıf türetin bildiriminin <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> arabirimi.  
  
    ```vb  
    Class EditorFactory Implements IVsEditorFacto  
    ```  
  
    ```csharp  
    class EditorFactory : IVsEditorFactory  
  
    ```  
  
8.  Sağ <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>, tıklatın **arabirimi uygulama**ve ardından **uygulama arabirimi açıkça**.  
  
     Bu uygulanmalı dört yöntem ekler <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> arabirimi.  
  
9. Değiştir `IVsEditorFactory.Close` aşağıdaki kod ile yöntemi.  
  
    ```vb  
    Return VSConstants.S_OK  
    ```  
  
    ```csharp  
    return VSConstants.S_OK;  
    ```  
  
10. Değiştir `IVsEditorFactory.SetSite` aşağıdaki kod ile.  
  
    ```vb  
    Me.serviceProvider = psp  
    Return VSConstants.S_OK  
    ```  
  
    ```csharp  
    this.serviceProvider = psp;  
    return VSConstants.S_OK;  
    ```  
  
11. Değiştir `IVsEditorFactory.MapLogicalView` aşağıdaki kod ile yöntemi.  
  
    ```vb  
    Dim retval As Integer = VSConstants.E_NOTIMPL  
    pbstrPhysicalView = Nothing ' We support only one view.  
    If rguidLogicalView.Equals(VSConstants.LOGVIEWID_Designer)OrElse _  
    rguidLogicalView.Equals(VSConstants.LOGVIEWID_Primary) Then  
        retval = VSConstants.S_OK  
    End If  
    Return retval  
    ```  
  
    ```csharp  
    int retval = VSConstants.E_NOTIMPL;  
    pbstrPhysicalView = null;   // We support only one view.  
    if (rguidLogicalView.Equals(VSConstants.LOGVIEWID_Designer) ||  
    rguidLogicalView.Equals(VSConstants.LOGVIEWID_Primary))  
    {  
        retval = VSConstants.S_OK;  
    }  
    return retval;  
    ```  
  
12. Değiştir `IVsEditorFactory.CreateEditorInstance` aşağıdaki kod ile yöntemi.  
  
    ```vb  
    Dim retval As Integer = VSConstants.E_FAIL          
  
    ' Initialize these to empty to start with   
    ppunkDocView = IntPtr.Zero  
    ppunkDocData = IntPtr.Zero  
    pbstrEditorCaption = ""  
    pguidCmdUI = Guid.Empty  
    pgrfCDW = 0  
  
    If (grfCreateDoc And (VSConstants.CEF_OPENFILE Or _  
    VSConstants.CEF_SILENT)) = 0 Then  
        Throw New ArgumentException("Only Open or Silent is valid")  
    End If  
    If punkDocDataExisting <> IntPtr.Zero Then  
        Return VSConstants.VS_E_INCOMPATIBLEDOCDATA  
    End If  
  
    ' Instantiate a text buffer of type VsTextBuffer.   
    ' Note: we only need an IUnknown (object) interface for   
    ' this invocation.   
    Dim clsidTextBuffer As Guid = GetType(VsTextBufferClass).GUID  
    Dim iidTextBuffer As Guid = VSConstants.IID_IUnknown  
    Dim pTextBuffer As Object = pTextBuffer = _  
    parentPackage.CreateInstance(clsidTextBuffer, iidTextBuffer, _  
    GetType(Object))  
  
    If Not pTextBuffer Is Nothing Then  
        ' "Site" the text buffer with the service provider we were   
        ' provided.   
        Dim textBufferSite As IObjectWithSite = TryCast(pTextBuffer, _  
        IObjectWithSite)  
        If Not textBufferSite Is Nothing Then  
            textBufferSite.SetSite(Me.serviceProvider)  
        End If  
  
        ' Instantiate a code window of type IVsCodeWindow.   
        Dim clsidCodeWindow As Guid = GetType(VsCodeWindowClass).GUID  
        Dim iidCodeWindow As Guid = GetType(IVsCodeWindow).GUID  
        Dim pCodeWindow As IVsCodeWindow = _  
        CType(Me.parentPackage.CreateInstance(clsidCodeWindow, _  
        iidCodeWindow, GetType(IVsCodeWindow)), IVsCodeWindow)  
        If Not pCodeWindow Is Nothing Then  
            ' Give the text buffer to the code window.   
            ' We are giving up ownership of the text buffer!   
            pCodeWindow.SetBuffer(CType(pTextBuffer, IVsTextLines))  
  
            ' Now tell the caller about all this new stuff   
            ' that has been created.   
            ppunkDocView = Marshal.GetIUnknownForObject(pCodeWindow)  
            ppunkDocData = Marshal.GetIUnknownForObject(pTextBuffer)  
  
            ' Specify the command UI to use so keypresses are   
            ' automatically dealt with.   
            pguidCmdUI = VSConstants.GUID_TextEditorFactory  
  
            ' This caption is appended to the filename and   
            ' lets us know our invocation of the core editor   
            ' is up and running.   
            pbstrEditorCaption = " [MyPackage]"  
  
            retval = VSConstants.S_OK  
        End If  
    End If  
    Return retval  
    ```  
  
    ```csharp  
    int retval = VSConstants.E_FAIL;  
  
    // Initialize these to empty to start with  
    ppunkDocView       = IntPtr.Zero;  
    ppunkDocData       = IntPtr.Zero;  
    pbstrEditorCaption = "";  
    pguidCmdUI         = Guid.Empty;   
    pgrfCDW            = 0;  
  
    if ((grfCreateDoc & (VSConstants.CEF_OPENFILE |   
          VSConstants.CEF_SILENT)) == 0)  
    {   
        throw new ArgumentException("Only Open or Silent is valid");  
    }  
    if (punkDocDataExisting != IntPtr.Zero)  
    {  
        return VSConstants.VS_E_INCOMPATIBLEDOCDATA;  
    }  
  
    // Instantiate a text buffer of type VsTextBuffer.  
    // Note: we only need an IUnknown (object) interface for   
    // this invocation.  
    Guid clsidTextBuffer = typeof(VsTextBufferClass).GUID;  
    Guid iidTextBuffer   = VSConstants.IID_IUnknown;  
    object pTextBuffer   = pTextBuffer = parentPackage.CreateInstance(  
          ref clsidTextBuffer,  
          ref iidTextBuffer,  
          typeof(object));  
  
    if (pTextBuffer != null)  
    {  
        // "Site" the text buffer with the service provider we were  
        // provided.  
        IObjectWithSite textBufferSite = pTextBuffer as IObjectWithSite;  
        if (textBufferSite != null)  
        {  
            textBufferSite.SetSite(this.serviceProvider);  
        }  
  
        // Instantiate a code window of type IVsCodeWindow.  
        Guid clsidCodeWindow = typeof(VsCodeWindowClass).GUID;  
        Guid iidCodeWindow   = typeof(IVsCodeWindow).GUID;  
        IVsCodeWindow pCodeWindow =  
        (IVsCodeWindow)this.parentPackage.CreateInstance(   
              ref clsidCodeWindow,  
              ref iidCodeWindow,  
              typeof(IVsCodeWindow));  
        if (pCodeWindow != null)  
        {  
            // Give the text buffer to the code window.  
            // We are giving up ownership of the text buffer!  
            pCodeWindow.SetBuffer((IVsTextLines)pTextBuffer);  
  
            // Now tell the caller about all this new stuff   
            // that has been created.  
            ppunkDocView = Marshal.GetIUnknownForObject(pCodeWindow);  
            ppunkDocData = Marshal.GetIUnknownForObject(pTextBuffer);  
  
            // Specify the command UI to use so keypresses are   
            // automatically dealt with.  
            pguidCmdUI = VSConstants.GUID_TextEditorFactory;  
  
            // This caption is appended to the filename and  
            // lets us know our invocation of the core editor   
            // is up and running.  
            pbstrEditorCaption = " [MyPackage]";  
  
            retval = VSConstants.S_OK;  
        }   
    }   
    return retval;   
    ```  
  
13. Projeyi derlemek ve hiçbir hata bulunmadığından emin olun.  
  
### <a name="to-register-the-editor-factory"></a>Düzenleyici üreteci kaydetmek için  
  
1.  İçinde **Çözüm Gezgini**, bu, dize tablosuna Resources.resx dosyasına çift tıklayarak açın giriş **Dize1** seçili.  
  
2.  Tanımlayıcı adını değiştirmek `IDS_EDITORNAME` ve metne **MyPackage Düzenleyici.** Bu dize, düzenleyicinin adı görünür.  
  
3.  VSPackage.resx dosyasını açın ve yeni bir ekleyin dize, adı ayarlamak **101** ve değeri `IDS_EDITORNAME`. Bu, yeni oluşturduğunuz dize erişmek için bir kaynak kimliği ile paket sağlar.  
  
    > [!NOTE]
    >  VSPackage.resx dosya başka bir içeriyorsa, dize `name` özniteliğini **101**, başka bir benzersiz, sayısal değer, burada ve aşağıdaki adımlarda yerleştirin.  
  
4.  İçinde **Çözüm Gezgini**, MyPackagePackage.cs dosyasını açın.  
  
     Bu ana paket dosyasıdır.  
  
5.  Aşağıdaki kullanıcı özniteliklerini hemen önüne ekleyin `Guid` özniteliği.  
  
    ```vb  
    <ProvideEditorFactoryAttribute(GetType(EditorFactory), 101)> _  
    <ProvideEditorExtensionAttribute(GetType(EditorFactory), _  
          ".myext", 32, NameResourceID:=101 )> _  
    ```  
  
    ```csharp  
    [ProvideEditorFactory(typeof(EditorFactory), 101)]  
    [ProvideEditorExtension(typeof(EditorFactory),   
          ".myext", 32, NameResourceID = 101)]   
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.ProvideEditorExtensionAttribute> Özniteliği uzantısı yüklenir, düzenleyici üreteci çağrılan sahip bir dosya kurduğunda böylece bu .myext dosya uzantısı, düzenleyici üreteci ile ilişkilendirir.  
  
6.  Özel bir değişkeni eklemek `MyPackage` , yalnızca Oluşturucusu önce sınıf ve türü verin `EditorFactory`.  
  
    ```vb  
    Private editorFactory As EditorFactory  
    ```  
  
    ```csharp  
    private EditorFactory editorFactory;  
    ```  
  
7.  Bul `Initialize` yöntemi (açmak zorunda kalabilirsiniz `Package Members` gizli bölge) ve çağrısından sonra aşağıdaki kodu ekleyin `base.Initialize()`.  
  
    ```vb  
    'Create our editor factory and register it.   
    Me.editorFactory = New EditorFactory(Me)  
    MyBase.RegisterEditorFactory(Me.editorFactory)  
    ```  
  
    ```csharp  
    // Create our editor factory and register it.  
    this.editorFactory = new EditorFactory(this);  
    base.RegisterEditorFactory(this.editorFactory);  
  
    ```  
  
8.  Programı derleyin ve hata olmadığından emin olun.  
  
     Bu adım için Deneysel kayıt defteri kovanında Düzenleyici üreteci kaydettirir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Resource.h dosya geçersiz kılmak için istenirse, tıklatın **Tamam**.  
  
9. TextFile1.myext adlandırılmış bir örnek dosyası oluşturun.  
  
10. Tuşuna **F5** deneysel örneği açmak için [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
11. Deneysel [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], **dosya** menüsündeki **açık** ve ardından **dosya**.  
  
12. TextFile1.myext bulun ve ardından **açık**.  
  
     Dosyanın artık yüklenmesi.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Çekirdek Düzenleyici işleme çok çeşitli metin tabanlı bir dosya türleri ve yakından eşleşen ayraç zengin bir sözdizimi vurgulama gibi özellikleri sağlamak için dil Hizmetleri ve IntelliSense Sözcük tamamlama ve üye tamamlanma listeleri ile çalışır. Daha sonra metin tabanlı dosyalarla çalışıyorsanız, çekirdek Düzenleyicisi'ni, belirli dosya türlerini destekleyen bir özel dil hizmeti ile birlikte kullanabilirsiniz.  
  
 Bir VSPackage çağırabileceği [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir düzenleyici üreteci sağlayarak çekirdek Düzenleyici. Bu düzenleyici üreteci ile ilişkili olan bir dosyayı yüklenen her zaman kullanılır. Dosya, projesinin bir parçası ise, çekirdek Düzenleyicisi'ni otomatik olarak, sizin VSPackage tarafından geçersiz kılınmadığı sürece çağrılır. Dışında bir proje dosyası yüklerse, ancak daha sonra çekirdek Düzenleyicisi'ni açıkça, VSPackage tarafından çağrılması gerekir.  
  
 Çekirdek Düzenleyicisi hakkında daha fazla bilgi için bkz: [içinde çekirdek düzenleyici](../extensibility/inside-the-core-editor.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçinde çekirdek Düzenleyicisi](../extensibility/inside-the-core-editor.md)   
 [Eski API kullanarak çekirdek Düzenleyici örneği](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)