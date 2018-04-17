---
title: "İzlenecek yol: Visual Basic Projesinde VBA'dan Kod Çağırma | Microsoft Docs"
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], Visual Basic for Applications and
- ThisDocument class
- Word [Office development in Visual Studio], calling code from VBA
- Visual Basic [Office development in Visual Studio], calling code from VBA
- VBA [Office development in Visual Studio], calling code in document-level customizations
- Office documents [Office development in Visual Studio, Visual Basic for Applications and
- calling code from VBA
- document-level customizations [Office development in Visual Studio], calling code
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: efb8f6c2759760fe2eb5c5d5ccf23e0942eac93a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-calling-code-from-vba-in-a-visual-basic-project"></a>İzlenecek Yol: Visual Basic Projesinde VBA'dan Kod Çağırma
  Bu kılavuz bir yöntem belge düzeyi özelleştirmelerinde için Microsoft Office Word Visual Basic for Applications (VBA) kodunu belgedeki nasıl çağrılacağını gösterir. Yordam üç temel adımdan oluşur: bir yöntem ekleme `ThisDocument` konak öğesi sınıfına, VBA kodunda yöntemi oluşturma ve belgedeki VBA kodundan yöntemini çağırın.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Bu kılavuzda Word özellikle kullansa da, izlenecek yol tarafından gösterilen kavramlar Excel için belge düzeyi projelerine de geçerlidir.  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   VBA kodu içeren bir belge oluşturma.  
  
-   Belgenin konumunu Word'de Güven Merkezi kullanarak güvenme.  
  
-   Bir yöntem ekleme `ThisDocument` ana öğesi sınıf.  
  
-   VBA kodu yönteme gösterme.  
  
-   VBA kodundan yöntemi çağırma.  
  
> [!NOTE]  
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="creating-a-document-that-contains-vba-code"></a>VBA kodu içeren bir belge oluşturma  
 İlk adım, basit VBA makrosu içeren makrosu etkin bir belge oluşturmaktır. Bu belgeyi temel alarak bir Visual Studio Proje oluşturmadan önce belgenin VBA projesi içermelidir. Aksi takdirde, Visual Studio özelleştirme derlemesini çağırmak VBA kodu etkinleştirmek için VBA projesini değiştiremez.  
  
 Kullanmak istediğiniz VBA kodu içeren bir belge zaten varsa bu adımı atlayabilirsiniz.  
  
#### <a name="to-create-a-document-that-contains-vba-code"></a>VBA kodu içeren bir belge oluşturmak için  
  
1.  Word'ü başlatın.  
  
2.  Word olarak etkin belgeyi Kaydet **Enabled Document (\*.docm)** adıyla **DocumentWithVBA**. Masaüstü gibi uygun bir konuma kaydedin.  
  
3.  Şerit'te tıklatın **Geliştirici** sekmesi.  
  
    > [!NOTE]  
    >  Varsa **Geliştirici** sekmesi görünür değilse, ilk Göster gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
4.  İçinde **kod** grubunda **Visual Basic**.  
  
     Visual Basic Düzenleyicisi'ni açar.  
  
5.  İçinde **proje** penceresinde çift **ThisDocument**.  
  
     İçin kod dosyası `ThisDocument` nesnesini açar.  
  
6.  Aşağıdaki VBA kodu kod dosyasına ekleyin. Bu kod, hiçbir şey yapmaz basit bir işlevi tanımlar. Bu işlev yalnızca amacı VBA projesi belgede var olduğundan emin olmaktır. Bu, bu kılavuzda sonraki adımlar için gereklidir.  
  
    ```  
    Sub EmptySub()  
    End Sub  
    ```  
  
7.  Belgeyi kaydedin ve Word çıkın.  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
 Artık daha önce oluşturduğunuz makrosu içerebilen belgeyi kullanan Word için belge düzeyi projesi oluşturabilirsiniz.  
  
#### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**. IDE'yi üzerinde Visual Basic geliştirme ayarlarını kullanmak üzere ayarlanmış olup olmadığını **dosya** menüsünde tıklatın **yeni proje**.  
  
3.  Şablonlar bölmesinde **Visual Basic**, genişletin ve ardından **Office/SharePoint**.  
  
4.  Seçin **Office eklentileri** düğümü.  
  
5.  Proje şablonları listesinde seçin **Word 2010 belgesine** veya **Word 2013 belge** projesi.  
  
6.  İçinde **adı** kutusuna **CallingCodeFromVBA**.  
  
7.  **Tamam**'ı tıklatın.  
  
     **Office Proje Sihirbazı için Visual Studio Araçları** açar.  
  
8.  Seçin **var olan bir belgeyi kopyalama**hem de **varolan belgenin tam yolu** kutusunda, konumu belirtin **DocumentWithVBA** daha önce oluşturduğunuz belge . Kendi makrosu etkin belgeyi kullanıyorsanız, bunun yerine bu belgenin konumunu belirtin.  
  
9. **Son**'a tıklayın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] açılır **DocumentWithVBA** belge Tasarımcısı'nda ve ekler **CallingCodeFromVBA** için proje **Çözüm Gezgini**.  
  
## <a name="trusting-the-location-of-the-document"></a>Belgenin konumunu güvenme  
 Çözümünüzdeki belgedeki VBA kodu için kod oluşturmadan önce çalıştırılacak belgede VBA güvenmesi gerekir. Bunu yapmanın birkaç yolu vardır. Bu kılavuzda belgede konumunu güven **Güven Merkezi** Word.  
  
#### <a name="to-trust-the-location-of-the-document"></a>Belgenin konumunu güvenmek için  
  
1.  Word'ü başlatın.  
  
2.  Tıklatın **dosya** sekmesi.  
  
3.  Tıklatın **Word Seçenekleri** düğmesi.  
  
4.  Kategoriler bölmesinde **Güven Merkezi**.  
  
5.  Ayrıntılar bölmesinde **Güven Merkezi Ayarları**.  
  
6.  Kategoriler bölmesinde **Güvenilen Konumlar**.  
  
7.  Ayrıntılar bölmesinde **yeni konum Ekle**.  
  
8.  İçinde **Microsoft Office güvenilir konum** iletişim kutusu, içeren klasöre gidin **CallingCodeFromVBA** projesi.  
  
9. Seçin **bu konumun alt klasörleri güvenilir de**.  
  
10. İçinde **Microsoft Office güvenilir konum** iletişim kutusu, tıklatın **Tamam**.  
  
11. İçinde **Güven Merkezi** iletişim kutusu, tıklatın **Tamam**.  
  
12. İçinde **Word Seçenekleri** iletişim kutusu, tıklatın **Tamam**.  
  
13. Word çıkın.  
  
## <a name="adding-a-method-to-the-thisdocument-class"></a>ThisDocument sınıfı için bir yöntem ekleme  
 VBA projesi kurulduğunda, bir yöntem ekleme `ThisDocument` ana VBA kodundan çağırabilirsiniz öğesi sınıf.  
  
#### <a name="to-add-a-method-to-the-thisdocument-class"></a>ThisDocument sınıfı için bir yöntem eklemek için  
  
1.  İçinde **Çözüm Gezgini**, sağ **ThisDocument.vb**ve ardından **görünümü kodu**.  
  
     **ThisDocument.vb** dosyasını Kod Düzenleyicisi'nde açar.  
  
2.  Aşağıdaki yöntemi ekleyin `ThisDocument` sınıfı. Bu yöntem, iki satır ve belgenin başlangıcına iki sütun içeren bir tablo oluşturur. Parametreler ilk satırda görüntülenen metni belirtin. Bu kılavuzda daha sonra belgedeki VBA kodundan bu yöntemi çağırır.  
  
     [!code-vb[Trin_CallingVBCustomizationFromVBA#1](../vsto/codesnippet/VisualBasic/CallingCodeFromVBA/ThisDocument.vb#1)]  
  
3.  Projeyi oluşturun.  
  
## <a name="exposing-the-method-to-vba-code"></a>VBA kodu yönteme gösterme  
 Kullanıma sunmak için `CreateTable` set belge VBA kodunda yöntemi **EnableVbaCallers** özelliği için `ThisDocument` konak öğesi **doğru**.  
  
#### <a name="to-expose-the-method-to-vba-code"></a>VBA kodu yönteme kullanıma sunmak için  
  
1.  İçinde **Çözüm Gezgini**, çift **ThisDocument.vb**.  
  
     **DocumentWithVBA** dosya Tasarımcısı'nda açılır.  
  
2.  İçinde **özellikleri** penceresinde, seçin **EnableVbaCallers** özelliği ve değerini değiştirin **doğru**.  
  
3.  Tıklatın **Tamam** iletisi görüntülenir.  
  
4.  Projeyi oluşturun.  
  
## <a name="calling-the-method-from-vba-code"></a>VBA kodundan yöntemi çağırma  
 Şimdi Ara `CreateTable` belgedeki VBA kodundan yöntemi.  
  
> [!NOTE]  
>  Bu kılavuzda, projenin hata ayıklama sırasında belgeye VBA kod ekleyeceksiniz. Visual Studio ile ana proje klasöründeki belgenin bir kopyasını yapı çıktı klasörüne belgede değiştirdiğinden bu belgeye eklediğiniz VBA kodu Projeyi derlemek bir sonraki başlatılışında üzerine yazılır. VBA kodu kaydetmek istiyorsanız, bu proje klasöründeki belgeye kopyalayabilirsiniz. Daha fazla bilgi için bkz: [birleştirme VBA ve belge düzeyi özelleştirmeleri](../vsto/combining-vba-and-document-level-customizations.md).  
  
#### <a name="to-call-the-method-from-vba-code"></a>VBA kodundan yöntemi çağırmak için  
  
1.  Projenizi çalıştırmak için F5 tuşuna basın.  
  
2.  Üzerinde **Geliştirici** sekmesinde **kod** grubunda **Visual Basic**.  
  
     Visual Basic Düzenleyicisi'ni açar.  
  
3.  Üzerinde **Ekle** menüsünde tıklatın **Modülü**.  
  
4.  Yeni bir modüle aşağıdaki kodu ekleyin.  
  
     Bu kod çağırır `CreateTable` özelleştirme derlemesindeki yöntemi. Makro bu yöntemi kullanarak erişen `CallVSTOAssembly` özelliği `ThisDocument` nesnesi. Ayarladığınızda bu özelliği otomatik olarak oluşturulan **EnableVbaCallers** özelliği bu kılavuzda daha önce.  
  
    ```  
    Sub CreateTable()  
        Call ThisDocument.CallVSTOAssembly.CreateTable("Employee Name", "Start Date")  
    End Sub  
    ```  
  
5.  F5 tuşuna basın.  
  
6.  Belgeye yeni bir tablo eklendiğini doğrulayın.  
  
7.  Word Değişikliklerinizi kaydetmeden kapatın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu konu başlıklarında VBA'dan Office çözümlerinde kod çağırma hakkında daha fazla bilgi edinebilirsiniz:  
  
-   Visual C# özelleştirmesinde VBA'dan kod çağırma. Bu işlem Visual Basic işleminden farklıdır. Daha fazla bilgi için bkz: [izlenecek yol: Visual C VBA'dan Kod Çağırma&#35; proje](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md).  
  
-   VBA içinden bir VSTO eklenti kodu çağırma. Daha fazla bilgi için bkz: [izlenecek yol: eklentide bir VSTO VBA'dan Kod Çağırma](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VBA ve belge düzeyi özelleştirmelerini birleştirme](../vsto/combining-vba-and-document-level-customizations.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Nasıl yapılır: Visual Basic projesinde VBA kodu kullanımına sunma](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md)   
 [Nasıl yapılır: Visual c VBA kodu kullanımına sunma&#35; proje](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)   
 [İzlenecek yol: Visual C VBA'dan Kod Çağırma&#35; proje](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md)  
  
  