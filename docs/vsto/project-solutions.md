---
title: Proje çözümleri
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [Office development in Visual Studio], Project
- Office solutions [Office development in Visual Studio], Project
- Project [Office development in Visual Studio]
- templates [Office development in Visual Studio], Project
- Office projects [Office development in Visual Studio], Project
- solutions [Office development in Visual Studio], Project
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c3364c778b8dfc290ef06b7daa5ba063ac31f3db
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692606"
---
# <a name="project-solutions"></a>Proje çözümleri
  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] Microsoft Office Project için VSTO eklentileri oluşturma için kullanabileceğiniz proje şablonları sağlar. VSTO eklentileri proje otomatikleştirmek, proje özelliklerini genişletmek veya Project kullanıcı arabirimi (UI) özelleştirmek için kullanabilirsiniz.  
  
 VSTO eklentileri hakkında daha fazla bilgi için bkz: [VSTO eklentileri programlamaya başlamak](../vsto/getting-started-programming-vsto-add-ins.md) ve [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md). Microsoft Office ile programlamada yeniyseniz, bkz: [başlama &#40;Visual Studio'da Office geliştirme&#41;](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 [!INCLUDE[appliesto_projallapp](../vsto/includes/appliesto-projallapp-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="automate-project-by-using-the-project-object-model"></a>Project nesne modelini kullanarak proje otomatikleştirme  
 Proje nesne modeli proje otomatikleştirmek için kullanabileceğiniz birçok türü ortaya çıkarır. Bu tür program aracılığıyla oluşturma ve bir Project'te değiştirme gibi genel görevleri gerçekleştirmek için kod yazma etkinleştirin.  
  
 Bir VSTO Eklentiden Project nesne modeli erişmek için `Application` alanını `ThisAddIn` projenizdeki sınıfı. `Application` Alan döndürür bir `Microsoft.Office.Interop.MsProject.Application` proje geçerli örneği temsil eden nesne. Daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 Proje nesne modelini çağırdığınızda, proje için birincil birlikte çalışma derlemesindeki sağlanan türleri kullanabilirsiniz. Birincil birlikte çalışma derlemesi yönetilen kod için VSTO eklentisi ve proje COM nesne modeli arasında bir köprü gibi davranır. Proje birincil birlikte çalışma derlemesi içindeki tüm türler tanımlanan `Microsoft.Office.Interop.MSProject` ad alanı. Birincil birlikte çalışma derlemeleri hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) ve [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="use-the-project-object-model-documentation"></a>Proje nesne modeli belgeleri kullanın  
 Proje nesne modeli hakkında tam bilgi için Project VBA nesne modeli başvurusu başvurabilir. Visual Basic for Applications (VBA) kodundaki sunulur gibi VBA nesne modeli başvurusu projesi nesne modeli belgeler. Daha fazla bilgi için bkz: [Project 2010 nesne modeli başvurusu](http://go.microsoft.com/fwlink/?LinkId=199771).  
  
 Tüm nesneleri ve VBA nesne modeli başvurusu üyeleri türleri ve üyeleri proje birincil birlikte çalışma derlemesi (PIA) karşılık gelir. VBA nesne modeli başvurusu Takvim nesnesinde Örneğin, karşılık gelen `Microsoft.Office.Interop.MSProject.Calendar` proje PIA yazın. VBA nesne modeli başvurusu kod örnekleri çoğu özellikleri, yöntemleri ve olayları sağlasa da, bunları kullanarak oluşturduğunuz proje VSTO eklenti projesindeki kullanmak istiyorsanız, Visual Basic veya Visual C# bu başvurusu VBA kodu çevrilmelidir Visual Studio.  
  
> [!NOTE]  
>  Şu anda proje birincil birlikte çalışma derlemesi için başvuru belgesi yoktur.  
  
### <a name="infrastructure-types-in-the-project-primary-interop-assembly"></a>Proje birincil birlikte çalışma derlemesindeki altyapı türler  
 Proje PIA kullanan kodu yazarken VBA başvurusunda açıklanmayan birçok tür fark edebilirsiniz. Bu ek türler proje COM tabanlı nesne modelinde yönetilen kod için çevir Yardım, kodunuzda doğrudan kullanılmak üzere tasarlanmamıştır.  
  
 Daha fazla bilgi için bkz: [sınıflar ve arabirimler Office birincil birlikte çalışma derlemeleri genel bakış](http://go.microsoft.com/fwlink/?LinkId=189592).  
  
## <a name="customize-the-user-interface-of-project"></a>Projenin kullanıcı arabirimini özelleştirme  
 Proje UI aşağıdaki yollarla özelleştirebilirsiniz.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Proje Şeritte özel sekmeler ekleme|[Şerite Genel Bakış](../vsto/ribbon-overview.md)|  
  
 Project UI ve diğer Microsoft Office uygulamaları özelleştirme hakkında daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İzlenecek yol: ilk VSTO eklentinizi proje oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [VSTO eklentileri programlama kullanmaya başlama](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Project 2010 ve Project Server 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199016)  
  
  