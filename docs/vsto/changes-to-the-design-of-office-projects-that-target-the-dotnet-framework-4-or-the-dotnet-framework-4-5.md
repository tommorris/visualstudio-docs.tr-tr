---
title: .NET Framework hedefleyen Office projelerinin tasarımı için değiştirir
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, what's new
- what's new [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 84a755d420da494f77397dbad445b7a649f0c943
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="changes-to-the-design-of-office-projects-that-target-the-net-framework-4-or-the-net-framework-45"></a>Office projelerinin tasarımı için hedef .NET Framework 4 veya .NET Framework 4.5 değiştirir
  İtibariyle [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)], Visual Studio hedefleyen Office projelerinin tasarımı için bazı değişiklikler sunulan [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Visual Studio'nun önceki sürümleri Office projelerinde biliyorsanız, bu .NET Framework 4.0 veya sonraki sürümlerini hedefleyen Office projelerinde geliştirmek önce bu değişikliklerden haberdar olmanız gerekir. Varsayılan olarak, Visual Studio 2013 veya üzeri kullanarak oluşturduğunuz tüm projeleri .NET Framework 4.0 veya üzeri hedefleyin.  
  
 Aşağıdaki bölümlerde bu Office proje tasarım değişiklikleri açıklanmaktadır.  
  
## <a name="understand-the-interface-based-design-of-the-visual-studio-2010-tools-for-office-runtime"></a>Office çalışma zamanı için Visual Studio 2010 Araçları arabirimi tabanlı tasarımını anlama  
 Hedefleyen Office projesinde geliştirirken [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya daha sonra Office çalışma zamanı için Visual Studio 2010 araçları kullanmak türlerinin çoğu arabirimlerdir. Bu ana önceki sürümlerden farklıdır [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], bu tür sınıflar olduğu. Hedeflediğinizde Örneğin, [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki sürümlerde, <xref:Microsoft.Office.Tools.Excel.Worksheet> ve <xref:Microsoft.Office.Tools.Word.Document> sınıfları yerine arabirimleri türleridir. Daha fazla bilgi için bkz: [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
 Doğrudan'ın önceki sürümlerinde örneği oluşturulamadı türleri için [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], şimdi yöntemlerini kullanın `Globals.Factory` bu tür örnekleri nesnesi. Örneğin, uygulayan bir nesne almak için <xref:Microsoft.Office.Tools.Excel.SmartTag> arabirim, kullanın `Globals.Factory.CreateSmartTag` yöntemi. Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [.NET Framework 4 veya .NET Framework 4. 5'e geçiş Excel ve Word projelerini güncelleştirme](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [.NET Framework 4 veya .NET Framework 4. 5'e geçiş Office projelerindeki Şerit Özelleştirmelerini Güncelleştirme](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [.NET Framework 4 veya .NET Framework 4. 5'e geçiş Outlook projelerindeki form bölgelerini güncelleştirme](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
### <a name="new-base-classes-in-office-projects"></a>Office Projelerindeki Yeni temel sınıflar  
 Office çalışma zamanı için Visual Studio 2010 Araçları yeni arabirimi tabanlı tasarımını Office projelerindeki oluşturulan sınıflar gibi etkiler `ThisDocument`, `ThisWorkbook`, ve `ThisAddIn`. .NET Framework 3.5 ve framework'ün önceki sürümlerini hedefleyen Office projelerinde sınıflarda Bu oluşturulmuş sınıflar türetmek [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] gibi `Microsoft.Office.Tools.Word.Document`, `Microsoft.Office.Tools.Excel.Worksheet`, ve `Microsoft.Office.Tools.AddIn`. ' İ hedefleyen projelerde [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki sürümleri, bu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] sınıflardır şimdi arabirimleri. Bu nedenle oluşturulan sınıflar Office projelerinde artık kendi uygulamasından türetilir. Bunun yerine, oluşturulan sınıflar yeni temel gibi sınıflarından <xref:Microsoft.Office.Tools.Word.DocumentBase>, <xref:Microsoft.Office.Tools.Excel.WorksheetBase>, ve <xref:Microsoft.Office.Tools.AddInBase>. Daha fazla bilgi için bkz: [Program VSTO eklentileri](../vsto/programming-vsto-add-ins.md) ve [Program belge düzeyi özelleştirmeleri](../vsto/programming-document-level-customizations.md).  
  
 Taban sınıfları olmayan bir parçası [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yeniden dağıtılabilir. Bunun yerine, bunlar Visual Studio ile birlikte yardımcı programları derlemelerde tanımlanır. Office projeleri oluşturmak ve çözümünüzle birlikte dağıtılmalıdır bu derlemeler çıkış klasörüne kopyalanır. Yardımcı program derlemeleri hakkında daha fazla bilgi için bkz: [Office çalışma zamanı için Visual Studio araçlarında derlemeler](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md).  
  
## <a name="breaking-changes-in-office-projects-that-are-retargeted-to-the-net-framework-4"></a>.NET Framework 4'e güncellendiyse Office projelerinde yeni değişiklikler  
 İçin güncellendiyse Office projelerinde karşılaştığınız ana önemli değişiklikler aşağıdaki tabloda listelenmektedir [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki bir sürümü. Daha fazla ayrıntı için bkz: [geçirmek Office çözümlerini .NET Framework 4 veya sonraki bir sürüme](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md).  
  
|Değişiklik kesiliyor|Sonucu|  
|---------------------|-----------------|  
|<xref:System.Security.SecurityTransparentAttribute> Artık kullanılmaz ve Office projelerinde desteklenmez.|Visual Studio 2008'den yükseltme Office projelerinde AssemblyInfo kod dosyasından bu öznitelik kaldırmanız gerekir. Daha fazla bilgi için bkz: [gerekli .NET Framework 4 veya .NET Framework 4. 5'e geçiş Office projelerini çalıştırmak için değişiklikler](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|**ExcelLocale1033Attribute** artık kullanılmaz ve Excel projelerinde desteklenmez.|Bu özniteliği kaldırın *AssemblyInfo* Excel projeleri kod dosyasında. Daha fazla bilgi için bkz: [.NET Framework 4 veya .NET Framework 4. 5'e geçiş güncelleştirme Excel ve Word projeleri](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Programlama modeli **Şerit (Görsel Tasarımcı)** proje öğeleri değişti.|Projenizde tüm Şerit öğeleri için arka plan kodu dosyasını değiştirmeniz gerekir. Şerit denetimlerini çalışma zamanında başlatır, Şerit olaylarını işleme veya program aracılığıyla bir Şerit bileşeninin konumunu ayarlar herhangi bir kodu aynı zamanda değiştirmeniz gerekir. Daha fazla bilgi için bkz: [.NET Framework 4 veya .NET Framework 4. 5'e geçiş Office projelerindeki güncelleştirme Şerit Özelleştirmelerini](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Outlook form bölgeleri programlama modeli değişti.|Projenizi ve çalışma zamanında bazı form bölgesi sınıflarını başlatır herhangi bir kod tüm form bölgeleri için arka plan kodu dosyasını değiştirmeniz gerekir. Daha fazla bilgi için bkz: [.NET Framework 4 veya .NET Framework 4. 5'e geçiş Outlook projelerindeki form bölgelerini güncelleştirme](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Excel ve Word projeleri akıllı etiketleri için programlama modeli değişti. Akıllı etiketler de kullanım dışı [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] ve [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].|Çözümünüzü akıllı etiketler kullanıyorsa, projeyi derlerken hatalar ortaya çıkar. Akıllı etiketler de kullanım dışı bırakılmıştır çünkü [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] ve [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)], test ve çözümde hata ayıklama önce etiketler kaldırmalısınız [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] ya da daha sonra.|  
|Söz dizimi `GetVstoObject` ve `HasVstoObject` yöntemleri değişti|Geçmesi gereken `Globals.Factory` yerel nesneler birincil birlikte çalışma derlemeleri (PIA) üzerinden bunlara erişim ya da bu yöntemleri tarafından döndürülen nesne üzerinde erişebilirsiniz, bu yöntemleri nesnesine `Globals.Factory` projenizdeki özelliği. Daha fazla bilgi için bkz: [.NET Framework 4 veya .NET Framework 4. 5'e geçiş güncelleştirme Excel ve Word projeleri](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Word içerik denetimlerinin olayları yeni temsilciler ile ilişkilendirilir.|Yeni temsilcileri belirtmek için Word içerik denetimlerinin olaylarını işleme herhangi bir kodu değiştirmeniz gerekir. Daha fazla bilgi için bkz: [.NET Framework 4 veya .NET Framework 4. 5'e geçiş güncelleştirme Excel ve Word projeleri](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|`OLEObject` Ve `OLEControl` sınıfları yeniden adlandırılmıştır.|Kullanmak için bu sınıfların örnekleri kullanan herhangi bir kod değiştirmelisiniz <xref:Microsoft.Office.Tools.Excel.ControlSite> veya <xref:Microsoft.Office.Tools.Word.ControlSite> nesnelerini. Daha fazla bilgi için bkz: [.NET Framework 4 veya .NET Framework 4. 5'e geçiş güncelleştirme Excel ve Word projeleri](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md).|  
|Öğe sınıfları gibi konak `ThisWorkbook`, `Sheet` *n*, `ThisDocument`, ve `ThisAddIn`, artık sağlayan bir `Dispose` geçersiz kılabilirsiniz yöntemi.|Herhangi bir kod taşımanız gerekir `Dispose` yöntemi geçersiz kılma `Shutdown` konak öğesi sınıfı, örneğin, olay işleyicisi `ThisAddIn_Shutdown`, kaldırıp `Dispose` yöntemi yok sayın, konak öğesi sınıfından.|  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümlerini .NET Framework 4 veya sonraki bir sürümüne geçirme](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Office geliştirme yenilikler nelerdir?](http://msdn.microsoft.com/en-us/bf054af2-c896-4723-aa15-6381145b14bb)   
 [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md)  
  
  