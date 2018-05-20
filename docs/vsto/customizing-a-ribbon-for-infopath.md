---
title: InfoPath için Şerit özelleştirme
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- InfoPath [Office development in Visual Studio], Ribbon
- Ribbon [Office development in Visual Studio], InfoPath
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 82238cc29504b3ad2b757e94efa89a3c521bca90
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="customize-a-ribbon-for-infopath"></a>InfoPath için Şerit özelleştirme
  Microsoft Office InfoPath Şeritte özelleştirdiğinizde, özel Şerit uygulamada nerede görüneceğini dikkate almanız gerekir. [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)] Şerit InfoPath uygulama windows aşağıdaki üç tür görüntüleyebilirsiniz:  
  
-   Tasarım modunda açılan bir form şablon görünen Windows.  
  
-   Bir form şablonunu temel alan bir form görüntüleyen pencereler.  
  
-   Baskı önizleme penceresi.  
  
 **Uygulandığı öğe:** Bu konu başlığı altındaki bilgiler InfoPath 2010 için VSTO eklentisi projelerine yöneliktir. Daha fazla bilgi için bkz: [Office uygulaması ve proje türüne göre kullanılabilen özellikler](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Kullanıcıları ve tasarımcıları bir form şablonu görünümünü ve şablonun düzenini değiştirmek için Tasarım modunda açın. Kullanıcıların içeriği eklemek için form şablonuna dayalı formları açın.  
  
 Baskı önizleme penceresi tasarımcıları ve kullanıcıların bunları yazdırma önce bir form veya form şablonu sayfaların önizleme sağlar.  
  
> [!NOTE]  
>  **Eklentileri** sekmesi Baskı Önizleme penceresinde görünmez. Baskı Önizleme penceresinde görüntülenecek özel sekme istiyorsanız emin olun **OfficeId** sekmenin özelliğini ayarlı değil **TabAddIns**.  
  
 Şerit görünmesini istediğiniz her pencerenin Şerit türünü belirtmeniz gerekir.  
  
## <a name="specify-the-ribbon-type-in-the-ribbon-designer"></a>Şerit Tasarımcısı'nda Şerit türünü belirtin  
 Kullanıyorsanız **Şerit (Görsel Tasarımcı)** öğesi, tıklatın **RibbonType** Şeritte özelliği **özellikleri** penceresinde ve ardından Şeritteki ID birini seçin Aşağıdaki tabloda açıklanmaktadır.  
  
|Şerit Kimliği|Şerit Projeyi çalıştırdığınızda görüntüleneceği penceresi|  
|---------------|---------------------------------------------------------------------|  
|**Microsoft.InfoPath.Designer**|Tasarım modunda açılan bir form şablon görünen Windows.|  
|**Microsoft.InfoPath.Editor**|Bir form şablonunu temel alan bir form görüntüleyen pencereler.|  
|**Microsoft.InfoPath.PrintPreview**|Baskı önizleme penceresi.|  
  
 Bir projeye birden çok Şerit ekleyebilirsiniz. Birden çok Şerit bir Şerit Kimliğini paylaşıyorsanız, geçersiz kılma `CreateRibbonExtensibilityObject` yönteminde `ThisAddin` sınıfı projenizin çalışma zamanında görüntülemek üzere hangi Şerit belirtin. Daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
## <a name="specify-the-ribbon-type-by-using-ribbon-xml"></a>Şerit XML kullanarak Şerit türünü belirtin  
 Kullanıyorsanız **Şerit (XML)** öğesi, değerini denetleyin *ribbonID* parametresinde <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> yöntemi ve return uygun Şerit.  
  
 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> Yöntemi Şerit kod dosyasında Visual Studio tarafından otomatik olarak oluşturulur. *RibbonID* parametredir açıyor InfoPath penceresini türünü tanımlayan bir dize.  
  
 Aşağıdaki kod örneğinde, özel bir Şerit Tasarım modunda bir form şablonu görüntüleyen bir pencere görüntülemek gösterilmiştir. Görüntülenecek Şerit belirtilen `GetResourceText()` Şerit sınıfında oluşturulan yöntemi. Şerit sınıfı hakkında daha fazla bilgi için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
 [!code-csharp[Trin_RibbonInfoPathBasic#1](../vsto/codesnippet/CSharp/myinfopathproject/ribbon.cs#1)]
 [!code-vb[Trin_RibbonInfoPathBasic#1](../vsto/codesnippet/VisualBasic/myinfopathproject/ribbon.vb#1)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Şerit XML](../vsto/ribbon-xml.md)  
  
  