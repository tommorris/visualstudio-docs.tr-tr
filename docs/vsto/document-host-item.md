---
title: "Belge konak öğesi | Microsoft Docs"
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
- documents [Office development in Visual Studio]
- documents [Office development in Visual Studio], document host items
- document host items
- Word [Office development in Visual Studio], Word documents
- Word [Office development in Visual Studio]
- Word documents
- host items [Office development in Visual Studio], Document
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 85c3520d852575eef6e9dae1fd8c1120b9eccd74
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="document-host-item"></a>Belge Konak Öğesi
  <xref:Microsoft.Office.Tools.Word.Document> Konak öğesi türüdür genişleten bir <xref:Microsoft.Office.Interop.Word.Document> Word için birincil birlikte çalışma derlemesinden türü. <xref:Microsoft.Office.Tools.Word.Document> Konak öğesi tüm özellikleri, yöntemleri ve olayları olarak sağlayan bir <xref:Microsoft.Office.Interop.Word.Document> nesnesi, ancak ayrıca ek olayları gösterir ve ana bilgisayar denetimleri ve Windows Forms denetimleri için kapsayıcı görevi görür.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Belge düzeyi projelerine bir varsayılan yok <xref:Microsoft.Office.Tools.Word.Document> projenizdeki belge temsil eden konak öğesi. VSTO eklenti projelerinde oluşturabileceğiniz <xref:Microsoft.Office.Tools.Word.Document> konak öğelerini çalışma zamanında.  
  
## <a name="understanding-the-document-host-item-in-document-level-projects"></a>Belge konak öğesi belge düzeyi projelerine anlama  
 Projenizdeki belgeye erişmek için `ThisDocument` sınıfı. Belge düzeyi projesi oluşturduğunuzda, Visual Studio'nun oluşturduğu `ThisDocument` Word ve özelleştirme kodunuz arasında iletişimi bağlantı olarak hizmet verecek sınıfı. `ThisDocument` Sınıf üyelerine erişim sağlar <xref:Microsoft.Office.Tools.Word.Document> belge açıldığında ya da kapalı olduğunda kodu çalıştırma gibi özelleştirme, temel görevlerini gerçekleştirmek için konak öğesi. Sınıfı, denetimleri belgeye eklemek için de kullanabilirsiniz. Farklı denetim kümelerini birleştirerek ve denetimleri veriye bağlayabilirsiniz kod, yazma, kullanıcıdan bilgi toplamak ve kullanıcı eylemlerine yanıt. Daha fazla bilgi için bkz: [belge düzeyi özelleştirmelerini programlama](../vsto/programming-document-level-customizations.md).  
  
 `ThisDocument` Sınıfı başlangıç projenizde kod yazma bir konum sağlar. Sınıfın tüm özellikleri, yöntemleri ve olayları olarak sağladığından <xref:Microsoft.Office.Interop.Word.Document> nesne Word için birincil birlikte çalışma derlemesindeki de kullanabilir `ThisDocument` Word nesne modeline erişmek için. Daha fazla bilgi için bkz: [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md).  
  
### <a name="limitations-of-the-document-host-item-in-document-level-projects"></a>Belge düzeyi projelerine belge konak öğesi sınırlamaları  
 Belge düzeyi projesi yalnızca bir tane içerebilir <xref:Microsoft.Office.Tools.Word.Document> konak öğesi (diğer bir deyişle, `ThisDocument` sınıfı). Yeni ekleyemezsiniz <xref:Microsoft.Office.Tools.Word.Document> konak öğeleri projenize tasarım zamanında ve yeni oluşturamazsınız <xref:Microsoft.Office.Tools.Word.Document> konak öğelerini bir belge düzeyi özelleştirmesinde çalışma zamanında.  
  
 Çalışma zamanında yeni bir Word belgesi oluşturursanız, türü olacaktır <xref:Microsoft.Office.Interop.Word.Document>. Bir konak öğesi olmadığı için herhangi bir ana bilgisayar denetimleri veya Windows Forms denetimleri içeremez. Çalışma zamanında belgeler oluşturma hakkında daha fazla bilgi için bkz: [nasıl yapılır: program aracılığıyla oluşturma yeni belgeler](../vsto/how-to-programmatically-create-new-documents.md).  
  
## <a name="understanding-document-host-items-in-application-level-projects"></a>Uygulama düzeyi projelerinde anlama belge konak öğeleri  
 VSTO eklenti projelerinde oluşturabileceğiniz bir <xref:Microsoft.Office.Tools.Word.Document> konak öğesi zamanında herhangi bir belgede Word'de açın. Kullanabileceğiniz <xref:Microsoft.Office.Tools.Word.Document> konak öğesi ilgili belgeye denetimleri eklemek veya üzerindeki kullanılabilir değil olayları işlemek için <xref:Microsoft.Office.Interop.Word.Document> nesneleri.  
  
 Oluşturulacak bir <xref:Microsoft.Office.Tools.Word.Document> konak öğesi, GetVstoObject yöntemi kullanın. Daha fazla bilgi için bkz: [genişletme Word belgelerini ve Excel çalışma kitaplarını VSTO eklentileri çalışma zamanında](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)   
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Word nesne modeline genel bakış](../vsto/word-object-model-overview.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [VSTO Eklentilerindeki Word Belgelerini ve Excel Çalışma Kitaplarını Çalışma Zamanında Genişletme](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)  
  
  