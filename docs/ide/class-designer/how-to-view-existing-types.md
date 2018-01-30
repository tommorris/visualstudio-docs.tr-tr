---
title: "Nasıl yapılır: Varolan türleri (Sınıf Tasarımcısı) görüntülemek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdesigner.CannotShowBaseType
helpviewer_keywords:
- types [Visual Studio], visualizing
- types [Visual Studio], class diagrams
- class diagrams, types
ms.assetid: de110a4e-5b51-4a40-9dee-615df4d8f999
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f9b5b4aed79dfbfda19020cfda17af68d7ae186c
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-view-existing-types-class-designer"></a>Nasıl Yapılır: Varolan Türleri Görüntüleme (Sınıf Tasarımcısı)
Mevcut bir türle ve üyelerini görmek için bir sınıf diyagramı şeklini ekleyin.  
  
Yerel ve başvurulan türleri görebilirsiniz. Yerel bir tür o anda açık olan projede mevcuttur ve okunur/yazılır. Başvurulan tür başka bir projede ya da başvurulan bir derlemede bulunur ve salt okunur özelliktedir.  
  
Sınıf diyagramları yeni türlerinde tasarlamak için bkz: [nasıl yapılır: Sınıf Tasarımcısı kullanarak türleri oluşturmak](how-to-create-types.md).  
  
### <a name="to-see-types-in-a-project-on-a-class-diagram"></a>Projedeki türleri bir sınıf diyagramı üzerinde görmek için  
  
1.  Çözüm Gezgini'ndeki bir projeden varolan bir sınıf diyagramı (.cd) dosyası açın. Ya da hiçbir sınıf diyagramı yoksa, projeye yeni bir sınıf diyagramı ekleyin. Bkz: [nasıl yapılır: projelere sınıf diyagramları ekleme](how-to-add-class-diagrams-to-projects.md).  
  
2.  Çözüm Gezgini'ndeki projeden bir kaynak kodu dosyasını sınıf diyagramına sürükleyin.  
  
    > [!WARNING]
    >  Çözümünüzün birden çok uygulama arasında kod paylaşan proje varsa, bir sınıf diyagramı dosyaları veya kod yalnızca bu kaynaklardan sürükleyebilirsiniz:  
    >   
    >  -   Diyagramı içeren uygulama projesi  
    > -   Uygulama projesi tarafından alınan paylaşılan bir proje  
    > -   Başvurulan bir proje  
    > -   Bir derleme  
  
    Kaynak kodu dosyasında tanımlı türleri temsil eden şekiller, diyagram üzerinde dosyayı sürüklediğiniz konumda görünür.  
  
Sınıf Görünümü'ndeki proje düğümünden bir veya daha fazla türü sınıf diyagramına sürükleyerek projedeki türleri de görüntüleyebilirsiniz.  
  
> [!TIP]
> Sınıf Görünümü açık değilse, sınıf görünümünden açmak **Görünüm** menüsü.
  
Varsayılan konumlara diyagramda türlerini görüntülemek için bir veya daha fazla türleri Sınıf Görünümü'nde seçin, seçili türleri sağ tıklatın ve seçin **görünüm sınıfı diyagramı**.  
  
> [!NOTE]
>  Türü içeren bir kapalı sınıf diyagramı projede zaten varsa, sınıf diyagramı açılarak tür şeklini görüntüler. Ancak, proje içinde bu türü içeren hiçbir sınıf diyagramı yoksa, Sınıf Tasarımcısı proje içinde yeni bir sınıf diyagramı oluşturur ve bu diyagramı açarak türü görüntüler.  
  
Bir türü diyagram üzerinde ilk kez görüntülediğinizde, bu türe ait şekil varsayılan olarak daraltılmış görünür. Şekli genişleterek içeriğini görüntüleyebilirsiniz.  
  
### <a name="to-display-the-contents-of-a-project-in-a-class-diagram"></a>Sınıf diyagramında proje içeriğini görüntülemek için  
  
1.  Çözüm Gezgini'nde veya sınıf görünümü, projeye sağ tıklayın ve seçin **Görünüm**, ardından **görünüm sınıfı diyagramı**.  
  
     Otomatik olarak doldurulan bir Sınıf Diyagramı oluşturulur.  
  
## <a name="see-also"></a>Ayrıca bkz.
[Nasıl yapılır: türler arasında devralmayı görüntüleme](how-to-view-inheritance-between-types.md)   
[Nasıl yapılır: sınıf diyagramlarını özelleştirme](how-to-customize-class-diagrams.md)   
[Türleri ve İlişkileri Görüntüleme](viewing-types-and-relationships.md)