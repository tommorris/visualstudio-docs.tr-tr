---
title: "Nasıl yapılır: bir iş akışı konsol uygulaması oluşturun | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 51a2eea7-921c-49f1-b358-68afc27f1ee9
caps.latest.revision: "16"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4b019c2733a8e411b1d3e5be15af3b272708ce1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-create-a-workflow-console-application"></a>Nasıl yapılır: bir iş akışı konsol uygulaması oluşturun
[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]Sistem veya İnsan işlemler yürütme iş akışları oluşturmanıza olanak sağlar. [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] Bu iş akışları oluşturmak için tasarım yüzeyi sağlar. [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] İçinden iş akışları oluşturmak için kullanılan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] veya tasarımcı yeniden barındırma diğer uygulamalara tümleştirilebilir.  
  
 Bu konuda nasıl kullanılacağını açıklar [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] içinde [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] bir konsol uygulamasında bir iş akışı oluşturmak için.  
  
### <a name="to-create-a-workflow-console-application"></a>Bir iş akışı konsol uygulaması oluşturmak için  
  
1.  Başlat [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].  
  
2.  Üzerinde **dosya** menüsündeki **yeni**ve ardından **proje...** .  
  
     **Yeni proje** iletişim kutusu açılır.  
  
3.  İçinde **yüklü şablonlar** bölmesinde, **iş akışı** da **Visual C#** veya **Visual Basic** gruplandırmaları, bağlı olarak, tercih dili.  
  
4.  Orta bölmede seçin **iş akışı konsol uygulaması**.  
  
5.  İçinde **adı** kutusuna, projenizin tanınmasını kolaylaştırmak için açıklayıcı bir ad girin.  
  
6.  İçinde **konumu** kutusunda, istediğiniz tıklayın veya projenizi kaydetmek istediğiniz dizini girin **Gözat** gitmek için.  
  
7.  İçinde **çözüm** kutusunda, yeni bir çözüm için bir ad girin. Tıklatın **Tamam** uygulaması oluşturmak için.  
  
    > [!NOTE]
    >  Varolan bir çözümü bir iş akışı konsol uygulama eklemek istiyorsanız, bu çözümde açmak [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], çözüme sağ tıklayın **Çözüm Gezgini**seçip **Ekle**, ardından  **Yeni proje...**  açmak için **yeni proje** iletişim kutusu. Bu yordamda yukarıda açıklandığı gibi devam edin.  
  
8.  Proje şablonu bir iş akışı tanımı XAML'de oluşturur ve kaynak kodunda konsol uygulaması tanımıdır. [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Açar ve oluşturduğunuz iş akışı için tuvale görüntüler.  
  
9. Bir iş akışı oluşturmak için etkinlikler veya diğer iş akışı öğeleri sürükleyin **araç** iş akışınızda tasarım yüzeyine.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir iş akışı projesi oluşturma](../workflow-designer/creating-a-workflow-project.md)