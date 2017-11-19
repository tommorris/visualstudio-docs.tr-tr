---
title: "Bir Windows oluşturma Forms araç kutusu denetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- winforms
- toolbox
- windows forms
ms.assetid: 0be6ffc1-8afd-4d02-9a5d-e27dde05fde6
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ca8795ba56833282bac600db79ba33da70aa6c3a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-a-windows-forms-toolbox-control"></a>Windows Forms araç kutusu denetimi oluşturma
Visual Studio genişletilebilirlik Araçları (VS SDK) dahil Windows Forms araç kutusu denetimi öğe şablonu, otomatik olarak eklenen bir denetim oluşturmanıza olanak tanır **araç** uzantısı yüklü olduğunda. Bu konu, şablon diğer kullanıcılara dağıtabilirsiniz basit bir sayaç denetimi oluşturmak için nasıl kullanılacağını gösterir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Visual Studio 2015'ten başlayarak, Visual Studio SDK'sını İndirme Merkezi'nden yüklemeyin. Visual Studio kurulumunda bir isteğe bağlı bir özellik olarak eklenmiştir. VS SDK'yı daha sonra da yükleyebilirsiniz. Daha fazla bilgi için bkz: [Visual Studio SDK'sını yükleme](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-windows-forms-toolbox-control"></a>Windows Forms araç kutusu denetimi oluşturma  
 Windows Forms araç kutusu denetim şablonu tanımsız kullanıcı denetimi oluşturur ve tüm denetime eklemek için gerekli işlevselliği sağlar **araç**.  
  
#### <a name="create-an-extension-with-a-windows-forms-toolbox-control"></a>Uzantı ile Windows Forms araç kutusu denetimi oluşturma  
  
1.  Adlı VSIX proje oluşturma `MyWinFormsControl`. VSIX proje şablonu bulabilirsiniz **yeni proje** altında iletişim **Visual C# / genişletilebilirlik**.  
  
2.  Proje açıldığında eklemek bir **Windows Forms araç kutusu denetimi** öğesi şablonuna `Counter`. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Ekle / yeni öğe**. İçinde **Yeni Öğe Ekle** iletişim kutusunda, Git **Visual C# / genişletilebilirlik** seçip **Windows Forms araç kutusu denetimi**  
  
3.  Bu bir kullanıcı denetimi ekler bir `ProvideToolboxControlAttribute` <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute> denetiminde yerleştirmek için **araç**ve bir **Microsoft.VisualStudio.ToolboxControl** dağıtımı için VSIX bildiriminde varlık girişi.  
  
### <a name="building-a-user-interface-for-the-control"></a>Denetim için bir kullanıcı arabirimi oluşturma  
 `Counter` Denetim gerektiren iki alt denetimleri: bir <xref:System.Windows.Forms.Label> geçerli sayısını görüntülemek için ve bir <xref:System.Windows.Forms.Button> sayısı 0 olarak sıfırlanır. Başka bir alt denetimleri gerekli olduğu arayanlar sayacı programlı olarak artırır.  
  
##### <a name="to-build-the-user-interface"></a>Kullanıcı arabirimini oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, Counter.cs Tasarımcısı'nda açmak için çift tıklayın.  
  
2.  "Buraya tıklayın!" Kaldır **Düğme** , varsayılan olarak eklenir, Windows Forms araç kutusu denetimi öğe şablonu ekleyin.  
  
3.  Gelen **araç**, sürükleyin bir `Label` denetim ve ardından bir `Button` tasarım yüzeyine altındaki denetimine.  
  
4.  150 genel kullanıcı denetimine yeniden boyutlandırmak, 50 piksel ve yeniden boyutlandırma düğme denetimi 50'ye 20 piksel.  
  
5.  İçinde **özellikleri** penceresindeki tasarım yüzeyine denetimleri için aşağıdaki değerleri ayarlayın.  
  
    |Denetim|Özellik|Değer|  
    |-------------|--------------|-----------|  
    |`Label1`|**Metin**|""|  
    |`Button1`|**Ad**|btnReset|  
    |`Button1`|**Metin**|Sıfırla|  
  
### <a name="coding-the-user-control"></a>Kullanıcı denetiminin kodlama  
 `Counter` Denetim kullanıma sunmak sayaç artırılır her oluşturulması için bir olay sayaç artırmak için bir yöntem bir `Reset` düğmesi ve geçerli sayısı, görüntülenecek metni ve Göster veya gizle depolamakiçinüçözellik`Reset`düğmesi. `ProvideToolboxControl` Özniteliği belirler where **araç** `Counter` denetim görünecektir.  
  
##### <a name="to-code-the-user-control"></a>Kod kullanıcı denetimi  
  
1.  Formun kendi yük olay işleyicisi kod penceresinde açmak için çift tıklayın.  
  
2.  Olay işleyicisi yöntemi denetimi sınıfta sayaç değeri ve aşağıdaki örnekte gösterildiği gibi görüntülenecek metni depolamak için bir dize depolamak üzere bir tamsayı oluşturun.  
  
    ```csharp  
    int currentValue;  
    string displayText;  
    ```  
  
3.  Aşağıdaki genel özellik bildirimlerini oluşturun.  
  
    ```csharp  
    public int Value {  
        get { return currentValue; }   
    }  
  
    public string Message {  
        get { return displayText; }  
        set { displayText = value; }  
    }  
  
    public bool ShowReset {  
        get { return btnReset.Visible; }  
        set { btnReset.Visible = value; }  
    }  
  
    ```  
  
     Arayanlar almak ve sayacın görüntülenecek metni ayarlamak için ve göstermek veya gizlemek için bu özellikleri erişebilir `Reset` düğmesi. Arayanlar salt okunur geçerli değeri elde edebilirsiniz `Value` özelliği, ancak bunlar değeri ayarlayamıyor doğrudan.  
  
4.  Aşağıdaki kod koyun `Load` denetimi için olay.  
  
    ```csharp  
    private void Counter_Load(object sender, EventArgs e)  
    {  
        currentValue = 0;  
        label1.Text = Message + Value;  
    }  
  
    ```  
  
     Ayarı **etiket** metinde <xref:System.Windows.Forms.UserControl.Load> olay değerlerine uygulanmadan önce yüklemek hedef özellikleri sağlar. Ayarı **etiket** Oluşturucusu metinde boş bir sonuçlanacak **etiket**.  
  
5.  Sayaç artırmak için aşağıdaki genel yöntem oluşturun.  
  
    ```csharp  
    public void Increment()  
    {  
        currentValue++;  
        label1.Text = displayText + Value;  
        Incremented(this, EventArgs.Empty);  
    }  
  
    ```  
  
6.  İçin bir bildirim eklemek `Incremented` olaya control sınıfı.  
  
    ```csharp  
    public event EventHandler Incremented;  
    ```  
  
     Arayanlar sayacın değeri değişikliklere yanıt vermesi için bu olay işleyicileri ekleyebilirsiniz.  
  
7.  Çift tıklayın ve Tasarım görünümü dön `Reset` oluşturmak için düğmesini `btnReset_Click` olay işleyicisi ve aşağıdaki örnekte gösterildiği gibi buna doldurun.  
  
    ```csharp  
    private void btnReset_Click(object sender, EventArgs e)  
    {  
        currentValue = 0;  
        label1.Text = displayText + Value;  
    }  
  
    ```  
  
8.  Sınıf tanımı üzerinde hemen içinde `ProvideToolboxControl` öznitelik bildirimi, ilk parametreyi değerini değiştirme `"MyWinFormsControl.Counter"` için `"General"`. Bu denetimde barındıracak öğesi grubu adını ayarlar **araç**.  
  
     Aşağıdaki örnekte gösterildiği `ProvideToolboxControl` özniteliği ve ayarlanmış sınıf tanımı.  
  
    ```csharp  
    [ProvideToolboxControl("General", false)]  
    public partial class Counter : UserControl  
    ```  
  
### <a name="testing-the-control"></a>Denetim test etme  
 Test etmek için bir **araç** denetlemek, önce geliştirme ortamında test ve derlenen bir uygulama olarak test etme.  
  
##### <a name="to-test-the-control"></a>Denetimi sınamak için  
  
1.  F5 tuşuna basın.  
  
     Bu projeyi oluşturur ve yüklü denetiminin Visual Studio ikinci Deneysel bir örneğini açar.  
  
2.  Visual Studio'nun deneysel örneği oluşturma bir **Windows Forms uygulaması** projesi.  
  
3.  İçinde **Çözüm Gezgini**, Form1.cs'i zaten açık değilse Tasarımcısı'nda açmak için çift tıklayın.  
  
4.  İçinde **araç**, `Counter` denetim görüntülenmesi **genel** bölümü.  
  
5.  Sürükleme bir `Counter` formunuza denetlemek ve seçin. `Value`, `Message`, Ve `ShowReset` özellikleri görüntülenir **özellikleri** kaynağından devralındı özelliklerle birlikte penceresi <xref:System.Windows.Forms.UserControl>.  
  
6.  Ayarlama `Message` özelliğine `Count:`.  
  
7.  Sürükleme bir <xref:System.Windows.Forms.Button> forma denetim ve düğme adını ve metin özelliklerini ayarlamak `Test`.  
  
8.  Kod görünümünde Form1.cs açmak ve bir click işleyicisi oluşturmak için düğmeye çift tıklayın.  
  
9. Click işleyicisi çağrı `counter1.Increment()`.  
  
10. Çağrısından sonra Oluşturucusu işlevinde `InitializeComponent`, türü `counter1``.``Incremented +=` ve sonra SEKME tuşuna iki kez basın.  
  
     Visual Studio için bir form düzeyinde işleyici oluşturur `counter1.Incremented` olay.  
  
11. Vurgula `Throw` olay işleyicisinin türü deyiminde `mbox`, sonra iki kez mbox kod parçacığını bir ileti kutusu üretmek için SEKME tuşuna basın.  
  
12. Sonraki satırında, aşağıdaki ekleyin `if` / `else` görünürlüğünü ayarlamak için blok `Reset` düğmesi.  
  
    ```csharp  
    if (counter1.Value < 5) counter1.ShowReset = false;  
    else counter1.ShowReset = true;  
    ```  
  
13. F5 tuşuna basın.  
  
     Form açılır. `Counter` Denetimi, aşağıdaki metni görüntüler.  
  
     **Sayı: 0**  
  
14. Tıklatın **Test**.  
  
     Sayaç artırır ve Visual Studio, bir ileti kutusu görüntüler.  
  
15. İleti kutusunu kapatın.  
  
     **Sıfırlama** düğme kaybolur.  
  
16. Tıklatın **Test** sayaç ulaşana kadar **5** iletiyi kapattıktan kutuları her zaman.  
  
     **Sıfırlama** düğmesini yeniden görüntülenir.  
  
17. Tıklatın **sıfırlama**.  
  
     Sayaç sıfırlanır için **0**.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Oluşturduğunuzda bir **araç** denetimi, Visual Studio adlı bir dosya oluşturur *ProjectName*projenizin \bin\debug\ klasöründeki .vsix. Bir ağ veya Web sitesine .vsix dosyasını karşıya yükleyerek denetimi dağıtabilirsiniz. .Vsix dosyasını bir kullanıcı oturum açtığında, Denetim yüklenir ve Visual Studio eklenen **araç** kullanıcının bilgisayarında. Alternatif olarak, .vsix dosyasını karşıya yükleyebilir [Visual Studio Galerisi](http://go.microsoft.com/fwlink/?LinkID=123847) Web sitesi kullanıcıların göz atarak bulabileceğiniz **Araçlar / uzantısı ve güncelleştirmeleri** iletişim.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio diğer bölümleri genişletme](../extensibility/extending-other-parts-of-visual-studio.md)   
 [WPF araç kutusu denetimi oluşturma](../extensibility/creating-a-wpf-toolbox-control.md)   
 [Visual Studio diğer bölümleri genişletme](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Windows Forms denetimi geliştirmenin esasları](/dotnet/framework/winforms/controls/windows-forms-control-development-basics)