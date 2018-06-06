---
title: Outlook nesne modeline genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.ProjectItem.OutlookAddin
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook [Office development in Visual Studio], object model overview
- object models [Office development in Visual Studio], Office
- objects [Office development in Visual Studio], Office object models
- object models [Office development in Visual Studio], Outlook
- Office object models
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7e2d0141611a13e7b1ee9b20b8988466c92f3ce2
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693052"
---
# <a name="outlook-object-model-overview"></a>Outlook nesne modeline genel bakış
  Microsoft Office Outlook için VSTO eklentileri geliştirmek için Outlook nesne modeli tarafından sağlanan nesnelerle etkileşim kurabilirsiniz. Outlook nesne modeli sınıfları ve kullanıcı arabirimi öğelerini temsil eden arabirimler sağlar. Örneğin, <xref:Microsoft.Office.Interop.Outlook.Application> nesnesini temsil eden tüm uygulama <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> nesnesi, e-posta veya diğer öğeleri içeren bir klasörü temsil eder ve <xref:Microsoft.Office.Interop.Outlook.MailItem> nesnesi, bir e-posta iletisini temsil eder.  
  
 Bu konu, bazı Outlook nesne modeli içindeki ana nesneler kısa bir genel bakış sağlar. Burada, öğrenin tüm Outlook nesne modeli hakkında daha fazla kaynaklar için bkz [Outlook nesne modeli belgeleri kullanın](#refdoc).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl Outlook'u özel görev raporu oluşturmak için I: kullanma musunuz?](http://go.microsoft.com/fwlink/?LinkID=130315).  
  
## <a name="access-objects-in-an-outlook-project"></a>Outlook projesinde nesnelere erişme  
 Outlook ile etkileşim kurabilen birçok nesne sağlar. Nesne modeli etkili bir şekilde kullanmak için aşağıdaki üst düzey nesneleriyle bilgi sahibi olmanız:  
  
-   <xref:Microsoft.Office.Interop.Outlook.Application>  
  
-   <xref:Microsoft.Office.Interop.Outlook.Explorer>  
  
-   <xref:Microsoft.Office.Interop.Outlook.Inspector>  
  
-   <xref:Microsoft.Office.Interop.Outlook.MAPIFolder>  
  
-   <xref:Microsoft.Office.Interop.Outlook.MailItem>  
  
-   <xref:Microsoft.Office.Interop.Outlook.AppointmentItem>  
  
-   <xref:Microsoft.Office.Interop.Outlook.TaskItem>  
  
-   <xref:Microsoft.Office.Interop.Outlook.ContactItem>  
  
### <a name="application-object"></a>Uygulama nesnesi  
 <xref:Microsoft.Office.Interop.Outlook.Application> Nesnesi, Outlook uygulamasını temsil eder ve Outlook nesne modelinde en üst düzey nesnedir. Bu nesne önemlileri üyeleri bazıları şunlardır:  
  
-   [CreateItem](http://msdn.microsoft.com/en-us/771707fb-5f34-473d-9fdf-09a6a7f55ece) bir e-posta iletisi, görev veya randevu gibi yeni bir öğe oluşturmak için kullanabileceğiniz yöntemi.  
  
-   <xref:Microsoft.Office.Interop.Outlook._Application.Explorers%2A> Bir klasörün içeriğini Outlook kullanıcı arabiriminde (UI) görüntüleyen pencerelerin erişmek için kullanabileceğiniz özelliği.  
  
-   <xref:Microsoft.Office.Interop.Outlook._Application.Inspectors%2A> Bir e-posta iletisi veya toplantı isteği gibi tek bir öğenin içeriğini görüntülemek windows erişmek için kullanabileceğiniz özelliği.  
  
 Bir örneğini almak <xref:Microsoft.Office.Interop.Outlook.Application> nesne, uygulama alanının kullanmak `ThisAddIn` projenizdeki sınıfı. Daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
> [!NOTE]  
>  Özellikleri ve Outlook nesne modeli Koruması tarafından engellenen yöntemleri kullandığınızda güvenlik uyarılarını önlemek için uygulama alanından Outlook nesnelerini Al `ThisAddIn` sınıfı. Daha fazla bilgi için bkz: [Office çözümleri için belirli güvenlik konuları](../vsto/specific-security-considerations-for-office-solutions.md).  
  
### <a name="explorer-object"></a>Explorer nesnesi  
 <xref:Microsoft.Office.Interop.Outlook.Explorer> Nesnesi e-posta iletileri, görevler veya randevular gibi öğeleri içeren bir klasörün içeriğini görüntüler bir pencereyi temsil eder. <xref:Microsoft.Office.Interop.Outlook.Explorer> Nesne yöntemleri ve pencereyi değiştirmek için kullanabileceğiniz özellikler ve pencere değiştiğinde oluşan olayları içerir.  
  
 Alınacak bir <xref:Microsoft.Office.Interop.Outlook.Explorer> nesne, aşağıdakilerden birini yapın:  
  
-   Kullanım <xref:Microsoft.Office.Interop.Outlook._Application.Explorers%2A> özelliği <xref:Microsoft.Office.Interop.Outlook.Application> tüm erişmek için nesne <xref:Microsoft.Office.Interop.Outlook.Explorer> Outlook nesneleri.  
  
-   Kullanım <xref:Microsoft.Office.Interop.Outlook._Application.ActiveExplorer%2A> yöntemi <xref:Microsoft.Office.Interop.Outlook.Application> nesnesi <xref:Microsoft.Office.Interop.Outlook.Explorer> geçerli odağa sahip.  
  
-   Kullanım `GetExplorer` yöntemi <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> nesnesi <xref:Microsoft.Office.Interop.Outlook.Explorer> geçerli klasör için.  
  
### <a name="inspector-object"></a>Inspector nesnesi  
 <xref:Microsoft.Office.Interop.Outlook.Inspector> Nesnesi bir e-posta iletisi, görev veya randevu gibi tek bir öğeyi görüntüleyen bir pencereyi temsil eder. <xref:Microsoft.Office.Interop.Outlook.Inspector> Nesne yöntemleri ve pencereyi değiştirmek için kullanabileceğiniz özellikler ve pencere değiştiğinde oluşan olayları içerir.  
  
 Alınacak bir <xref:Microsoft.Office.Interop.Outlook.Inspector> nesne, aşağıdakilerden birini yapın:  
  
-   Kullanım <xref:Microsoft.Office.Interop.Outlook._Application.Inspectors%2A> özelliği <xref:Microsoft.Office.Interop.Outlook.Application> tüm erişmek için nesne <xref:Microsoft.Office.Interop.Outlook.Inspector> Outlook nesneleri.  
  
-   Kullanım <xref:Microsoft.Office.Interop.Outlook._Application.ActiveInspector%2A> yöntemi <xref:Microsoft.Office.Interop.Outlook.Application> nesnesi <xref:Microsoft.Office.Interop.Outlook.Inspector> geçerli odağa sahip.  
  
-   Kullanım `GetInspector` gibi belirli bir yöntemi öğesi bir <xref:Microsoft.Office.Interop.Outlook.MailItem> veya <xref:Microsoft.Office.Interop.Outlook.AppointmentItem>, onunla ilişkilendirilen denetçisi almak için.  
  
### <a name="mapifolder-object"></a>MAPIFolder nesnesi  
 <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> Nesnesi, e-posta, kişiler, görevler ve diğer öğeleri içeren bir klasörü temsil eder. Outlook 16 varsayılan sağlar <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> nesneleri.  
  
 Varsayılan <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> nesneleri tarafından tanımlanan <xref:Microsoft.Office.Interop.Outlook.OlDefaultFolders> numaralandırma değerleri. Örneğin,  
  
 Microsoft.Office.Interop.Outlook.OlDefaultFolders.olFolderInbox karşılık gelen **gelen** Outlook klasöründe.  
  
 Varsayılan erişim gösteren bir örnek <xref:Microsoft.Office.Interop.Outlook.MAPIFolder> ve yeni bir <xref:Microsoft.Office.Interop.Outlook.MAPIFolder>, bkz: [nasıl yapılır: program aracılığıyla özel klasör öğeleri oluşturma](../vsto/how-to-programmatically-create-custom-folder-items.md).  
  
### <a name="mailitem-object"></a>MailItem Nesnesi  
 <xref:Microsoft.Office.Interop.Outlook.MailItem> Nesnesi, bir e-posta iletisini temsil eder. <xref:Microsoft.Office.Interop.Outlook.MailItem> nesneleridir genellikle klasörler gibi **gelen**, **Gönderilmiş öğeler**, ve **Giden Kutusu**. <xref:Microsoft.Office.Interop.Outlook.MailItem> özellikleri ve oluşturmak ve e-posta iletileri göndermek için kullanılan yöntemleri gösterir.  
  
 E-posta iletisine oluşturmayı gösteren bir örnek için bkz: [nasıl yapılır: program aracılığıyla e-posta öğesi oluşturma](../vsto/how-to-programmatically-create-an-e-mail-item.md).  
  
### <a name="appointmentitem-object"></a>AppointmentItem nesnesi  
 <xref:Microsoft.Office.Interop.Outlook.AppointmentItem> Nesneyi temsil ediyor toplantı, bir kerelik randevu veya yinelenen bir randevu veya toplantı **Takvim** klasör. <xref:Microsoft.Office.Interop.Outlook.AppointmentItem> Nesnesi yanıtlama veya toplantı istekleri ve toplantı ayrıntılarını saat ve konum gibi belirten özellikleri iletme gibi eylemleri gerçekleştiren yöntemleri içerir.  
  
 Randevu oluşturmayı gösteren bir örnek için bkz: [nasıl yapılır: program aracılığıyla toplantı isteği oluşturma](../vsto/how-to-programmatically-create-a-meeting-request.md).  
  
### <a name="taskitem-object"></a>TaskItem nesnesi  
 <xref:Microsoft.Office.Interop.Outlook.TaskItem> Nesnesi, belirli bir zaman çerçevesinde gerçekleştirilecek bir görevi temsil eder. <xref:Microsoft.Office.Interop.Outlook.TaskItem> nesneleri içinde bulunur **görevleri** klasör.  
  
 Bir görev oluşturmak için kullanmak [CreateItem](http://msdn.microsoft.com/en-us/771707fb-5f34-473d-9fdf-09a6a7f55ece) yöntemi <xref:Microsoft.Office.Interop.Outlook.Application> nesne ve değer geçirmek <xref:Microsoft.Office.Interop.Outlook.OlItemType.olTaskItem> parametresi için.  
  
### <a name="contactitem-object"></a>ContactItem nesnesi  
 <xref:Microsoft.Office.Interop.Outlook.ContactItem>Nesnesini temsil eden bir kişi **kişiler** klasör. <xref:Microsoft.Office.Interop.Outlook.ContactItem> Bunlar, adresini, e-posta adresleri ve telefon numaraları gibi temsil eden kişiler için kişi bilgilerini, çeşitli nesneleri içerir.  
  
 Yeni bir kişinin nasıl oluşturulduğunu gösteren bir örnek için bkz: [nasıl yapılır: Outlook Kişilerine program aracılığıyla giriş ekleme](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md). Var olan bir kişi arama gösteren örnek için bkz: [nasıl yapılır: program aracılığıyla belirli bir kişi arama](../vsto/how-to-programmatically-search-for-a-specific-contact.md).  
  
##  <a name="refdoc"></a> Outlook nesne modeli belgeleri kullanın  
 Outlook nesne modeli hakkında tam bilgi için Outlook birincil birlikte çalışma derlemesi (PIA) başvuru ve VBA nesne modeli başvurusu başvurabilir.  
  
### <a name="primary-interop-assembly-reference"></a>Birincil birlikte çalışma derleme başvurusu  
 Outlook PIA başvuru Outlook 2010 için birincil birlikte çalışma derlemeleri türlerinde belgeler. Daha fazla bilgi için bkz: [Outlook 2010 birincil birlikte çalışma derleme başvurusu](http://go.microsoft.com/fwlink/?LinkId=189580).  
  
 Tüm PIA türler için bilgi sağlamaya ek olarak, bu belgeleri de ortak Outlook Otomasyon görevler için kod örnekleri ve PIA yapısı hakkında ek bilgi sağlar.  
  
### <a name="vba-object-model-reference"></a>VBA nesne modeli başvurusu  
 Visual Basic for Applications (VBA) kodundaki sunulur gibi VBA nesne modeli başvurusu Outlook nesne modeli belgeler. Daha fazla bilgi için bkz: [Outlook 2010 nesne modeli başvurusu](http://go.microsoft.com/fwlink/?LinkId=199769).  
  
 Tüm nesneleri ve VBA nesne modeli başvurusu üyeleri türleri ve Outlook PIA üyelerine karşılık gelir. VBA nesne modeli başvurusu denetçisi nesnesinde Örneğin, karşılık gelen <xref:Microsoft.Office.Interop.Outlook.Inspector> Outlook PIA nesne. VBA nesne modeli başvurusu kod örnekleri çoğu özellikleri, yöntemleri ve olayları sağlasa da, bunları kullanarak oluşturduğunuz Outlook VSTO eklenti projesindeki kullanmak istiyorsanız, Visual Basic veya Visual C# bu başvurusu VBA kodu çevrilmelidir Visual Studio.  
  
### <a name="related-topics"></a>İlgili konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Kişi öğeleriyle çalışma](../vsto/working-with-contact-items.md)|Kişilerle görevlerin nasıl gerçekleştirileceği Göster konuları sağlar.|  
|[Posta öğeleriyle çalışma](../vsto/working-with-mail-items.md)|Posta öğeleri görevleri gerçekleştirmek nasıl Göster konuları sağlar.|  
|[Klasörlerle çalışma](../vsto/working-with-folders.md)|Klasörlerle görevlerin nasıl gerçekleştirileceği Göster konuları sağlar.|  
|[Takvim öğeleriyle çalışma](../vsto/working-with-calendar-items.md)|Takvim öğeleri görevleri gerçekleştirmek nasıl Göster konuları sağlar.|  
|[Nasıl yapılır: program aracılığıyla geçerli Outlook öğesini belirleme](../vsto/how-to-programmatically-determine-the-current-outlook-item.md)|Görünen adı geçerli klasörde ve seçili öğe hakkında bazı bilgiler gösterilmektedir.|  
  