---
title: "Nasıl yapılır: Office projelerinde olay işleyicileri oluşturma | Microsoft Docs"
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
- Visual Basic [Office development in Visual Studio], event handlers
- event handlers [Office development in Visual Studio]
- Visual C# [Office development in Visual Studio], event handlers
- events [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: c392d365ca14daeb204f4ee2f331bb1fe86ad304
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-event-handlers-in-office-projects"></a>Nasıl Yapılır: Office Projelerinde Olay İşleyicileri Oluşturma
  Visual Basic ve C# ' olay işleyicileri oluşturmanın birkaç yolu vardır. Tasarım görünümünde, varsayılan denetimleri için olay işleyicileri denetimi çift tıklatarak oluşturabilir, veya olayları bölmesini kullanarak **özellikleri** herhangi bir olay işleyicileri denetimi oluşturmak için pencere. Bununla birlikte, kod görünümünde varsa, olay işleyici oluşturmak için Tasarım görünümüne geçiş istemeyebilirsiniz.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-create-an-event-handler-in-visual-basic"></a>Visual Basic'te bir olay işleyicisi oluşturmak için  
  
1.  Gelen **sınıf adı** aşağı açılan liste Kod Düzenleyicisi'nin üstünde seçin, istediğiniz nesne oluşturmak için bir olay işleyicisi.  
  
    > [!NOTE]  
    >  Olay işleyicileri oluşturmak istiyorsanız `ThisDocument` veya `ThisWorkbook`, seçmelisiniz **(ThisDocument olayları)** veya **(ThisWorkbook olayları)** içinde **sınıf adı**aşağı açılan liste  
  
2.  Gelen **yöntem adı** aşağı açılan liste Kod Düzenleyicisi'nin en üstünde, olayı seçin.  
  
     Visual Studio, olay işleyicisi oluşturur ve yeni oluşturulan olay işleyicisi ekleme noktasını taşır. Olay işleyicisi zaten varsa, mevcut olay işleyicisi ekleme noktasını taşır.  
  
### <a name="to-create-an-event-handler-in-c"></a>Olay işleyici C# ' ta oluşturmak için  
  
1.  Olay temsilcisini oluşturmak **başlangıç** bir boşluk bırakarak tam olay adını yazarak ve ardından yazarak sınıfının olayını  **+=**  boşluk daha sonra. Örneğin:  
  
     `this.<object name>.<event name> +=`  
  
2.  Kod satırının sonunda, iki kez SEKME tuşuna basın.  
  
     Visual Studio otomatik olarak kod satırını tamamlar, olay işleyicisi oluşturur ve yeni oluşturulan olay işleyicisi ekleme noktasını taşır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [İzlenecek yol: NamedRange denetimi olaylarına karşı programlama](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Office Çözümleri Oluşturma](../vsto/building-office-solutions.md)  
  
  