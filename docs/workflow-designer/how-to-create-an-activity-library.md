---
title: "Nasıl yapılır: bir etkinlik kitaplığı oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1eeebe74-7303-4345-8a83-fe37a26bc84b
caps.latest.revision: "12"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6a61c8f4ea5e9d9cc6d4ab13437d2ec4d4eef7ca
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-create-an-activity-library"></a>Nasıl yapılır: bir etkinlik kitaplığı oluşturma
Özel etkinlikler belirli İş süreçlerinizi bir iş akışında model oluşturmak için kullanılır. Etkinlik kitaplığı şablonunda [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] görsel olarak kullanarak bu tür özel etkinlikler oluşturmanıza olanak sağlaması için sağlanan [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)].  
  
### <a name="to-create-a-workflow-activity-library"></a>Bir iş akışı etkinlik kitaplığı oluşturmak için  
  
1.  Başlat [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje...** .  
  
     **Yeni proje** iletişim kutusu açılır.  
  
3.  İçinde **proje türleri** bölmesinde, **iş akışı** da **Visual C#** projeleri veya **Visual Basic** gruplandırmaları bağlı olarak, dil tercihi.  
  
4.  İçinde **şablonları** bölmesinde, **etkinlik Kitaplığı**.  
  
5.  İçinde **adı** kutusuna tanınmasını kolaylaştırmak için projeniz için açıklayıcı bir ad yazın.  
  
6.  İçinde **konumu** kutusuna istediğiniz projeyi kaydedin veya dizinde **Gözat** gitmek için.  
  
7.  İçinde **çözüm** kutusunda, çözümünüz için açıklayıcı bir ad yazın ve ardından **Tamam**.  
  
    > [!NOTE]
    >  Varolan bir çözümü bir iş akışı konsol uygulama eklemek istiyorsanız, bu çözümde açmak [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], çözüme sağ tıklayın **Çözüm Gezgini**seçip **Ekle**, ardından  **Yeni proje...**  açmak için **yeni proje** iletişim kutusu. Bu yordamda yukarıda açıklandığı gibi devam edin.  
  
8.  Proje şablonu XAML içinde bir etkinlik tanımı oluşturur. [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]açılır ve özel etkinliklerinizi tuvale görüntüler.  
  
9. Bir etkinlikten sürükleyin **araç** özel etkinlik eklemek için tasarım yüzeyine.  
  
    > [!CAUTION]
    >  Yalnızca bir alt etkinlik özel etkinliklerinizi gövdesinde izin verilir; Ancak, bu alt etkinlik bileşik bir etkinlik gibi olabilir bir <xref:System.Activities.Statements.Sequence> etkinlik veya <xref:System.Activities.Statements.Flowchart> etkinlik.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir etkinlik oluşturmak](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)   
 [Bir iş akışı projesi oluşturma](../workflow-designer/creating-a-workflow-project.md)