---
title: "Özel Eylemler Outlook Form bölgeleri | Microsoft Docs"
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
- form regions [Office development in Visual Studio], custom actions
- custom actions [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 66a4d81728d438a749b46e42b003c02d08f13d67
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="custom-actions-in-outlook-form-regions"></a>Outlook Form Bölgelerindeki Özel Eylemler
  Eylemler bir Microsoft Office Outlook öğesine yanıt vermesine olanak sağlayan düğmeler görüntüler. Örneğin, bir posta öğesine yanıtlamak için kullanıcılar'ı tıklatın **yanıt**, **Tümünü Yanıtla**, veya **İleri** eylem düğmesi. Bu eylemlerin her biri, yeni bir posta öğesi oluşturur ve özgün öğedeki bilgileri kullanarak öğenin alanlarını doldurur.  
  
 Her türlü Outlook öğesini açan özel bir eylem oluşturabilirsiniz. Örneğin, yeni bir randevu veya görev öğesi açan özel bir eylem ekleyebilirsiniz. Özel bir eylem özelliklerini ayarlamak veya yeni öğe alanları doldurmak için özel kod kullanın. Özel eylemler görüntülenir **özel eylemler** bir Outlook Inspector penceresinde açık olan bir öğenin açılır.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="adding-custom-actions-to-a-form-region"></a>Özel Eylemler için bir Form bölgesi ekleme  
 Özel bir eylem form bölgesine eklemek için kullanın **özel eylemler** iletişim kutusu. Açabilirsiniz **özel eylemler** iletişim kutusunda **Çözüm Gezgini** genişleterek **bildirim** düğümü seçerek **CustomActions**özelliği ve üç nokta düğmesini (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips")).  
  
 Kullanabileceğiniz **özel eylemler** belirtmek için iletişim kutusunu bir *hedef form*. Hedef form kullanıcı özel eylemi çalıştırdığında görüntülenen formdur.  
  
 Aynı zamanda **özel eylemler** hedef formda görünmesi özgün öğedeki bilgileri nasıl istediğinizi belirtmek için iletişim kutusu.  
  
 Aşağıdaki tabloda kullanılabilir olan özellikleri açıklar **özel eylemler** iletişim kutusu.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**AddressLike**|Hedef formun nasıl ele alınacağını belirtir.|  
|**Gövde**|Özgün öğe gövdesi hedef forma nasıl eklendiğini belirler.|  
|**Etkin**|Özel eylem etkinleştirilip etkinleştirilmeyeceğini gösterir. Bu özellik ayarlanmışsa **yanlış**, özel eylem devre dışıdır.|  
|**Yöntemi**|Özel eylem çalıştırıldığında kullanılabilir yanıt türünü belirtir. Özel eylem form gönderme formunu açmak veya göndermek veya formunu açmak istediğinizi sorar.|  
|**Ad**|Bu özel eylem kodda başvurmak için kullanabileceğiniz iç adını belirtir.|  
|**ShowOnRibbon**|Özel eylem özgün öğenin Şerit'te görüntülenip görüntülenmeyeceğini gösterir.|  
|**SubjectPrefix**|Hedef formun konu satırı başlangıcında eklenen metin belirtir.|  
|**TargetForm**|Hedef form ileti sınıf adını belirtir. Örneğin, **IPM. Görev** görev formunu açmak için.|  
|**Başlık**|Özel eylem düğmesi etiketi belirtir.|  
  
## <a name="customizing-a-custom-action-at-run-time"></a>Çalışma zamanında özel bir eylem özelleştirme  
 Kod kullanarak özel eylem davranış da ekleyebilirsiniz. Örneğin, e-posta alıcılarının adlarını alır ve yeni bir randevu öğesi katılımcılarına olarak bu adlar ekler kodu ekleyebilirsiniz. Bunu yapmak için işleyin [özel](http://msdn.microsoft.com/library/office/ff862186.aspx) olayı [MailItem Nesnesi](http://msdn.microsoft.com/library/office/ff861332.aspx).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [İzlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Form Bölgesini Outlook İleti Sınıfıyla İlişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md)  
  
  