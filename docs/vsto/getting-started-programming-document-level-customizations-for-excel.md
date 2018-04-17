---
title: Excel için belge düzeyi özelleştirme programlamasına başlama | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel solutions in Visual Studio
- Excel projects [Office development in Visual Studio], getting started
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5f10e0c2d3dc7a561b4fff7ad74081e9a26570b0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="getting-started-programming-document-level-customizations-for-excel"></a>Excel İçin Belge Düzeyi Özelleştirme Programlamasına Başlama
  Yalnızca Visual Studio kullanarak Microsoft Office Excel için belge düzeyi özelleştirmeleri oluşturma başlıyorsanız, işte bilmeniz gerekir.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
## <a name="understanding-how-document-level-customizations-for-excel-work"></a>Excel çalışma için belge düzeyi özelleştirmeleri anlama  
 Excel için belge düzeyi özelleştirme tek bir çalışma kitabına temel alır. Özelleştirmeyi kullanmaya başlamak için son kullanıcı çalışma kitabını açar veya çalışma kitabını Excel şablonundan oluşturur. Örneğin hücrelere yazma veya menü öğeleri ve düğmelere çalışma kitabı olayları olay işleme yöntemleri derlemede çağırabilirsiniz. Çalışma kitabı kapatıldığında özelleştirme tarafından sağlanan özellikler artık bunları içeren belgede Excel'de kullanılabilir.  
  
 Daha fazla bilgi için bkz: [belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md).  
  
## <a name="creating-document-level-projects-for-excel"></a>Excel için belge düzeyi projelerine oluşturma  
 Excel için belge düzeyi özelleştirme oluşturmak için Excel çalışma kitabı veya Excel Şablonu proje şablonu kullanmak **yeni proje** iletişim kutusu. Bu şablonlar gerekli derleme başvurularını ve proje dosyalarını içerir.  
  
 Excel için belge düzeyi projesi oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md). Proje şablonları hakkında daha fazla bilgi için bkz: [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md).  
  
## <a name="programming-excel-workbooks-by-using-host-items-and-host-controls"></a>Konak denetimlerinin ve konak öğelerinin kullanarak Excel çalışma kitaplarını programlama  
 *Konak öğelerini* ve *konak denetimlerini* , Visual Studio kullanılarak oluşturulan belge düzeyi özelleştirmeleri için programlama modeli sağlar.  
  
 Konak öğeleri kodunuz için giriş noktası sağlar ve bunlar da ana bilgisayar denetimleri ve Windows Forms denetimleri için kapsayıcılar olarak çalışabilir. Excel için belge düzeyi projelerine içinde bu ana bilgisayar öğeleri tarafından temsil edilen `ThisWorkbook`, `Sheet1`, `Sheet2`, ve `Sheet3` sınıfları.  
  
 Konak denetimleri liste nesneleri ve aralıklar gibi yerel Excel nesneleri temel alır. Konak denetimleri için yerel Excel nesnelerine benzer işlevsellik sağlasa da, aynı zamanda yeni olaylar, tasarımcı desteği ve veri bağlama özelliği vardır. Proje kodunuzda ve Excel nesne modeline gitmek zorunda kalmadan, doğrudan kodunuzda belirli nesnelere başvurma kolaylaştırır IntelliSense birinci sınıf nesneler olarak görünürler.  
  
 Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Belge Düzeyi Özelleştirmelerini Programlama](../vsto/programming-document-level-customizations.md)  
  
-   [Genişletilmiş Nesneleri Kullanarak Excel'i Otomatikleştirme](../vsto/automating-excel-by-using-extended-objects.md)  
  
-   [Konak Öğelerine ve Denetimlerine Genel Bakış](../vsto/host-items-and-host-controls-overview.md)  
  
## <a name="customizing-the-user-interface-of-excel"></a>Excel kullanıcı arabirimini özelleştirme  
 Microsoft Office çözümlerinin çoğu kullanıcı arabirimi (UI) çözümü ile etkileşim kullanıcılar için herhangi bir şekilde sağlamak için Office uygulamasının değiştirin. Belge düzeyi özelleştirme kullanarak Excel'in UI'ını değişiklik yapabilirsiniz birçok yolu vardır. Örneğin, Şerit denetimlerini ekleyebilirsiniz veya Eylemler bölmesinde görüntüleyebilirsiniz. Daha fazla bilgi için bkz: [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
 Projeniz Visual Studio'da doğrudan ilişkilendirildiği çalışma kitabını da açabilirsiniz. Çalışma kitabı Visual Studio'da açıkken, çalışma kitabını Excel kullanıcı arabirimini kullanarak değiştirebilirsiniz. Çalışma sayfasına denetimler sürükleyin olanak tanıyan bir tasarım yüzeyi olarak çalışma kitabı de kullanabilirsiniz. Daha fazla bilgi için bkz: [Visual Studio ortamında Office projeleri](../vsto/office-projects-in-the-visual-studio-environment.md).  
  
## <a name="using-data-binding"></a>Veri bağlama işlemini kullanma  
 Konak denetimleri'ndan sürükleyebilirsiniz denetim listesinde de bulunan **veri kaynakları** penceresi. Konak denetimleri bu yolla ekleme penceresini kullanarak ayarlamak veri kaynağına doğru bağlar. Herhangi bir kod yazmak zorunda kalmadan, veritabanları, web hizmetleri ve iş nesneleri verilerini görüntüleyebilir. Daha fazla bilgi için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Excel için belge düzeyi özelleştirme oluşturmayı öğrenmek için bkz: [izlenecek yol: oluşturma bilgisayarınızı ilk belge düzeyi özelleştirme Excel için](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md). Bu kılavuzda Office geliştirme araçlarını Visual Studio ve Excel belge düzeyi özelleştirmelerini programlama modeli sunar.  
  
 Excel projeleri ortak görevlerin bazıları size yol konuların listesi için bkz: [Office programlama ortak görevlerin](../vsto/common-tasks-in-office-programming.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)   
 [Excel çözümleri](../vsto/excel-solutions.md)   
 [İzlenecek yol: Excel için ilk belge düzeyi özelleştirmeyi oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)   
 [Excel kullanarak izlenecek yollar](../vsto/walkthroughs-using-excel.md)   
 [Excel nesne modeline genel bakış](../vsto/excel-object-model-overview.md)   
 [Office Çözümlerinde Kod Yazma](../vsto/writing-code-in-office-solutions.md)  
  
  