---
title: İş akışlarında form desteği | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9b3a07f56819818e55548292f3dbcdc1095d9f00
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326086"
---
# <a name="form-support-in-workflows"></a>İş akışlarında form desteği
  Forms dört tür bir iş akışında kullanılabilir: ilişki, başlatma, görev ve değişikliği. Bu form türleri bir ASPX formunu veya InfoPath formu temel alabilir. Düzeyi destek [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] belirli bir formu aşağıdaki tablolarda açıklanan, birkaç etkene bağlıdır sağlar. İş akışı form türleri hakkında daha fazla bilgi için bkz: [iş akışı formları genel bakış](http://go.microsoft.com/fwlink/?LinkId=185228) MSDN Web sitesinde.  
  
## <a name="xml-refactoring"></a>XML yeniden düzenleme
 Bir ASPX association veya başlatma formu eklediğinizde bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] iş akışı proje öğesi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] otomatik olarak iş akışının XML'de refactors *Elements.xml* dosya ilişkilendirme başvuruyor öznitelik tutmak için veya başlatma form adı veya dağıtım yol güncelleştirildiğinde eşitlenmiş veya formundaki silinir. Ancak, kullandığınızda, diğer form türleri bir görev veya değiştirme formu gibi bir iş akışındaki *Elements.xml* dosya bulunanad değil.  
  
## <a name="form-support-in-new-visual-studio-workflows"></a>Yeni Visual Studio akışlarında form desteği
 Aşağıdaki tabloda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ASPX veya InfoPath formlarında oluşturulan iş akışlarındaki farklı form türleri için destek [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
|Form türü|Visual Studio'da bir ASPX Form ile oluşturulan iş akışı|Visual Studio'da InfoPath formu kullanılarak oluşturulan iş akışı|  
|---------------|---------------------------------------------------------|-----------------------------------------------------------------|  
|İlişkilendirme|-Bir ASPX ilişkilendirme formu kullanarak iş akışına eklenebilir **iş akışı ilişkilendirme formu** öğe şablonu.<br />- *Elements.xml* formun eklendiğinde, yeniden adlandırılmış veya silinmiş veya onun dağıtım yol değiştiğinde iş akışının dosya bulunanad.<br />-Daha fazla bilgi için [izlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).|-Hiçbir InfoPath ilişkilendirme form şablonunda olduğundan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Yok arasında hiçbir tümleştirme [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve InfoPath Tasarımcısı.<br />- *Elements.xml* dosya akışının bulunanad değil.|  
|Başlatma|-Bir ASPX başlatma formu kullanarak iş akışına eklenebilir **iş akışı başlatma formu** öğe şablonu.<br />- *Elements.xml* formun eklendiğinde, yeniden adlandırılmış veya silinmiş veya onun dağıtım yol değiştiğinde iş akışının dosya bulunanad.<br />-Daha fazla bilgi için [izlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).|-Hiçbir InfoPath ilişkilendirme form şablonunda olduğundan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Yok arasında hiçbir tümleştirme [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve InfoPath Tasarımcısı.<br />- *Elements.xml* dosya akışının bulunanad değil.|  
|Görev|-Herhangi bir ASPX görev form şablonu kullanılabilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Uygulama sayfası oluşturma ve kodu ekleyin.<br />- *Elements.xml* dosya akışının bulunanad değil.<br />-Daha fazla bilgi için [iş akışı görev formları (SharePoint Foundation)](http://go.microsoft.com/fwlink/?LinkId=187674)|-Hiçbir InfoPath görev form şablonunda olduğundan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Yok arasında hiçbir tümleştirme [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve InfoPath Tasarımcısı.<br />- *Elements.xml* dosya akışının bulunanad değil.|  
|Değişiklik|-Herhangi bir ASPX değişikliği form şablonu kullanılabilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Bir değişiklik form eklemek için uygulama sayfası oluşturma ve kodu ekleyin.<br />- *Elements.xml* dosya akışının bulunanad değil. El ile uygun şekilde düzenlemeden gerekir.<br />-Daha fazla bilgi için [iş akışı değişikliği formları (SharePoint Foundation)](http://go.microsoft.com/fwlink/?LinkId=187675)|-Hiçbir InfoPath değişikliği form şablonunda olduğundan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Yok arasında hiçbir tümleştirme [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve InfoPath Tasarımcısı.<br />- *Elements.xml* dosya akışının bulunanad değil.|  
  
## <a name="form-support-in-imported-sharepoint-reusable-workflows"></a>İçeri aktarılan SharePoint yeniden kullanılabilir iş akışlarında form desteği
 Aşağıdaki tabloda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] içine aktarılır SharePoint arası yeniden kullanılabilir iş akışlarını ASPX veya InfoPath formlarda farklı form türleri için destek [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
|Form türü|SharePoint Tasarımcısı'ndan alınan bir ASPX form sahip yeniden kullanılabilir iş akışı|SharePoint Tasarımcısı'ndan alınan InfoPath formu sahip yeniden kullanılabilir iş akışı|  
|---------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|  
|İlişkilendirme|-Form başvuru *Elements.xml* iş akışı dosyası.<br />- *Elements.xml* formu yeniden adlandırılmış veya silinmiş veya onun dağıtım yol değiştiğinde iş akışının dosya bulunanad.|-Form alındı, ancak başvurulan değil *Elements.xml* iş akışı.<br />- *Elements.xml* dosya akışının bulunanad değil.|  
|Başlatma|-İş akışında tarafından başvurulan formu *Elements.xml* iş akışı dosyası.<br />- *Elements.xml* formu yeniden adlandırılmış veya silinmiş veya onun dağıtım yol değiştiğinde iş akışının dosya bulunanad.|-Form alındı, ancak başvurulan değil *Elements.xml* iş akışı.<br />- *Elements.xml* dosya akışının bulunanad değil. **Not:** kurallar ve Özellikler gerekir eklenebilir ve bu senaryonun işe yaraması için değiştirildi.|  
|Görev|-Form başvuru *Elements.xml* iş akışı dosyası.<br />- *Elements.xml* dosya akışının bulunanad değil.|-Form alındı, ancak başvurulan değil *Elements.xml* iş akışı.<br />- *Elements.xml* dosya akışının bulunanad değil. **Not:** kurallar ve Özellikler gerekir eklenebilir ve bu senaryonun işe yaraması için değiştirildi.|  
|Değişiklik|Yok. ASPX değişikliği forms SharePoint Tasarımcısı'nda oluşturulamıyor.|Yok. Formlara değişikliği iş akışı dışarı aktardığınızda, .wsp dosyasına dahil edilmeyen yerleşik SharePoint Server iş akışı dışında SharePoint Tasarımcısı'nda oluşturulamıyor.|  
  
## <a name="see-also"></a>Ayrıca bkz.
 [İzlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)   
 [SharePoint iş akışı çözümleri oluşturma](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [Mevcut bir SharePoint sitesinden öğeleri içeri aktarma](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)  
  
  
