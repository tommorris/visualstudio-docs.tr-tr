---
title: Visio nesne modeline genel bakış
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], object model
- object models [Office development in Visual Studio], Office
- object models [Office development in Visual Studio], Visio
- objects [Office development in Visual Studio], Office object models
- Office object models
- Visio object model
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0da6dac3ffde6e6394546e78462205eb4fa08c8c
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767838"
---
# <a name="visio-object-model-overview"></a>Visio nesne modeline genel bakış
  Microsoft Office Visio için Office çözümleri geliştirmek için Visio nesne modeli ile etkileşim kurabilirsiniz. Bu nesne modeli sınıfları ve birincil birlikte çalışma derlemesi Visio için sağlanan ve içinde tanımlanan arabirimleri oluşur `Microsoft.Office.Interop.Visio` ad alanı.  
  
 Bu konu, Visio nesne modeline kısa bir genel bakış sağlar. Office projelerinde görevleri gerçekleştirmek için Visio nesne modelini kullanma hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Visio belgeleriyle çalışma](../vsto/working-with-visio-documents.md)  
  
-   [Visio şekilleri ile çalışma](../vsto/working-with-visio-shapes.md)  
  
## <a name="understand-the-visio-object-model"></a>Visio nesne modelini anlama  
 Visio ile etkileşim kurabilen birçok nesne sağlar. Bu nesneler kullanıcı arabirimini yakından takip eden hiyerarşik olarak düzenlenir. Hiyerarşisinin en üstünde olduğu [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx) nesnesi. Bu nesne Visio'nun geçerli örneğini temsil eder. `Microsoft.Office.Interop.Visio.Application` Nesnesini içeren `Microsoft.Office.Interop.Visio.Document` ve `Microsoft.Office.Interop.Visio.Page` nesneleri yanı sıra `Microsoft.Office.Interop.Visio.Documents` ve `Microsoft.Office.Interop.Visio.Pages` koleksiyonları. Bu nesneleri ve koleksiyonları her birçok yöntem ve işlemek ve ile etkileşim için erişebileceği özellikler vardır.  
  
 Daha fazla bilgi için VBA başvuru belgelerine bakın [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx), [Microsoft.Office.Interop.Visio.Document](https://msdn.microsoft.com/library/office/ff765575.aspx), ve [ Microsoft.Office.Interop.Visio.Page](https://msdn.microsoft.com/library/office/ff767035.aspx) nesneleri ve ayrıca [Microsoft.Office.Interop.Visio.Documents](https://msdn.microsoft.com/library/office/ff768812.aspx) ve [Microsoft.Office.Interop.Visio.Pages](https://msdn.microsoft.com/library/office/ff766165.aspx) koleksiyonları.  
  
 Aşağıdaki bölümlerde, üst düzey nesneleri ve birbirleri ile nasıl etkileşim kurduklarını kısaca açıklanmaktadır. Aşağıdaki nesneler bu nesneler Ekle:  
  
-   Uygulama nesnesi  
  
-   Belge nesnesi  
  
-   Sayfa nesnesi  
  
### <a name="application-object"></a>Uygulama nesnesi  
 Microsoft.Office.Interop.Visio.Application nesnesi Visio uygulamasını temsil eder ve tüm diğer nesnelerin üst. Üyeleri, genellikle bir bütün olarak Visio uygular. Özellikleri ve yöntemleri Microsoft.Office.Interop.Visio.Application kullanabilirsiniz ve `Microsoft.Office.Interop.Visio.ApplicationSettings` Visio ortamını denetlemek için nesneleri.  
  
 VSTO eklenti projelerinde Microsoft.Office.Interop.Visio.Application nesnesi kullanarak erişebilirsiniz `Application` alanını `ThisAddIn` sınıfı. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
### <a name="document-object"></a>Belge nesnesi  
 Programlama Visio'ya merkezi Microsoft.Office.Interop.Visio.Document nesnesidir. Çizim, şablon veya şablon dosyasını temsil eder. Visio belgelerini açın veya yeni bir belge oluşturun, Microsoft.Office.Interop.Visio.Application nesnesi Microsoft.Office.Interop.Visio.Documents koleksiyonuna eklenen yeni bir Microsoft.Office.Interop.Visio.Document nesne oluşturma .  
  
 Odaklanmış belge etkin belgeyi denir. Tarafından temsil edilen `Microsoft.Office.Interop.Visio.Application.ActiveDocument` Microsoft.Office.Interop.Visio.Application nesnesinin özelliği.  
  
### <a name="page-object"></a>Sayfa nesnesi  
 Microsoft.Office.Interop.Visio.Page nesnesi bir ön plan veya arka plan sayfası çizim alanını temsil eder. Kullanabileceğiniz `Microsoft.Office.Interop.Visio.Page.Background` bir sayfa bir ön plan veya arka plan sayfa olup olmadığını belirlemek için özellik.  
  
 Şekiller oluşturmak için içeren yöntemleri kullanabilirsiniz `Microsoft.Office.Interop.Visio.Page.DrawSpline` ve `Microsoft.Office.Interop.Visio.Page.DrawOval` yöntemleri. Ayrıca, kalıp örnekleri alabilir ve şekiller kullanarak bir sayfada yerleştirin `Microsoft.Office.Interop.Visio.Page.Drop` veya `Microsoft.Office.Interop.Visio.Page.DropMany` yöntemleri.  
  
## <a name="use-the-visio-object-model-documentation"></a>Visio nesne modeli belgeleri kullanın  
 Visio nesne modeli hakkında tam bilgi için Visio VBA nesne modeli başvurusu başvurabilir. Visual Basic for Applications (VBA) kodundaki sunulur gibi VBA nesne modeli başvurusu Visio nesne modeline belgeler. Daha fazla bilgi için bkz: [Visio 2010 nesne modeli başvurusu](http://go.microsoft.com/fwlink/?LinkId=199775).  
  
 Tüm nesneleri ve VBA nesne modeli başvurusu üyeleri türleri ve üyeleri Visio birincil birlikte çalışma derlemesi (PIA) karşılık gelir. Örneğin, `Document` VBA nesne modeli başvurusu nesnesinde Visio PIA Microsoft.Office.Interop.Visio.Document türünde karşılık gelir. VBA nesne modeli başvurusu kod örnekleri çoğu özellikleri, yöntemleri ve olayları sağlasa da, bunları Visual kullanarak oluşturduğunuz bir Visio VSTO eklenti projesindeki kullanmak istiyorsanız, Visual Basic veya Visual C# bu başvurusu VBA kodu çevrilmelidir Studio.  
  
> [!NOTE]  
>  Şu anda Visio birincil birlikte çalışma derlemesi için başvuru belgesi yoktur.  
  
 İlgili kod örnekleri ve Visio çözümleri oluşturmak için ek araçlar için bkz: [Visio 2010 Yazılım Geliştirme Seti](http://go.microsoft.com/fwlink/?LinkId=196501).  
  
### <a name="additional-types-in-primary-interop-assemblies"></a>Birincil birlikte çalışma derlemeleri ek türleri  
 Uygulama farklılıkları nedeniyle VBA'ya görünür olmayan birincil birlikte çalışma derlemeleri türleri bulabilirsiniz. VBA yalnızca nesneleri ve doğrudan kullanabileceğiniz üyeleri içeren Visio nesne modeline bir görünümünü sağlar. Birincil birlikte çalışma derlemeleri aynı nesne modelini sunar, ancak aynı zamanda diğer arabirimleri, sınıflar ve yönetilen kod için COM nesne modelinde Çevir üyeleri içerir. Bu ek öğeler kodunuzda doğrudan kullanılmak üzere tasarlanmamıştır.  
  
 Daha fazla bilgi için bkz: [sınıflar ve arabirimler Office birincil birlikte çalışma derlemeleri genel bakış](http://go.microsoft.com/fwlink/?LinkId=189592) ve [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visio çözümleri](../vsto/visio-solutions.md)   
 [Visio belgeleriyle çalışma](../vsto/working-with-visio-documents.md)   
 [Visio şekilleri ile çalışma](../vsto/working-with-visio-shapes.md)  
  
  