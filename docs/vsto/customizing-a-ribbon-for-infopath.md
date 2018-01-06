---
title: "InfoPath için Şerit özelleştirme | Microsoft Docs"
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
- InfoPath [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], InfoPath
ms.assetid: 498c6457-679a-46f2-939f-c0597a17b7ec
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 647f3a61582c58ee2d132ebd0f81fc6ecff44a02
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-a-ribbon-for-infopath"></a>InfoPath İçin Şerit Özelleştirme
  Microsoft Office InfoPath Şeritte özelleştirdiğinizde, özel Şerit uygulamada nerede görüneceğini dikkate almanız gerekir. [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]Şerit InfoPath uygulama windows aşağıdaki üç tür görüntüleyebilirsiniz:  
  
-   Tasarım modunda açılan bir form şablon görünen Windows.  
  
-   Bir form şablonunu temel alan bir form görüntüleyen pencereler.  
  
-   Baskı önizleme penceresi.  
  
 **Uygulandığı öğe:** Bu konu başlığı altındaki bilgiler InfoPath 2010 için VSTO eklentisi projelerine yöneliktir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Kullanıcıları ve tasarımcıları bir form şablonu görünümünü ve şablonun düzenini değiştirmek için Tasarım modunda açın. Kullanıcıların içeriği eklemek için form şablonuna dayalı formları açın.  
  
 Baskı önizleme penceresi tasarımcıları ve kullanıcıların bunları yazdırma önce bir form veya form şablonu sayfaların önizleme sağlar.  
  
> [!NOTE]  
>  **Eklentileri** sekmesi Baskı Önizleme penceresinde görünmez. Baskı Önizleme penceresinde görüntülenecek özel sekme istiyorsanız emin olun **OfficeId** sekmenin özelliğini ayarlı değil **TabAddIns**.  
  
 Şerit görünmesini istediğiniz her pencerenin Şerit türünü belirtmeniz gerekir.  
  
## <a name="specifying-the-ribbon-type-in-the-ribbon-designer"></a>Şerit Tasarımcısı'nda Şerit türünü belirleme  
 Kullanıyorsanız **Şerit (Görsel Tasarımcı)** öğesi, tıklatın **RibbonType** Şeritte özelliği **özellikleri** penceresinde ve ardından Şeritteki ID birini seçin Aşağıdaki tabloda açıklanmaktadır.  
  
|Şerit Kimliği|Şerit Projeyi çalıştırdığınızda görüntüleneceği penceresi|  
|---------------|---------------------------------------------------------------------|  
|**Microsoft.InfoPath.Designer**|Tasarım modunda açılan bir form şablon görünen Windows.|  
|**Microsoft.InfoPath.Editor**|Bir form şablonunu temel alan bir form görüntüleyen pencereler.|  
|**Microsoft.InfoPath.PrintPreview**|Baskı önizleme penceresi.|  
  
 Bir projeye birden çok Şerit ekleyebilirsiniz. Birden çok Şerit bir Şerit Kimliğini paylaşıyorsanız, içinde yöntemini geçersiz kılma `ThisAddin` sınıfı projenizin çalışma zamanında görüntülemek üzere hangi Şerit belirtin. Daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
## <a name="specifying-the-ribbon-type-by-using-ribbon-xml"></a>Şerit XML kullanarak Şerit türünü belirleme  
 Kullanıyorsanız **Şerit (XML)** öğesi, değerini denetleyin *ribbonID* parametresinde <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> yöntemi ve return uygun Şerit.  
  
 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> Yöntemi Şerit kod dosyasında Visual Studio tarafından otomatik olarak oluşturulur. *RibbonID* parametredir açıyor InfoPath penceresini türünü tanımlayan bir dize.  
  
 Aşağıdaki kod örneğinde, özel bir Şerit Tasarım modunda bir form şablonu görüntüleyen bir pencere görüntülemek gösterilmiştir. Görüntülenecek Şerit belirtilen `GetResourceText()` Şerit sınıfında oluşturulan yöntemi. Şerit sınıfı hakkında daha fazla bilgi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
 [!code-csharp[Trin_RibbonInfoPathBasic#1](../vsto/codesnippet/CSharp/myinfopathproject/ribbon.cs#1)]
 [!code-vb[Trin_RibbonInfoPathBasic#1](../vsto/codesnippet/VisualBasic/myinfopathproject/ribbon.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Şerit XML](../vsto/ribbon-xml.md)  
  
  