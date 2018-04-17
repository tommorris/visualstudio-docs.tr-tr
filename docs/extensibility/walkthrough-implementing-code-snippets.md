---
title: 'İzlenecek yol: Kod parçacıkları uygulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: adbc5382-d170-441c-9fd0-80faa1816478
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ae260951160bc3d4ed3bb1535f47eb1f33649957
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-implementing-code-snippets"></a>İzlenecek yol: Kod parçacıkları uygulama
Kod parçacıkları oluşturabilir ve böylece kullanıcılar uzantısı'nın kendi kodlarını ekleyebilirsiniz bunları bir düzenleyici uzantısına dahil etme.  
  
 Kod parçacığı kodu veya bir dosyada birleştirilebilir başka bir metin bir parçası olur. Üzerinde belirli programlama dili için kayıtlı tüm parçacıkları görüntülemek için **Araçları** menüsünde tıklatın **kod parçacığını Yöneticisi**. Parçacık parçacığı istediğiniz yere sağ gibi bir dosya eklemek için tıklatın **Ekle parçacığı** veya **Surround With**istediğiniz parçacığı bulun ve çift tıklatın. SEKME veya üst karakter + sekme kod parçacığını ilgili bölümleri değiştirebilir ve bunu kabul etmek için ENTER veya ESC tuşuna basın. Daha fazla bilgi için bkz: [kod parçacıkları](../ide/code-snippets.md).  
  
 Kod parçacığı .snippet dosya adı uzantısına sahip bir XML dosyasında yer alır. Bir kod parçacığında, böylece kullanıcı bulmak ve onları değiştirebilir kod parçacığını eklendikten sonra vurgulanmıştır alanlar içerebilir. Parçacık dosyası bilgilerini de sağlar **kod parçacığını Yöneticisi** doğru kategorisinde parçacığını ad görüntüleyebilmesi. Kod parçacığında şeması hakkında daha fazla bilgi için bkz: [kod parçacıkları şema başvurusu](../ide/code-snippets-schema-reference.md).  
  
 Bu kılavuzda, bu görevleri gerçekleştirmek üzere öğretir:  
  
1.  Oluşturun ve belirli bir dil için kod parçacıkları kaydedin.  
  
2.  Ekleme **Ekle parçacığı** bir kısayol menü komutu.  
  
3.  Kod parçacığında genişletme uygulayın.  
  
 Bu kılavuzda dayanır [izlenecek yol: deyim tamamlama görüntüleme](../extensibility/walkthrough-displaying-statement-completion.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-and-registering-code-snippets"></a>Oluşturma ve kod parçacıkları kaydetme  
 Genellikle, kod parçacıkları kayıtlı dil hizmeti ile ilişkilendirilmiş. Ancak, uygulama gerekmez bir <xref:Microsoft.VisualStudio.Package.LanguageService> kod parçacıkları kaydetmek için. Bunun yerine, yalnızca parçacığı dizini dosyasında bir GUID belirtin ve ardından aynı GUID'ye <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> , projenize ekleyin.  
  
 Aşağıdaki adımları kod parçacıkları oluşturmak ve bunları belirli bir GUID ile ilişkilendirmek nasıl ekleyebileceğiniz gösterilmektedir.  
  
1.  Aşağıdaki dizin yapısını oluşturun:  
  
     **%InstallDir%\TestSnippets\Snippets\1033\\**  
  
     Burada *InstallDir %* Visual Studio yükleme klasörüdür. (Bu yol genellikle kod parçacıkları yüklemek için kullanılsa da, herhangi bir yol belirtebilirsiniz.)  
  
2.  \1033\ klasördeki bir .xml dosyası oluşturun ve adlandırın **TestSnippets.xml**. (Bu ad genel parçacığını dizin dosyası için kullanılsa da bir .xml dosya adı uzantısına sahip olduğu sürece herhangi bir ad belirtebilirsiniz.) Aşağıdaki metni ekleyin ve ardından yer tutucu GUID silin ve kendi ekleyin.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <SnippetCollection>  
        <Language Lang="TestSnippets" Guid="{00000000-0000-0000-0000-000000000000}">  
            <SnippetDir>  
                <OnOff>On</OnOff>  
                <Installed>true</Installed>  
                <Locale>1033</Locale>  
                <DirPath>%InstallRoot%\TestSnippets\Snippets\%LCID%\</DirPath>  
                <LocalizedName>Snippets</LocalizedName>  
            </SnippetDir>  
        </Language>  
    </SnippetCollection>  
    ```  
  
3.  Kod parçacığında klasöründe bir dosya oluşturun, adlandırın **test**`.snippet`ve ardından aşağıdaki metni ekleyin:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
        <CodeSnippet Format="1.0.0">  
            <Header>  
                <Title>Test replacement fields</Title>  
                <Shortcut>test</Shortcut>  
                <Description>Code snippet for testing replacement fields</Description>  
                <Author>MSIT</Author>  
                <SnippetTypes>  
                    <SnippetType>Expansion</SnippetType>  
                </SnippetTypes>  
            </Header>  
            <Snippet>  
                <Declarations>  
                    <Literal>  
                      <ID>param1</ID>  
                        <ToolTip>First field</ToolTip>  
                        <Default>first</Default>  
                    </Literal>  
                    <Literal>  
                        <ID>param2</ID>  
                        <ToolTip>Second field</ToolTip>  
                        <Default>second</Default>  
                    </Literal>  
                </Declarations>  
                <References>  
                   <Reference>  
                       <Assembly>System.Windows.Forms.dll</Assembly>  
                   </Reference>  
                </References>  
                <Code Language="TestSnippets">  
                    <![CDATA[MessageBox.Show("$param1$");  
         MessageBox.Show("$param2$");]]>  
                </Code>    
            </Snippet>  
        </CodeSnippet>  
    </CodeSnippets>  
    ```  
  
 Aşağıdaki adımlar kod parçacıkları nasıl gösterir.  
  
#### <a name="to-register-code-snippets-for-a-specific-guid"></a>Kod parçacıkları için belirli bir GUID kaydetmek için  
  
1.  Açık **CompletionTest** projesi. Bu proje oluşturma hakkında daha fazla bilgi için bkz: [izlenecek yol: deyim tamamlama görüntüleme](../extensibility/walkthrough-displaying-statement-completion.md).  
  
2.  Projede aşağıdaki derlemelerine başvurular ekleyin:  
  
    -   Microsoft.VisualStudio.TextManager.Interop  
  
    -   Microsoft.VisualStudio.TextManager.Interop.8.0  
  
    -   Microsoft.MSXML  
  
3.  Projede source.extension.vsixmanifest dosyasını açın.  
  
4.  Olduğundan emin olun **varlıklar** sekmesini içeren bir **VsPackage** içerik türü ve, **proje** proje adına ayarlayın.  
  
5.  CompletionTest projesini seçin ve Özellikler penceresinde ayarlayın **Pkgdef dosya oluşturmak** için **doğru**. Projeyi kaydedin.  
  
6.  Statik eklemek `SnippetUtilities` projeye sınıfı.  
  
     [!code-csharp[VSSDKCompletionTest#22](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_1.cs)]
     [!code-vb[VSSDKCompletionTest#22](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_1.vb)]  
  
7.  SnippetUtilities sınıfı bir GUID tanımlayın ve SnippetsIndex.xml dosyasında kullanılan değer verin.  
  
     [!code-csharp[VSSDKCompletionTest#23](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_2.cs)]
     [!code-vb[VSSDKCompletionTest#23](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_2.vb)]  
  
8.  Ekleme <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> için `TestCompletionHandler` sınıfı. Bu öznitelik, hiçbir ortak veya dahili (statik olmayan) sınıfta proje eklenebilir. (Eklemek zorunda kalabilirsiniz bir `using` Microsoft.VisualStudio.Shell ad alanı bildirimi.)  
  
     [!code-csharp[VSSDKCompletionTest#24](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_3.cs)]
     [!code-vb[VSSDKCompletionTest#24](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_3.vb)]  
  
9. Oluşturun ve projeyi çalıştırın. Projeyi çalıştırdığınızda başlayan Visual Studio deneysel örneği yalnızca kayıtlı parçacığı görüntülenmelidir **kod parçacıkları Yöneticisi** altında **TestSnippets** dili.  
  
## <a name="adding-the-insert-snippet-command-to-the-shortcut-menu"></a>INSERT parçacığı komutu için kısayol menüsü ekleme  
 **Ekle parçacığı** komutu bir metin dosyası için kısayol menüsünde dahil değildir. Bu nedenle, komut etkinleştirmeniz gerekir.  
  
#### <a name="to-add-the-insert-snippet-command-to-the-shortcut-menu"></a>Kısayol menüsünün Ekle parçacığı komut eklemek için  
  
1.  Açık `TestCompletionCommandHandler` sınıf dosyası.  
  
     Bu sınıf uyguladığından <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>, etkinleştirebilir **Ekle parçacığı** komutunu <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi. Komut etkinleştirmeden önce bu yöntem bir Otomasyon işlevinde çünkü çağrılmakta değil olduğunu denetleyin zaman **Ekle parçacığı** komutu tıklandığında, kod parçacığında Seçici kullanıcı arabirimi (UI) görüntülenir.  
  
     [!code-csharp[VSSDKCompletionTest#25](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_4.cs)]
     [!code-vb[VSSDKCompletionTest#25](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_4.vb)]  
  
2.  Oluşturun ve projeyi çalıştırın. Deneysel örneği .zzz dosya adı uzantısına sahip bir dosyayı açın ve sonra her yerden içinde sağ tıklatın. **Ekle parçacığı** komutu, kısayol menüsünde görünmelidir.  
  
## <a name="implementing-snippet-expansion-in-the-snippet-picker-ui"></a>Kod parçacığında genişletme parçacığı Seçici kullanıcı arabirimini uygulama  
 Bu bölümde, böylece parçacığı Seçici UI kod parçacığını genişletme uygulamak gösterilmektedir ne zaman görüntülenen **Ekle parçacığı** kısayol menüsünde tıklattınız. Bir kullanıcı kod parçacığını kısayol türleri ve ardından SEKME tuşuna bastığında bir kod parçacığı da genişletilir.  
  
 UI parçacığı Seçici görüntülemek ve gezinti ve sonrası ekleme parçacığı kabulünü etkinleştirmek için kullanın <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemi. Ekleme tarafından işlenen <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A> yöntemi.  
  
 Eski kod parçacığını genişletme uyarlamasını kullanan <xref:Microsoft.VisualStudio.TextManager.Interop> arabirimleri. Eski kod geçerli Düzenleyici sınıflardan Çevir olduğunda eski arabirimleri metin arabellekte konumları belirtmek için satır numaralarını ve sütun numaraları oluşan bir bileşim kullanmanız unutmayın, ancak geçerli sınıfları bir dizin kullanın. Bu nedenle, her birinin on karakter olan üç satır (artı 1 karakter olarak sayılır bir satır başı karakteri) bir arabellek sahiptir, üçüncü satır dördüncü karakteri geçerli 27 konumunda, ancak satırında 2, 3 eski uygulamasında getirin.  
  
#### <a name="to-implement-snippet-expansion"></a>Kod parçacığında genişletme uygulamak için  
  
1.  İçeren dosyasının `TestCompletionCommandHandler` sınıfında, aşağıdaki ekleyin `using` deyimleri.  
  
     [!code-csharp[VSSDKCompletionTest#26](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_5.cs)]
     [!code-vb[VSSDKCompletionTest#26](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_5.vb)]  
  
2.  Olun `TestCompletionCommandHandler` sınıfı uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient> arabirimi.  
  
     [!code-csharp[VSSDKCompletionTest#27](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_6.cs)]
     [!code-vb[VSSDKCompletionTest#27](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_6.vb)]  
  
3.  İçinde `TestCompletionCommandHandlerProvider` sınıfı, alma <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>.  
  
     [!code-csharp[VSSDKCompletionTest#28](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_7.cs)]
     [!code-vb[VSSDKCompletionTest#28](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_7.vb)]  
  
4.  Kod genişletme arabirimleri için bazı özel alanlar ekleyin ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.  
  
     [!code-csharp[VSSDKCompletionTest#29](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_8.cs)]
     [!code-vb[VSSDKCompletionTest#29](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_8.vb)]  
  
5.  Oluşturucusunun içinde `TestCompletionCommandHandler` sınıfında, aşağıdaki alanları ayarlayın.  
  
     [!code-csharp[VSSDKCompletionTest#30](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_9.cs)]
     [!code-vb[VSSDKCompletionTest#30](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_9.vb)]  
  
6.  Kullanıcı tıklattığında parçacığı Seçici görüntülenecek **Ekle parçacığı** komutu, aşağıdaki kodu ekleyin <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemi. (Bu açıklama daha okunabilir hale getirmek için ifade tamamlama için kullanılan Exec() kodu görüntülenmez; kod bloklarını varolan bir yöntemi için bunun yerine, eklenir.) Bir karakterin denetleyen koddan sonra aşağıdaki kod bloğunu ekleyin.  
  
     [!code-csharp[VSSDKCompletionTest#31](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_10.cs)]
     [!code-vb[VSSDKCompletionTest#31](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_10.vb)]  
  
7.  Parçacık gittiğinizde alanı varsa, genişletme açıkça kabul edilinceye kadar genişletme oturumu açık tutulur; kod parçacığını hiçbir alan varsa, oturumu kapatılır ve olarak döndürülür `null` tarafından <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionManager.InvokeInsertionUI%2A> yöntemi. İçinde <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemi, önceki adımda eklediğiniz UI kod parçacığı Seçici sonra (kullanıcı sekme veya üst karakter + sekme parçacığı ekleme sonra bastığında) parçacığı Gezinti işlemek için aşağıdaki kodu ekleyin.  
  
     [!code-csharp[VSSDKCompletionTest#32](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_11.cs)]
     [!code-vb[VSSDKCompletionTest#32](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_11.vb)]  
  
8.  Kullanıcı karşılık gelen kısayol türleri ve ardından SEKME tuşuna bastığında kod parçacığını eklemek için kodu ekleyin <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemi. Kod parçacığını ekler özel yöntem bir sonraki adımda gösterilir. Önceki adımda eklediğiniz Gezinti koddan sonra aşağıdaki kodu ekleyin.  
  
     [!code-csharp[VSSDKCompletionTest#33](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_12.cs)]
     [!code-vb[VSSDKCompletionTest#33](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_12.vb)]  
  
9. Yöntemleri uygulamak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient> arabirimi. Bu uygulama, ilgi yalnızca yöntemlerdir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.EndExpansion%2A> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A>. Diğer yöntemleri yalnızca döndürmelidir <xref:Microsoft.VisualStudio.VSConstants.S_OK>.  
  
     [!code-csharp[VSSDKCompletionTest#34](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_13.cs)]
     [!code-vb[VSSDKCompletionTest#34](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_13.vb)]  
  
10. Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A> yöntemi. Gerçekte genişletmeler ekler yardımcı yöntemi, bir sonraki adımda ele alınacaktır. <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> Elde edebilirsiniz, satır ve sütun bilgileri sağlayan <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.  
  
     [!code-csharp[VSSDKCompletionTest#35](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_14.cs)]
     [!code-vb[VSSDKCompletionTest#35](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_14.vb)]  
  
11. Aşağıdaki özel yöntem kısayol veya başlık ve yol tabanlı bir kod parçacığı ekler. Daha sonra çağırır <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansion.InsertNamedExpansion%2A> kod parçacığını yöntemiyle.  
  
     [!code-csharp[VSSDKCompletionTest#36](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_15.cs)]
     [!code-vb[VSSDKCompletionTest#36](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_15.vb)]  
  
## <a name="building-and-testing-code-snippet-expansion"></a>Derleme ve kod parçacığını genişletme test etme  
 Projenizde parçacığı genişletme çalışır olup olmadığını sınayabilirsiniz.  
  
1.  Çözümü oluşturun. Bu proje Hata Ayıklayıcısı'ndaki çalıştırdığınızda, Visual Studio ikinci bir örneğini örneği.  
  
2.  Bir metin dosyasını açın ve bir metin yazın.  
  
3.  Herhangi bir yerde metnin sağ tıklayın ve ardından **Ekle parçacığı**.  
  
4.  UI bildiren bir açılır pencere ile görünmelidir parçacığı Seçici **Test değiştirme alanları**. Açılır pencere çift tıklayın.  
  
     Aşağıdaki kod parçacığında eklenen.  
  
    ```  
    MessageBox.Show("first");  
    MessageBox.Show("second");  
    ```  
  
     ENTER veya ESC tuşuna basmayın.  
  
5.  SEKME ve üst karakter + sekme geçiş yapmak için basın "ilk" ve "ikinci" arasında.  
  
6.  Ekleme ENTER veya ESC tuşuna basarak kabul edin.  
  
7.  Metni farklı bir parçası, "test" yazın ve sonra SEKME tuşuna basın. "Test" kod parçacığını kısayol olduğundan, kod parçacığını yeniden eklenmesi.  
  
## <a name="next-steps"></a>Sonraki Adımlar