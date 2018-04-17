---
title: Office projelerinde Özellikler | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Trust Assemblies Location property
- Cache in Document property
- properties [Office development in Visual Studio]
- Namespace for Host Item property
- Office projects [Office development in Visual Studio], properties
- projects [Office development in Visual Studio], properties
- Value2 property
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 47af1dae914528a3a338503989e53f081dfffde5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-in-office-projects"></a>Office Projelerinde Özellikler
  Visual Studio'da Office projeleri için kullanılabilen çeşitli önemli özellikler vardır. Bu özellikleri erişilebilen **özellikleri** penceresi.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="namespace-for-host-item"></a>Namespace konak öğesi  
 Kullanım **Namespace konak öğesi için** konak öğesi sınıfları için ad alanı değiştirmek için özelliği (örneğin, `ThisAddIn`, `ThisWorkbook`, veya `ThisDocument` sınıfları) Visual C# projelerine. Bu özellik görünür **özellikleri** (örneğin, Excel veya Word'den VSTO eklenti projesindeki (örneğin, ExcelWorkbook1.xlsx veya WordDocument1.docx) belge düzeyi projede belge düğümü veya uygulama düğümünü seçtiğinizde penceresi ) içinde **Çözüm Gezgini**.  
  
 Visual C# Office proje oluşturduğunuzda, ana bilgisayar öğeleri proje adını temel alarak bir ad verilir. Kullanmanız önerilir **Namespace konak öğesi için** yerine ad değiştirmek için kodu düzenleme özelliği dosyaları doğrudan. Bu özellik kullandığınızda, ad alanı oluşturulan (gizli) kod dosyalarında yanı sıra görünür kod dosyalarında değiştirilir.  
  
## <a name="cacheindocument"></a>CacheInDocument  
 **CacheInDocument** özelliği görünür **özellikleri** örneği seçtiğinizde belge düzeyi projelerine penceresi bir <xref:System.Data.DataSet> Visual Studio Tasarımcısı'nda. Yalnızca Genel üyeler önbelleğe alınabilir; emin **değiştiricileri** özelliği ayarlanmış **ortak** önbelleğe almak istiyorsanız bir <xref:System.Data.DataSet>.  
  
 Bu özelliği bir Boole değeri alır:  
  
-   Seçin **true** belge kümesindeki önbelleğe almak için.  
  
-   Seçin **false** belgede önbelleğe alınacak veri kümesi istemiyorsanız.  
  
 Verileri önbelleğe alma hakkında daha fazla bilgi için bkz: [önbelleğe alınmış verileri belge düzeyi özelleştirmelerinde](../vsto/cached-data-in-document-level-customizations.md).  
  
## <a name="value2"></a>Value2  
 **Value2** özelliktir yalnızca Excel çalışma kitabı veya şablon projeleri için kullanılabilir. Altında görünür **veri bağlamaları** özelliği düğümünde **özellikleri** seçtiğinizde penceresi bir <xref:Microsoft.Office.Tools.Excel.NamedRange> çalışma sayfası tasarımcısında denetim.  
  
 Kullanım **Value2** özelliğinde **özellikleri** bağlamak için pencere <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> özelliği <xref:Microsoft.Office.Tools.Excel.NamedRange> , veri kaynağında bir alan için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office proje şablonlarına genel bakış](../vsto/office-project-templates-overview.md)   
 [Office Projelerindeki Olaylar](../vsto/events-in-office-projects.md)  
  
  