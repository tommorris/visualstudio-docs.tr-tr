---
title: VBA ve karşılaştırıldığında Visual Studio'da Office çözümleri | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VBA code, managed code extensions
- managed code extensions [Office development in Visual Studio], VBA compared to
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a5a92727f08729fc7f8a871d0528c9e652d92f8a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="vba-and-office-solutions-in-visual-studio-compared"></a>Visual Studio'da VBA ve Office Çözümleri Karşılaştırması
  Microsoft Visual Basic for Applications (VBA) Office uygulamaları ile tümleşiktir, yönetilmeyen kod kullanır. Visual Studio kullanılarak oluşturulan Microsoft Office projeleri .NET Framework ve Visual Studio Tasarım araçları yararlanmak etkinleştirin.  
  
 Visual Studio kullanarak oluşturabileceğiniz Office çözümlerinin türleri hakkında bilgi için bkz [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
## <a name="comparison"></a>Karşılaştırma  
 Aşağıdaki tabloda temel karşılaştırması VBA çözümleri ve Visual Studio'da Office çözümleri sağlar.  
  
|VBA çözümleri|Visual Studio'da Office çözümleri|  
|-------------------|---------------------------------------|  
|Belirli bir belgeyle bağlı ve kalıcı kodu kullanır.|Belgedeki (için belge düzeyi özelleştirmeleri), ayrı ayrı depolanan kod kullanır veya derlemedeki uygulamada (VSTO VSTO eklentileri) tarafından yüklenir.|  
|Office nesne modelleri ve VBA API'leri ile çalışır.|Hem Office nesne modelleri için erişim sağlar ve [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] API'leri.|  
|Makro kaydetme ve Basitleştirilmiş bir geliştirici deneyimi için tasarlanmıştır.|Güvenlik, kolay kod bakımı ve tam Visual Studio tümleşik geliştirme ortamı (IDE) kullanma olanağı için tasarlanmıştır.|  
|İyi Office uygulamaları ile çok sıkı tümleştirme yararlı çözümleri için çalışır.|İyi Visual Studio tam kaynaklardan yararlanan çözümler için çalışır ve [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)].|  
|Sınırlamaları kuruluş için güvenlik ve dağıtım alanlarında özellikle vardır.|Kurumsal kullanım için tasarlanmıştır.|  
  
 Bazı şeyleri hızlıca VBA kullanarak yapmak hala daha kolay. Özellikle, VBA için kullanmaya devam etmek istiyor:  
  
-   Özel çalışma sayfası işlevleri.  
  
-   Makro kaydetme.  
  
## <a name="combining-vba-solutions-and-office-solutions-created-by-using-visual-studio"></a>VBA çözümleri ve Visual Studio kullanarak oluşturulan Office çözümlerini birleştirme  
 Visual Studio kullanılarak oluşturulan Office Çözümlerinden gelen VBA kodu çağırabilir ve VBA'dan Visual Studio kullanılarak oluşturulan Office çözümlerinde kod çağırabilir. Belirli teknik Office çözümünüzü VSTO eklenti veya belge düzeyi özelleştirme olmasına bağlı olarak farklılık gösterir. Daha fazla bilgi için bkz: [VSTO eklentileri diğer Office Çözümlerinden gelen çağırma kodda](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md) ve [birleştirme VBA ve belge düzeyi özelleştirmeleri](../vsto/combining-vba-and-document-level-customizations.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri geliştirmesine genel bakış &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO eklentilerinde diğer Office Çözümlerinden kod çağırma](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)   
 [VBA ve belge düzeyi özelleştirmelerini birleştirme](../vsto/combining-vba-and-document-level-customizations.md)   
 [Belge düzeyi özelleştirmeler mimarisi](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO eklentileri mimarisi](../vsto/architecture-of-vsto-add-ins.md)   
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [Başlarken &#40;Visual Studio'da Office geliştirme&#41;](../vsto/getting-started-office-development-in-visual-studio.md)  
  
  