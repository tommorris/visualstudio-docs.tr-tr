---
title: "Office çözümleri geliştirme | Microsoft Docs"
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
- Office development in Visual Studio, about developing solutions
- solutions [Office development in Visual Studio], developing
- Office solutions [Office development in Visual Studio], developing
ms.assetid: 7361cfe0-dee4-48d7-a066-232f87f093ca
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 478bd6d27d6e4ef0fe75891d95cdc4b3258a74e8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="developing-office-solutions"></a>Office Çözümleri Geliştirme
  Visual Studio'da Office geliştirici araçları kullanarak bir proje tasarlama ve sonra proje dosyalarını kurduğunuzda, özel kullanıcı arabirimi (UI) ve kod uygulanmasına yoğunlaşabilirsiniz başlayabilirsiniz.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
> [!NOTE]  
>  Office deneyimi boyunca genişletmek çözümleri geliştirirken ilgileniyor [birden çok platform](https://dev.office.com/add-in-availability)? Yeni [Office eklentileri modeli](https://dev.office.com/docs/add-ins/overview/office-add-ins). VSTO eklentilerini ve çözümlerle karşılaştırıldığında küçük bir yer Office eklentileri sahip ve teknoloji, HTML5, JavaScript, CSS3 ve XML gibi programlama neredeyse her web kullanarak oluşturabilirsiniz.  
  
## <a name="office-solutions-programming-model"></a>Office çözümleri programlama modeli  
 Office nesne modeli çeşitli karşı program nesneleri gösterir. Yönetilen kod kullanarak Office çözümleri program her Office birincil birlikte çalışma derlemeleri içinde türlerini kullanan bir kod yazın. Visual Studio'da Office proje şablonları kullanarak oluşturduğunuz çözümlerde, ayrıca projenizde oluşturulan sınıflar karşı doğrudan kod yazın. Daha fazla bilgi için bkz: [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md).  
  
## <a name="programming-different-types-of-office-solutions"></a>Office çözümleri farklı türlerde programlama  
 Oluşturmakta olduğunuz çözümünün türüyle ilgili projenizde kullanabileceğiniz hangi özellikleri belirler. Örneğin, Windows Forms denetimleri ve genişletilmiş Office denetimleri ekleyebilirsiniz (adlı *konak denetimlerini*) öğeleri sürükleyerek belge düzeyi özelleştirmeleri için **araç** tasarım zamanında Visual Studio'da . Bir VSTO eklentisi geliştiriyorsanız, ancak, yalnızca bu tür denetimleri belgelere çalışma zamanında kodlar yazarak ekleyebilirsiniz.  
  
 Çözümleri farklı türleri için özel özellikler hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [VSTO eklentilerini programlamaya](../vsto/programming-vsto-add-ins.md).  
  
-   [Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md).  
  
-   [Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md).  
  
 Office çözümleri ve projeleri oluşturmanıza yardımcı olacak yordamlar planlamanıza yardımcı olması arka plan bilgileri için bkz: [tasarlama ve oluşturma Office çözümleri](../vsto/designing-and-creating-office-solutions.md).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)|Office çözümlerinde kod yazma farklı yönlerini açıklar.|  
|[VSTO eklentilerini programlama](../vsto/programming-vsto-add-ins.md)|VSTO eklentileri ve ilgili programlama görevleri programlama modeline genel bakış sağlar.|  
|[Belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md)|Belge düzeyi özelleştirmeleri ve ilgili programlama görevleri programlama modeline genel bakış sağlar.|  
|[Office kullanıcı arabirimini özelleştirme](../vsto/office-ui-customization.md)|VSTO eklentileri ve belge düzeyi özelleştirmeleri kullanarak, Office uygulamalarının UI özelleştirebilirsiniz farklı yolları açıklanmaktadır.|  
|[Office çözümlerindeki veriler](../vsto/data-in-office-solutions.md)|Office çözümlerindeki veriler denetimlere veri bağlama ve belge düzeyi özelleştirmelerinde verileri önbelleğe alma gibi çalışabilirsiniz farklı yolları açıklanmaktadır.|  
|[Office çözümleri otomatik kaydetme nasıl etkiler](./how-autosave-impacts-office-solutions.md)|Office çözümleri için otomatik kaydetme etkinleştirildiğinde yapmanız gerekebilir ayarlamalar açıklar.|
|[Office çözümlerinde sorun giderme](../vsto/troubleshooting-office-solutions.md)|Office çözümleri oluşturma sırasında karşılaşabileceğiniz ortak sorunları çözmek için ipuçları verilmektedir.|  
|[Office'te iş parçacığı desteği](../vsto/threading-support-in-office.md)|Office çözümlerinde birden çok iş parçacığı çalışmaya genel bir bakış sağlar.|  
|[Office projelerinde erişilebilirlik](../vsto/accessibility-in-office-projects.md)|Office çözümlerinde kullanılabilen erişilebilirlik özelliklerini açıklar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: oluşturma ve özel belge özelliklerini değiştirme](../vsto/how-to-create-and-modify-custom-document-properties.md)   
 [Nasıl yapılır: Okuma ve belge özellikleri yazma](../vsto/how-to-read-from-and-write-to-document-properties.md)   
 [Nasıl yapılır: Office Çok Dilde Kullanıcı arabirimini hedefleme](../vsto/how-to-target-the-office-multilingual-user-interface.md)   
 [İzlenecek yol: Excel için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)   
 [İzlenecek yol: Excel için ilk belge düzeyi özelleştirmeyi oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)   
 [İzlenecek yol: Outlook için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)   
 [İzlenecek yol: PowerPoint için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)   
 [İzlenecek yol: Proje için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [İzlenecek yol: Word için ilk VSTO eklentinizi oluşturma](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)   
 [İzlenecek yol: Word için ilk belge düzeyi özelleştirmeyi oluşturma](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)  
  
  