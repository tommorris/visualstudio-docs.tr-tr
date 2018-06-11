---
title: Office çözümlerinde kod yazma
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.Project.RefactoringCancelled
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], writing code
- managed code [Office development in Visual Studio]
- Office development in Visual Studio, programming languages supported
- Office applications [Office development in Visual Studio], automating
- Office applications [Office development in Visual Studio], writing code
- writing code for Office solutions
- programming [Office development in Visual Studio], model
- Automation [Office development in Visual Studio], managed code
- application development [Office development in Visual Studio], programming model
- Office solutions [Office development in Visual Studio], writing code
- automating Office applications
- application development [Office development in Visual Studio], writing code
- application development [Office development in Visual Studio], automating
- Office projects [Office development in Visual Studio], changing namespaces
- solutions [Office development in Visual Studio], programming model
- programming [Office development in Visual Studio]
- namespaces [Office developmentin Visual Studio], changing in Office solutions
- projects [Office development in Visual Studio], writing code
- Office applications [Office development in Visual Studio], programming model
- managed code extensions [Office development in Visual Studio], writing code
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6e8212b336af5ba1a0c71d81d5464f198df77b15
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/11/2018
ms.locfileid: "35258664"
---
# <a name="write-code-in-office-solutions"></a>Office çözümlerinde kod yazma
  Bazı yönlerini diğer Visual Studio Proje türleri farklıdır Office projelerinde kod yazma vardır. Bu farklılıklar birçoğunu Office nesne modelleri için yönetilen kod gösterilen şekilde ilişkilidir. Diğer farklar Office projelerinin tasarımı için ilişkilidir.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="managed-code-and-office-programming"></a>Yönetilen kod ve Office programlama  
 Tümleşik Microsoft Office çözümü oluşturma olanaklı kılan anahtar Bileşen Nesne Modeli (COM) teknolojisi parçası olan Otomasyon teknolojidir. Otomasyon oluşturmak ve herhangi bir uygulama tarafından DLL, kullanıma sunulan yazılım nesnelerini denetlemek için kod kullanmanıza olanak sağlar veya ActiveX denetimi uygun programlama arabirimleri destekler.  
  
### <a name="understand-primary-interop-assemblies"></a>Birincil birlikte çalışma derlemeleri anlama  
 Microsoft Office uygulamaları Otomasyon için işlevlerinin çoğunu kullanıma sunar. Ancak, doğrudan Office uygulamalarını otomatikleştirmek için yönetilen kod (örneğin, Visual Basic veya C#) kullanamazsınız. Yönetilen kod kullanarak Office uygulamalarını otomatikleştirmek için Office birincil birlikte çalışma derlemeleri (PIA) kullanmanız gerekir. Birincil birlikte çalışma derlemeleri COM tabanlı nesne modeli Office uygulamaları ile etkileşim kurmak yönetilen kod etkinleştirin.  
  
 Her Microsoft Office uygulamasının bir PIA sahiptir. Visual Studio'da Office proje oluşturduğunuzda, uygun PIA başvuru projeye otomatik olarak eklenir. Diğer Office uygulamalarından proje özelliklerini otomatikleştirmek için uygun PIA başvuru el ile eklemeniz gerekir. Daha fazla bilgi için bkz: [nasıl yapılır: birincil birlikte çalışma derlemeleriyle hedef Office uygulamaları](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md).  
  
### <a name="use-primary-interop-assemblies-at-design-time-and-runtime"></a>Birincil birlikte çalışma derlemeleri tasarım zamanı ve çalışma zamanı kullanın  
 Office yüklü ve geliştirme bilgisayarınızda genel derleme önbelleğinde kayıtlı çoğu geliştirme görevleri gerçekleştirmek için PIA olması gerekir. Daha fazla bilgi için bkz: [Office çözümleri geliştirmek için bilgisayarı yapılandırma](../vsto/configuring-a-computer-to-develop-office-solutions.md).  
  
 Office PIA son kullanıcı bilgisayarlarında hedefleyen Office çözümlerini çalıştırmak için gerekli değildir [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Daha fazla bilgi için bkz: [tasarım ve Office çözümleri oluşturmak](../vsto/designing-and-creating-office-solutions.md).  
  
### <a name="use-types-in-primary-interop-assemblies"></a>Birincil birlikte çalışma derlemeleri kullanma türleri  
 Office PIA Office uygulamalarının nesne modeli kullanıma türleri ve kodunuzda doğrudan kullanılmak üzere tasarlanmamıştır ek altyapı türleri birleşimini içerir. Office PIA türlerinde genel bakış için bkz: [sınıflar ve arabirimler Office birincil birlikte çalışma derlemeleri genel bakış](http://msdn.microsoft.com/en-us/da92dc3c-8209-44de-8095-a843659368d5).  
  
 Office PIA türler COM tabanlı nesne modellerindeki türlerine karşılık gelen olduğundan, bu tür kullanmak genellikle diğer yönetilen türlerden farklı yoludur. Örneğin, bir Office birincil birlikte çalışma derlemesindeki isteğe bağlı parametreleri olan yöntemleri çağırma yolunuz projenizde kullandığınız programlama dili bağlıdır. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md).  
  
-   [Office çözümlerinde geç bağlama](../vsto/late-binding-in-office-solutions.md).  
  
## <a name="program-model-of-office-projects"></a>Office projeleri program modeli  
 Tüm Office projeleri kodunuz için giriş noktası sağlayan bir veya daha fazla oluşturulan sınıflar içerir. Bu sınıf ayrıca konak uygulamasının nesne modeline erişim ve Eylemler bölmesi ve özel görev bölmeleri gibi özelliklere erişim sağlar.  
  
### <a name="understand-the-generated-classes"></a>Oluşturulan sınıflar anlama  
 Excel ve Word için belge düzeyi projelerine içinde oluşturulan sınıf uygulamanın nesne modeline üst düzey bir nesnesinde benzer. Örneğin, oluşturulan `ThisDocument` bir Word belgesi projesi sınıfında aynı üyeleri sağlar <xref:Microsoft.Office.Interop.Word.Document> Word nesne modelindeki sınıfı. Belge düzeyi projelerine oluşturulan sınıflar hakkında daha fazla bilgi için bkz: [Program belge düzeyi özelleştirmeleri](../vsto/programming-document-level-customizations.md).  
  
 VSTO eklentisi projelerine sağlamak adında bir oluşturulmuş sınıf `ThisAddIn`. Bu sınıf, konak uygulamanın nesne modelinde bir sınıf benzemez. Bunun yerine, bu sınıf için VSTO eklentisi kendisini temsil eder ve ana bilgisayar uygulamasının nesne modeline erişme ve VSTO eklentileri için kullanılabilir diğer özelliklerine erişmek için kullanabileceğiniz üyeleri sağlar. Daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md).  
  
 Office projelerindeki tüm oluşturulan sınıflar dahil `Startup` ve `Shutdown` olay işleyicileri. Kod yazmaya başlamak için genellikle bu olay işleyicilerine kod eklemeniz gerekir. VSTO Eklentinizi başlatmak için kod ekleyebilirsiniz `Startup` olay işleyicisi. VSTO eklentinizi tarafından kullanılan kaynakları temizlemek için kod ekleyebilirsiniz `Shutdown` olay işleyicisi. Daha fazla bilgi için bkz: [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md).  
  
### <a name="access-the-generated-classes-at-runtime"></a>Oluşturulan sınıflar çalışma zamanında erişme  
 Office çözümünü yüklendiğinde [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] her projenizdeki oluşturulan sınıflar başlatır. Kullanarak projenizde herhangi bir kodda bu nesnelere erişebilirsiniz `Globals` sınıfı. Örneğin, kullanabileceğiniz `Globals` kodu çağırmak için sınıf `ThisAddIn` VSTO eklenti bir Şerit düğmesinin olay işleyicisinden sınıfı.  
  
 Daha fazla bilgi için bkz: [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md).  
  
### <a name="namespace-considerations-in-office-solutions"></a>Office çözümlerinde Namespace konuları  
 Değiştiremezsiniz *varsayılan ad alanı* (veya *kök ad alanı* Visual Basic'te) projesi oluşturduktan sonra bir Office Project'in. Varsayılan ad alanı her zaman proje oluşturduğunuzda, belirttiğiniz proje adı ile eşleşir. Projenizi yeniden adlandırırsanız, varsayılan ad alanını değiştirmez. Varsayılan ad alanı projelerinde hakkında daha fazla bilgi için bkz: [uygulama sayfası, Proje Tasarımcısı &#40;C&#35; &#41; ](/visualstudio/ide/reference/application-page-project-designer-csharp) ve [uygulama sayfası, Proje Tasarımcısı &#40;Visual Basic&#41; ](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
### <a name="change-the-namespace-of-host-item-classes-in-c-projects"></a>C# projelerine konak öğesi sınıflarının ad değiştirin  
 Konak öğesi sınıflarının (örneğin, `ThisAddIn`, `ThisWorkbook`, veya `ThisDocument` sınıfları), kendi ad Visual C# Office projelerinde sahip. Varsayılan olarak, ana bilgisayar öğeleri projenizdeki için ad alanı proje oluşturduğunuzda, belirttiğiniz proje adı ile eşleşir.  
  
 Ad alanı bir Visual C# Office proje ana bilgisayar öğeleri değiştirmek için kullanın **Namespace konak öğesi için** özelliği. Daha fazla bilgi için bkz: [Office projelerinde Özellikler](../vsto/properties-in-office-projects.md).  
  
## <a name="supported-programming-languages-in-office-projects"></a>Office projelerinde desteklenen programlama dilleri  
 Visual Studio'da Office proje şablonları yalnızca Visual Basic ve Visual C# programlama dillerini destekler. Bu nedenle, bu proje şablonları yalnızca altında kullanılabilir **Visual Basic** ve **Visual C#** düğümlerinin **yeni proje** iletişim kutusunda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio oluşturma Office projelerinde](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
## <a name="language-choice-and-office-programming"></a>Dil Seçimi ve Office programlama  
 Microsoft Office ve Visual Basic for Applications (VBA) uygulama özelleştirme iş akışı iyileştirmek için birlikte çalışmak üzere geliştirilmiştir. Visual Basic bu geliştirmelerin bazılarını devralmış demektir. Örneğin, Visual Basic, Visual C# kullandığınızda, daha Microsoft Office birincil birlikte çalışma derlemeleri bazı yöntemleri çağrılırken daha az kod yazabilirsiniz başka bir deyişle, isteğe bağlı parametreler destekler.  
  
## <a name="program-with-visual-basic-vs-visual-c-in-office-solutions"></a>Visual Basic vs programla. Visual C# Office çözümleri  
 Visual Basic veya Visual C# kullanarak Office çözümleri oluşturabilirsiniz. Microsoft Office nesne modelleri Microsoft Visual Basic for Applications (VBA) kullanılmak üzere tasarlanmış olması nedeniyle, Visual Basic geliştiricileri Microsoft Office uygulamaları tarafından oluşturulan nesnelerle rahatça çalışabilirsiniz. Visual C# geliştiricileri Visual Basic geliştiricilerinin aynı özelliklerin çoğunu kullanabilirsiniz, ancak burada Office nesne modelleri kullanmak için ek kod yazmalısınız bazı durumlar vardır. Office geliştirme temel programlama özellikleri ve Visual Basic ve C# ' da yazılmış yönetilen kod arasındaki bazı farklar vardır.  
  
## <a name="key-differences-between-visual-basic-and-visual-c"></a>Visual Basic ve Visual C# arasındaki farklar  
 Aşağıdaki tabloda, Office geliştirme Visual Basic ve Visual C# arasındaki farklar gösterilmektedir.  
  
|Özellik|Açıklama|Visual Basic desteği|Visual C# desteği|  
|-------------|-----------------|--------------------------|------------------------|  
|İsteğe bağlı parametreler|Birçok Microsoft Office yöntemi yöntemini çağırdığınızda, gerekli olmayan parametrelere sahip. Parametresi için değer iletilmezse, varsayılan değer kullanılır.|Visual Basic isteğe bağlı parametreleri destekler.|Visual C# çoğu durumda isteğe bağlı parametreleri destekler. Daha fazla bilgi için bkz: [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md).|  
|Parametreleri başvuruya göre geçirme|Microsoft Office birincil birlikte çalışma derlemeleri çoğunu isteğe bağlı parametre değerine göre geçirilebilir. Ancak, bazı birincil birlikte çalışma derlemeleri içinde başvuruya göre başvuru türlerini kabul eden isteğe bağlı parametreler geçirilmelidir.<br /><br /> Değer ve başvuru türü parametreleri hakkında daha fazla bilgi için bkz: [değere ve başvuruya göre bağımsız değişkenler geçirme &#40;Visual Basic&#41; ](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference) (Visual Basic için) ve [geçirmek parametreleri &#40;C&#35; Programlama Kılavuzu&#41;](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters).|Ek bir iş tarafından başvuru parametreleri geçirmek için gereklidir. Visual Basic derleyici parametreleri gerektiğinde başvuru tarafından otomatik olarak geçirir.|Çoğu durumda, Visual C# Derleyici gerektiğinde başvuruya göre parametreleri otomatik olarak geçirir. Daha fazla bilgi için bkz: [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md).|  
|Parametreli özellikleri|Bazı özellikler parametreleri kabul eder ve salt okunur işlevler olarak davranır.|Visual Basic parametreleri kabul eden özellikleri destekler.|Visual C# parametreleri kabul eden özellikleri destekler.|  
|Geç bağlama|Geç bağlama atama değişkenleri tasarım zamanında nesne türü için yerine çalışma zamanında nesnelerin özelliklerini belirleme içerir.|Visual Basic geç bağlamayı gerçekleştirir **Option Strict** kapalıdır. Zaman **Option Strict** açıktır, gerekir açıkça dönüştürdüğünüz nesneleri ve kullanım türlerinde <xref:System.Reflection> geç bağlama üyelere erişmek için ad alanı. Daha fazla bilgi için bkz: [Office çözümlerinde geç bağlama](../vsto/late-binding-in-office-solutions.md).|Visual C# gerçekleştiren hedefleyen projelerde geç bağlama [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. Daha fazla bilgi için bkz: [Office çözümlerinde geç bağlama](../vsto/late-binding-in-office-solutions.md).|  
  
## <a name="key-differences-between-office-development-and-managed-code"></a>Office geliştirme ve yönetilen kod arasındaki farklar  
 Aşağıdaki tabloda Office geliştirme ve Visual Basic veya Visual C# ile yazılmış yönetilen kod arasındaki farklar gösterilmektedir.  
  
|Özellik|Açıklama|Visual Basic ve Visual C# desteği|  
|-------------|-----------------|-----------------------------------------|  
|Dizi dizinleri|Microsoft Office uygulamalarında koleksiyonların düşük dizi sınırı 1 ile başlar. Visual Basic ve Visual C# 0 tabanlı diziler kullanın. Daha fazla bilgi için bkz: [diziler &#40;C&#35; Programlama Kılavuzu&#41; ](/dotnet/csharp/programming-guide/arrays/index) ve [Visual Basic'de diziler](/dotnet/visual-basic/programming-guide/language-features/arrays/index).|Microsoft Office uygulamasının nesne modelinde bir koleksiyonun ilk öğeye erişmek için dizin 1 yerine 0 kullanın.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümlerinde isteğe bağlı parametreler](../vsto/optional-parameters-in-office-solutions.md)   
 [Office projelerindeki nesnelere genel erişim](../vsto/global-access-to-objects-in-office-projects.md)   
 [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md)   
 [Nasıl yapılır: birincil birlikte çalışma derlemeleriyle hedef Office uygulamaları](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md)   
 [Office çözümlerinde geç bağlama](../vsto/late-binding-in-office-solutions.md)   
 [Office çözümlerinin işbirlikçi geliştirme](../vsto/collaborative-development-of-office-solutions.md)  
  
  