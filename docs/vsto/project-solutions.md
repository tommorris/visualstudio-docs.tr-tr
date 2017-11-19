---
title: "Proje çözümleri | Microsoft Docs"
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
- projects [Office development in Visual Studio], Project
- Office solutions [Office development in Visual Studio], Project
- Project [Office development in Visual Studio]
- templates [Office development in Visual Studio], Project
- Office projects [Office development in Visual Studio], Project
- solutions [Office development in Visual Studio], Project
ms.assetid: 4ce92269-eb6d-44aa-bee3-6d38ec9995f9
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 584f98e9fbe6a8883039cad03e6b0782d225b8bb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="project-solutions"></a>Proje Çözümleri
  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]Microsoft Office Project için VSTO eklentileri oluşturma için kullanabileceğiniz proje şablonları sağlar. VSTO eklentileri proje otomatikleştirmek, proje özelliklerini genişletmek veya Project kullanıcı arabirimi (UI) özelleştirmek için kullanabilirsiniz.  
  
 VSTO eklentileri hakkında daha fazla bilgi için bkz: [başlatılan programlama VSTO alma eklentileri](../vsto/getting-started-programming-vsto-add-ins.md) ve [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md). Microsoft Office ile programlamada yeniyseniz, bkz: [Başlarken &#40; Visual Studio &#41; Office geliştirme](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 [!INCLUDE[appliesto_projallapp](../vsto/includes/appliesto-projallapp-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="automating-project-by-using-the-project-object-model"></a>Project nesne modelini kullanarak proje otomatikleştirme  
 Proje nesne modeli proje otomatikleştirmek için kullanabileceğiniz birçok türü ortaya çıkarır. Bu tür program aracılığıyla oluşturma ve bir Project'te değiştirme gibi genel görevleri gerçekleştirmek için kod yazma etkinleştirin.  
  
 Bir VSTO Eklentiden Project nesne modeli erişmek için `Application` alanını `ThisAddIn` projenizdeki sınıfı. `Application` Alan Proje geçerli örneği temsil eden bir Microsoft.Office.Interop.MSProject.Application nesnesini döndürür. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 Proje nesne modelini çağırdığınızda, proje için birincil birlikte çalışma derlemesindeki sağlanan türleri kullanabilirsiniz. Birincil birlikte çalışma derlemesi yönetilen kod için VSTO eklentisi ve proje COM nesne modeli arasında bir köprü gibi davranır. Proje birincil birlikte çalışma derlemesi içindeki tüm türler Microsoft.Office.Interop.MSProject ad alanında tanımlanır. Birincil birlikte çalışma derlemeleri hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) ve [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="using-the-project-object-model-documentation"></a>Proje Nesne Model belgelerini kullanma  
 Proje nesne modeli hakkında tam bilgi için Project VBA nesne modeli başvurusu başvurabilir. Visual Basic for Applications (VBA) kodundaki sunulur gibi VBA nesne modeli başvurusu projesi nesne modeli belgeler. Daha fazla bilgi için bkz: [Project 2010 nesne modeli başvurusu](http://go.microsoft.com/fwlink/?LinkId=199771).  
  
 Tüm nesneleri ve VBA nesne modeli başvurusu üyeleri türleri ve üyeleri proje birincil birlikte çalışma derlemesi (PIA) karşılık gelir. Örneğin, VBA nesne modeli başvurusu Takvim nesnesinde proje PIA Microsoft.Office.Interop.MSProject.Calendar türüne karşılık gelir. VBA nesne modeli başvurusu kod örnekleri çoğu özellikleri, yöntemleri ve olayları sağlasa da, bunları kullanarak oluşturduğunuz proje VSTO eklenti projesindeki kullanmak istiyorsanız, Visual Basic veya Visual C# bu başvurusu VBA kodu çevrilmelidir Visual Studio.  
  
> [!NOTE]  
>  Şu anda proje birincil birlikte çalışma derlemesi için başvuru belgesi yoktur.  
  
### <a name="infrastructure-types-in-the-project-primary-interop-assembly"></a>Proje birincil birlikte çalışma derlemesindeki altyapı türler  
 Proje PIA kullanan kodu yazarken VBA başvurusunda açıklanmayan birçok tür fark edebilirsiniz. Bu ek türler proje COM tabanlı nesne modelinde yönetilen kod için çevir Yardım, kodunuzda doğrudan kullanılmak üzere tasarlanmamıştır.  
  
 Daha fazla bilgi için bkz:[genel bakış, sınıflar ve arabirimler Office birincil birlikte çalışma derlemeleri](http://go.microsoft.com/fwlink/?LinkId=189592).  
  
## <a name="customizing-the-user-interface-of-project"></a>Proje kullanıcı arabirimini özelleştirme  
 Proje UI aşağıdaki yollarla özelleştirebilirsiniz.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Proje Şeritte özel sekmeler ekleme|[Şerite Genel Bakış](../vsto/ribbon-overview.md)|  
  
 Project UI ve diğer Microsoft Office uygulamaları özelleştirme hakkında daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Proje için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [Başlarken VSTO eklentilerini programlama](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Project 2010 ve Project Server 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199016)  
  
  