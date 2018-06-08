---
title: "İzlenecek yol: bir Visual C# projesinde VBA'dan kod çağırmak"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel [Office development in Visual Studio], calling code from VBA
- Word [Office development in Visual Studio], calling code from VBA
- Visual C# [Office development in Visual Studio], calling code from VBA
- workbooks [Office development in Visual Studio], calling code from VBA
- VBA [Office development in Visual Studio], calling code in document-level customizations
- Office documents [Office development in Visual Studio, Visual Basic for Applications and
- calling code from VBA
- document-level customizations [Office development in Visual Studio], calling code
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e2803ef31ec1009215d4490ac527c42cbdc90571
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845484"
---
# <a name="walkthrough-call-code-from-vba-in-a-visual-c-project"></a>İzlenecek yol: bir Visual C# projesinde VBA'dan kod çağırmak
  Bu kılavuz bir yöntem bir belge düzeyi özelleştirmelerinde Microsoft Office Excel için Visual Basic for Applications (VBA) kodunu çalışma kitabı nasıl çağrılacağını gösterir. Yordam üç temel adımdan oluşur: bir yöntem ekleme `Sheet1` konak öğesi sınıfına, çalışma kitabı VBA kodunda yöntemi oluşturma ve çalışma kitabı VBA kodundan yöntemini çağırın.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Bu kılavuzda özellikle Excel kullanıyor olsa da, izlenecek yol tarafından gösterilen kavramlar Ayrıca Word için belge düzeyi projelerine uygulanabilir.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   VBA kodu içeren bir çalışma kitabı oluşturma.  
  
-   Çalışma kitabının konumuna Excel'de Güven Merkezi kullanarak güvenme.  
  
-   Bir yöntem ekleme `Sheet1` ana öğesi sınıf.  
  
-   İçin bir arayüz çıkarma `Sheet1` ana öğesi sınıf.  
  
-   VBA kodu yönteme gösterme.  
  
-   VBA kodundan yöntemi çağırma.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Excel  
  
## <a name="create-a-workbook-that-contains-vba-code"></a>VBA kodu içeren bir çalışma kitabı oluşturun  
 İlk adım, basit VBA makrosu içeren bir makro etkin bir çalışma kitabı oluşturmaktır. VBA özelleştirmelerinde kodu oluşturmadan önce çalışma kitabı zaten VBA kodu içermesi gerekir. Aksi takdirde, Visual Studio özelleştirme derlemesini çağırmak VBA kodu etkinleştirmek için VBA projesini değiştiremez.  
  
 Kullanmak istediğiniz VBA kodu içeren bir çalışma kitabı zaten varsa bu adımı atlayabilirsiniz.  
  
### <a name="to-create-a-workbook-that-contains-vba-code"></a>VBA kodu içeren bir çalışma kitabı oluşturmak için  
  
1.  Excel'i başlatın.  
  
2.  Etkin belgeyi farklı kaydet bir **etkin çalışma kitabı (\*.xlsm)** adıyla **WorkbookWithVBA**. Masaüstü gibi uygun bir konuma kaydedin.  
  
3.  Şerit'te tıklatın **Geliştirici** sekmesi.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesi görünür değilse, ilk Göster gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
4.  İçinde **kod** grubunda **Visual Basic**.  
  
     Visual Basic Düzenleyicisi'ni açar.  
  
5.  İçinde **proje** penceresinde çift **ThisWorkbook**.  
  
     İçin kod dosyası `ThisWorkbook` nesnesini açar.  
  
6.  Aşağıdaki VBA kodu kod dosyasına ekleyin. Bu kod, hiçbir şey yapmaz basit bir işlevi tanımlar. Tek amacı, bu işlevi VBA projesi çalışma kitabında var olduğundan emin olmaktır. Bu, bu kılavuzda sonraki adımlar için gereklidir.  
  
    ```vb  
    Sub EmptySub()  
    End Sub  
    ```  
  
7.  Belgeyi kaydedin ve Excel çıkın.  
  
## <a name="create-the-project"></a>Projeyi oluşturma  
 Şimdi, daha önce oluşturduğunuz makrosu etkin çalışma kitabını kullanan Excel için belge düzeyi projesi oluşturabilirsiniz.  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
3.  Şablonlar bölmesinde **Visual C#**, genişletin ve ardından **Office/SharePoint**.  
  
4.  Seçin **Office eklentileri** düğümü.  
  
5.  Proje şablonları listesinde seçin **Excel 2010 Çalışma kitabı** veya **Excel 2013 çalışma kitabı** projesi.  
  
6.  İçinde **adı** kutusuna **CallingCodeFromVBA**.  
  
7.  **Tamam**'ı tıklatın.  
  
     **Office Proje Sihirbazı için Visual Studio Araçları** açar.  
  
8.  Seçin **var olan bir belgeyi kopyalama**hem de **varolan belgenin tam yolu** kutusunda, konumu belirtin **WorkbookWithVBA** daha önce oluşturduğunuz çalışma kitabı . Kendi makrosu etkin çalışma kitabı kullanıyorsanız, bunun yerine bu çalışma kitabının konumunu belirtin.  
  
9. **Son**'a tıklayın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] açılır **WorkbookWithVBA** çalışma kitabı Tasarımcısı'nda ve ekler **CallingCodeFromVBA** için proje **Çözüm Gezgini**.  
  
## <a name="trust-the-location-of-the-workbook"></a>Çalışma kitabının konumuna güven  
 VBA kodu çalışma kitabı Çözümünüzdeki kodu oluşturmadan önce çalıştırmak için çalışma kitabını VBA güvenmesi gerekir. Bunu yapmanın birkaç yolu vardır. Bu kılavuzda, bu görevin çalışma kitabında konumunu güvenerek yapabiliriz **Güven Merkezi** Excel'de.  
  
### <a name="to-trust-the-location-of-the-workbook"></a>Çalışma kitabının konumuna güvenmek için  
  
1.  Excel'i başlatın.  
  
2.  Tıklatın **dosya** sekmesi.  
  
3.  Tıklatın **Excel Seçenekleri** düğmesi.  
  
4.  Kategoriler bölmesinde **Güven Merkezi**.  
  
5.  Ayrıntılar bölmesinde **Güven Merkezi Ayarları**.  
  
6.  Kategoriler bölmesinde **Güvenilen Konumlar**.  
  
7.  Ayrıntılar bölmesinde **yeni konum Ekle**.  
  
8.  İçinde **Microsoft Office güvenilir konum** iletişim kutusu, içeren klasöre gidin **CallingCodeFromVBA** projesi.  
  
9. Seçin **bu konumun alt klasörleri güvenilir de**.  
  
10. İçinde **Microsoft Office güvenilir konum** iletişim kutusu, tıklatın **Tamam**.  
  
11. İçinde **Güven Merkezi** iletişim kutusu, tıklatın **Tamam**.  
  
12. İçinde **Excel Seçenekleri** iletişim kutusu, tıklatın **Tamam**.  
  
13. Çıkış **Excel**.  
  
## <a name="add-a-method-to-the-sheet1-class"></a>Sheet1 sınıfına bir yöntem ekleme  
 VBA projesi kurulduğunda, ortak bir yöntem eklemek `Sheet1` ana VBA kodundan çağırabilirsiniz öğesi sınıf.  
  
### <a name="to-add-a-method-to-the-sheet1-class"></a>Sheet1 sınıfı için bir yöntem eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **Sheet1.cs**ve ardından **görünümü kodu**.  
  
     **Sheet1.cs** dosyasını Kod Düzenleyicisi'nde açar.  
  
2.  Aşağıdaki kodu ekleyin `Sheet1` sınıfı. `CreateVstoNamedRange` Yöntemi yeni bir oluşturur <xref:Microsoft.Office.Tools.Excel.NamedRange> belirlenen aralıkta nesnesi. Bu yöntem de bir olay işleyicisi oluşturur <xref:Microsoft.Office.Tools.Excel.NamedRange.Selected> olayı <xref:Microsoft.Office.Tools.Excel.NamedRange>. Bu kılavuzda daha sonra çağıracaksınız `CreateVstoNamedRange` belgedeki VBA kodundan yöntemi.  
  
     [!code-csharp[Trin_CallingCSCustomizationFromVBA#2](../vsto/codesnippet/CSharp/CallingCodeFromVBA/Sheet1.cs#2)]  
  
3.  Aşağıdaki yöntemi ekleyin `Sheet1` sınıfı. Bu yöntem geçersiz kılmaları <xref:Microsoft.Office.Tools.Excel.Worksheet.GetAutomationObject%2A> geçerli örneği döndürülecek yöntemi `Sheet1` sınıfı.  
  
     [!code-csharp[Trin_CallingCSCustomizationFromVBA#3](../vsto/codesnippet/CSharp/CallingCodeFromVBA/Sheet1.cs#3)]  
  
4.  İlk satırı önce aşağıdaki öznitelikler uygulamak `Sheet1` sınıf bildiriminin. Bu öznitelikler sınıfı görünür yapmak COM, ancak bir sınıf arabirimi oluşturma olmadan.  
  
     [!code-csharp[Trin_CallingCSCustomizationFromVBA#1](../vsto/codesnippet/CSharp/CallingCodeFromVBA/Sheet1.cs#1)]  
  
## <a name="extract-an-interface-for-the-sheet1-class"></a>Sheet1 sınıfı için bir arabirimi Ayıkla  
 Oluşturmadan önce `CreateVstoNamedRange` yöntemi VBA kodu için bu yöntemi tanımlayan ortak bir arabirim oluşturmanız gerekir ve bu arabirime com kullanıma sunma  
  
### <a name="to-extract-an-interface-for-the-sheet1-class"></a>Sheet1 sınıfı için bir arabirimi ayıklamak için  
  
1.  İçinde **Sheet1.cs** kod dosyası, herhangi bir yeri tıklatın `Sheet1` sınıfı.  
  
2.  Üzerinde **yeniden düzenlemeniz** menüsünde tıklatın **arayüz**.  
  
3.  İçinde **arayüz** iletişim kutusunda **form arabirimi ortak üyeleri seçin** kutusunda, girişini tıklatın `CreateVstoNamedRange` yöntemi.  
  
4.  **Tamam**'ı tıklatın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] adlı yeni bir arayüz yaratır `ISheet1`, ve tanımını değiştirdiği `Sheet1` bunu uygulayan sınıfının `ISheet1` arabirimi. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Ayrıca açar **Isheet1.cs** Kod Düzenleyicisi'nde dosya.  
  
5.  İçinde **Isheet1.cs** dosya, yerine `ISheet1` arayüzü bildirimini aşağıdaki kodla. Bu kod yapar `ISheet1` ortak arabirim ve uygular <xref:System.Runtime.InteropServices.ComVisibleAttribute> arabirimi COM görünür yapmak için özniteliği  
  
     [!code-csharp[Trin_CallingCSCustomizationFromVBA#4](../vsto/codesnippet/CSharp/CallingCodeFromVBA/ISheet1.cs#4)]  
  
6.  Projeyi oluşturun.  
  
## <a name="expose-the-method-to-vba-code"></a>VBA kodunda yöntemi oluşturma  
 Kullanıma sunmak için `CreateVstoNamedRange` VBA kodu çalışma kitabını yönteme ayarlamak **ReferenceAssemblyFromVbaProject** özelliği için `Sheet1` konak öğesi **doğru**.  
  
### <a name="to-expose-the-method-to-vba-code"></a>VBA kodu yönteme kullanıma sunmak için  
  
1.  İçinde **Çözüm Gezgini**, çift **Sheet1.cs**.  
  
     **WorkbookWithVBA** dosyasını açar Sheet1 görünürken Tasarımcısı'nda.  
  
2.  İçinde **özellikleri** penceresinde, seçin **ReferenceAssemblyFromVbaProject** özelliği ve değerini değiştirin **doğru**.  
  
3.  Tıklatın **Tamam** iletisi görüntülenir.  
  
4.  Projeyi oluşturun.  
  
## <a name="call-the-method-from-vba-code"></a>VBA kodundan yöntemini çağırın  
 Şimdi Ara `CreateVstoNamedRange` çalışma kitabı VBA kodundan yöntemi.  
  
> [!NOTE]  
>  Bu kılavuzda, projede hata ayıklarken VBA kodu çalışma kitabına ekleyeceksiniz. Visual Studio ile ana proje klasöründeki belgenin bir kopyasını yapı çıktı klasörüne belgede değiştirdiğinden bu belgeye eklediğiniz VBA kodu Projeyi derlemek bir sonraki başlatılışında üzerine yazılır. VBA kodu kaydetmek istiyorsanız, bu proje klasöründeki belgeye kopyalayabilirsiniz. Daha fazla bilgi için bkz: [birleştirmek VBA ve belge düzeyi özelleştirmeleri](../vsto/combining-vba-and-document-level-customizations.md).  
  
### <a name="to-call-the-method-from-vba-code"></a>VBA kodundan yöntemi çağırmak için  
  
1.  Tuşuna **F5** projeyi çalıştırın.  
  
2.  Üzerinde **Geliştirici** sekmesinde **kod** grubunda **Visual Basic**.  
  
     Visual Basic Düzenleyicisi'ni açar.  
  
3.  Üzerinde **Ekle** menüsünde tıklatın **Modülü**.  
  
4.  Yeni bir modüle aşağıdaki kodu ekleyin.  
  
     Bu kod çağırır `CreateTable` özelleştirme derlemesindeki yöntemi. Genel kullanarak bu yöntem makrosu erişir `GetManagedClass` erişmek için yöntemi `Sheet1` ana VBA kodu kullanıma sunulan öğesi sınıf. `GetManagedClass` Yöntemi ayarladığınızda otomatik olarak üretilen **ReferenceAssemblyFromVbaProject** özelliği bu kılavuzda daha önce.  
  
    ```vb  
    Sub CallVSTOMethod()  
        Dim VSTOSheet1 As CallingCodeFromVBA.Sheet1  
        Set VSTOSheet1 = GetManagedClass(Sheet1)  
        Call VSTOSheet1.CreateVstoNamedRange(Sheet1.Range("A1"), "VstoNamedRange")  
    End Sub  
    ```  
  
5.  Tuşuna **F5**.  
  
6.  Açık çalışma kitabında hücreyi tıklatın **A1** üzerinde **Sheet1**. İleti kutusu göründüğünden emin olun.  
  
7.  Excel Değişikliklerinizi kaydetmeden kapatın.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Bu konu başlıklarında VBA'dan Office çözümlerinde kod çağırma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Konak öğesi VBA'dan Visual Basic özelleştirmelerinde kodu çağırma. Bu işlem Visual C# işleminden farklıdır. Daha fazla bilgi için bkz: [izlenecek yol: çağrı kodu VBA içinden bir Visual Basic projesinde](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md).  
  
-   VBA içinden bir VSTO eklenti kodu çağırma. Daha fazla bilgi için bkz: [izlenecek yol: çağrı kod bir VSTO eklentide VBA'dan](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [VBA ve belge düzeyi özelleştirmelerini birleştirme](../vsto/combining-vba-and-document-level-customizations.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Nasıl yapılır: Visual Basic projesinde VBA'ya sunmaya kodu](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md)   
 [Nasıl yapılır: Visual c VBA'ya sunmaya kodu&#35; proje](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)   
 [İzlenecek yol: bir Visual Basic projesinde VBA'dan kod çağırmak](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)  
  