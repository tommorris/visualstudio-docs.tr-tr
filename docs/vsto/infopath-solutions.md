---
title: InfoPath çözümleri
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f61607f904740a48bc73d7b4b310e36b3894df17
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="infopath-solutions"></a>InfoPath çözümleri
  Visual Studio Proje şablonları Microsoft Office InfoPath 2013 ve InfoPath 2010 için VSTO eklentileri oluşturma için kullanabileceğiniz sağlar. InfoPath Office 2016'da kullanılabilir değil.  
  
> [!NOTE]  
>  Office 2016 yüklediğiniz olsa bile, yine bir VSTO eklenti InfoPath için oluşturabilirsiniz. Yalnızca Office 2016 ile InfoPath 2013 veya Office 2013 yan yana yükleyin.  
  
 [!INCLUDE[appliesto_infoallapp](../vsto/includes/appliesto-infoallapp-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). Office eklentileri VSTO eklentileri ve çözümlerle karşılaştırıldığında küçük bir yer olan ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
 VSTO eklentileri InfoPath için VSTO eklentileri diğer Microsoft Office uygulamaları için benzer. Bu tür çözümler uygulama tarafından yüklenen bir derleme oluşur. Son kullanıcıların hangi veya formunun olsun bu derleme işlevselliği için açık şablonudur erişebilir. VSTO eklentileri hakkında daha fazla bilgi için bkz: [VSTO eklentileri programlamaya başlamak](../vsto/getting-started-programming-vsto-add-ins.md) ve [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md).  
  
> [!NOTE]  
>  Visual Studio 2015, Visual Studio'nun önceki sürümleri sağlanan InfoPath form şablon projelerini içermez. Ayrıca, açın veya Visual Studio'nun önceki bir sürümde oluşturulmuş bir InfoPath form şablon projesini düzenlemek için Visual Studio 2015 kullanamazsınız. Ancak, açın ve bir InfoPath form şablon projesini Visual Studio Tools for Applications kullanarak düzenleyin. Daha fazla bilgi için bkz: [InfoPath 2010 VSTO 2008 projelerinde ile çalışırsınız.](http://go.microsoft.com/fwlink/?LinkID=218903).  
  
## <a name="automate-infopath-by-using-an-add-in"></a>Bir eklenti kullanarak InfoPath otomatikleştirme  
 Bir Office VSTO Visual Studio'da Office geliştirme araçlarını kullanarak oluşturduğunuz eklenti gelen InfoPath nesne modeline erişmek için `Application` alanını `ThisAddIn` projenizdeki sınıfı. `Application` Alan döndürür bir <xref:Microsoft.Office.Interop.InfoPath.Application> InfoPath geçerli örneği temsil eden nesne. Daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 Bir VSTO eklentiden InfoPath nesne modelini çağırdığınızda, InfoPath için birincil birlikte çalışma derlemesindeki sağlanan türleri kullanabilirsiniz. Birincil birlikte çalışma derlemesi için VSTO eklentisi yönetilen kodda ve InfoPath COM nesne modelinde arasında bir köprü gibi davranır. InfoPath birincil birlikte çalışma derlemesi içindeki tüm türler tanımlanan <xref:Microsoft.Office.Interop.InfoPath> ad alanı. InfoPath birincil birlikte çalışma derlemesi hakkında daha fazla bilgi için bkz: [Microsoft Office InfoPath hakkında birincil birlikte çalışma derlemesi](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72). Genel olarak, birincil birlikte çalışma derlemeleri hakkında daha fazla bilgi için bkz [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) ve [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="customize-the-user-iterface-of-infopath-by-using-an-add-in"></a>Bir eklenti kullanarak InfoPath'in kullanıcı iterface özelleştirme  
 InfoPath için VSTO eklenti oluşturmak için birçok farklı kullanıcı Arabirimi özelleştirme seçeneğiniz vardır. Aşağıdaki tabloda bu seçeneklerden bazısı listeler.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Özel görev bölmesini oluşturun.|[Özel görev bölmeleri](../vsto/custom-task-panes.md)|  
|InfoPath Şeritte özel sekmeler ekleme.|[InfoPath için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-infopath.md)|  
  
 InfoPath UI ve diğer Microsoft Office uygulamaları özelleştirme hakkında daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Microsoft Office InfoPath birincil birlikte çalışma derleme hakkında](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72)   
 [VSTO eklentileri programlama kullanmaya başlama](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [InfoPath 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199012)  
  
  