---
title: Office projelerinde hata ayıklama
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel projects [Office development in Visual Studio], debugging
- Word projects [Office development in Visual Studio], debugging
- Outlook [Office development in Visual Studio], debugging
- debugging [Office development in Visual Studio], Outlook projects
- Office projects [Office development in Visual Studio], debugging
- Outlook [Office development in Visual Studio], projects
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e9ce3b064f97c2a04b8d7483080e260105aebab9
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="debug-office-projects"></a>Office projelerinde hata ayıklama
  Aynı Microsoft kullanarak Office projelerinde ayıklayabilirsiniz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] diğer için kullandığınız araçları [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projeleri. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] hata ayıklayıcı, kesme noktaları ekleme ve değişkenleri görüntüleme olanağı gibi özellikleri **Yereller** penceresinde, Office projelerinde hata ayıklama işlemi yaparken de kullanılabilir. Hakkında daha fazla bilgi için [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] hata ayıklama araçları, bkz: [Visual Studio'da hata ayıklama](/visualstudio/debugger/debugging-in-visual-studio).  
  
> [!TIP]  
>  Hata ayıklama işlemini basitleştirmek için derleme ve hata ayıklama önce Office uygulamasının açık tüm örneklerini kapatın.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="start-and-stop-the-debugger"></a>Hata ayıklayıcı durdurup başlatın  
 Diğer hata ayıklamayı başlatmak gibi Office projesinde hata ayıklamayı Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projeleri; Örneğin, basabilirsiniz **F5** anahtarı. Bir VSTO eklenti projesi hata ayıklama başlattığınızda, hedeflenen Office uygulaması için yeni bir işlem başlatıldı ve VSTO eklentisi yüklenir.  
  
 Belge düzeyi projede hata ayıklamaya başladığınızda, belge veya çalışma kitabı yeni bir Word veya Excel işleminde açılır.  
  
 Hata ayıklayıcıyı durdurduğunuzda, hata ayıklayıcı uygulama işleminin beklenmedik şekilde sonlandırır veya kullanımdan çıkarmak için hata ayıklayıcıyı varsa ayırır. Sonlandırılmış Office uygulama işleminin açık olan diğer tüm belgeler uyarmadan kapalı olduğundan ve kaydedilmeyen tüm değişiklikler kaybolur. Bu, tüm belgelerin veya hata ayıklayıcı çalışırken, açık olan çalışma kitaplarını içerebilir.  
  
 Genellikle, böylece Office uygulaması normal bir şekilde çıkabilirsiniz işleminden hata ayıklayıcı durdurmadan önce ayrılmak daha iyidir. Hala açık bir belge veya çalışma sayfası ile hata ayıklayıcıyı durdurduktan sonra iş istiyorsanız aynı zamanda işleminden önce ayırabilirsiniz.  
  
 Word için belge düzeyi özelleştirme ayıkladığınız, art arda hata ayıklamayı durdurma ve aniden kapanmasına neden bozulmasını Normal şablon neden olabilir. Bu olursa, bozulmuş Normal şablonunu silebilirsiniz ve otomatik olarak Word bir sonraki açışınızda yeniden. Bununla birlikte, Normal şablonunda kaydedilmiş makroların yeniden oluşturulmaz.  
  
### <a name="debug-office-2013-vsto-add-ins-by-using-either-office-2013-or-office-2016"></a>Office 2013 veya Office 2016 kullanarak Office 2013 VSTO eklentileri hata ayıklama  
 Visual Studio 2015 kullanıyorsanız ve Office yüklü yan yana her iki sürümü varsa, Visual Studio Office 2016 başlatır. Visual Studio, Visual Studio 2013 kullanıyorsanız, Office 2013 başlatır.  
  
 VSTO eklentinizi Office (2013 veya 2016) açık farklı bir sürümünü kullanarak hata ayıklama istiyorsanız **Proje Tasarımcısı**hem de **hata ayıklama** sekmesinde, seçin **başlangıç dış program**seçenek düğmesi. Ardından, uygun Office uygulaması yürütülebilir konuma göz atın.  
  
## <a name="f10-and-f11-behavior"></a>F10 ve F11 davranışı  
 Office projesinde hata ayıklamayı başlattığınızda **F10** ve **F11** diğer Visual Basic veya C# projelerinde hata ayıklama başlattığınızda olarak aynı davranışı sahip değil. Visual Basic veya C# projelerinde hata ayıklayıcı ana işlev durdurur; Office projelerinde Visual Studio Office uygulamasının main işlevi üzerinde denetime sahip değil. Ancak, hata ayıklama sırasında **F10** ve **F11** Visual Basic ve Visual C# projeleri olduğu gibi aynı işlevleri vardır.  
  
## <a name="display-exceptions"></a>Özel durumları görüntüleme  
 Yönetilen kod yolu nedeniyle etkileşim yönetilmeyen kod ile Visual Studio, Microsoft Office uygulamaları tarafından oluşturulan hataları görüntülemez. Örneğin, bir VSTO Visual Studio'da Office geliştirme araçlarını kullanarak oluşturduğunuz eklentisi bir özel durum oluşturursa, Microsoft Office uygulama hata görüntülemeden devam eder. Bu hataları görmek için ortak dil çalışma zamanı özel durumları ayırmak için hata ayıklayıcı ayarlayın. Daha fazla bilgi için bkz: [özel durumları hata ayıklayıcısı ile yönetme](/visualstudio/debugger/managing-exceptions-with-the-debugger).  
  
 Ortak dil çalışma zamanı özel durumları ayırmak için hata ayıklayıcı ayarlarsanız, tüm özel durumları şimdi işlediğiniz ve bazı ilk fırsat özel durumlar çalışma zamanının kendisinden, hangi projeniz için uygun olmayabilir dahil olmak üzere, hata ayıklayıcı içine çalışmamasına neden olur. Msosec bulunmamasını hataları her projede görünür ancak yoksaymak güvenlidir. Msosec özel durumları çözümünüzü etkilemez.  
  
 Aynı zamanda **deneyin... Catch** deyimleri yöntemlerinizi özel durumları yakalamak için geçici.  
  
 Varsayılan olarak, Visual Studio değil görüntü sadece zamanında hata ayıklama hataları Office projeleri için de yapar; Ancak, ortaya hataları görebilmeniz için bu özelliği etkinleştirebilirsiniz. Daha fazla bilgi için bkz: [sadece zaman içinde Visual Studio'da hata ayıklamayı](/visualstudio/debugger/just-in-time-debugging-in-visual-studio).  
  
## <a name="command-line-arguments"></a>Komut satırı bağımsız değişkenleri  
 Varsa **eylemi Başlat** üzerinde **hata ayıklama** özellik sayfası ayarlandığında **başlangıç projesi**, Visual Studio kullanmayan komut satırı bağımsız değişkenleri, projenin hata ayıklama sırasında olsa bile başlatma seçenekleri gibi komut satırı bağımsız değişkenleri belirtildi. Hata ayıklama başlattığınızda komut satırı bağımsız değişkenlerini kullanmak istiyorsanız, seçmelisiniz bir **eylemi Başlat** dışında **başlangıç projesi**.  
  
## <a name="source-control"></a>Kaynak denetimi  
 Hata ayıklama özellikleri paylaşılamaz kaynak denetimi altında birden çok kullanıcı. Visual Basic ve C# projeleri, kullanıcıya özel dosyada hata ayıklama özelliklerini depolar (*ProjectName*. vbproj.user veya *ProjectName*. csproj.user), ve bu dosya kaynak denetimi altında değil. Birden çok kişi hata ayıklama, her kişi hata ayıklama özelliklerini el ile girmeniz gerekir.  
  
## <a name="debug-cached-datasets-in-a-document-level-project"></a>Önbelleğe alınan veri kümelerini bir belge düzeyi projede hata ayıklama  
 Her zaman bir projeyi derleme, veri kümesi boşaltılır ve yeniden. Önbelleğe alınan bir veri kümesi hata ayıklama istiyorsanız, Visual Studio dışında belgeyi açın ve ardından hata ayıklayıcı ekleyin.  
  
## <a name="debug-word-document-projects-based-on-the-word-97-2003-document-doc-format"></a>Hata ayıklama Word belgesi projeleri Word 97-2003 belgeyi temel alarak (* .doc) biçimi  
 Word 97-2003 belgeyi temel alarak bir Word belgesi proje hata ayıklamak için (*/*.doc *) biçimi, proje klasöründen güvenilir klasör listesine eklemeniz gerekir. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [belgelere güven verme](../vsto/granting-trust-to-documents.md).  
  
## <a name="debug-disabled-add-ins"></a>Hata ayıklama eklentileri devre dışı  
 Microsoft Office uygulamaları VSTO beklenmedik bir şekilde davranan eklentileri devre dışı bırakabilirsiniz. Microsoft Office uygulama VSTO sorunlu kodun uygulama başladığında her zaman yüklenmesini engellemek için eklentileri devre dışı bırakır. Ancak, bu da tipik hata ayıklama sırasında beklenmeyen davranışlara neden kolaydır. VSTO eklentileri yeniden etkinleştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir VSTO devre dışı bırakılmış eklentiyi yeniden etkinleştirme](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md).  
  
 Microsoft Office uygulamaları VSTO eklentileri için kullandığınız devre dışı bırakmanın iki tür vardır: sabit devre dışı bırakma ve yazılım devre dışı bırakma.  
  
### <a name="hard-disabling"></a>Sabit devre dışı bırakma  
 Bir VSTO eklentisi uygulamanın beklenmedik şekilde kapanmasına neden olduğunda sabit devre dışı bırakma ortaya çıkabilir. Hata ayıklayıcıyı, ayrıca geliştirme bilgisayarınızda ortaya çıkabilir <xref:Microsoft.Office.Tools.AddIn.Startup> VSTO eklentinizi olay işleyicisini yürütülüyor. Bir VSTO eklenti sabit devre dışı olduğunda görünür **devre dışı öğeler** uygulama listesinde.  
  
 Sabit bir Office uygulamasında bir VSTO Visual Studio'da Office geliştirme araçlarını kullanarak oluşturduğunuz eklenti devre dışı bırakırsa yalnızca VSTO eklenti hataya neden, uygulamayı devre dışı bırakır. Diğer VSTO o Office uygulaması için Visual Studio'da Office geliştirme araçları kullanılarak oluşturulan eklentileri yüklemeye devam eder.  
  
### <a name="soft-disabling"></a>Yumuşak devre dışı bırakma  
 Bir VSTO eklenti uygulamanın beklenmedik şekilde kapanmasına neden olmaz ve bir hata üretir yumuşak devre dışı bırakma ortaya çıkabilir. Sırasında işlenmeyen bir özel durum oluşturursa Örneğin, bir uygulama yumuşak VSTO eklenti devre dışı bırakabilir <xref:Microsoft.Office.Tools.AddIn.Startup> olay işleyicisi yürütülüyor. Bir VSTO eklenti yumuşak devre dışı olduğunda görünür **etkin olmayan uygulama eklentileri** uygulama ve uygulama listesinde değerini değiştirir **LoadBehavior** VSTO için kayıt defteri girdisi Kaldırılmış olduğunu belirtmek için eklenti. Hakkında daha fazla bilgi için **LoadBehavior** kayıt defteri girdisi bkz [VSTO eklentileri için kayıt defteri girişleri](../vsto/registry-entries-for-vsto-add-ins.md).  
  
## <a name="troubleshoot-installation-errors-by-using-the-event-viewer"></a>Olay Görüntüleyicisi'ni kullanarak yükleme hatalarını giderme  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] İletileri Windows Olay Görüntüleyicisi'ni yüklediğinizde veya kaldırdığınızda Office çözümleri olmadığında oluşan tüm özel durumları için yazar. Bu iletiler, yükleme ve dağıtım sorunlarını gidermek için kullanabilirsiniz.  
  
## <a name="troubleshoot-startup-errors-by-using-a-log-file-and-error-messages"></a>Günlük dosyası ve hata iletileri kullanarak başlatma hataları giderme  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Günlüğe başlatma sırasında oluşan tüm hataları dosya veya her hata bir ileti kutusu görüntüleme yazabilirsiniz. Varsayılan olarak, bu seçenekleri devre dışı bırakılmıştır. Ortam değişkenleri oluşturarak seçenekleri açabilirsiniz.  
  
 Her bir hata iletişim kutusunda görüntülenecek adlı bir ortam değişkeni oluşturma `VSTO_SUPPRESSDISPLAYALERTS` ve 0 (sıfır) olarak ayarlayın. Ortam değişkeni silerek veya 1 (bir) olarak ayarlayarak iletileri gizleyebilirsiniz.  
  
 Hataları bir günlük dosyasına yazmak için adlı bir ortam değişkeni oluşturma `VSTO_LOGALERTS` ve 1 (bir) olarak ayarlayın. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] VSTO eklenti için dağıtım bildirimi içeren klasöre veya belge veya özelleştirme ile ilişkili olan bir çalışma kitabı içeren klasörü günlük dosyası oluşturur. Başarısız olursa, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yerel günlük dosyası oluşturur *% TEMP %* klasör. Uygulama düzeyi VSTO eklentileri için varsayılan addır *eklenti adı*. vsto.log. Belge düzeyi projelerine için günlük dosyasının adıdır *belge adı*. *Uzantı*ExcelWorkbook1.xlsx.log gibi .log. Günlük kaydı hataları durdurmak için ortam değişkenini silin veya 0 (sıfır) olarak ayarlayın.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Nasıl yapılır: bir VSTO devre dışı bırakılmış eklentiyi yeniden etkinleştirme](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)  
  
  