---
title: Outlook için Şerit özelleştirme
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Inspectors [Office development in Visual Studio]
- Outlook [Office development in Visual Studio], Ribbon
- customizing the Ribbon, about customizing the Ribbon
- custom Ribbon, about customizing the Ribbon
- Ribbon [Office development in Visual Studio], Outlook
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ef1c72d5c24c70a539b909e8d338a235ceb52a49
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="customize-a-ribbon-for-outlook"></a>Outlook için Şerit özelleştirme
  Microsoft Office Outlook Şeritte özelleştirdiğinizde, özel Şerit uygulamada nerede görüneceğini dikkate almanız gerekir. Outlook ana uygulama kullanıcı arabirimi (UI) ve kullanıcıların e-posta iletileri oluşturmak gibi belirli görevleri gerçekleştirdiğinizde, açık windows Şerit görüntüler. Bu uygulama windows denetçiler adlandırılır.  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl I: Outlook Şeritte özelleştirmek için Şerit Tasarımcısı musunuz?](http://go.microsoft.com/fwlink/?LinkID=130312).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="add-a-custom-ribbon-to-the-main-application-ui"></a>Özel Şerit ana uygulama kullanıcı Arabirimi ekleme  
 Ana uygulama kullanıcı Arabirimi Outlook'ta Gezgin olarak adlandırılır. Kullanıyorsanız **Şerit (Görsel Tasarımcı)** Gezgini'ne tıklayarak bir Şerit öğesi, ekleyebilirsiniz **RibbonType** Şeritte özelliğinin **özellikleri** penceresi ardından seçerek **Microsoft.Outlook.Explorer**.  
  
## <a name="assign-a-ribbon-to-an-inspector"></a>Bir denetleyici Şerit atayın  
 İleti sınıfı denetleyici için karşılık gelen Şerit türü belirterek özelleştirmek istediğiniz denetçisi tanımlayın.  
  
 Kullanıyorsanız **Şerit (Görsel Tasarımcı)** öğesi, tıklatın **RibbonType** Şeritte özelliğinin **özellikleri** penceresinde ve ardından bir veya daha fazla Şerit kimlikleri değerlerin listesi.  
  
 Bir projeye birden çok Şerit ekleyebilirsiniz. Birden çok Şerit bir Şerit Kimliğini paylaşıyorsa, geçersiz kılma `CreateRibbonExtensibilityObject` yönteminde `ThisAddin` sınıfı projenizin hangi çalışma zamanında görüntülemek için Şerit belirtin. Daha fazla bilgi için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md). Şerit türleri hakkında daha fazla bilgi için teknik makalesine bakın [Outlook 2007 Şerit özelleştirme](http://msdn.microsoft.com/en-us/946e97ea-f556-4e84-8fac-01cd9214e170).  
  
## <a name="specify-the-ribbon-type-by-using-ribbon-xml"></a>Şerit XML kullanarak Şerit türünü belirtin  
 Kullanıyorsanız **Şerit (XML)** öğesi, değerini denetleyin *ribbonID* parametresinde <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> yöntemi ve return uygun Şerit.  
  
 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> Yöntemi Şerit kod dosyasında Visual Studio tarafından otomatik olarak oluşturulur. *RibbonID* parametredir Gezgin'i ya da belirli bir denetleyici türünü tanımlayan bir dize. Olası değerlerini tam listesi için *ribbonID* parametresi, teknik makalesine bakın [Outlook 2007 Şerit özelleştirme](http://msdn.microsoft.com/en-us/946e97ea-f556-4e84-8fac-01cd9214e170).  
  
 Aşağıdaki kod örneğinde, özel bir görüntülenecek gösterilmiştir yalnızca Şerit `Microsoft.Outlook.Mail.Compose` denetçisi. Bir kullanıcı yeni bir e-posta iletisi oluşturduğunda açar Inspector budur. Görüntülenecek Şerit belirtilen `GetResourceText()` üretildi yöntemi **Şerit** sınıfı. Hakkında daha fazla bilgi için **Şerit** sınıfı için bkz: [Şerit XML](../vsto/ribbon-xml.md).  
  
 [!code-csharp[Trin_RibbonOutlookBasic#1](../vsto/codesnippet/CSharp/Trin_RibbonOutlookBasic/Ribbon1.cs#1)]
 [!code-vb[Trin_RibbonOutlookBasic#1](../vsto/codesnippet/VisualBasic/Trin_RibbonOutlookBasic/Ribbon1.vb#1)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Şerit çalışma zamanında erişme](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [Şerit Tasarımcısı](../vsto/ribbon-designer.md)   
 [Şerit XML](../vsto/ribbon-xml.md)  
  
  