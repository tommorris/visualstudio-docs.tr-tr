---
title: Office Projelerindeki Olaylar
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Sheet1_Startup
- ThisDocument_Shutdown
- ThisDocument_Startup
- application-level add-ins [Office development in Visual Studio], events
- event handlers [Office development in Visual Studio]
- ThisWorkbook_Startup
- Sheet2_Startup
- ThisWorkbook_Shutdown
- document-level customizations [Office development in Visual Studio], events
- Sheet2_Shutdown
- Startup event
- Sheet3_Shutdown
- add-ins [Office development in Visual Studio], events
- Shutdown event
- ThisAddIn_Startup
- Sheet3_Startup
- Startup method [Office development in Visual Studio]
- Shutdown method [Office development in Visual Studio]
- Sheet1_Shutdown
- events [Office development in Visual Studio]
- ThisAddIn_Shutdown
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 10cd0e1740aa53902d266ed0af6820b500a453e9
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="events-in-office-projects"></a>Office Projelerindeki Olaylar
  Her Office proje şablonu otomatik olarak birçok olay işleyicisi oluşturur. Belge düzeyi özelleştirmeleri için olay işleyicileri VSTO eklentileri için olay işleyicileri biraz farklıdır.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="document-level-projects"></a>Belge düzeyi projelerine  
 Visual Studio yeni veya var olan belgeler veya belge düzeyi özelleştirmelerinde çalışma sayfalarını arkasındaki oluşturulan kod sağlar. Bu kod iki farklı olayları başlatır: **başlangıç** ve **kapatma**.  
  
### <a name="startup-event"></a>Startup olayı  
 **Başlangıç** olayı her ana bilgisayar öğeleri (belge, çalışma kitabını veya çalışma) için belge çalışıyorken ve derlemedeki tüm başlatma kod çalıştırdıktan sonra. Kodunuzun çalıştığı sınıf çalıştırılacak son şeydir. Konak öğeleri hakkında daha fazla bilgi için bkz: [konak öğelerini ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
 Belge düzeyi projesi oluşturduğunuzda, Visual Studio için olay işleyicileri oluşturur **başlangıç** oluşturulan kod dosyalarında olay:  
  
-   Microsoft Office Word projeleri için olay işleyici adlı `ThisDocument_Startup`.  
  
-   Microsoft Office Excel projeleri için olay işleyicileri aşağıdaki adlara sahiptir:  
  
    -   `Sheet1_Startup`  
  
    -   `Sheet2_Startup`  
  
    -   `Sheet3_Startup`  
  
    -   `ThisWorkbook_Startup`  
  
### <a name="shutdown-event"></a>Shutdown olayı  
 **Kapatma** olayı her ana bilgisayar öğeleri (belge veya çalışma) için kodunuzu yüklendiği uygulama etki alanı olduğunda kaldırılmak üzere. Bunu çağırılacak sınıfında çağrılacak son şeydir.  
  
 Belge düzeyi projesi oluşturduğunuzda, Visual Studio için olay işleyicileri oluşturur **kapatma** oluşturulan kod dosyalarında olay:  
  
-   Microsoft Office Word projeleri için olay işleyici adlı `ThisDocument_Shutdown`.  
  
-   Microsoft Office Excel projeleri için olay işleyicileri aşağıdaki adlara sahiptir:  
  
    -   `Sheet1_Shutdown`  
  
    -   `Sheet2_Shutdown`  
  
    -   `Sheet3_Shutdown`  
  
    -   `ThisWorkbook_Shutdown`  
  
> [!NOTE]  
>  Program aracılığıyla denetimleri sırasında kaldırmayın **kapatma** belgenin olay işleyicisi. Kullanıcı Arabirimi öğeleri artık kullanılamaz **kapatma** olayı oluşur. Uygulama kapanmadan denetimleri kaldırmak istiyorsanız, kodunuzu başka bir olay işleyicisine gibi ekleyin **BeforeClose** veya **BeforeSave**.  
  
### <a name="event-handler-method-declarations"></a>Olay işleyicisi yöntem bildirimleri  
 Her olay işleyicisi yöntem bildirimi kendisine geçirilen aynı bağımsız değişkenlere sahiptir: *gönderen* ve *e*. Excel'de *gönderen* bağımsız değişkeni başvuruyor sayfasına gibi `Sheet1` veya `Sheet2`; Word'de *gönderen* bağımsız değişkeni belgeye anlamına gelir. *e* bağımsız değişkeni, bu durumda kullanılmayan için standart bağımsız bir olay anlamına gelir.  
  
 Aşağıdaki kod örneğinde, Word için belge düzeyi projelerine varsayılan olay işleyicileri gösterir.  
  
 [!code-vb[Trin_VstcoreWordAutomation#121](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#121)]
 [!code-csharp[Trin_VstcoreWordAutomation#121](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#121)]  
  
 Aşağıdaki kod örneğinde, Excel için belge düzeyi projelerine varsayılan olay işleyicileri gösterir.  
  
> [!NOTE]  
>  Aşağıdaki kod örneğinde olay işleyicileri gösterilir `Sheet1` sınıfı. Olay işleyicileri diğer konak öğesi sınıf adları sınıf adına karşılık gelir. Örneğin, `Sheet2` sınıfı, **başlangıç** olay işleyicisi adlandırılan `Sheet2_Startup`. İçinde `ThisWorkbook` sınıfı, **başlangıç** olay işleyicisi adlandırılan `ThisWorkbook_Startup`.  
  
 [!code-csharp[Trin_VstcoreExcelAutomation#83](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#83)]
 [!code-vb[Trin_VstcoreExcelAutomation#83](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#83)]  
  
### <a name="order-of-events-in-document-level-excel-projects"></a>Belge düzeyi Excel projelerinde olayların sırası  
 **Başlangıç** Excel projelerinde olay işleyicileri bu sırayla çağrılır:  
  
1.  `ThisWorkbook_Startup`.  
  
2.  `Sheet1_Startup`.  
  
3.  `Sheet2_Startup`.  
  
4.  `Sheet3_Startup`.  
  
5.  Sıralı diğer sayfalar.  
  
 **Kapatma** olay işleyicileri çalışma kitabı çözümünde bu sırayla çağrılır:  
  
1.  `ThisWorkbook_Shutdown`.  
  
2.  `Sheet1_Shutdown`.  
  
3.  `Sheet2_Shutdown`.  
  
4.  `Sheet3_Shutdown`.  
  
5.  Sıralı diğer sayfalar.  
  
 Projesi derlendiğinde sırası belirlenir. Kullanıcı çalışma zamanında sayfaları yeniden düzenler, olaylar çalışma kitabı açık veya kapalı başlatıldığında oluşturulur sipariş değiştirmez.  
  
## <a name="vsto-add-in-projects"></a>VSTO eklentisi projelerine  
 Visual Studio VSTO eklentileri oluşturulan kod sağlar. Bu kod iki farklı olayları başlatır: <xref:Microsoft.Office.Tools.AddInBase.Startup> ve <xref:Microsoft.Office.Tools.AddInBase.Shutdown>.  
  
### <a name="startup-event"></a>Startup olayı  
 <xref:Microsoft.Office.Tools.AddIn.Startup> Olayı için VSTO eklentisi yüklenir ve derlemedeki tüm başlatma kod çalıştırdıktan sonra oluşturulur. Bu olay tarafından işlenen `ThisAddIn_Startup` oluşturulan kod dosyasındaki yöntemi.  
  
 Kod `ThisAddIn_Startup` işleyicidir çalıştırmak için ilk kullanıcı kodu VSTO eklentinizi geçersiz kılmadıkça <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> yöntemi. Bu durumda, `ThisAddIn_Startup` olay işleyicisi sonra çağrılır <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A>.  
  
 Kodda eklemeyin `ThisAdd-In_Startup` kod açılması için bir belge gerektiriyorsa olay işleyicisi. Bunun yerine, bir kullanıcı oluşturur veya bir belgeyi açtığında, Office uygulaması oluşturan bir olay bu kodu ekleyin. Daha fazla bilgi için bkz: [Office uygulaması başlatıldığında, bir belgeye erişme](../vsto/programming-vsto-add-ins.md#AccessingDocuments).  
  
 VSTO eklentileri başlatma sırası hakkında daha fazla bilgi için bkz: [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
### <a name="shutdown-event"></a>Shutdown olayı  
 <xref:Microsoft.Office.Tools.AddInBase.Shutdown> Olayı kodunuzun yüklendiği uygulama etki alanı kaldırılmak üzere olduğunda oluşturulur. Bu olay tarafından işlenen `ThisAddIn_Shutdown` oluşturulan kod dosyasındaki yöntemi. Bu olay işleyicisi için VSTO eklentisi kaldırıldığında çalıştırmak için son kullanıcı kodudur.  
  
#### <a name="shutdown-event-in-outlook-vsto-add-ins"></a>Outlook VSTO eklentileri kapatma olayı  
 <xref:Microsoft.Office.Tools.AddInBase.Shutdown> Yalnızca kullanıcı için VSTO eklentisi Outlook'ta COM eklentileri iletişim kutusunu kullanarak devre dışı bıraktığında olayı oluşturulur. Outlook çıktığında yükseltilmiş değil. Outlook çıktığında, çalıştırmanız gereken kodu varsa, aşağıdaki olaylardan biri ya da işler:  
  
-   <xref:Microsoft.Office.Interop.Outlook.ApplicationEvents_11_Event.Quit> Olayı <xref:Microsoft.Office.Interop.Outlook.Application> nesnesi.  
  
-   <xref:Microsoft.Office.Interop.Outlook.ExplorerEvents_10_Event.Close> Olayı <xref:Microsoft.Office.Interop.Outlook.Explorer> nesnesi.  
  
> [!NOTE]  
>  Yükseltmek için Outlook zorlayabilirsiniz <xref:Microsoft.Office.Tools.AddInBase.Shutdown> kayıt defterini değiştirerek çıktığında olay. Bir yöneticinin bu ayarı döndürüyorsa, ancak herhangi bir için ekleme kodu `ThisAddIn_Shutdown` yöntemi artık Outlook çıktığında çalıştırır. Daha fazla bilgi için bkz: [kapatma değişiklikleri Outlook 2010 için](http://go.microsoft.com/fwlink/?LinkID=184614).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri geliştirmek](../vsto/developing-office-solutions.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md)  
  
  