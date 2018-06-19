---
title: "İzlenecek yol: Görselleştirici C# ' de yazma | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
helpviewer_keywords:
- visualizers, writing
- walkthroughs [Visual Studio], visualizers
ms.assetid: 53467461-8e0f-45ee-9bc4-374bbaeaf00f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 490c2c2b15eff701cee751b57bbf55024910beab
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479844"
---
# <a name="walkthrough-writing-a-visualizer-in-c"></a>İzlenecek Yol: C# ile Görselleştirici Yazma #
Bu kılavuz, C# kullanarak basit Görselleştirici yazma gösterilmektedir. Bu kılavuzda oluşturacak Görselleştirici bir Windows forms ileti kutusu kullanarak bir dize içeriğini görüntüler. Bu basit bir dize Görselleştirici kendisini özellikle yararlı değildir, ancak diğer veri türleri için daha kullanışlı görselleştiriciler oluşturmak için izlemeniz gereken temel adımlarda gösterir.  
  
> [!NOTE]
>  İletişim kutuları ve menü komutlarını gördüğünüz açıklanana Yardım'da etkin ayarlarınıza veya sürümünüze bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için Git **Araçları** menü ve **içeri ve dışarı aktarma ayarları**. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
 Hata ayıklayıcı tarafından okunacak bir DLL Görselleştirici kod yerleştirilmelidir. Bu nedenle, ilk adım bir sınıf kitaplığı proje için DLL oluşturmaktır.  

## <a name="create-a-visualizer-manually"></a>Görselleştirici el ile oluşturma

Görselleştirici oluşturmak için aşağıdaki görevleri izleyin.
  
#### <a name="to-create-a-class-library-project"></a>Bir sınıf kitaplığı proje oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni > Proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **Visual C#** seçin **.NET standart**.  
  
3.  Orta bölmede seçin **sınıf kitaplığı**.  
  
4.  İçinde **adı** MyFirstVisualizer gibi bir sınıf kitaplığı için uygun bir ad yazın.  
  
5.  **Tamam**'ı tıklatın.  
  
 Sınıf kitaplığı oluşturduktan sonra tanımlanan sınıflar var. kullanabilmesi için Microsoft.VisualStudio.DebuggerVisualizers.DLL bir başvuru eklemeniz gerekir. Ancak, başvuru eklemeden önce böylece anlamlı adlara sahip bazı sınıfları yeniden adlandırmanız gerekir.  
  
#### <a name="to-rename-class1cs-and-add-microsoftvisualstudiodebuggervisualizers"></a>Class1.cs yeniden adlandırın ve Microsoft.VisualStudio.DebuggerVisualizers eklemek için  
  
1.  İçinde **Çözüm Gezgini**Class1.cs sağ tıklatın ve seçin **yeniden adlandırma** kısayol menüsünde.  
  
2.  Ad Class1.cs DebuggerSide.cs gibi anlamlı bir şey değiştirin.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik olarak yeni dosya adı ile eşleşmesi için DebuggerSide.cs sınıfı bildiriminde değiştirir.  
  
3.  İçinde **Çözüm Gezgini**, sağ **başvuruları** ve **Başvuru Ekle** kısayol menüsünde.  
  
4.  İçinde **Başvuru Ekle** iletişim kutusundaki **.NET** sekmesinde, Microsoft.VisualStudio.DebuggerVisualizers.DLL seçin.  
  
5.  **Tamam**'ı tıklatın.  
  
6.  Şu deyimi DebuggerSide.cs içinde eklemek `using` deyimleri:  
  
    ```csharp  
    using Microsoft.VisualStudio.DebuggerVisualizers;  
    ```  
  
 Şimdi hata ayıklayıcı tarafı kodlar oluşturmak hazır olursunuz. Görselleştirmek için istediğiniz bilgileri görüntülemek için hata ayıklayıcı içinde çalışan bir kod budur. Bildirimi değiştirmek zorunda ilk olarak, `DebuggerSide` , taban sınıfından devralıyor şekilde nesne `DialogDebuggerVisualizer`.  
  
#### <a name="to-inherit-from-dialogdebuggervisualizer"></a>DialogDebuggerVisualizer devralacak şekilde  
  
1.  DebuggerSide.cs içinde aşağıdaki kod satırına gidin:  
  
    ```csharp  
    public class DebuggerSide  
    ```  
  
2.  Kodla değiştirin:  
  
    ```csharp  
    public class DebuggerSide : DialogDebuggerVisualizer  
    ```  
  
 `DialogDebuggerVisualizer` bir Özet yöntem vardır (`Show`), geçersiz kılmanız gerekir.  
  
#### <a name="to-override-the-dialogdebuggervisualizershow-method"></a>DialogDebuggerVisualizer.Show yöntemi geçersiz kılmak için  
  
-   İçinde `public class DebuggerSide`, aşağıdakileri ekleyin **yöntemi:**  
  
    ```csharp  
    protected override void Show(IDialogVisualizerService windowService, IVisualizerObjectProvider objectProvider)  
    {  
    }  
    ```  
  
 `Show` Yöntemi gerçekten görselleştiricisi iletişim kutusu veya diğer kullanıcı arabirimi oluşturan ve Görselleştirici Hata Ayıklayıcı'dan geçirilen bilgilerini görüntüler kodunu içerir. İletişim kutusu oluşturur ve bilgileri görüntüleyen kodu eklemeniz gerekir. Bu kılavuzda, bir Windows forms ileti kutusu kullanarak bunu. İlk olarak, bir başvuru eklemeniz gerekir ve `using` System.Windows.Forms bildirimi.  
  
#### <a name="to-add-systemwindowsforms"></a>System.Windows.Forms eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **başvuruları** ve **Başvuru Ekle** kısayol menüsünde.  
  
2.  İçinde **Başvuru Ekle** iletişim kutusundaki **.NET** sekmesinde, System.Windows.Forms.DLL seçin.  
  
3.  **Tamam**'ı tıklatın.  
  
4.  Şu deyimi DebuggerSide.cs içinde eklemek `using` deyimleri:  
  
    ```csharp  
    using System.Windows.Forms;  
    ```  
  
 Şimdi, oluşturup, Görselleştirici için kullanıcı arabirimini göstermek için bazı kod ekleyeceksiniz. Bu, ilk Görselleştirici olduğundan, biz kullanıcı arabirimini basit tutmak ve bir ileti kutusu kullanın.  
  
#### <a name="to-show-the-visualizer-output-in-a-dialog-box"></a>Görselleştirici çıktı iletişim kutusunda göstermek için  
  
1.  İçinde `Show` yöntemi, aşağıdaki kod satırını ekleyin:  
  
    ```csharp  
    MessageBox.Show(objectProvider.GetObject().ToString());  
    ```  
  
     Bu örnek kodu, hata işleme içermez. Hata işleme gerçek Görselleştirici veya herhangi bir uygulama türünün içermelidir.  
  
2.  Üzerinde **yapı** menüsünde seçin **yapı MyFirstVisualizer**. Proje başarıyla oluşturması gerekir. Devam etmeden önce yapı hataları düzeltin.  
  
 Hata ayıklayıcı tarafı kodu sonuna olmasıdır. Ancak bir adım daha vardır; sınıfları hangi koleksiyonu ayıklayıcı yan söyler öznitelik Görselleştirici oluşur.  
  
#### <a name="to-add-the-debuggee-side-code"></a>Ayıklayıcı tarafı kodu eklemek için  
  
1.  DebuggerSide.cs için aşağıdaki öznitelik kodu ekleyin `using` deyimleri önce `namespace MyFirstVisualizer`:  
  
    ```csharp  
    [assembly:System.Diagnostics.DebuggerVisualizer(  
    typeof(MyFirstVisualizer.DebuggerSide),  
    typeof(VisualizerObjectSource),  
    Target = typeof(System.String),  
    Description = "My First Visualizer")]  
    ```  
  
2.  Üzerinde **yapı** menüsünde seçin **yapı MyFirstVisualizer**. Proje başarıyla oluşturması gerekir. Devam etmeden önce yapı hataları düzeltin.  
  
 Bu noktada, ilk Görselleştirici tamamlanmış olur. Doğru adımları tamamladıysanız, Görselleştirici oluşturun ve içine yüklemek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Görselleştirici içine yüklemeden önce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ancak, doğru şekilde çalıştığından emin olmak için test etmeniz gerekir. Görselleştirici içine yüklemeden çalıştırmak için bir test bandı şimdi oluşturacak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
#### <a name="to-add-a-test-method-to-show-the-visualizer"></a>Görselleştirici göstermek için bir Test yöntemi eklemek için  
  
1.  Sınıfına aşağıdaki yöntemi ekleyin `public DebuggerSide`:  
  
    ```csharp  
    public static void TestShowVisualizer(object objectToVisualize)  
    {  
       VisualizerDevelopmentHost visualizerHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));  
       visualizerHost.ShowVisualizer();  
    }  
    ```  
  
2.  Üzerinde **yapı** menüsünde seçin **yapı MyFirstVisualizer**. Proje başarıyla oluşturması gerekir. Devam etmeden önce yapı hataları düzeltin.  
  
 Ardından, sizin Görselleştirici DLL çağırmak için yürütülebilir bir proje oluşturmanız gerekir. Kolaylık olması için bir konsol uygulama projesi kullanacağız.  
  
#### <a name="to-add-a-console-application-project-to-the-solution"></a>Bir konsol uygulama projesi çözüme eklemek için  
  
1.  Üzerinde **dosya** menüsünde seçin **Ekle** ve ardından **yeni proje**.  
  
2.  İçinde **Yeni Proje Ekle** iletişim kutusunda **şablonları** kutusunda, seçin **konsol uygulaması**.  
  
3.  İçinde **adı** kutusunda, konsol uygulaması için anlamlı bir ad yazın `MyTestConsole`.  
  
4.  **Tamam**'ı tıklatın.  
  
 Şimdi, MyTestConsole MyFirstVisualizer çağırması gerekli başvuran eklemeniz gerekir.  
  
#### <a name="to-add-necessary-references-to-mytestconsole"></a>Gerekli MyTestConsole eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **MyTestConsole** ve **Başvuru Ekle** kısayol menüsünde.  
  
2.  İçinde **Başvuru Ekle** iletişim kutusu, **.NET** sekmesinde, Microsoft.VisualStudio.DebuggerVisualizers.DLL seçin.  
  
3.  **Tamam**'ı tıklatın.  
  
4.  Sağ **MyTestConsole** ve **Başvuru Ekle** yeniden.  
  
5.  İçinde **Başvuru Ekle** iletişim kutusu, tıklatın **projeleri** sekmesine ve ardından MyFirstVisualizer tıklayın.  
  
6.  **Tamam**'ı tıklatın.  
  
 Şimdi, test bandı sonlandırmak için kod ekleyeceksiniz.  
  
#### <a name="to-add-code-to-mytestconsole"></a>Kod için MyTestConsole eklemek için  
  
1.  İçinde **Çözüm Gezgini**, Program.cs sağ tıklatın ve seçin **yeniden adlandırma** kısayol menüsünde.  
  
2.  Program.cs adından TestConsole.cs gibi daha anlamlı bir şey düzenleyin.  
  
     **Not** [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik olarak yeni dosya adı ile eşleşmesi için TestConsole.cs sınıfı bildiriminde değiştirir.  
  
3.  Aşağıdaki kodu TestConsole.cs içinde eklemek `using` deyimleri:  
  
    ```csharp  
    using MyFirstVisualizer;  
    ```  
  
4.  Yönteminde `Main`, aşağıdaki kodu ekleyin:  
  
    ```csharp  
    String myString = "Hello, World";  
    DebuggerSide.TestShowVisualizer(myString);  
    ```  
  
 Şimdi, ilk Görselleştirici test etmek hazırsınız.  
  
#### <a name="to-test-the-visualizer"></a>Görselleştirici sınamak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **MyTestConsole** ve **başlangıç projesi olarak ayarla** kısayol menüsünde.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Başlat**.  
  
     Konsol uygulaması başlatır ve Görselleştirici görünür ve "Hello, World" dizesi görüntüler  
  
 Tebrikler. Yalnızca yerleşik sahip ve ilk Görselleştirici test.  
  
 Görselleştirici kullanmak istiyorsanız, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yalnızca, test bandı çağırmak yerine, bunu yüklemeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Görselleştiriciyi yükleme](../debugger/how-to-install-a-visualizer.md).  
  
## <a name="create-a-visualizer-using-the-visualizer-item-template"></a>Görselleştirici öğesi şablonu kullanarak Görselleştirici oluşturma  
 Şu ana kadar bu kılavuzda Görselleştirici el ile oluşturmak nasıl göstermiştir. Bu bir öğrenme alıştırma olarak gerçekleştirilir. Basit Görselleştirici nasıl çalıştığını bildiğinize göre oluşturmak için daha kolay bir yolu yoktur: Görselleştirici öğesi şablonu kullanarak.  
  
 İlk olarak, yeni bir sınıf kitaplığı projesi oluşturmanız gerekir.  
  
#### <a name="to-create-a-new-class-library"></a>Yeni bir sınıf kitaplığı oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni > Proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **Visual C#** seçin **.NET standart**.  
  
3.  Orta bölmede seçin **sınıf kitaplığı**.   
  
4.  İçinde **adı** MySecondVisualizer gibi bir sınıf kitaplığı için uygun bir ad yazın.  
  
5.  **Tamam**'ı tıklatın.  
  
 Şimdi, ona bir Görselleştirici öğesi ekleyebilirsiniz:  
  
#### <a name="to-add-a-visualizer-item"></a>Görselleştirici öğesi eklemek için  
  
1.  İçinde **Çözüm Gezgini**, MySecondVisualizer sağ tıklayın.  
  
2.  Kısayol menüsünden seçin **Ekle** ve ardından **yeni öğe**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Visual C# öğeleri**seçin **hata ayıklayıcı Görselleştirici**.  
  
4.  İçinde **adı** SecondVisualizer.cs gibi uygun bir ad yazın.  
  
5.  **Ekle**'yi tıklatın.  
  
 Tüm İşte bu kadar olmasıdır. Dosyaya SecondVisualizer.cs bakması ve şablonu eklediğiniz kodunu görüntüleyin. Bir tane kodu deneyebilirsiniz. Temellerini artık bildiğinize göre yolda olan daha karmaşık ve yararlı görselleştiriciler kendi oluşturma.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görselleştirici mimarisi](../debugger/visualizer-architecture.md)   
 [Nasıl yapılır: Görselleştiriciyi yükleme](../debugger/how-to-install-a-visualizer.md)   
 [Özel Görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md)
