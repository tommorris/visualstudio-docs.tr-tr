---
title: Belge düzeyi özelleştirmelerini programlama
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- Sheet3
- thisWorkbook
- thisDocument
- Sheet1
- Sheet2
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ThisDocument class
- Sheet3 class
- ThisWorkbook class
- writing code for Office solutions
- programming [Office development in Visual Studio], document-level customizations
- Sheet1 class
- Office applications [Office development in Visual Studio], document-level customizations
- Sheet2 class
- document-level customizations [Office development in Visual Studio], programming
- application development [Office development in Visual Studio], document-level customizations
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 512952a27e2b1c22df256e36f8cbea59f04a3295
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692837"
---
# <a name="program-document-level-customizations"></a>Belge düzeyi özelleştirmelerini programlama
  Belge düzeyi özelleştirme kullanarak Microsoft Office Word veya Microsoft Office Excel genişlettiğinizde, aşağıdaki görevleri gerçekleştirebilirsiniz:  
  
-   Uygulamanın kendi nesne modelini kullanarak otomatikleştirin.  
  
-   Denetimleri belge yüzeyine ekleyin.  
  
-   Visual Basic for Applications (VBA) kodunu belgedeki özelleştirme derlemesinden çağırın.  
  
-   Kodu VBA özelleştirme derlemesinden çağırın.  
  
-   Microsoft Office yüklü olmayan bir sunucuda durumdayken belge belirli yönlerini yönetin.  
  
-   Uygulama kullanıcı arabirimi (UI) özelleştirin.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Belge düzeyi projelerine kod yazmaya bazı yönleri, diğer Visual Studio Proje türleri farklıdır. Bu farklılıklar birçoğu Office nesne modelleri için yönetilen kod gösterilen şekilde hatalardır. Daha fazla bilgi için bkz: [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md).  
  
 Visual Studio'da Office geliştirme araçlarını kullanarak oluşturabilirsiniz belge düzeyi özelleştirmeleri ve çözümlerin diğer türleri hakkında genel bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
## <a name="use-the-generated-classes-in-document-level-projects"></a>Belge düzeyi projelerine oluşturulan sınıflarını kullanma  
 Belge düzeyi projesi oluşturduğunuzda, Visual Studio bir sınıf kodunuzu yazmaya başlamak için kullanabileceğiniz projede otomatik olarak oluşturur. Visual Studio, Word ve Excel için farklı sınıflar oluşturur:  
  
-   Word için belge düzeyi projelerine içinde sınıf adlandırılır `ThisDocument` varsayılan olarak.  
  
-   Excel için belge düzeyi projelerine sahip birden çok oluşturulan sınıflar: çalışma kitabının kendisi için ve her çalışma sayfası için bir. Varsayılan olarak, bu sınıfları aşağıdaki adlara sahiptir:  
  
    -   `ThisWorkbook`  
  
    -   `Sheet1`  
  
    -   `Sheet2`  
  
    -   `Sheet3`  
  
 Oluşturulan sınıf belge açıldığında ya da kapalı olduğunda, çağrılan olay işleyicileri içerir. Belge açıldığında kodu çalıştırmak için kodu ekleyin `Startup` olay işleyicisi. Belge kapatıldığında hemen önce kodu çalıştırmak için kodu ekleyin `Shutdown` olay işleyicisi. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
### <a name="understand-the-design-of-the-generated-classes"></a>Oluşturulan sınıflar tasarımını anlama  
 ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], konak öğesi türleri [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] arabirimleri olduğundan, bunları kendi uygulamasından oluşturulan sınıflar türetilemez. Bunun yerine, oluşturulan sınıflar birçok üyelerini aşağıdaki temel sınıflarından:  
  
-   `ThisDocument`: türetir <xref:Microsoft.Office.Tools.Word.DocumentBase>.  
  
-   `ThisWorkbook`: türetir <xref:Microsoft.Office.Tools.Excel.WorkbookBase>.  
  
-   `Sheet` *n*: türetilen <xref:Microsoft.Office.Tools.Excel.WorksheetBase>.  
  
 Temel sınıflar tüm çağrıları kendi üyelerine karşılık gelen ana bilgisayar öğesi arabirimlerde iç uygulamalarına yönlendirir [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Örneğin, çağırırsanız <xref:Microsoft.Office.Tools.Word.DocumentBase.Protect%2A> yöntemi `ThisDocument` sınıfı, <xref:Microsoft.Office.Tools.Word.DocumentBase> sınıfı bu çağrıyı iç uygulamalarına yönlendirir <xref:Microsoft.Office.Tools.Word.Document> arabiriminde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
## <a name="access-the-object-model-of-the-host-application"></a>Ana bilgisayar uygulamasının nesne modeline erişme  
 Konak uygulamasının nesne modeline erişmek için oluşturulan sınıf üyeleri projenizde kullanın. Bu sınıfların her biri bir Excel veya Word nesne modeline nesnesinde karşılık gelir ve özellikleri, yöntemleri ve olayları çoğunu içerir. Örneğin, `ThisDocument` Word aynı üyeleri çoğunu sağlar için belge düzeyi projede sınıf <xref:Microsoft.Office.Interop.Word.Document> Word nesne modelindeki.  
  
 Aşağıdaki kod örneğinde, Word için belge düzeyi özelleştirme parçası olan bir belgeyi kaydetmek için Word nesne modeli kullanmayı gösterir. Bu örnek çalıştırılmak üzere tasarlanmıştır `ThisDocument` sınıfı.  
  
```vb  
Me.Save()  
```  
  
```csharp  
this.Save();  
```  
  
 Dışından aynı şeyi yapmak için `ThisDocument` sınıfı, kullanın `Globals` nesne erişimi `ThisDocument` sınıfı. Dahil etmek istiyorsanız, örneğin, bu kod bir eylemler bölmesi kod dosyasına ekleyebilirsiniz bir **kaydetmek** Eylemler bölmesinde UI düğmesi.  
  
```vb  
Globals.ThisDocument.Save()  
```  
  
```csharp  
Globals.ThisDocument.Save();  
```  
  
 Çünkü `ThisDocument` sınıfı alır, üyelerinden çoğunu <xref:Microsoft.Office.Tools.Word.Document> konak öğesi `Save` bu kodda çağrılan yöntemdir gerçekten <xref:Microsoft.Office.Tools.Word.Document.Save%2A> yöntemi <xref:Microsoft.Office.Tools.Word.Document> konak öğesi. Bu yöntem karşılık gelen <xref:Microsoft.Office.Interop.Word._Document.Save%2A> yöntemi <xref:Microsoft.Office.Interop.Word.Document> Word nesne modelindeki.  
  
 Word ve Excel nesne modelleri kullanma hakkında daha fazla bilgi için bkz: [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md) ve [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md).  
  
 Hakkında daha fazla bilgi için `Globals` nesne için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
## <a name="add-controls-to-documents"></a>Belgelere denetimler ekleme  
 Belgenin UI'ını özelleştirmek için Windows Forms denetimleri ekleyebilirsiniz veya *konak denetimlerini* belge yüzeyine. Farklı denetim kümelerini birleştirerek ve denetimleri veriye bağlayabilirsiniz kod, yazma, kullanıcıdan bilgi toplamak ve kullanıcı eylemlerine yanıt.  
  
 Konak denetimleri bazı nesneler Word ve Excel nesne modelindeki genişleten sınıflarıdır. Örneğin, <xref:Microsoft.Office.Tools.Excel.ListObject> konak kontrolü tüm işlevselliğini sağlar <xref:Microsoft.Office.Interop.Excel.ListObject> Excel'de. Ancak, <xref:Microsoft.Office.Tools.Excel.ListObject> konak kontrolü ek olaylar ve veri bağlama özellikleri de sahiptir.  
  
 Daha fazla bilgi için bkz: [konak öğelerini ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md) ve [Windows forms denetimleri Office belgeleri genel bakış üzerinde](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
## <a name="combine-vba-and-document-level-customizations"></a>VBA ve belge düzeyi özelleştirmelerini birleştirme  
 Belge düzeyi özelleştirme parçası olan bir belgede VBA kodu kullanabilirsiniz. VBA kodu özelleştirme derlemesinden belgede çağırabilir ve özelleştirme derlemesindeki kodu çağırmak için belgedeki VBA kodu etkinleştirmek için projenizi de yapılandırabilirsiniz.  
  
 Daha fazla bilgi için bkz: [birleştirmek VBA ve belge düzeyi özelleştirmeleri](../vsto/combining-vba-and-document-level-customizations.md).  
  
## <a name="manage-documents-on-a-server"></a>Bir sunucu üzerinde belgeleri yönetme  
 Microsoft Office Excel'in yüklü veya belge düzeyi özelleştirmeleri Microsoft Office Word'ün yüklü olmadığı bir sunucuda farklı yönlerini yönetebilirsiniz. Örneğin, erişim ve belgenin veri önbellekteki verileri değiştirin. Ayrıca, belge ile ilişkili özelleştirme derlemesini yönetebilirsiniz. Örneğin, program aracılığıyla derleme belgeden belgeyi artık kodunuzun çalıştığı ya da bir belgeye program aracılığıyla bir derleme iliştirebilirsiniz kaldırabilirsiniz.  
  
 Daha fazla bilgi için bkz: [ServerDocument sınıfını kullanarak sunucu üzerinde belgeleri yönetme](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).  
  
## <a name="customize-the-user-interface-of-microsoft-office-applications"></a>Microsoft Office uygulamaları kullanıcı arabirimini özelleştirme  
 Belge düzeyi özelleştirme kullanarak, aşağıdaki yollarla Excel ve Word UI'ını özelleştirebilirsiniz:  
  
-   Konak denetimleri veya Windows Forms denetimleri belge yüzeyine ekleyin.  
  
     Daha fazla bilgi için bkz: [otomatikleştirmek genişletilmiş nesneleri kullanarak Word'ü](../vsto/automating-word-by-using-extended-objects.md), [Excel genişletilmiş nesneleri kullanarak otomatikleştirmek](../vsto/automating-excel-by-using-extended-objects.md), ve [Windows Forms denetimleri Office belgeleri bir genel bakış](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
-   Eylemler bölmesi belgeye ekleyin.  
  
     Daha fazla bilgi için bkz: [Eylemler bölmesine genel bakış](../vsto/actions-pane-overview.md).  
  
-   Özel sekmeler Şerit'e ekleyin.  
  
     Daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
-   Şerit'te yerleşik bir sekmeyi özel gruplar ekleyin.  
  
     Daha fazla bilgi için bkz: [nasıl yapılır: yerleşik bir sekmeyi özelleştirme](../vsto/how-to-customize-a-built-in-tab.md).  
  
 Microsoft Office UI uygulamaları özelleştirme hakkında daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
## <a name="get-extended-objects-from-native-office-objects-in-document-level-customizations"></a>Belge düzeyi özelleştirmelerinde yerel Office nesnelerinden genişletilmiş nesneleri alma  
 Office olayları için birçok olay işleyicileri çalışma kitabı, çalışma sayfası veya olayı belge temsil eden yerel bir Office nesnesi alır. Bazı durumlarda, yalnızca çalışma kitabı veya belge düzeyi özelleştirmeyi belgede olayı varsa bazı kodlar çalıştırmak isteyebilirsiniz. Örneğin, Excel için belge düzeyi özelleştirmelerinde kullanıcı özelleştirilmiş çalışma kitabında çalışma etkinleştirdiğinde, ancak kullanıcı çalışma kitabındaki aynı anda açık olmasını gerçekleşen bazı diğer etkinleştirdiğinde değil, bazı kodlar çalıştırmak isteyebilirsiniz.  
  
 Yerel Office nesnesi varsa, söz konusu nesne uygulamasına genişletilmiş olup olmadığını sınayabilirsiniz bir *konak öğesi* veya *konak kontrolü* belge düzeyi özelleştirmelerinde. Konak denetimlerinin ve konak öğelerinin olan tarafından sağlanan türleri [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] işlevsellik ekleyen yerel Word veya Excel nesne modellerinde varolan nesneleri (adlı *yerel Office nesneleri*). Konak denetimlerinin ve konak öğelerinin toplu olarak da bilinir *genişletilmiş nesneleri*. Konak denetimlerinin ve konak öğeleri hakkında daha fazla bilgi için bkz: [konak öğelerini ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
## <a name="understand-the-getvstoobject-and-hasvstoobject-methods"></a>GetVstoObject ve HasVstoObject yöntemlerini anlama  
 Yerel Office nesnesi sınamak için kullanın `HasVstoObject` ve `GetVstoObject` projenizdeki yöntemleri:  
  
-   Kullanım `HasVstoObject` yerel Office nesnesinin özelleştirme sırasında genişletilmiş bir nesne olup olmadığını belirlemek istiyorsanız yöntemi. Bu yöntem **true** yerel Office nesnesine genişletilmiş bir nesne varsa ve **false** Aksi takdirde.  
  
-   Kullanım `GetVstoObject` bir yerel Office nesnesi için Genişletilmiş nesne almak istiyorsanız yöntemi. Bu yöntem bir <xref:Microsoft.Office.Tools.Excel.ListObject>, <xref:Microsoft.Office.Tools.Excel.Workbook>, <xref:Microsoft.Office.Tools.Excel.Worksheet>, veya <xref:Microsoft.Office.Tools.Word.Document> belirtilen yerel Office nesnesinin varsa, nesne. Aksi takdirde, `GetVstoObject` döndürür **null**. Örneğin, `GetVstoObject` yöntemi döndürür bir <xref:Microsoft.Office.Tools.Word.Document> , belirtilen <xref:Microsoft.Office.Interop.Word.Document> Word belgesi projenizdeki belge için temel nesnedir.  
  
 Belge düzeyi projelerine kullanamazsınız `GetVstoObject` yeni yöntemi <xref:Microsoft.Office.Tools.Excel.Workbook>, <xref:Microsoft.Office.Tools.Excel.Worksheet>, veya <xref:Microsoft.Office.Tools.Word.Document> çalışma zamanında konak öğesi. Yalnızca projenizde tasarım zamanında oluşturulan varolan konak öğelerine erişmek için bu yöntemi kullanabilirsiniz. Çalışma zamanında yeni ana bilgisayar öğeleri oluşturmak istiyorsanız, VSTO eklenti projesindeki geliştirmelisiniz. Daha fazla bilgi için bkz: [konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md) ve [genişletmek Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="use-the-getvstoobject-and-hasvstoobject-methods"></a>GetVstoObject ve HasVstoObject yöntemlerini kullanma  
 Çağrılacak `HasVstoObject` ve `GetVstoObject` yöntemi, kullanım `Globals.Factory.GetVstoObject` veya `Globals.Factory.HasVstoObject` yöntemi ve yerel Word veya Excel nesnesine geçirin (gibi bir <xref:Microsoft.Office.Interop.Word.Document> veya <xref:Microsoft.Office.Interop.Excel.Worksheet>) test etmek istediğiniz.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office belgelerindeki denetimler](../vsto/controls-on-office-documents.md)   
 [VBA ve belge düzeyi özelleştirmelerini birleştirme](../vsto/combining-vba-and-document-level-customizations.md)   
 [ServerDocument sınıfını kullanarak sunucu üzerinde belgeleri yönetme](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)  
  
  