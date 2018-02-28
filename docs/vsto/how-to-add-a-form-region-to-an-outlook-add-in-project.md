---
title: "Nasıl yapılır: Outlook eklenti projesine Form bölgesi ekleme | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VSTO.NewFormRegionWizard.Page1
- VSTO.NewFormRegionWizard.Page3
- VSTO.NewFormRegionWizard.Page2
- VSTO.NewFormRegionWizard.Page0
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], adding
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 2029b154ca97f2e856a9e6af8ef58b82f4438df6
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-form-region-to-an-outlook-add-in-project"></a>Nasıl Yapılır: Outlook Eklenti Projesine Form Bölgesi Ekleme
  Standart veya özel bir Microsoft Office Outlook form kullanarak genişletmek için bir form bölgesi oluşturmak **yeni Outlook Form bölgesi** Sihirbazı. Yeni bir form bölgesi oluşturmak ve Visual Studio kullanıcı arabiriminde tasarım veya Outlook'ta tasarlanan form bölgesini içeri aktarabilir ve Visual Basic veya C# kodu ekleyin.  
  
 Başka bir Outlook projesinde kullanılan bir Outlook form bölgesi varsa, onu geçerli Outlook VSTO eklenti projenizde kullanarak tekrar kullanabilirsiniz **varolan öğeyi Ekle** iletişim kutusu. Daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
### <a name="to-add-a-new-form-region-to-an-outlook-project"></a>Yeni bir form bölgesini Outlook projesine eklemek için  
  
1.  Bir Outlook VSTO eklenti projesindeki oluşturun veya açın [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  İçinde **Çözüm Gezgini**, Outlook VSTO eklenti projesi düğümünü seçin.  
  
3.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
4.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **Outlook Form bölgesi**.  
  
5.  Form bölgesi için bir ad yazın **adı** kutusuna ve ardından **Ekle**.  
  
     **NewOutlook Form bölgesi** Sihirbazı'nı başlatır.  
  
6.  Üzerinde **nasıl form bölgesi oluşturmak istediğinizi seçin** sayfasında, yönetilen denetimleri görsel tasarımcıya sürükleyerek form bölgesi tasarlama veya Outlook'ta tasarlanan form bölgesini içeri istediğinizi seçin.  
  
    > [!NOTE]  
    >  Outlook'ta tasarlanan form bölgesini içeri aktarmak seçerseniz, bir Outlook Form Depolama (.ofs) dosyasının konumunu belirtmeniz gerekir. Yönetilen denetimleri Outlook'ta tasarım bir form bölgesi eklenemiyor; yalnızca var olan kullanıcı Arabirimi arka plan kod ekleyebilirsiniz. Daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
7.  Üzerinde **oluşturmak istediğiniz form bölgesini seçin** sayfasında, form bölgesi türlerini gözden geçirin ve seçin ve ardından **sonraki**. Form bölgesi türleri hakkında daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
8.  Üzerinde **açıklayıcı metin sağlayın ve görüntüleme tercihlerini seçin** sayfasında **adı** form bölgesi için bir ad yazın. Değişim ve Tümünü Değiştir form bölgesi türleri için **başlık** ve **açıklama** kutularıdır de kullanılabilir.  
  
     Form bölgesini dağıttığınız zaman ad, başlık ve açıklama Outlook'ta göründüğü hakkında daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
9. Form bölgesi görünmesini istediğiniz bir veya daha fazla görüntü modu seçin.  
  
     Tüm form bölgesi türleri Inspector, görünebilir içinde (öğeleri oluşturma) modunu oluşturun ve (öğeleri görüntüleme için) okuma modunda. Ayrıca bitişik, değişim ve Tümünü Değiştir form bölgesi türleri Okuma Bölmesi'nde yer alabilir.  
  
10. **İleri**'ye tıklayın.  
  
11. Üzerinde **bu form bölgesini görüntüleyecek ileti sınıflarını tanımlayın** sayfasında, standart Outlook ileti sınıflarını seçin veya bir veya daha fazla özel ileti sınıfları adlarını yazın ve ardından **son**. Daha fazla bilgi için bkz: [Form bölgesini Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Form bölgesine çalışma zamanında erişme](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook çözümleri](../vsto/outlook-solutions.md)   
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [Outlook Form bölgeleri oluşturma yönergeleri](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [İzlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [İzlenecek yol: Outlook'ta tasarlanan Form bölgesini içeri aktarma](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [Outlook Form Bölgelerindeki Özel Eylemler](../vsto/custom-actions-in-outlook-form-regions.md)  
  
  