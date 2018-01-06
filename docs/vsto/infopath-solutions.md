---
title: "InfoPath çözümleri | Microsoft Docs"
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
- solutions [Office development in Visual Studio], InfoPath
- templates [Office development in Visual Studio], InfoPath
- InfoPath [Office development in Visual Studio]
- Office development in Visual Studio, InfoPath solutions
- projects [Office development in Visual Studio], InfoPath
- Office solutions [Office development in Visual Studio], InfoPath
- Office projects [Office development in Visual Studio], InfoPath
ms.assetid: 20ac6bee-b17f-4217-9f78-11304a11236a
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: da9cebf8d4c8a30821585160ff07edd6eae0cd7c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="infopath-solutions"></a>InfoPath Çözümleri
  Visual Studio Proje şablonları Microsoft Office InfoPath 2013 ve InfoPath 2010 için VSTO eklentileri oluşturma için kullanabileceğiniz sağlar. InfoPath Office 2016'da kullanılabilir değil.  
  
> [!NOTE]  
>  Office 2016 yüklediğiniz olsa bile, yine bir VSTO eklenti InfoPath için oluşturabilirsiniz. Yalnızca Office 2016 ile InfoPath 2013 veya Office 2013 yan yana yükleyin.  
  
 [!INCLUDE[appliesto_infoallapp](../vsto/includes/appliesto-infoallapp-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
 VSTO eklentileri InfoPath için VSTO eklentileri diğer Microsoft Office uygulamaları için benzer. Bu tür çözümler uygulama tarafından yüklenen bir derleme oluşur. Son kullanıcıların hangi veya formunun olsun bu derleme işlevselliği için açık şablonudur erişebilir. VSTO eklentileri hakkında daha fazla bilgi için bkz: [başlatılan programlama VSTO alma eklentileri](../vsto/getting-started-programming-vsto-add-ins.md) ve [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
> [!NOTE]  
>  Visual Studio 2015, Visual Studio'nun önceki sürümleri sağlanan InfoPath form şablon projelerini içermez. Ayrıca, açın veya Visual Studio'nun önceki bir sürümde oluşturulmuş bir InfoPath form şablon projesini düzenlemek için Visual Studio 2015 kullanamazsınız. Ancak, açın ve bir InfoPath form şablon projesini Visual Studio Tools for Applications kullanarak düzenleyin. Daha fazla bilgi için bkz: [VSTO 2008 projelerle InfoPath 2010 Çalışma.](http://go.microsoft.com/fwlink/?LinkID=218903).  
  
## <a name="automating-infopath-by-using-an-add-in"></a>Eklenti kullanarak InfoPath otomatikleştirme  
 Bir Office VSTO Visual Studio'da Office geliştirme araçlarını kullanarak oluşturduğunuz eklenti gelen InfoPath nesne modeline erişmek için `Application` alanını `ThisAddIn` projenizdeki sınıfı. `Application` Alan döndürür bir <xref:Microsoft.Office.Interop.InfoPath.Application> InfoPath geçerli örneği temsil eden nesne. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 Bir VSTO eklentiden InfoPath nesne modelini çağırdığınızda, InfoPath için birincil birlikte çalışma derlemesindeki sağlanan türleri kullanabilirsiniz. Birincil birlikte çalışma derlemesi için VSTO eklentisi yönetilen kodda ve InfoPath COM nesne modelinde arasında bir köprü gibi davranır. InfoPath birincil birlikte çalışma derlemesi içindeki tüm türler tanımlanan <xref:Microsoft.Office.Interop.InfoPath> ad alanı. InfoPath birincil birlikte çalışma derlemesi hakkında daha fazla bilgi için bkz: [hakkında Microsoft Office InfoPath birincil birlikte çalışma derlemesi](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72). Genel olarak, birincil birlikte çalışma derlemeleri hakkında daha fazla bilgi için bkz [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) ve [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="customizing-the-user-interface-of-infopath-by-using-an-add-in"></a>Eklenti kullanarak InfoPath kullanıcı arabirimini özelleştirme  
 InfoPath için VSTO eklenti oluşturmak için birçok farklı kullanıcı Arabirimi özelleştirme seçeneğiniz vardır. Aşağıdaki tabloda bu seçeneklerden bazısı listeler.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Özel görev bölmesini oluşturun.|[Özel Görev Bölmeleri](../vsto/custom-task-panes.md)|  
|InfoPath Şeritte özel sekmeler ekleme.|[InfoPath İçin Şerit Özelleştirme](../vsto/customizing-a-ribbon-for-infopath.md)|  
  
 InfoPath UI ve diğer Microsoft Office uygulamaları özelleştirme hakkında daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft Office InfoPath birincil birlikte çalışma derleme hakkında](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72)   
 [Başlarken VSTO eklentilerini programlama](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [InfoPath 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199012)  
  
  