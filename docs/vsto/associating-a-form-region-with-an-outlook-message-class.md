---
title: Form bölgesini Outlook ileti sınıfıyla ilişkilendirme | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.InvalidMessageClassName
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FormRegionMessageClassAttribute
- form regions [Office development in Visual Studio], message classes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: e3e3deeb55fb93b1a393d0489213f1d0e7acd85b
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="associating-a-form-region-with-an-outlook-message-class"></a>Form Bölgesini Outlook İleti Sınıfıyla İlişkilendirme
  Form bölgesini her öğenin ileti sınıfıyla ilişkilendirme tarafından hangi Microsoft Office Outlook öğeleri form bölgesini görüntülemek belirtebilirsiniz. Örneğin, bir posta öğesinin altına bir form bölgesi eklemek istiyorsanız, form bölgesini IPM ile ilişkilendirebilirsiniz. İleti sınıfı unutmayın.  
  
 Form bölgesini bir ileti sınıfıyla ilişkilendirmek için ileti sınıf adını belirtin **yeni Outlook Form bölgesi** Sihirbazı'nı veya bir özniteliği form bölgesi üretici sınıfına uygulayın.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="understanding-outlook-message-classes"></a>Outlook ileti sınıflarını anlama  
 Outlook ileti sınıfı Outlook öğesi türünü tanımlar. Aşağıdaki tabloda bu sekiz standart türlerini öğeleri ve onların ileti sınıf adlarını listeler.  
  
|Outlook öğe türü|İleti sınıf adı|  
|-----------------------|------------------------|  
|AppointmentItem|IPM. Randevu|  
|ContactItem|IPM. İlgili kişi|  
|DistListItem|IPM. DistList|  
|JournalItem|IPM. Etkinlik|  
|MailItem|IPM. Not|  
|PostItem|IPM. POST veya IPM. Post.RSS|  
|TaskItem|IPM. Görev|  
  
 Özel ileti sınıflarının adlarını da belirtebilirsiniz. Özel ileti sınıfları Outlook'ta tanımladığınız özel formları tanımlar.  
  
> [!NOTE]  
>  Değişim ve Tümünü Değiştir form bölgeleri için yeni bir özel ileti sınıf adını belirtebilirsiniz. Varolan bir özel formu ileti sınıf adını kullanmak gerekmez. Özel ileti sınıfı adı benzersiz olmalıdır. Adının benzersiz olduğundan emin olmak için bir yolu, aşağıdakine benzer bir adlandırma kuralı kullanmaktır: \< *StandardMessageClassName*>.\< *Şirket*>.\< *MessageClassName*> (örneğin: IPM. Note.Contoso.MyMessageClass).  
  
## <a name="associating-a-form-region-with-an-outlook-message-class"></a>Form Bölgesini Outlook İleti Sınıfıyla İlişkilendirme  
 Bir form bölgesini bir ileti sınıfıyla ilişkilendirmek için iki yolu vardır:  
  
-   Kullanım **yeni Outlook Form bölgesi** Sihirbazı.  
  
-   Sınıf özniteliklerini uygulayın.  
  
### <a name="using-the-new-outlook-form-region-wizard"></a>Yeni Outlook Form bölgesi sihirbazını kullanma  
 Sihirbazın son sayfasında **yeni Outlook Form bölgesi** sihirbazında, standart ileti sınıflarını seçebilir ve form bölgesi ile ilişkilendirmek istediğiniz özel ileti sınıfları adlarını yazın.  
  
 Form bölgesi tüm formu veya formun varsayılan sayfasını değiştirmek için tasarlanmıştır standart ileti sınıfları kullanılamaz. Bir form için yeni bir sayfa ekleyin veya bir form altına eklenen formlar için standart ileti sınıf adları belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Outlook eklenti projesine Form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
 Bir veya daha fazla özel ileti sınıfları eklemek için adlarını yazın **hangi özel ileti sınıfları bu form bölgesini görüntüleyecek?** kutusu.  
  
 Yazdığınız adları aşağıdaki yönergelere uygun olmalıdır:  
  
-   Tam nitelikli ileti sınıf adı kullanın (örneğin: "IPM. Note.Contoso").  
  
-   Birden çok ileti sınıf adlarını ayırmak için noktalı virgül kullanın.  
  
-   "IPM. gibi standart Outlook ileti sınıflarını dahil etmeyin Not"veya"IPM. Başvurun". Yalnızca "IPM. gibi özel ileti sınıfları içerir Note.Contoso".  
  
-   Temel ileti sınıfını tek başına belirtmeyin (örneğin: "IPM").  
  
-   Her ileti sınıf adı 256 karakterden uzun değil.  
  
 **Yeni Outlook Form bölgesi** Sihirbazı doğrular giriş biçimi tıkladığınızda **son**.  
  
> [!NOTE]  
>  **Yeni Outlook Form bölgesi** Sihirbazı sağladığınız ileti sınıf adlarının doğru ya da geçerli olduğunu doğrulamaz.  
  
 Sihirbazı tamamladığınızda **yeni Outlook Form bölgesi** sihirbaz, belirtilen ileti sınıf adlarını içeren form bölgesi sınıfına öznitelikleri uygular. Bu öznitelikler el ile uygulayabilirsiniz.  
  
### <a name="applying-class-attributes"></a>Sınıf öznitelikleri uygulama  
 Tamamlandıktan sonra bir form bölgesini Outlook ileti sınıfıyla ilişkilendirebilirsiniz **yeni Outlook Form bölgesi** Sihirbazı. Bunu yapmak için form bölgesi üretici sınıfına öznitelikleri uygulanır.  
  
 Aşağıdaki örnekte iki gösterir <xref:Microsoft.Office.Tools.Outlook.FormRegionMessageClassAttribute> adlı form bölgesi üretici sınıfına uygulanan öznitelikleri `myFormRegion`. İlk öznitelik standart ileti sınıfı bir posta iletisi form için form bölgesini ilişkilendirir. İkinci öznitelik form bölgesini adlı özel bir ileti sınıfı ile ilişkilendirir `IPM.Task.Contoso`.  
  
 [!code-vb[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Attributes/FormRegion1.vb#1)]
 [!code-csharp[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Attributes/FormRegion1.cs#1)]  
  
 Öznitelikler aşağıdaki yönergelere uygun olmalıdır:  
  
-   Özel ileti sınıfları için tam nitelikli ileti sınıf adı kullanın (örneğin: "IPM. Note.Contoso").  
  
-   Temel ileti sınıfını tek başına belirtmeyin (örneğin: "IPM").  
  
-   Her ileti sınıf adı 256 karakterden uzun değil.  
  
-   Form bölgesi tüm formu veya formun varsayılan sayfasını değiştirirse, standart ileti sınıflarının adlarını dahil etmeyin. Bir form için yeni bir sayfa ekleyin veya bir form altına eklenen formlar için standart ileti sınıf adları belirtebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Outlook eklenti projesine Form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
 Projeyi derlerken visual Studio ileti sınıf adlarının biçimini doğrular.  
  
> [!NOTE]  
>  Visual Studio, sağladığınız ileti sınıf adlarının doğru ya da geçerli olduğunu doğrulamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Form bölgesine çalışma zamanında erişme](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [İzlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Outlook Form bölgeleri oluşturma yönergeleri](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [Form adı ve ileti sınıfına genel bakış](http://msdn.microsoft.com/library/office/ff867629.aspx)   
 [Outlook form ve öğeleri birlikte nasıl çalışır](http://msdn.microsoft.com/library/office/ff869706.aspx)  
  
  