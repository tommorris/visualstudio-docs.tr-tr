---
title: "İzlenecek yol: Proje için ilk VSTO eklentinizi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- Project [Office development in Visual Studio], creating your first project
- add-ins [Office development in Visual Studio], creating your first project
ms.assetid: da2b727e-6db8-4853-bf00-7afe0ef13213
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 391bd4bbdfe87f1bc00ac14356c61f988b8bf041
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-your-first-vsto-add-in-for-project"></a>İzlenecek yol: Proje için ilk VSTO eklentinizi oluşturma
  Bu kılavuzda nasıl Microsoft Office Project için VSTO eklenti oluşturulacağını gösterir. Bu tür bir çözüm içinde oluşturduğunuz özellikler uygulamanın kendisinin projeleri açık olan bağımsız olarak kullanılabilir. Daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_projallapp](../vsto/includes/appliesto-projallapp-md.md)]  
  
 Bu izlenecek yol aşağıdaki görevleri gösterir:  
  
-   Bir proje VSTO eklenti projesi oluşturma.  
  
-   Bir görev için yeni bir proje eklemek için proje nesne modelini kullanan kod yazma.  
  
-   Derleme ve test etmek için proje çalışıyor.  
  
-   VSTO eklenti artık otomatik olarak geliştirme bilgisayarınızda çalışmaması için tamamlanmış projeyi temizleme.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için aşağıdaki bileşenlere ihtiyacınız vardır:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Project_15_short](../vsto/includes/project-15-short-md.md)]veya [!INCLUDE[Project_14_short](../vsto/includes/project-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Projeyi Oluşturma  
  
#### <a name="to-create-a-new-project-in-visual-studio"></a>Visual Studio'da yeni bir proje oluşturmak için  
  
1.  Başlat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje**.  
  
3.  Şablonlar bölmesinde **Visual C#** veya **Visual Basic**, genişletin ve ardından **Office/SharePoint**.  
  
4.  Genişletilmiş altında **Office/SharePoint** düğümü, select **Office eklentileri** düğümü.  
  
5.  Proje şablonları listesinde seçin **Project 2010 Eklentisi** veya **proje 2013 eklenti**.  
  
6.  İçinde **adı** kutusuna **FirstProjectAddIn**.  
  
7.  **Tamam**'ı tıklatın.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]oluşturur **FirstProjectAddIn** proje ve açılır **ThisAddIn** Düzenleyicisi'nde kod dosyası.  
  
## <a name="writing-code-that-adds-a-new-task-to-a-project"></a>Bir projeye yeni bir görev ekler kod yazma  
 Ardından, kodu ThisAddIn kod dosyasına ekleyin. Yeni kod, bir projeye yeni bir görev eklemek için proje nesne modelini kullanır. Varsayılan olarak, aşağıdaki oluşturulmuş kodu ThisAddIn kod dosyasını içerir:  
  
-   Kısmi tanımının `ThisAddIn` sınıfı. Bu sınıf kodunuz için giriş noktası sağlar ve proje nesne modeline erişim sağlar. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md). Geri kalan `ThisAddIn` sınıfı değiştirmemeniz gereken gizli kod dosyasında tanımlanır.  
  
-   `ThisAddIn_Startup` Ve `ThisAddIn_Shutdown` olay işleyicileri. Bu olay işleyicileri proje yüklediğinde ve VSTO eklentinizi bellekten denir. Bu olay işleyicilerini VSTO eklentinizi yüklendiğinde başlatmak ve kaldırıldığında VSTO eklentinizi tarafından kullanılan kaynakları temizlemek için kullanın. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
#### <a name="to-add-a-task-to-a-new-project"></a>Bir görev için yeni bir proje eklemek için  
  
1.  ThisAddIn kod dosyasında aşağıdaki kodu ekleyin `ThisAddIn` sınıfı. Bu kod Microsoft.Office.Interop.MSProject.Application sınıfının NewProject olayı için bir olay işleyicisi tanımlar.  
  
     Kullanıcı yeni bir proje oluşturduğunda, bu olay işleyicisi projeye bir görev ekler.  
  
     [!code-vb[Trin_ProjectAddInTutorial#1](../vsto/codesnippet/VisualBasic/Trin_ProjectAddInTutorial/ThisAddIn.vb#1)]
     [!code-csharp[Trin_ProjectAddInTutorial#1](../vsto/codesnippet/CSharp/Trin_ProjectAddInTutorial/ThisAddIn.cs#1)]  
  
 Bu kod örneği projeyi değiştirmek için aşağıdaki nesneleri kullanır:  
  
-   `Application` Alanını `ThisAddIn` sınıfı. `Application` Alan Proje geçerli örneği temsil eden bir Microsoft.Office.Interop.MSProject.Application nesnesini döndürür.  
  
-   `pj` NewProject olay için olay işleyicisini parametresi. `pj` Parametresi projeyi temsil eden bir Microsoft.Office.Interop.MSProject.Project nesnesi değildir. Daha fazla bilgi için bkz: [proje çözümleri](../vsto/project-solutions.md).  
  
1.  C# kullanıyorsanız aşağıdaki kodu ekleyin `ThisAddIn_Startup` olay işleyicisi. Bu kod bağlayan `Application_Newproject` NewProject olayın olay işleyicisi.  
  
     [!code-csharp[Trin_ProjectAddInTutorial#2](../vsto/codesnippet/CSharp/Trin_ProjectAddInTutorial/ThisAddIn.cs#2)]  
  
-  
  
## <a name="testing-the-project"></a>Projeyi test etme  
 Derleme ve projeyi çalıştırın, yeni görev sonuçlanan yeni projede göründüğünü doğrulayın.  
  
#### <a name="to-test-the-project"></a>Projeyi test etmek için  
  
1.  Tuşuna **F5** oluşturun ve projenizin çalıştırın. Microsoft Project başlatır ve yeni boş bir proje otomatik olarak açar.  
  
     Projeyi derlerken kodunu projeyi derleme çıktı dosyasına dahil bütünleştirilmiş derlenir. Visual Studio ayrıca bulmak ve VSTO eklentisi yüklemek projenizi etkinleştirin kayıt defteri girdileri kümesini oluşturur ve VSTO eklenti çalıştırmak, geliştirici bilgisayarının güvenlik ayarlarını yapılandırır. Daha fazla bilgi için bkz: [Office çözümü oluşturma işlemine genel bakış](http://msdn.microsoft.com/en-us/a9d12e4f-c9ea-4a62-a841-c42b91f831ee).  
  
2.  Yeni bir görev boş projeye eklendiğini doğrulayın.  
  
3.  Aşağıdaki metni göründüğünü doğrulayın **görev adı** görev alanını.  
  
     **Bu metin, kod kullanarak eklendi.**  
  
4.  Microsoft Project kapatın.  
  
## <a name="cleaning-up-the-project"></a>Projeyi temizleme  
 Projeyi geliştirmeyi bitirdiğinizde VSTO eklenti derlemesi, kayıt defteri girdileri ve güvenlik ayarlarını Geliştirme bilgisayarınızdan kaldırın. Aksi halde, Microsoft Project geliştirme bilgisayarınızda her açtığınızda VSTO eklenti çalışacaktır.  
  
#### <a name="to-clean-up-your-project"></a>Projenizi temizlemek için  
  
1.  Visual Studio'da üzerinde **yapı** menüsünde tıklatın **temiz çözüm**.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bir temel VSTO eklenti projesi için oluşturduğunuza göre VSTO eklentileri aşağıdaki konulardan geliştirme hakkında daha fazla bilgi edinebilirsiniz:  
  
-   VSTO eklentileri proje için de gerçekleştirebileceğiniz genel programlama görevleri: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
-   Proje nesne modelini kullanma: [proje çözümleri](../vsto/project-solutions.md).  
  
-   Derleme ve VSTO eklentileri projesi için hata ayıklama: [Office çözümleri oluşturma](../vsto/building-office-solutions.md).  
  
-   Project için VSTO eklentileri dağıtma: [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Proje çözümleri](../vsto/project-solutions.md)   
 [Office çözümleri oluşturma](../vsto/building-office-solutions.md)   
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office Proje Şablonlarına Genel Bakış](../vsto/office-project-templates-overview.md)  
  
  