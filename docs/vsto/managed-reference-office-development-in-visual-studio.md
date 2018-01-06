---
title: "Yönetilen başvuru (Visual Studio'da Office Geliştirme) | Microsoft Docs"
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
- reference [Office development in Visual Studio], 2007 Microsoft Office system
- Office development in Visual Studio, reference
ms.assetid: 1fa66da0-9d90-4524-ba4f-4da13aab73b5
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 04d89dee1c078ae0b27b96f2e72b25f30dc52845
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="managed-reference-office-development-in-visual-studio"></a>Yönetilen Başvuru (Visual Studio'da Office Geliştirme)
  Bu bölüm, ad alanları için API başvuru belgeleri içerir ve ofisinde kullanılan türleri hedefleyen projeler [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Ad alanları ve .NET Framework 3.5 hedefleyen Office projelerinde kullanılan türler hakkında API başvuru belgeleri için Visual Studio belgelerinde şu bölüme bakın: [http://go.microsoft.com/fwlink/? LinkId 160658 =](http://go.microsoft.com/fwlink/?LinkId=160658).  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 <xref:Microsoft.Office.Tools>  
 Office çözümleri programlama için ortak olan sınıflar içerir. Bunlar VSTO eklentileri, özel görev bölmeleri VSTO eklentileri oluşturmak için sınıflar, Excel ve Word çözümleri akıllı etiketleri oluşturmak için sınıflar ve belge düzeyi özelleştirmelerinde Eylemler bölmeleri oluşturmak için sınıflar için temel sınıf içerir.  
  
 <xref:Microsoft.Office.Tools.Excel>  
 Konak denetimleri ve çözümleri Excel için kullanılabilecek konak öğeleri içerir.  
  
 <xref:Microsoft.Office.Tools.Excel.Controls>  
 Excel denetimleri ve çözümleri Excel için kullanılabilir Windows Forms denetimlerini içerir.  
  
 <xref:Microsoft.Office.Tools.Outlook>  
 Özel form bölgeleri oluşturmak için kullanılan sınıfları dahil olmak üzere Outlook için VSTO eklentileri tarafından kullanılan sınıfları içerir.  
  
 <xref:Microsoft.Office.Tools.Ribbon>  
 Şerit Tasarımcısı kullanılarak oluşturulan Şerit Özelleştirmelerini programlı olarak değiştirmek için kullanılan sınıfları içerir.  
  
 <xref:Microsoft.Office.Tools.Word>  
 Konak denetimleri ve çözümleri için Word kullanılabilir ana bilgisayar öğeleri içerir.  
  
 <xref:Microsoft.Office.Tools.Word.Controls>  
 Word denetimleri ve çözümleri için Word kullanılabilir Windows Forms denetimlerini içerir.  
  
 <xref:Microsoft.VisualStudio.Tools.Applications>  
 İçeren <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> sınıfı ve bir dizi ilgili önbelleğe alınmış veri sınıfları. Bu sınıfları, Microsoft Office yüklü olmayan bilgisayarlara belge düzeyi özelleştirmeleri bazı yönlerini değiştirmek için kullanılabilir.  
  
 <xref:Microsoft.VisualStudio.Tools.Applications.Deployment>  
 İçeren <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> arabirimi (oluşturmak için uygulayabileceğiniz bir *dağıtım eylemi sonrası* Office çözümü için), Office çözümünü yükleme sırasında oluşturulan özel durumları ve görsel parçası olan diğer API'leri Studio altyapısı.  
  
 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime>  
 Tarafından oluşturulan özel durumları çoğunu içeren [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], belge düzeyi özelleştirmeleri veriyi önbelleğe alma için kullanılan birkaç sınıfları ve Visual Studio altyapı parçası olan diğer API'leri.  
  
 <xref:Microsoft.VisualStudio.Tools.Office.BuildTasks>  
 Office projeleri oluşturmak için kullanılan MSBuild görev sınıfları içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çalışma zamanı genel bakış için Visual Studio Araçları](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Başlarken &#40; Office geliştirme Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [Office Çözümleri Tasarlama ve Oluşturma](../vsto/designing-and-creating-office-solutions.md)  
  
  