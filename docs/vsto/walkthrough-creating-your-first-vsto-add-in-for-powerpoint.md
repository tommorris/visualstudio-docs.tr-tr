---
title: 'İzlenecek yol: PowerPoint için ilk VSTO eklentinizi oluşturma'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- PowerPoint [Office development in Visual Studio], creating your first project
- add-ins [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0f55ebded09782f6a6ab15ec5646778cc2b688b1
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845827"
---
# <a name="walkthrough-create-your-first-vsto-add-in-for-powerpoint"></a>İzlenecek yol: PowerPoint için ilk VSTO eklentinizi oluşturma
  Bu kılavuzda nasıl Microsoft Office PowerPoint için VSTO eklenti oluşturulacağını gösterir. Bu tür bir çözüm içinde oluşturduğunuz özellikler uygulamanın kendisinin sunuları açık olan bağımsız olarak kullanılabilir. Daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_pptallapp](../vsto/includes/appliesto-pptallapp-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   PowerPoint için PowerPoint VSTO eklenti projesi oluşturma.  
  
-   Her yeni slayta bir metin kutusu eklemek için PowerPoint nesne modelini kullanan kod yazma.  
  
-   Derleme ve test etmek için proje çalışıyor.  
  
-   VSTO eklenti artık otomatik olarak geliştirme bilgisayarınızda çalışır projeyi temizleme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   PowerPoint  
  
## <a name="create-the-project"></a>Projeyi oluşturma  
  
### <a name="to-create-a-new-project"></a>Yeni bir proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
3.  Şablonlar bölmesinde **Visual C#** veya **Visual Basic**, genişletin ve ardından **Office/SharePoint**.  
  
4.  Genişletilmiş altında **Office/SharePoint** düğümü, select **Office eklentileri** düğümü.  
  
5.  Proje şablonları listesinde bir PowerPoint VSTO eklenti projesini seçin.  
  
6.  İçinde **adı** kutusuna **FirstPowerPointAddIn**.  
  
7.  **Tamam**'ı tıklatın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] oluşturur **FirstPowerPointAddIn** proje ve açılır **ThisAddIn** Düzenleyicisi'nde kod dosyası.  
  
## <a name="write-code-that-adds-text-to-each-new-slide"></a>Her yeni slayta metin ekleyen kod yazma  
 Ardından, kodu ThisAddIn kod dosyasına ekleyin. Yeni kod, her yeni slayta bir metin kutusu eklemek için PowerPoint nesne modelini kullanır. Varsayılan olarak, aşağıdaki oluşturulmuş kodu ThisAddIn kod dosyasını içerir:  
  
-   Kısmi tanımının `ThisAddIn` sınıfı. Bu sınıf kodunuz için giriş noktası sağlar ve PowerPoint nesne modeline erişim sağlar. Daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md). Geri kalan `ThisAddIn` sınıfı değiştirmemeniz gereken gizli kod dosyasında tanımlanır.  
  
-   `ThisAddIn_Startup` Ve `ThisAddIn_Shutdown` olay işleyicileri. Bu olay işleyicileri PowerPoint yüklediğinde ve VSTO eklentinizi bellekten denir. Bu olay işleyicilerini VSTO eklentinizi yüklendiğinde başlatmak ve kaldırıldığında VSTO eklentinizi tarafından kullanılan kaynakları temizlemek için kullanın. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
### <a name="to-add-a-text-box-to-each-new-slide"></a>Her yeni slayta bir metin kutusu eklemek için  
  
1.  ThisAddIn kod dosyasında aşağıdaki kodu ekleyin `ThisAddIn` sınıfı. Bu kod için olay işleyicisini tanımlar <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.PresentationNewSlide> olayı <xref:Microsoft.Office.Interop.PowerPoint.Application> nesnesi.  
  
     Kullanıcı etkin sunuya yeni bir slayt eklediğinde, bu olay işleyicisi metin kutusuna yeni bir slayt üst kısmına ekler ve bazı metin metin kutusuna ekler.  
  
     [!code-vb[Trin_PowerPointAddInTutorial#1](../vsto/codesnippet/VisualBasic/Trin_PowerPointAddInTutorial/ThisAddIn.vb#1)]
     [!code-csharp[Trin_PowerPointAddInTutorial#1](../vsto/codesnippet/CSharp/Trin_PowerPointAddInTutorial/ThisAddIn.cs#1)]  
  
2.  C# kullanıyorsanız aşağıdaki kodu ekleyin `ThisAddIn_Startup` olay işleyicisi. Bu kod bağlanmak için gereken `Application_PresentationNewSlide` olay işleyicisi ile <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.PresentationNewSlide> olay.  
  
     [!code-csharp[Trin_PowerPointAddInTutorial#2](../vsto/codesnippet/CSharp/Trin_PowerPointAddInTutorial/ThisAddIn.cs#2)]  
  
 Her yeni slayta değiştirmek için aşağıdaki nesneler önceki kod örnekleri kullanın:  
  
-   `Application` Alanını `ThisAddIn` sınıfı. `Application` Alan döndürür bir <xref:Microsoft.Office.Interop.PowerPoint.Application> PowerPoint geçerli örneği temsil eden nesne.  
  
-   `Sld` İçin olay işleyicisini parametresinin <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.PresentationNewSlide> olay. `Sld` Parametresi bir <xref:Microsoft.Office.Interop.PowerPoint.Slide> yeni slayt temsil eden nesne. Daha fazla bilgi için bkz: [PowerPoint çözümleri](../vsto/powerpoint-solutions.md).  
  
## <a name="test-the-project"></a>Projeyi test  
 Derleme ve projeyi çalıştırın, metin kutusunun sunuya ekleme yeni slayt göründüğünü doğrulayın.  
  
### <a name="to-test-the-project"></a>Projeyi test etmek için  
  
1.  Tuşuna **F5** oluşturun ve projenizin çalıştırın.  
  
     Projeyi derlerken projesi için derleme çıktısı klasöründeki put bütünleştirilmiş kod derlenir. Visual Studio ayrıca bulup VSTO eklenti PowerPoint'i etkinleştirme kayıt defteri girdileri kümesini oluşturur ve geliştirme bilgisayarınızın VSTO çalıştırmak eklentiyi etkinleştirmek için güvenlik ayarlarını yapılandırır. Daha fazla bilgi için bkz: [yapı Office çözümleri](../vsto/building-office-solutions.md).  
  
2.  PowerPoint içinde yeni bir slayt etkin sunuya ekleyin.  
  
3.  Aşağıdaki metni yeni bir metin kutusu slayt üstündeki eklendiğini doğrulayın.  
  
     **Bu metin, kod kullanarak eklendi.**  
  
4.  PowerPoint kapatın.  
  
## <a name="clean-up-the-project"></a>Projeyi temizleyin  
 Projeyi geliştirmeyi bitirdiğinizde VSTO eklenti derlemesi, kayıt defteri girdileri ve güvenlik ayarlarını Geliştirme bilgisayarınızdan kaldırın. Aksi halde, PowerPoint geliştirme bilgisayarınızda her açtığınızda VSTO eklenti çalışacaktır.  
  
### <a name="to-clean-up-your-project"></a>Projenizi temizlemek için  
  
1.  Visual Studio'da üzerinde **yapı** menüsünde tıklatın **temiz çözüm**.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 PowerPoint için temel bir VSTO eklentisi oluşturduğunuza göre VSTO eklentileri aşağıdaki konulardan geliştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   PowerPoint için VSTO eklentileri gerçekleştirebileceğiniz genel programlama görevleri. Daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
-   PowerPoint nesne modelini kullanarak. Daha fazla bilgi için bkz: [PowerPoint çözümleri](../vsto/powerpoint-solutions.md).  
  
-   Kullanıcı Arabirimi, PowerPoint, örneğin, özelleştirme Şerite özel bir sekme ekleme veya kendi özel görev bölmesi oluşturma. Daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
-   Derleme ve PowerPoint için VSTO eklentileri hata ayıklama. Daha fazla bilgi için bkz: [yapı Office çözümleri](../vsto/building-office-solutions.md).  
  
-   PowerPoint için VSTO eklentileri dağıtma. Daha fazla bilgi için bkz: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [PowerPoint çözümleri](../vsto/powerpoint-solutions.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Office çözümünü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md)  
  
  