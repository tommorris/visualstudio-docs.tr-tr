---
title: "İş akışlarında form desteği | Microsoft Docs"
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
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
ms.assetid: 1706f6a2-ea84-4234-85ae-19feb8540507
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e2c63af83c6ca8249e87d60f23043c0639c7fd43
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="form-support-in-workflows"></a>İş Akışlarında Form Desteği
  Forms dört tür bir iş akışında kullanılabilir: ilişki, başlatma, görev ve değişikliği. Bu form türleri bir ASPX formunu veya InfoPath formu temel alabilir. Düzeyi destek [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] belirli bir formu aşağıdaki tablolarda açıklanan, birkaç etkene bağlıdır sağlar. İş akışı form türleri hakkında daha fazla bilgi için bkz: [iş akışı formları genel bakış](http://go.microsoft.com/fwlink/?LinkId=185228) MSDN Web sitesinde.  
  
## <a name="xml-refactoring"></a>XML yeniden düzenleme  
 Bir ASPX association veya başlatma formu eklediğinizde bir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] iş akışı proje öğesi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] otomatik olarak bir ilişki veya başlatma forma eşitlenmiş başvuruda bulunan öznitelik tutmak için iş akışı Elements.xml dosyasındaki XML refactors Her form adı veya dağıtım yol güncelleştirilir veya formun silinir. Bir görev veya değiştirme formu gibi bir iş akışındaki diğer form türleri kullandığınızda ancak Elements.xml dosya bulunanad değil.  
  
## <a name="form-support-in-new-visual-studio-workflows"></a>Yeni Visual Studio akışlarında form desteği  
 Aşağıdaki tabloda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ASPX veya InfoPath formlarında oluşturulan iş akışlarındaki farklı form türleri için destek [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
|Form türü|Visual Studio'da bir ASPX Form ile oluşturulan iş akışı|Visual Studio'da InfoPath formu kullanılarak oluşturulan iş akışı|  
|---------------|---------------------------------------------------------|-----------------------------------------------------------------|  
|İlişkilendirme|-Bir ASPX ilişkilendirme formu kullanarak iş akışına eklenebilir **iş akışı ilişkilendirme formu** öğe şablonu.<br />-İş akışının Elements.xml dosya, formun eklendiğinde, yeniden adlandırılmış veya silinmiş veya onun dağıtım yol değiştiğinde bulunanad.<br />-Daha fazla bilgi için [izlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).|-Hiçbir InfoPath ilişkilendirme form şablonunda olduğundan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Yok arasında hiçbir tümleştirme [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve InfoPath Tasarımcısı.<br />-İş akışının Elements.xml dosya bulunanad değil.|  
|Başlatma|-Bir ASPX başlatma formu kullanarak iş akışına eklenebilir **iş akışı başlatma formu** öğe şablonu.<br />-İş akışının Elements.xml dosya, formun eklendiğinde, yeniden adlandırılmış veya silinmiş veya onun dağıtım yol değiştiğinde bulunanad.<br />-Daha fazla bilgi için [izlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md).|-Hiçbir InfoPath ilişkilendirme form şablonunda olduğundan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Yok arasında hiçbir tümleştirme [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve InfoPath Tasarımcısı.<br />-İş akışının Elements.xml dosya bulunanad değil.|  
|Görev|-Herhangi bir ASPX görev form şablonu kullanılabilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Uygulama sayfası oluşturma ve kodu ekleyin.<br />-İş akışının Elements.xml dosya bulunanad değil.<br />-Daha fazla bilgi için [iş akışı görev formları (SharePoint Foundation)](http://go.microsoft.com/fwlink/?LinkId=187674)|-Hiçbir InfoPath görev form şablonunda olduğundan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Yok arasında hiçbir tümleştirme [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve InfoPath Tasarımcısı.<br />-İş akışının Elements.xml dosya bulunanad değil.|  
|Değişiklik|-Herhangi bir ASPX değişikliği form şablonu kullanılabilir [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Bir değişiklik form eklemek için uygulama sayfası oluşturma ve kodu ekleyin.<br />-İş akışının Elements.xml dosya bulunanad değil. El ile uygun şekilde düzenlemeden gerekir.<br />-Daha fazla bilgi için [iş akışı değişikliği formları (SharePoint Foundation)](http://go.microsoft.com/fwlink/?LinkId=187675)|-Hiçbir InfoPath değişikliği form şablonunda olduğundan [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].<br />-Yok arasında hiçbir tümleştirme [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ve InfoPath Tasarımcısı.<br />-İş akışının Elements.xml dosya bulunanad değil.|  
  
## <a name="form-support-in-imported-sharepoint-reusable-workflows"></a>İçeri aktarılan SharePoint yeniden kullanılabilir iş akışlarında form desteği  
 Aşağıdaki tabloda [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] içine aktarılır SharePoint arası yeniden kullanılabilir iş akışlarını ASPX veya InfoPath formlarda farklı form türleri için destek [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
|Form türü|SharePoint Tasarımcısı'ndan alınan bir ASPX form sahip yeniden kullanılabilir iş akışı|SharePoint Tasarımcısı'ndan alınan InfoPath formu sahip yeniden kullanılabilir iş akışı|  
|---------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|  
|İlişkilendirme|-İş akışı Elements.xml dosyasında başvurulan formu.<br />-İş akışının Elements.xml dosya, formu yeniden adlandırılmış veya silinmiş veya onun dağıtım yol değiştiğinde bulunanad.|-Form alındı, ancak iş akışı Elements.xml içinde başvurulmayan.<br />-İş akışının Elements.xml dosya bulunanad değil.|  
|Başlatma|-Form, iş akışının Elements.xml dosyasındaki iş akışı tarafından başvuruluyor.<br />-İş akışının Elements.xml dosya, formu yeniden adlandırılmış veya silinmiş veya onun dağıtım yol değiştiğinde bulunanad.|-Form alındı, ancak iş akışı Elements.xml içinde başvurulmayan.<br />-İş akışının Elements.xml dosya bulunanad değil. **Not:** kurallar ve Özellikler gerekir eklenebilir ve bu senaryonun işe yaraması için değiştirildi.|  
|Görev|-İş akışı Elements.xml dosyasında başvurulan formu.<br />-İş akışının Elements.xml dosya bulunanad değil.|-Form alındı, ancak iş akışı Elements.xml içinde başvurulmayan.<br />-İş akışının Elements.xml dosya bulunanad değil. **Not:** kurallar ve Özellikler gerekir eklenebilir ve bu senaryonun işe yaraması için değiştirildi.|  
|Değişiklik|Yok. ASPX değişikliği forms SharePoint Tasarımcısı'nda oluşturulamıyor.|Yok. Formlara değişikliği iş akışı dışarı aktardığınızda, .wsp dosyasına dahil edilmeyen yerleşik SharePoint Server iş akışı dışında SharePoint Tasarımcısı'nda oluşturulamıyor.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: İlişkilendirme ve başlatma formları ile iş akışı oluşturma](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)   
 [SharePoint iş akışı çözümleri oluşturma](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [Mevcut bir SharePoint sitesinden öğeleri içeri aktarma](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)  
  
  