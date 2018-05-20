---
title: Genişletilebilirlik arabirimlerini kullanarak kullanıcı Arabirimi özelliklerini özelleştirme
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ICustomTaskPaneConsumer interface
- IRibbonExtensibility interface
- UI customizing [Office development in Visual Studio]
- user interfaces [Office development in Visual Studio], customizing
- application-level add-ins [Office development in Visual Studio], extensibility interfaces
- customizing UI features [Office development in Visual Studio]
- FormRegionStartup interface
- add-ins [Office development in Visual Studio], extensibility interfaces
- extensibility interfaces [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6d9fd69cb747c235f78be8065d07f03f5b39d66b
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="customize-ui-features-by-using-extensibility-interfaces"></a>Genişletilebilirlik arabirimlerini kullanarak kullanıcı Arabirimi özelliklerini özelleştirme
  Visual Studio'da Office geliştirme araçları, sınıflar ve çok sayıda uygulama ayrıntılarını VSTO eklenti içinde özel görev bölmeleri, Şerit özelleştirmelerini ve Outlook form bölgeleri oluşturma için kullanıldıklarında işleyen tasarımcılar sağlar. Ancak, siz de uygulayabilirsiniz *genişletilebilirlik arabirimi* her özel gereksinimleriniz varsa kendiniz özelliği.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
## <a name="overview-of-extensibility-interfaces"></a>Genişletilebilirlik arabirimleri genel bakış  
 Microsoft Office COM VSTO eklentileri Şerit gibi belirli özellikleri özelleştirmek için uygulayabileceğiniz genişletilebilirlik arabirimleri kümesini tanımlar. Bu arabirimleri erişim sağlayan özellikler üzerinde tam denetim sağlar. Ancak, bu arabirimleri uygulama yönetilen kodda COM birlikte çalışabilirliği bazı bilgi gerektirir. Bazı durumlarda, bu arabirimleri programlama modeli de .NET Framework alışkın geliştiriciler için sezgisel değil.  
  
 Bir VSTO eklenti Visual Studio'da Office proje şablonları kullanarak oluşturduğunuz Şerit gibi özellikleri özelleştirmek için genişletilebilirlik arabirimlerini gerekmez. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Sizin için bu arabirimlerini uygular. Bunun yerine, daha sezgisel sınıfları ve Visual Studio tarafından sağlanan tasarımcıları kullanabilirsiniz. Ancak, isterseniz genişletilebilirlik arabirimleri doğrudan VSTO eklentinizi içinde hala uygulayabilirsiniz.  
  
 Sınıflar ve Visual Studio bu özellikler için sağladığı tasarımcılar hakkında daha fazla bilgi için bkz: [özel görev bölmeleri](../vsto/custom-task-panes.md), [Şerit Tasarımcısı](../vsto/ribbon-designer.md), ve [oluşturmak Outlook form bölgeleri](../vsto/creating-outlook-form-regions.md).  
  
## <a name="extensibility-interfaces-you-can-implement-in-a-vsto-add-in"></a>Bir VSTO eklenti uygulayabileceğiniz genişletilebilirlik arabirimleri  
 Aşağıdaki tabloda, uygulayabileceğiniz genişletilebilirlik arabirimleri ve bunları destekleyen uygulamaları listeler.  
  
|Arabirim|Açıklama|Uygulamalar|  
|---------------|-----------------|------------------|  
|<xref:Microsoft.Office.Core.IRibbonExtensibility>|Şerit UI'si özelleştirmek için bu arabirimi uygular. **Not:** ekleyebileceğiniz bir **Şerit (XML)** varsayılan oluşturmak için bir proje öğesi <xref:Microsoft.Office.Core.IRibbonExtensibility> VSTO eklentinizi uygulamasında. Daha fazla bilgi için bkz: [Şerit XML](../vsto/ribbon-xml.md).|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)]<br /><br /> InfoPath 2010<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Proje<br /><br /> Visio<br /><br /> Word|  
|<xref:Microsoft.Office.Core.ICustomTaskPaneConsumer>|Özel görev bölmesi oluşturmak için bu arabirimi uygular.|Excel<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Word|  
|<xref:Microsoft.Office.Interop.Outlook.FormRegionStartup>|Outlook form bölgesi oluşturmak için bu arabirimi uygular.|Outlook|  
  
 Microsoft Office tarafından tanımlanan gibi diğer genişletilebilirlik arabirimleri vardır <xref:Microsoft.Office.Core.IBlogExtensibility>, <xref:Microsoft.Office.Core.EncryptionProvider>, ve <xref:Microsoft.Office.Core.SignatureProvider>. Visual Studio bu arabirimleri eklentide bir VSTO Office proje şablonları kullanılarak oluşturulan uygulama desteklemez.  
  
## <a name="use-extensibility-interfaces"></a>Genişletilebilirlik arabirimleri kullanın  
 Genişletilebilirlik arabirimini kullanarak bir UI özelliği özelleştirmek için VSTO eklentisi projenizde uygun arabirimini uygular. Ardından, geçersiz kılma <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> arabirimini uygulayan sınıf örneği döndürülecek yöntemi.  
  
 Nasıl uygulandığını gösteren örnek bir uygulama için <xref:Microsoft.Office.Core.IRibbonExtensibility>, <xref:Microsoft.Office.Core.ICustomTaskPaneConsumer>, ve <xref:Microsoft.Office.Interop.Outlook.FormRegionStartup> VSTO eklenti Outlook için arabirimlerde UI Yöneticisi örnekte bkz [Office geliştirme örnekleri](../vsto/office-development-samples.md).  
  
### <a name="example-of-implementing-an-extensibility-interface"></a>Genişletilebilirlik arabirimi uygulama örneği  
 Aşağıdaki kod örneğinde basit bir uygulama ortaya koyar <xref:Microsoft.Office.Core.ICustomTaskPaneConsumer> özel görev bölmesi oluşturmak için arabirimi. Bu örnekte, iki sınıf tanımlar:  
  
-   `TaskPaneHelper` Uygulayan sınıf <xref:Microsoft.Office.Core.ICustomTaskPaneConsumer> oluşturmak ve bir özel görev bölmesi görüntülemek için.  
  
-   `TaskPaneUI` Sınıfı, görev bölmesinin kullanıcı Arabirimi sağlar. Öznitelikleri `TaskPaneUI` sınıfı sınıfı sınıfı keşfetmek için Microsoft Office uygulamalarını sağlayan COM görünür hale. Bu örnekte, boş bir UI'dir <xref:System.Windows.Forms.UserControl>, ancak kodu değiştirerek denetimler ekleyebilirsiniz.  
  
    > [!NOTE]  
    >  Kullanıma sunmak için `TaskPaneUI` sınıfı COM için de ayarlamalısınız **kaydetmek için COM birlikte çalışma** projesine özelliği.  
  
 [!code-vb[Trin_SimpleExtensibilityInterface#1](../vsto/codesnippet/VisualBasic/Trin_SimpleExtensibilityInterface/ThisAddIn.vb#1)]
 [!code-csharp[Trin_SimpleExtensibilityInterface#1](../vsto/codesnippet/CSharp/Trin_SimpleExtensibilityInterface/ThisAddIn.cs#1)]  
  
 Uygulama hakkında daha fazla bilgi için <xref:Microsoft.Office.Core.ICustomTaskPaneConsumer>, bkz: [2007 Office sistemi özel görev bölmeleri oluşturmak](http://msdn.microsoft.com/en-us/256313db-18cc-496c-a961-381ed9ca94be) Microsoft Office belgelerinde.  
  
### <a name="example-of-overriding-the-requestservice-method"></a>RequestService yöntemini geçersiz kılma örneği  
 Aşağıdaki kod örneğinde nasıl geçersiz kılınacağı gösterilmektedir <xref:Microsoft.Office.Tools.AddInBase.RequestService%2A> örneği döndürülecek yöntemi `TaskPaneHelper` önceki kod örneğinde sınıfından. Değeri kontrol *serviceGuid* hangi arabirimi istenen ve arabirimi uygulayan bir nesne döndürür belirlemek için parametre.  
  
 [!code-vb[Trin_SimpleExtensibilityInterface#2](../vsto/codesnippet/VisualBasic/Trin_SimpleExtensibilityInterface/ThisAddIn.vb#2)]
 [!code-csharp[Trin_SimpleExtensibilityInterface#2](../vsto/codesnippet/CSharp/Trin_SimpleExtensibilityInterface/ThisAddIn.cs#2)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)   
 [VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)   
 [Office çözümleri geliştirmek](../vsto/developing-office-solutions.md)   
 [VSTO eklentileri diğer Office Çözümlerinden kodu çağırma](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md)   
 [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO Eklentileri Mimarisi](../vsto/architecture-of-vsto-add-ins.md)  
  
  