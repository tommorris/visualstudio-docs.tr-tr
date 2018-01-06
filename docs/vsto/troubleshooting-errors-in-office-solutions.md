---
title: "Office çözümlerinde sorun giderme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.Project.DesignerDisabled
- VST.Designer.CannotActivate
- VST.Project.ExcelBusy
- VST.SelectDocWizard.AlreadyCustomized
- VST.SelectDocWizard.DocPath
- VST.Project.CannotOpen
- VST.Designer.ErrorsOccurred
dev_langs:
- VB
- CSharp
helpviewer_keywords: troubleshooting [Office development in Visual Studio]
ms.assetid: 8bbf5433-1992-4ecf-ae1b-19117b8ebe43
caps.latest.revision: "69"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: e74b2daab5d9a8f5840b9109edd871e311bc4cb9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-errors-in-office-solutions"></a>Office Çözümleri Hatalarında Sorun Giderme
  Visual Studio'da Office çözümleri geliştirirken, aşağıdaki görevleri gerçekleştirdiğinizde sorunlarla karşılaşabilirsiniz:  
  
-   [Projeler oluşturma ve yükseltme](#creating)  
  
-   [Tasarımcılar kullanma](#designers)  
  
-   [Kod yazma](#code)  
  
-   [Proje oluşturma](#building)  
  
-   [Projelerde hata ayıklama](#debugging)  
  
##  <a name="creating"></a>Projeler oluşturma ve yükseltme  
 Office projeleri oluşturduğunuzda veya açtığınızda aşağıdaki hatalarla karşılaşabilirsiniz.  
  
### <a name="the-project-cannot-be-created"></a>Proje oluşturulamaz  
 Bir Office projesi oluşturun veya açın çalışıldı, ancak Visual Studio nedenini belirlemek için yeterli bilgiye sahip olmayan bir hata oluştu. Visual Studio çıkmak ve yeniden başlatmayı projenizi kapatmayı deneyin.  
  
 Belge düzeyi projesi oluşturmak çalışıyorsanız, belgenin yeni projede aynı ada sahip başka bir belge zaten Excel veya Word'den açık olduğunu mümkündür. Tüm diğer örneklerini Excel veya Word'den kapalı olduğundan emin olun.  
  
### <a name="control-properties-are-lost-when-you-create-a-new-project-based-on-a-document-from-an-existing-project"></a>Kaybedilen, yeni bir proje varolan projeyi belgeden göre oluşturduğunuzda denetim özellikler:  
 Varolan projeyi belgeden temel alan yeni bir Office proje oluşturursanız, belge üzerinde olan herhangi bir denetim özelliklerini yeni projeye kopyalanmaz. Önceden var olan herhangi bir denetim özelliklerini el ile sıfırlamanız gerekir. Alternatif olarak, yeni bir proje oluşturmak yerine var olan proje kopyasını oluşturarak veya varolan projeyi yeni çözüme (tasarımcıda) yükleme ve kopyalama ve varolan denetimlerinin yapıştırma denetimi özellikleri koruyabilir Yeni belge belgeye.  
  
### <a name="errors-when-you-create-an-excel-workbook-project-based-on-an-existing-workbook"></a>Var olan bir çalışma kitabına bağlı bir Excel çalışma kitabı projesi oluşturduğunuzda hataları  
 Var olan bir çalışma kitabına bağlı yeni bir Excel çalışma kitabı projesi oluşturursanız, aşağıdaki hatalar birlikte görebilirsiniz.  
  
 Excel'den: "Gizlilik uyarısı: Bu belgede makroları, ActiveX denetimleri, XML genişletme paketi bilgileri veya Web bileşenleri içerir. Bu belge denetçisi tarafından kaldırılamayan kişisel bilgiler içerebilir."  
  
 Visual Studio'dan: "Düzgün yüklenemedi Tasarımcısı."  
  
 Belge denetçisi kullanarak kendi kişisel bilgilerine sahip bir çalışma kitabı dayalı bir projesi oluşturmayı denerseniz şu hatalar oluşabilir. Bu hatayı önlemek için proje oluşturmadan önce aşağıdaki adımları gerçekleştirin.  
  
1.  Çalışma kitabını Excel'de açın.  
  
2.  Güven Merkezi Excel'de açın.  
  
3.  Üzerinde **Gizlilik Seçenekleri** sekmesini Temizle **kaydederken dosya özelliklerinden kişisel bilgileri Kaldır** onay kutusu.  
  
4.  Çalışma kitabını kaydedin ve Excel'i kapatın.  
  
### <a name="cannot-open-a-project-after-migration"></a>Bir proje geçişten sonra açılamıyor  
 Bir Office çözümü için Microsoft Office 2010 geçirildikten sonra yalnızca 2007 Microsoft Office sistemi yüklü geliştirme bilgisayarınızda proje açılamaz. Aşağıdaki hatalar görebilirsiniz.  
  
 "Çözümde bir veya daha fazla proje doğru şekilde yüklenmedi. Lütfen ayrıntılar için Çıktı Penceresi'ne bakın."  
  
 "Bu proje türü ile ilişkili uygulamayı bu bilgisayarda yüklü olmadığı için projesi oluşturamıyor. Bu proje türü ile ilişkili Microsoft Office uygulamasını yüklemeniz gerekir."  
  
 Bu sorunu çözmek için .vbproj veya .csproj dosyasını düzenleyin. Word projesi için HostPackage "{763FDC83-64E5-4651-AC9B-28C4FEB985A1}" ile HostPackage = "{6CE98B71-D55A-4305-87A8-0D6E368D9600}". Bir Excel projesi için HostPackage "{B284B16A-C42C-4438-BDCD-B72F4AC43CFB}" ile HostPackage = "{825100CF-0BA7-47ea-A084-DCF3308DAF74}". Bir Outlook projesi için HostPackage "{D2B20FF5-A6E5-47E1-90E8-463C6860CB05}" ile HostPackage = "{20A848B8-E01F-4801-962E-25DB0FF57389}".  
  
 Alternatif olarak, Microsoft Office 2010 yüklü olan geliştirme bilgisayarlarında, geçirilen projeleri yalnızca açıldığından emin olun.  
  
### <a name="errors-in-upgraded-office-2003-document-level-projects-that-contain-windows-forms-controls"></a>Windows Forms denetimleri içeren yükseltilmiş Office 2003 belge düzeyi projelerine hataları  
 Microsoft Office 2003 belge düzeyi projesi yükseltin ve belgeyi Windows Forms denetimleri içeriyorsa, yükseltilen proje derleme veya zamanı hataları çalıştırılmamış olabilir. Proje yükseltme yapmadan önce bu sorunu önlemek için Visual Studio 2005 araçları Office ikinci Edition çalışma zamanı için geliştirme bilgisayara yükleyin. Bu sürüm çalışma zamanının Microsoft Download Center yeniden dağıtılabilir paket olarak kullanılabilir [için Microsoft Visual Studio 2005 araçları Office ikinci Edition çalışma zamanı (VSTO 2005 SE) (x86)](http://go.microsoft.com/fwlink/?linkid=49612).  
  
 Proje yükseltme işlemini tamamladıktan sonra diğer Office çözümleri tarafından kullanılmadığından, Visual Studio 2005 araçları Office ikinci Edition çalışma zamanı için geliştirme bilgisayardan kaldırabilirsiniz.  
  
##  <a name="designers"></a>Tasarımcılar kullanma  
 Belge, çalışma kitabı veya belge düzeyi projelerine çalışma Tasarımcısı ile çalışırken aşağıdaki hatalarla karşılaşabilirsiniz.  
  
### <a name="designer-failed-to-load-correctly"></a>Tasarımcı düzgün yüklenemedi  
 Visual Studio Tasarımcısı aşağıdaki durumlarda açılamıyor:  
  
-   Excel veya Word'den zaten açık olan ve bir modal iletişim kutusunu görüntüleme. Tasarımcısı'nı açmak için Excel veya Word'den açın ve açık kalıcı iletişim kutularını kapatın kalıcı bir iletişim kutusu olup olmadığını denetleyin. Açık hiçbir kalıcı iletişim kutuları varsa, bazı diğer eylem Excel önce gerekli olabilir veya Word yanıt verir.  
  
-   Proje ayıklanıyor. Tasarımcısı'nı açmak için durdurmak veya hata ayıklaması son.  
  
-   Bir Excel VSTO geliştirme bilgisayarınızda yüklü olan eklenti Excel başladığında bir iletişim kutusu görüntülüyor. Bir Excel belge düzeyi projesi oluşturmak için ilk VSTO eklenti devre dışı bırakmalısınız.  
  
### <a name="controls-appear-as-black-rectangles-on-the-document-or-worksheet"></a>Denetimleri belge veya çalışma sayfası üzerinde siyah dikdörtgenler olarak görünür  
 Denetimleri bir belge veya çalışma grubu, Visual Studio artık denetimleri tanır. Gruplandırılmış denetimleri erişilemiyor **özellikleri** penceresi ve bunların görünür belge veya çalışma sayfası üzerinde siyah dikdörtgenler olarak. İşlevselliklerini geri yüklemek için denetimler grubunu gerekir.  
  
### <a name="controls-on-a-word-template-are-not-visible-in-visual-studio"></a>Word şablonu denetimlere Visual Studio'da görünür olan  
 Visual Studio Tasarımcısı'nda bir Word şablonu açarsanız, şablonda metinle olmayan denetimler görünür olmayabilir. Visual Studio içindeki Word şablonlarını açıyor olmasıdır **Normal** görünümü. Denetimleri görüntülemek için tıklatın **Görünüm** menüsündeki **Microsoft Office Word görüntüsü** ve ardından **yazdırma düzeni**.  
  
### <a name="insert-clip-art-command-does-nothing-in-the-visual-studio-designer"></a>Küçük Resim Ekle komutu, Visual Studio Tasarımcısı'nda hiçbir şey yapmıyor  
 Excel veya Word'den Visual Studio Tasarımcısı'nda açıkken tıklatarak **küçük resim** düğmesini **çizimler** sekmesini Şeritte açık değil **küçük resim** görev bölmesi. Küçük resim eklemek için çalışma kitabı veya ana proje klasöründeki (\bin klasöründe yer alan kopya değil) dışında Visual Studio belgesinde kopyasını açın, küçük resim eklemek ve ardından çalışma kitabını veya belgeyi kaydedin.  
  
##  <a name="code"></a>Kod yazma  
 Office projelerinde kodu yazarken aşağıdaki hatalarla karşılaşabilirsiniz.  
  
### <a name="some-events-of-office-objects-are-not-accessible-when-using-c"></a>Office nesneleri bazı olayların C# kullanırken erişilebilir değil  
 Bazı durumlarda, bir Office birincil birlikte çalışma derlemesi (PIA) yazın bir Visual C# projesinde örneği belirli bir olay erişmeye çalıştığınızda bir derleyici hatası aşağıdaki gibi görebilirsiniz.  
  
 "'Microsoft.Office.Interop.Excel._Application.NewWorkbook' ve 'Microsoft.Office.Interop.Excel.AppEvents_Event.NewWorkbook' arasında bir belirsizliğe"  
  
 Bu hata başka bir özelliği veya yöntemi nesnenin aynı ada sahip bir olay erişmeye çalıştığınız anlamına gelir. Olay erişmek için nesneyi cast kendi *olay arabirimini*.  
  
 Olayları office PIA türleri uygulamak için iki arabirim: tüm özellikleri ve yöntemleri çekirdek arabirimiyle ve nesne tarafından sunulan olayları içeren bir olay arabirimi. Bu olay arabirimleri adlandırma kuralı kullanmak *objectname*olayları*n*_Event, gibi <xref:Microsoft.Office.Interop.Excel.AppEvents_Event> ve <xref:Microsoft.Office.Interop.Word.ApplicationEvents2_Event>. Bir nesne bulmayı beklediğinize bir olay erişemiyorsanız, olay arabirimiyle nesnesine dönüştürün.  
  
 Örneğin, <xref:Microsoft.Office.Interop.Excel.Application> nesneler sahip bir <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.NewWorkbook> olay ve <xref:Microsoft.Office.Interop.Excel._Application.NewWorkbook%2A> özelliği. İşlenecek <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.NewWorkbook> olay, cast <xref:Microsoft.Office.Interop.Excel.Application> için <xref:Microsoft.Office.Interop.Excel.AppEvents_Event> arabirimi. Aşağıdaki kod örneğinde, Excel için belge düzeyi projede bunu gösterilmiştir.  
  
 [!code-csharp[Trin_VstcoreTroubleshootingExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreTroubleshootingExcelCS/ThisWorkbook.cs#1)]  
  
 Office PIA olay arabirimlerde hakkında daha fazla bilgi için bkz: [genel bakış, sınıflar ve arabirimler Office birincil birlikte çalışma derlemeleri](http://msdn.microsoft.com/en-us/da92dc3c-8209-44de-8095-a843659368d5).  
  
### <a name="cannot-reference-office-pia-classes-in-projects-that-target-the-includenetv40shortsharepointincludesnet-v40-short-mdmd-or-the-includenetv45vstoincludesnet-v45-mdmd"></a>Hedefleyen Office projelerinde PIA sınıflar başvuramaz [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya[!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]  
 ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], bir Office PIA tanımlanan bir sınıftan başvuran kodu varsayılan olarak derlenmez. PIA sınıfları kullanın adlandırma kuralı *objectname*gibi sınıfı <xref:Microsoft.Office.Interop.Word.DocumentClass> ve <xref:Microsoft.Office.Interop.Excel.WorkbookClass>. Örneğin, aşağıdaki kodu Word VSTO eklenti projesindeki derlenmez.  
  
```vb  
Dim document As Word.DocumentClass = Globals.ThisAddIn.Application.ActiveDocument  
```  
  
```csharp  
Word.DocumentClass document = (Word.DocumentClass) Globals.ThisAddIn.Application.ActiveDocument;  
```  
  
 Bu kod, aşağıdaki derleme hataları oluşur:  
  
-   Visual Basic: ", derleme Hayır PIA modunu kullanarak bağlandığında sınıfı 'Belge sınıfı' referansı izin verilmez."  
  
-   Visual C#: "'Microsoft.Office.Interop.Word.DocumentClass' katıştırılmış birlikte çalışma türü. Geçerli arabirimi kullanın."  
  
 Bu hatayı gidermek için bunun yerine karşılık gelen arabirimi başvurmak için kodu değiştirin. Örneğin, başvuru yerine bir <xref:Microsoft.Office.Interop.Word.DocumentClass> nesne, bir örneği başvuru <xref:Microsoft.Office.Interop.Word.Document> yerine arabirim.  
  
```vb  
Dim document As Word.Document = Globals.ThisAddIn.Application.ActiveDocument  
```  
  
```csharp  
Word.Document document = Globals.ThisAddIn.Application.ActiveDocument;  
```  
  
 Hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], otomatik olarak varsayılan olarak Office PIA gelen tüm birlikte çalışma türlerini katıştır. Katıştırılmış birlikte çalışma türlerini özelliği yalnızca sınıfları değil arabirimleri ile çalıştığı için bu derleme hatası oluşur. Arabirimleri ve Office PIA sınıfları hakkında daha fazla bilgi için bkz: [genel bakış, sınıflar ve arabirimler Office birincil birlikte çalışma derlemeleri](http://go.microsoft.com/fwlink/?LinkId=189592). Office projelerinde katıştırılmış birlikte çalışma türlerini özelliği hakkında daha fazla bilgi için bkz: [tasarlama ve oluşturma Office çözümleri](../vsto/designing-and-creating-office-solutions.md).  
  
### <a name="references-to-office-classes-are-not-recognized"></a>Office sınıflarına başvurular tanınmıyor.  
 Bazı sınıfı, uygulama, örneğin birden çok ad alanları gibi adlardır <xref:Microsoft.Office.Interop.Word> ve <xref:System.Windows.Forms>. Bu nedenle, **içeri aktarmalar**/**kullanarak** proje şablonları üstündeki deyimi durumu kısayol niteleyici sabiti içerir:  
  
 [!code-csharp[Trin_VstcoreTroubleshootingWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreTroubleshootingWordCS/ThisDocument.cs#2)]
 [!code-vb[Trin_VstcoreTroubleshootingWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreTroubleshootingWordVB/ThisDocument.vb#2)]  
  
 Bu kullanımı **içeri aktarmalar**/**kullanarak** Office Word veya Excel niteleyicisi sınıflarıyla başvurular örneğin ayırt gerektirir:  
  
 [!code-csharp[Trin_VstcoreTroubleshootingWord#3](../vsto/codesnippet/CSharp/Trin_VstcoreTroubleshootingWordCS/ThisDocument.cs#3)]
 [!code-vb[Trin_VstcoreTroubleshootingWord#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreTroubleshootingWordVB/ThisDocument.vb#3)]  
  
 Niteleyici olmayan bir bildirim örneğin kullanırsanız hataları alırsınız:  
  
 [!code-csharp[Trin_VstcoreTroubleshootingWord#4](../vsto/codesnippet/CSharp/Trin_VstcoreTroubleshootingWordCS/ThisDocument.cs#4)]
 [!code-vb[Trin_VstcoreTroubleshootingWord#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreTroubleshootingWordVB/ThisDocument.vb#4)]  
  
 Word veya Excel ad alanı içe aktardıktan ve onun içindeki tüm sınıflara erişiminiz olsa bile, tüm türleriyle Word veya Excel ad alanı belirsizliğini kaldırmak için tam olarak nitelemek gerekir.  
  
##  <a name="building"></a>Proje oluşturma  
 Office projeleri oluşturma sırasında şu hatalarla karşılaşabilirsiniz.  
  
### <a name="cannot-build-a-document-level-project-that-is-based-on-a-document-with-restricted-permissions"></a>Sınırlı izinlere sahip bir belge dayalı bir belge düzeyi proje oluşturamaz  
 Belge sınırlı izinlere sahipse, visual Studio belge düzeyi projelerine oluşturamaz. Projeniz sınırlı izinlere sahip bir belge içeriyorsa, proje derlenmez ve aşağıdaki iletiyi alacak **hata listesi** penceresi.  
  
 "Özelleştirme ekleme başarısız oldu."  
  
 Sınırlı izinlere sahip bir belge dahil etmek istiyorsanız, geliştirmek ve çözümü derleme sırasında Kısıtlamasız belge kullanın. Ardından, Çözümü yayımladıktan sonra kısıtlı izinleri yayımlama konumu belgeye uygulanır.  
  
### <a name="compiler-errors-occur-after-a-namedrange-control-is-deleted"></a>NamedRange denetimi silindikten sonra derleyici hataları oluşur.  
 Silerseniz bir <xref:Microsoft.Office.Tools.Excel.NamedRange> denetim etkin çalışma sayfasında otomatik olarak oluşturulan kodu Tasarımcısı'nda olmayan bir çalışma kitabından kaldırılmaması projenizden ve derleyici hataları oluşabilir. Kod kaldırılır emin olmak için her zaman içeren çalışma seçmelisiniz <xref:Microsoft.Office.Tools.Excel.NamedRange> denetimi silmeden önce etkin çalışma yapmak için denetim. Denetim sildiğinizde otomatik olarak oluşturulan kodu silinmez, kodu çalışma etkinleştirme ve böylece çalışma değiştirilmiş olarak işaretlenmiş hale bir değişiklik yapmadan silmek Tasarımcı neden olabilir. Projeyi yeniden kod kaldırılır.  
  
##  <a name="debugging"></a>Projelerde hata ayıklama  
 Office projelerinde hata ayıklama işlemi yaparken aşağıdaki hatalarla karşılaşabilirsiniz.  
  
### <a name="prompt-to-uninstall-appears-when-you-publish-and-install-a-solution-on-the-development-computer"></a>Yayımlama ve bir çözüm geliştirme bilgisayarınızda yüklediğinizde kaldırmak için istemi belirir.  
 Office çözümünü hata ayıklamasını yaparken, aşağıdaki hatayı görebilirsiniz.  
  
 "Başka bir sürümü yüklü olan ve bu konumdan yükseltilemez özelleştirme yüklenemez."  
  
 Bu hata, önceden yayımlanmış ve Office çözümü geliştirme bilgisayarınızda yüklü olduğunu gösterir. Çözüm hata ayıklama önce iletiyi görünmesini engellemek için çözümü bilgisayarda yüklü programlar listesinde kaldırın. Alternatif olarak, yayımlanan çözüm yüklemesini test etmek için geliştirme bilgisayarınızda başka bir kullanıcı hesabı oluşturabilirsiniz.  
  
### <a name="document-level-projects-created-at-unc-network-locations-do-not-run-from-visual-studio"></a>Belge düzeyi projelerine UNC ağ konumlarında oluşturulan Visual Studio'dan çalıştırma  
 Excel veya UNC ağ konumunda Word için belge düzeyi projesi oluşturursanız, Excel veya Word'den güvenilir konumlar listesinde belgenin konumu eklemeniz gerekir. Aksi takdirde, çalıştırmak veya Visual Studio projesinde hata ayıklama çalıştığınızda özelleştirme yüklenmeyecek. Güvenilen konumları hakkında daha fazla bilgi için bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
### <a name="threads-are-not-stopped-correctly-after-debugging"></a>Hata ayıklama sonra iş parçacıkları doğru durdurulmaz  
 Visual Studio'da Office projeleri programı doğru kapatmak hata ayıklayıcı sağlar adlandırma bir iş parçacığı izleyin. İş parçacığı çözümünüzde oluşturursanız, her iş parçacığı hata ayıklama durdurduğunuzda, bu iş parçacıkları doğru şekilde işlenir emin olmak için VSTA_ önekiyle adlandırmanız gerekir. Örneğin, ayarlayabilir `Name` ağ olayını bekler bir iş parçacığı özelliğinin **VSTA_NetworkListener**.  
  
### <a name="cannot-run-or-debug-any-office-solution-on-the-development-computer"></a>Çalıştıramaz veya herhangi bir Office çözümü geliştirme bilgisayarındaki hata ayıklama  
 Çalıştırma veya bir Office proje geliştirme bilgisayarınızda geliştirmek, aşağıdaki hata iletisini görebilirsiniz.  
  
 "Uygulama etki alanı oluşturulamadı çünkü özelleştirme yüklenemedi."  
  
 Visual Studio Fusion, .NET Framework derleme yükleyicisi Office çözümlerini yüklemeden önce derlemeleri önbelleğe almak için kullanır. Visual Studio Fusion önbelleği yazma ve yeniden deneyin emin olun. Daha fazla bilgi için bkz: [gölge kopyalama derlemeleri](/dotnet/framework/app-domains/shadow-copy-assemblies).  
  
### <a name="error-when-stopping-the-debugger-in-a-document-level-project-after-using-edit-and-continue"></a>Belge düzeyi projede hata ayıklayıcı kullandıktan sonra durdururken hata Düzenle ve devam et  
 Düzenle ve devam et proje kesme modundayken bir belge düzeyi projesindeki kod Excel veya Word için değişiklik için kullanırsanız, hata ayıklayıcı sonradan durdurursanız, aşağıdaki hata iletisini içeren bir iletişim kutusu görebilirsiniz.  
  
 ", Geçerli durumunda işlem sonlandırılıyor veri ve sistem kararsızlığına kaybı dahil istenmeyen sonuçlara neden olabilir."  
  
 Tıklattığınız olup **Evet** veya **Hayır** iletişim kutusu, Visual Studio Excel veya Word'den işlemi sonlandırır ve hata ayıklayıcısı durdurur. Bu iletişim kutusu görüntülenmeden projenin hata ayıklamasını durdurmak için Excel veya Word doğrudan yerine Visual Studio'da hata ayıklamayı durdurma çıkın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde sorun giderme](../vsto/troubleshooting-office-solutions.md)   
 [Office çözüm güvenliğinde sorunu giderme](../vsto/troubleshooting-office-solution-security.md)   
 [Office Çözümü Dağıtımında Sorunu Giderme](../vsto/troubleshooting-office-solution-deployment.md)  
  
  