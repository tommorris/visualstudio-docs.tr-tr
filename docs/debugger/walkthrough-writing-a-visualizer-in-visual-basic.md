---
title: "İzlenecek yol: Visual Basic'de Görselleştirici yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, writing
- walkthroughs [Visual Studio], visualizers
ms.assetid: c93bf5a1-3e5e-422f-894e-bd72c9bc1b57
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc15612fe7a59516483bb6b077e1b44b44f7fba8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-writing-a-visualizer-in-visual-basic"></a>İzlenecek Yol: Visual Basic'de Görselleştirici Yazma
Bu kılavuzu kullanarak basit Görselleştirici yazma gösterilmektedir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. Bu kılavuzda oluşturacak Görselleştirici bir Windows Forms ileti kutusu kullanarak bir dize içeriğini görüntüler. Bu basit bir dize Görselleştirici nasıl görselleştiriciler diğer veri türleri için daha uygun projelerinize oluşturabilirsiniz göstermek için basit bir örnektir.  
  
> [!NOTE]
>  İletişim kutuları ve menü komutlarını gördüğünüz açıklanana Yardım'da etkin ayarlarınıza veya sürümünüze bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için Git **Araçları** menü ve **içeri ve dışarı aktarma** . Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
 Hata ayıklayıcı tarafından okunan DLL Görselleştirici kod yerleştirilmelidir. İlk adım, DLL için bir sınıf kitaplığı proje oluşturmaktır.  
  
## <a name="create-and-prepare-a-class-library-project"></a>Oluşturma ve bir sınıf kitaplığı proje hazırlama  
  
#### <a name="to-create-a-class-library-project"></a>Bir sınıf kitaplığı proje oluşturmak için  
  
1.  Üzerinde **dosya** menüsünde seçin **yeni** tıklatıp **yeni proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **proje türü**s, tıklatın **Visual Basic**.  
  
3.  İçinde **şablonları** kutusunda, **sınıf kitaplığı**.  
  
4.  İçinde **adı** kutusunda, sınıf kitaplığı için uygun bir ad yazın **MyFirstVisualizer**.  
  
5.  **Tamam**'ı tıklatın.  
  
 Sınıf kitaplığı oluşturduğunuzda, tanımlanan sınıflar var. kullanabilmesi için Microsoft.VisualStudio.DebuggerVisualizers.DLL, bir başvuru eklemeniz gerekir. İlk olarak, Bununla birlikte, projenizin anlamlı bir ad verin.  
  
#### <a name="to-rename-class1vb-and-add-microsoftvisualstudiodebuggervisualizers"></a>Class1.vb'ye yeniden adlandırın ve Microsoft.VisualStudio.DebuggerVisualizers eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **Class1.vb'ye**ve kısayol menüsünde **yeniden adlandırma**.  
  
2.  Ad Class1.vb'ye DebuggerSide.vb gibi anlamlı bir şey değiştirin.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]otomatik olarak yeni dosya adı ile eşleşmesi için DebuggerSide.vb sınıfı bildiriminde değiştirir.  
  
3.  İçinde **Çözüm Gezgini**, sağ **My ilk Görselleştirici**ve kısayol menüsünde **Başvuru Ekle**.  
  
4.  İçinde **Başvuru Ekle** iletişim kutusundaki **.NET** sekmesinde, Microsoft.VisualStudio.DebuggerVisualizers.DLL tıklayın.  
  
5.  **Tamam**'ı tıklatın.  
  
6.  Şu deyimi DebuggerSide.vb içinde eklemek `Imports` deyimleri:  
  
    ```  
    Imports Microsoft.VisualStudio.DebuggerVisualizers  
    ```  
  
## <a name="add-the-debugger-side-code"></a>Hata ayıklayıcı tarafı kodu ekleyin  
 Şimdi, hata ayıklayıcı tarafı kodlar oluşturmak hazır olursunuz. Görselleştirmek için istediğiniz bilgileri görüntülemek için hata ayıklayıcı içinde çalışan bir kod budur. Bildirimi değiştirmek zorunda ilk olarak, `DebuggerSide` taban sınıfından devralıyor nesnesini `DialogDebuggerVisualizer`.  
  
#### <a name="to-inherit-from-dialogdebuggervisualizer"></a>DialogDebuggerVisualizer devralacak şekilde  
  
1.  DebuggerSide.vb içinde aşağıdaki kod satırına gidin:  
  
    ```  
    Public Class DebuggerSide  
    ```  
  
2.  Kod şuna benzer şekilde düzenleyin:  
  
    ```  
    Public Class DebuggerSide  
    Inherits DialogDebuggerVisualizer  
    ```  
  
 `DialogDebuggerVisualizer`bir Özet yöntem, sahip `Show`, geçersiz kılmanız gerekir.  
  
#### <a name="to-override-the-dialogdebuggervisualizershow-method"></a>DialogDebuggerVisualizer.Show yöntemi geçersiz kılmak için  
  
-   İçinde `public class DebuggerSide`, aşağıdaki yöntemi ekleyin:  
  
    ```  
    Protected Overrides Sub Show(ByVal windowService As Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService, ByVal objectProvider As Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider)  
  
        End Sub  
    ```  
  
 `Show` Yöntemi gerçekten görselleştiricisi iletişim kutusu veya diğer kullanıcı arabirimi oluşturan ve Görselleştirici Hata Ayıklayıcı'dan geçirilen bilgilerini görüntüler kodunu içerir. İletişim kutusu oluşturur ve bilgileri görüntüleyen kodu eklemeniz gerekir. Bu kılavuzda, bir Windows Forms ileti kutusu kullanarak bunu. İlk olarak, bir başvuru eklemeniz gerekir ve `Imports` bildirimi <xref:System.Windows.Forms>.  
  
#### <a name="to-add-systemwindowsforms"></a>System.Windows.Forms eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **başvuruları**ve kısayol menüsünde **Başvuru Ekle**.  
  
2.  İçinde **Başvuru Ekle** iletişim kutusundaki **.NET** sekmesini tıklatın, **System.Windows.Forms**.  
  
3.  **Tamam**'ı tıklatın.  
  
4.  Şu deyimi DebuggerSide.cs içinde eklemek `Imports` deyimleri:  
  
    ```  
    Imports System.Windows.Forms  
    ```  
  
## <a name="create-your-visualizers-user-interface"></a>Görselleştirici'nın kullanıcı arabirimi oluşturma  
 Şimdi oluşturun ve sizin Görselleştirici için kullanıcı arabirimini göstermek için bazı kod ekleyeceksiniz. Bu, ilk Görselleştirici olduğundan, kullanıcı arabirimini basit tutmak ve bir ileti kutusu kullanın.  
  
#### <a name="to-show-the-visualizer-output-in-a-dialog-box"></a>Görselleştirici çıktı iletişim kutusunda göstermek için  
  
1.  İçinde `Show` yöntemi, aşağıdaki kod satırını ekleyin:  
  
    ```  
    MessageBox.Show(objectProvider.GetObject().ToString())  
    ```  
  
     Bu örnek kodu, hata işleme içermez. Hata işleme gerçek Görselleştirici veya herhangi bir uygulama türünün içermelidir.  
  
2.  Üzerinde **yapı** menüsünde tıklatın **yapı MyFirstVisualizer**. Proje başarıyla oluşturması gerekir. Devam etmeden önce yapı hataları düzeltin.  
  
## <a name="add-the-necessary-attribute"></a>Gerekli öznitelik Ekle  
 Hata ayıklayıcı tarafı kodu sonuna olmasıdır. Var olan bir adım daha ancak: Görselleştirici ayıklayıcı yan sınıfları hangi koleksiyonu söyler öznitelik oluşur.  
  
#### <a name="to-add-the-debugee-side-code"></a>Debugee tarafı kodu eklemek için  
  
1.  DebuggerSide.vb için aşağıdaki öznitelik kodu ekleyin `Imports` deyimleri önce `namespace MyFirstVisualizer`:  
  
    ```  
    <Assembly: System.Diagnostics.DebuggerVisualizer(GetType(MyFirstVisualizer.DebuggerSide), GetType(VisualizerObjectSource), Target:=GetType(System.String), Description:="My First Visualizer")>  
    ```  
  
2.  Üzerinde **yapı** menüsünde tıklatın **yapı MyFirstVisualizer**. Proje başarıyla oluşturması gerekir. Devam etmeden önce yapı hataları düzeltin.  
  
## <a name="create-a-test-harness"></a>Bir Test bandı oluşturun  
 Bu noktada, ilk Görselleştirici tamamlanmış olur. Doğru adımları tamamladıysanız, Görselleştirici oluşturun ve içine yüklemek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Görselleştirici içine yüklemeden önce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ancak, doğru şekilde çalıştığından emin olmak için test etmeniz gerekir. Görselleştirici içine yüklemeden çalıştırmak için bir test bandı şimdi oluşturacak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
#### <a name="to-add-a-test-method-to-show-the-visualizer"></a>Görselleştirici göstermek için bir test yöntemi eklemek için  
  
1.  Sınıfına aşağıdaki yöntemi ekleyin `public DebuggerSide`:  
  
    ```  
    Shared Public Sub TestShowVisualizer(ByVal objectToVisualize As Object)  
        Dim visualizerHost As New VisualizerDevelopmentHost(objectToVisualize, GetType(DebuggerSide))  
    visualizerHost.ShowVisualizer()  
    End Sub  
    ```  
  
2.  Üzerinde **yapı** menüsünde tıklatın **yapı MyFirstVisualizer**. Proje başarıyla oluşturması gerekir. Devam etmeden önce yapı hataları düzeltin.  
  
 Ardından, sizin Görselleştirici DLL çağırmak için yürütülebilir bir proje oluşturmanız gerekir. Kolaylık olması için konsol uygulama projesi kullanın.  
  
#### <a name="to-add-a-console-application-project-to-the-solution"></a>Bir konsol uygulama projesi çözüme eklemek için  
  
1.  Üzerinde **dosya** menüsünde tıklatın **Ekle**ve ardından **yeni proje**.  
  
2.  İçinde **Yeni Proje Ekle** iletişim kutusunda **şablonları** kutusunda, **konsol uygulaması**.  
  
3.  İçinde **adı** kutusunda, konsol uygulaması için anlamlı bir ad yazın **MyTestConsole**.  
  
4.  **Tamam**'ı tıklatın.  
  
 Şimdi, MyTestConsole MyFirstVisualizer çağırması gerekli başvuran eklemeniz gerekir.  
  
#### <a name="to-add-necessary-references-to-mytestconsole"></a>Gerekli MyTestConsole eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **MyTestConsole**ve kısayol menüsünde **Başvuru Ekle**.  
  
2.  İçinde **Başvuru Ekle** iletişim kutusundaki **.NET** sekmesinde, Microsoft.VisualStudio.DebuggerVisualizers tıklayın.  
  
3.  **Tamam**'ı tıklatın.  
  
4.  Sağ **MyTestConsole**ve ardından **Başvuru Ekle** yeniden.  
  
5.  İçinde **Başvuru Ekle** iletişim kutusu, tıklatın **projeleri** sekmesini tıklatın ve ardından MyFirstVisualizer seçin.  
  
6.  **Tamam**'ı tıklatın.  
  
## <a name="finish-your-test-harness-and-test-your-visualizer"></a>Test bandı son ve, Görselleştirici test etme  
 Şimdi, test bandı sonlandırmak için kod ekleyeceksiniz.  
  
#### <a name="to-add-code-to-mytestconsole"></a>Kod için MyTestConsole eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **Program.vb**ve kısayol menüsünde **yeniden adlandırma**.  
  
2.  Module1.vb adından uygun bir şey gibi Düzenle **TestConsole.vb**.  
  
     Dikkat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik olarak yeni dosya adı ile eşleşmesi için TestConsole.vb sınıfı bildiriminde değiştirir.  
  
3.  TestConsole içinde. vb, aşağıdakileri ekleyin `Imports` deyimi:  
  
    ```  
    Imports MyFirstVisualizer  
    ```  
  
4.  Yönteminde `Main`, aşağıdaki kodu ekleyin:  
  
    ```  
    Dim myString As String = "Hello, World"  
    DebuggerSide.TestShowVisualizer(myString)  
    ```  
  
 Artık ilk Görselleştirici test etmek hazırsınız.  
  
#### <a name="to-test-the-visualizer"></a>Görselleştirici sınamak için  
  
1.  İçinde **Çözüm Gezgini**, sağ **MyTestConsole**, kısayol menüsünde tıklatıp **başlangıç projesi olarak ayarla**.  
  
2.  Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat**.  
  
     Konsol uygulaması başlatır. Görselleştirici görünür ve "Hello, World." dizesi görüntüler  
  
 Tebrikler. Yalnızca yerleşik sahip ve ilk Görselleştirici test.  
  
 Görselleştirici kullanmak istiyorsanız, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yalnızca, test bandı çağırmak yerine, bunu yüklemeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Görselleştiriciyi yükleme](../debugger/how-to-install-a-visualizer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görselleştirici mimarisi](../debugger/visualizer-architecture.md)   
 [Nasıl yapılır: Görselleştiriciyi yükleme](../debugger/how-to-install-a-visualizer.md)   
 [Özel Görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md)