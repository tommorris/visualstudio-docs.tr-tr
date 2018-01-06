---
title: "PowerPoint çözümleri | Microsoft Docs"
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
- Office solutions [Office development in Visual Studio], PowerPoint
- templates [Office development in Visual Studio], PowerPoint
- solutions [Office development in Visual Studio], PowerPoint
- projects [Office development in Visual Studio], PowerPoint
- PowerPoint [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], PowerPoint
ms.assetid: 02ebad64-9fd3-495f-ab27-4f6206b3d6d2
caps.latest.revision: "46"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: dd03b3e14599535c99f8a8ddd17314ce7f0cc719
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="powerpoint-solutions"></a>PowerPoint Çözümleri
  Visual Studio Proje şablonları, Microsoft Office PowerPoint için VSTO eklentileri oluşturma için kullanabileceğiniz sağlar. VSTO eklentileri PowerPoint'i otomatikleştirmek, PowerPoint özelliklerini genişletmek veya PowerPoint kullanıcı arabirimini (UI) özelleştirmek için kullanabilirsiniz.  
  
 VSTO eklentileri hakkında daha fazla bilgi için bkz: [başlatılan programlama VSTO alma eklentileri](../vsto/getting-started-programming-vsto-add-ins.md) ve [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md). Microsoft Office ile programlamada yeniyseniz, bkz: [Başlarken &#40; Visual Studio &#41; Office geliştirme](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 [!INCLUDE[appliesto_pptallapp](../vsto/includes/appliesto-pptallapp-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [I: oluşturma nasıl bir eklenti için Microsoft PowerPoint?](http://go.microsoft.com/fwlink/?LinkId=132767).  
  
## <a name="automating-powerpoint-by-using-the-powerpoint-object-model"></a>PowerPoint nesne modelini kullanarak PowerPoint otomatikleştirme  
 PowerPoint nesne modeli PowerPoint'i otomatikleştirmek için kullanabileceğiniz birçok türü ortaya çıkarır. Bu tür ortak görevleri gerçekleştirmek için kod yazmayı etkinleştir:  
  
-   Program aracılığıyla oluşturma ve sunular biçimlendirin.  
  
-   Ekleyin veya slayt sunuları kaldırın.  
  
-   Ekleyebilir veya bir slayt şekillerdeki değiştirebilirsiniz.  
  
 Bir VSTO eklentiden PowerPoint nesne modeline erişmek için `Application` alanını `ThisAddIn` projenizdeki sınıfı. `Application` Alan döndürür bir <xref:Microsoft.Office.Interop.PowerPoint.Application> PowerPoint geçerli örneği temsil eden nesne. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 PowerPoint nesne modelini çağırdığınızda, PowerPoint için birincil birlikte çalışma derlemesindeki sağlanan türleri kullanabilirsiniz. Birincil birlikte çalışma derlemesi için VSTO eklentisi yönetilen kodda ve PowerPoint COM nesne modelinde arasında bir köprü gibi davranır. PowerPoint birincil birlikte çalışma derlemesi içindeki tüm türler tanımlanan <xref:Microsoft.Office.Interop.PowerPoint> ad alanı. Birincil birlikte çalışma derlemeleri hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) ve [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md).  
  
##  <a name="WordOMDocumentation"></a>PowerPoint nesne Model belgelerini kullanma  
 PowerPoint nesne modeli hakkında tam bilgi için PowerPoint birincil birlikte çalışma derlemesi (PIA) başvuru ve VBA nesne modeli başvurusu başvurabilir.  
  
### <a name="primary-interop-assembly-reference"></a>Birincil birlikte çalışma derleme başvurusu  
 PowerPoint PIA başvuru belgeleri PowerPoint için birincil birlikte çalışma derlemesindeki türler açıklanmaktadır. Bu belge aşağıdaki konumdan kullanılabilir: [PowerPoint 2010 birincil birlikte çalışma derleme başvurusu](http://go.microsoft.com/fwlink/?LinkId=189588).  
  
 PIA ve olayları PIA nasıl uygulandığı, sınıflar ve arabirimler arasındaki fark gibi PowerPoint PIA tasarımı hakkında daha fazla bilgi için bkz: [genel bakış, sınıflar ve arabirimler Office birincil birlikte çalışma derlemeleri ](http://go.microsoft.com/fwlink/?LinkId=199885).  
  
### <a name="vba-object-model-reference"></a>VBA nesne modeli başvurusu  
 Visual Basic for Applications (VBA) kodundaki sunulur gibi VBA nesne modeli başvurusu PowerPoint nesne modelini belgeler. Daha fazla bilgi için bkz: [PowerPoint 2010 nesne modeli başvurusu](http://go.microsoft.com/fwlink/?LinkId=199770)  
  
 Tüm nesneleri ve VBA nesne modeli başvurusu üyeleri türleri ve üyeleri PowerPoint birincil birlikte çalışma derlemesi (PIA) karşılık gelir. VBA nesne modeli başvurusu sunu nesnesinde Örneğin, karşılık gelen <xref:Microsoft.Office.Interop.PowerPoint.Presentation> PowerPoint PIA yazın. VBA nesne modeli başvurusu kod örnekleri çoğu özellikleri, yöntemleri ve olayları sağlasa da, bunları kullanarak oluşturduğunuz bir PowerPoint VSTO eklenti projesindeki kullanmak istiyorsanız, Visual Basic veya Visual C# bu başvurusu VBA kodu çevrilmelidir Visual Studio.  
  
## <a name="customizing-the-user-interface-of-powerpoint"></a>PowerPoint kullanıcı arabirimini özelleştirme  
 Aşağıdaki yollarla PowerPoint UI değiştirebilirsiniz.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Özel görev bölmesini oluşturun.|[Özel Görev Bölmeleri](../vsto/custom-task-panes.md)|  
|Özel sekmeler Şerit'e ekleyin.|[Şeride Genel Bakış](../vsto/ribbon-overview.md)|  
|Şerit'te yerleşik bir sekmeyi özel gruplar ekleyin.|[Nasıl Yapılır: Yerleşik Bir Sekmeyi Özelleştirme](../vsto/how-to-customize-a-built-in-tab.md)|  
  
 PowerPoint UI ve diğer Microsoft Office uygulamaları özelleştirme hakkında daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: PowerPoint için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)   
 [Başlarken VSTO eklentilerini programlama](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [PowerPoint 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199015)  
  
  