---
title: ".NET Framework 4 veya .NET Framework 4.5 hedefleyen Office projelerinde tasarımını değişiklikleri | Microsoft Docs"
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
- Office development in Visual Studio, what's new
- what's new [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 059d259b669e63c26759782010be7ff78691ffc3
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="changes-to-the-design-of-office-projects-that-target-the-net-framework-4-or-the-net-framework-45"></a>.NET Framework 4 veya .NET Framework 4.5'i Hedefleyen Office Projelerinin Tasarımı Üzerinde Yapılan Değişiklikler
  İtibariyle [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)], Visual Studio hedefleyen Office projelerinin tasarımı için bazı değişiklikler sunulan [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Visual Studio'nun önceki sürümleri Office projelerinde biliyorsanız, bu .NET Framework 4.0 veya sonraki sürümlerini hedefleyen Office projelerinde geliştirmek önce bu değişikliklerden haberdar olmanız gerekir. Varsayılan olarak, Visual Studio 2013 veya üzeri kullanarak oluşturduğunuz tüm projeleri .NET Framework 4.0 veya üzeri hedefleyin.  
  
 Aşağıdaki bölümlerde bu Office proje tasarım değişiklikleri açıklanmaktadır.  
  
## <a name="understanding-the-interface-based-design-of-the-visual-studio-2010-tools-for-office-runtime"></a>Visual Studio 2010 Araçları arabirimi tabanlı tasarım Office çalışma zamanı için anlama  
 Hedefleyen Office projesinde geliştirirken [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra Office çalışma zamanı için Visual Studio 2010 araçları kullanmak türlerinin çoğu arabirimlerdir. Bu ana önceki sürümlerden farklıdır [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], bu tür sınıflar olduğu. Hedeflediğinizde Örneğin, [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki sürümlerde, <xref:Microsoft.Office.Tools.Excel.Worksheet> ve <xref:Microsoft.Office.Tools.Word.Document> sınıfları yerine arabirimleri türleridir. Daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
 Doğrudan'ın önceki sürümlerinde örneği oluşturulamadı türleri için [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], bu tür örnekleri almak için şimdi Globals.Factory yöntemlerinden birini kullanın. Örneğin, uygulayan bir nesne almak için <xref:Microsoft.Office.Tools.Excel.SmartTag> arabirim, Globals.Factory.CreateSmartTag yöntemi kullanın. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Excel ve .NET Framework 4 veya .NET Framework 4. 5'e geçiş Word projelerini güncelleştirme](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [.NET Framework 4 veya .NET Framework 4. 5'e geçiş Office projelerindeki Şerit Özelleştirmelerini Güncelleştirme](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [.NET Framework 4 veya .NET Framework 4. 5'e geçiş Outlook projelerindeki form bölgelerini güncelleştirme](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
### <a name="new-base-classes-in-office-projects"></a>Office Projelerindeki Yeni temel sınıflar  
 Office çalışma zamanı için Visual Studio 2010 Araçları yeni arabirimi tabanlı tasarımını Office projelerindeki oluşturulan sınıflar gibi etkiler `ThisDocument`, `ThisWorkbook`, ve `ThisAddIn`. .NET Framework 3.5 ve framework'ün önceki sürümlerini hedefleyen Office projelerinde sınıflarda Bu oluşturulmuş sınıflar türetmek [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Microsoft.Office.Tools.Word.Document, Microsoft.Office.Tools.Excel.Worksheet, gibi ve Microsoft.Office.Tools.AddIn. ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki sürümleri, bu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] sınıflardır şimdi arabirimleri. Bu nedenle oluşturulan sınıflar Office projelerinde artık kendi uygulamasından türetilir. Bunun yerine, oluşturulan sınıflar yeni temel gibi sınıflarından <xref:Microsoft.Office.Tools.Word.DocumentBase>, <xref:Microsoft.Office.Tools.Excel.WorksheetBase>, ve <xref:Microsoft.Office.Tools.AddInBase>. Daha fazla bilgi için bkz: [programlama VSTO eklentileri](../vsto/programming-vsto-add-ins.md) ve [belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md).  
  
 Taban sınıfları olmayan bir parçası [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yeniden dağıtılabilir. Bunun yerine, bunlar Visual Studio ile birlikte yardımcı programları derlemelerde tanımlanır. Office projeleri oluşturmak ve çözümünüzle birlikte dağıtılmalıdır bu derlemeler çıkış klasörüne kopyalanır. Yardımcı program derlemeleri hakkında daha fazla bilgi için bkz: [Office çalışma zamanı için Visual Studio araçlarında derlemeler](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md).  
  
## <a name="breaking-changes-in-office-projects-that-are-retargeted-to-the-net-framework-4"></a>.NET Framework 4 güncellendiyse Office projelerinde yeni değişiklikler  
 İçin güncellendiyse Office projelerinde karşılaştığınız ana önemli değişiklikler aşağıdaki tabloda listelenmektedir [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Daha fazla ayrıntı için bkz: [geçirme Office çözümlerini .NET Framework 4 veya sonraki bir sürüme](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
|Değişiklik kesiliyor|Sonucu|  
|---------------------|-----------------|  
|<xref:System.Security.SecurityTransparentAttribute> Artık kullanılmaz ve Office projelerinde desteklenmez.|Visual Studio 2008'den yükseltme Office projelerinde AssemblyInfo kod dosyasından bu öznitelik kaldırmanız gerekir. Daha fazla bilgi için bkz: [Çalıştır Office .NET Framework 4 veya .NET Framework 4. 5'e geçiş projeler, yapılması gereken değişiklikler](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|ExcelLocale1033Attribute artık kullanılmaz ve Excel projelerinde desteklenmez.|Excel projelerinde AssemblyInfo kod dosyasından bu öznitelik kaldırmanız gerekir. Daha fazla bilgi için bkz: [güncelleştirme Excel ve Word projelerini, .NET Framework 4 veya .NET Framework 4. 5'e geçiş](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Programlama modeli **Şerit (Görsel Tasarımcı)** proje öğeleri değişti.|Projenizde tüm Şerit öğeleri için arka plan kodu dosyasını değiştirmeniz gerekir. Şerit denetimlerini çalışma zamanında başlatır, Şerit olaylarını işleme veya program aracılığıyla bir Şerit bileşeninin konumunu ayarlar herhangi bir kodu aynı zamanda değiştirmeniz gerekir. Daha fazla bilgi için bkz: [Office Şerit Özelleştirmelerini Güncelleştirme projeleri bu geçiş, .NET Framework 4 veya .NET Framework 4.5](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Outlook form bölgeleri programlama modeli değişti.|Projenizi ve çalışma zamanında bazı form bölgesi sınıflarını başlatır herhangi bir kod tüm form bölgeleri için arka plan kodu dosyasını değiştirmeniz gerekir. Daha fazla bilgi için bkz: [Outlook Form bölgeleri güncelleştirme projeleri bu geçiş, .NET Framework 4 veya .NET Framework 4.5](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Excel ve Word projeleri akıllı etiketleri için programlama modeli değişti. Akıllı etiketler de kullanım dışı [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] ve [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].|Çözümünüzü akıllı etiketler kullanıyorsa, projeyi derlerken hatalar ortaya çıkar. Akıllı etiketler de kullanım dışı bırakılmıştır çünkü [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] ve [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)], test ve çözümde hata ayıklama önce etiketler kaldırmalısınız [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] ya da daha sonra.|  
|GetVstoObject ve HasVstoObject yöntemlerini sözdizimi değişti|Yerel nesneler birincil birlikte çalışma derlemeleri (PIA) üzerinden bunlara erişim ya da bu yöntemlere projenizdeki Globals.Factory özelliği tarafından döndürülen nesne erişebilmeniz için bu yöntemlere Globals.Factory nesne geçmesi gerekir. Daha fazla bilgi için bkz: [güncelleştirme Excel ve Word projelerini, .NET Framework 4 veya .NET Framework 4. 5'e geçiş](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Word içerik denetimlerinin olayları yeni temsilciler ile ilişkilendirilir.|Yeni temsilcileri belirtmek için Word içerik denetimlerinin olaylarını işleme herhangi bir kodu değiştirmeniz gerekir. Daha fazla bilgi için bkz: [güncelleştirme Excel ve Word projelerini, .NET Framework 4 veya .NET Framework 4. 5'e geçiş](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|OLEObject ve OLEControl sınıfları yeniden adlandırılmıştır.|Kullanmak için bu sınıfların örnekleri kullanan herhangi bir kod değiştirmelisiniz <xref:Microsoft.Office.Tools.Excel.ControlSite> veya <xref:Microsoft.Office.Tools.Word.ControlSite> nesnelerini. Daha fazla bilgi için bkz: [güncelleştirme Excel ve Word projelerini, .NET Framework 4 veya .NET Framework 4. 5'e geçiş](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Öğe sınıfları gibi konak `ThisWorkbook`, `Sheet`  *n* , `ThisDocument`, ve `ThisAddIn`, artık geçersiz kılabilirsiniz Dispose yöntemini sağlar.|Herhangi bir kod Dispose yöntemini geçersiz kılma seçeneğinde kapatma olay işleyicisine konak öğesi sınıf, örneğin, taşımanız `ThisAddIn_Shutdown`ve konak öğesi sınıfından Dispose yöntemini geçersiz kılmayı kaldıracak.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerini geçirme .NET Framework 4 veya üstü](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Office geliştirme yenilikler nelerdir?](http://msdn.microsoft.com/en-us/bf054af2-c896-4723-aa15-6381145b14bb)   
 [Office Çalışma Zamanı İçin Visual Studio Araçlarına Genel Bakış](../vsto/visual-studio-tools-for-office-runtime-overview.md)  
  
  