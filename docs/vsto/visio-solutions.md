---
title: "Visio çözümleri | Microsoft Docs"
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
- Office projects [Office development in Visual Studio], Visio
- solutions [Office development in Visual Studio], Visio
- Visio [Office development in Visual Studio]
- templates [Office development in Visual Studio], Visio
- projects [Office development in Visual Studio], Visio
- Office solutions [Office development in Visual Studio], Visio
ms.assetid: c52948c6-6891-43ec-93ff-c54c74ec6016
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 77c4b8e13071486bf483fc5b281bf86ae13aa965
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="visio-solutions"></a>Visio Çözümleri
  Visual Studio Proje şablonları, Microsoft Office Visio için VSTO eklentileri oluşturmak için kullanabileceğiniz sağlar. VSTO eklentileri Visio otomatikleştirmek, Visio özelliklerini genişletmek veya Visio kullanıcı arabirimi (UI) özelleştirmek için kullanabilirsiniz.  
  
 VSTO eklentileri hakkında daha fazla bilgi için bkz: [başlatılan programlama VSTO alma eklentileri](../vsto/getting-started-programming-vsto-add-ins.md) ve [mimarisi, VSTO eklentileri](../vsto/architecture-of-vsto-add-ins.md). Microsoft Office ile programlamada yeniyseniz, bkz: [Başlarken &#40; Visual Studio &#41; Office geliştirme](../vsto/getting-started-office-development-in-visual-studio.md).  
  
 **Uygulandığı öğe:** Bu konu başlığı altındaki bilgiler Visio 2010 VSTO eklentisi projelerine yöneliktir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="automating-visio-by-using-the-visio-object-model"></a>Visio nesne modelini kullanarak Visio otomatikleştirme  
 Visio nesne modeline kuruluş şemaları, akış çizelgeleri, proje zaman çizelgeleri, ağ şemaları, office alanları ve daha fazlası için diyagramlar oluşturmak için Visio otomatikleştirmek için kullanabileceğiniz birçok sınıf sağlar. API, ortak görevleri gerçekleştirmek için kod yazmanıza olanak sağlar:  
  
-   Oluşturun ve şekil ve metinler diyagramlarda getirin.  
  
-   İş mantığına göre şekil davranışını ve kullanıcı girişi yönetin.  
  
-   Kaydırma ve yakınlaştırma gibi diyagramı görselleştirme denetler.  
  
-   Uygulama kullanıcı Arabirimi özelleştirin.  
  
-   Visio'ya dış veri almak, şekillere bağlama ve grafik bir sayfada görüntüleme.  
  
 Adım adım yordamlar görüntülemek ve kod belgeler ve şekiller çalışmak için Visio nesne modelini kullanma örnekleri [Visio belgeleriyle çalışma](../vsto/working-with-visio-documents.md) ve [Visio şekilleri ile çalışma](../vsto/working-with-visio-shapes.md).  
  
 Bir VSTO eklentiden Visio nesne modeline erişmek için `Application` alanını `ThisAddIn` projenizdeki sınıfı. `Application` Alan Visio geçerli örneği temsil eden bir Microsoft.Office.Interop.Visio.Application nesnesini döndürür. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 Visio nesne modeline çağırdığınızda, Visio için birincil birlikte çalışma derlemesi (PIA) sağlanan türleri kullanabilirsiniz. PIA yönetilen kod için VSTO eklentisi ve Visio'da COM nesne modeli arasında köprü gibi davranır. Visio PIA içindeki tüm türler Microsoft.Office.Interop.Visio ad alanında tanımlanır. Birincil birlikte çalışma derlemeleri hakkında daha fazla bilgi için bkz: [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) ve [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="visio-object-model-overview"></a>Visio Nesne Modeline Genel Bakış  
 Visio nesne modeline genel bakış bulabilirsiniz [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md), Visio nesne modeli başvurusu ve SDK'ları bağlantılar içerir.  
  
## <a name="customizing-the-user-interface-of-visio"></a>Visio kullanıcı arabirimini özelleştirme  
 Visio UI aşağıdaki özelleştirme seçenekleri vardır.  
  
|Görev|Daha fazla bilgi için|  
|----------|--------------------------|  
|Şerit özelleştirin.|[Şeride Genel Bakış](../vsto/ribbon-overview.md)|  
  
 UI özelleştirme hakkında daha fazla bilgi için VBA başvuru belgelerine bakın [Visio.UIObject](https://msdn.microsoft.com/library/office/ff765763.aspx) sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken VSTO eklentilerini programlama](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office çözümleri geliştirmesine genel bakış &#40; VSTO &#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md)   
 [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)   
 [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)   
 [Visio 2010 Office geliştirme](http://go.microsoft.com/fwlink/?LinkId=199017)  
  
  