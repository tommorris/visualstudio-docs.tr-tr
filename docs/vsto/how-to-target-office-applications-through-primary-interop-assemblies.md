---
title: "Nasıl yapılır: birincil birlikte çalışma derlemeleriyle Office uygulamalarını | Microsoft Docs"
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
- assemblies [Office development in Visual Studio], PIA references
- primary interop assemblies [Office development in Visual Studio], adding references to
- Office primary interop assemblies in Visual Studio, adding references to
- Office applications [Office development in Visual Studio], automating
- application development [Office development in Visual Studio], automating
ms.assetid: 9bedae85-32b6-4df6-82b2-9d124fb49636
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9a96ec16afda8823ddf9918340498e29efdff2f0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-target-office-applications-through-primary-interop-assemblies"></a>Nasıl Yapılır: Birincil Birlikte Çalışma Derlemeleriyle Office Uygulamalarını Hedefleme
  Yeni bir Office proje oluşturduğunuzda, Visual Studio projenizi derleme için gerekli olan Microsoft Office birincil birlikte çalışma derlemeleri (PIA) başvuruları otomatik olarak ekler. Aşağıdaki senaryolarda diğer PIA başvuruları eklemeniz gerekir:  
  
-   Projenizde diğer Microsoft Office uygulamaları özelliklerini kullanmak istiyorsunuz. Örneğin, Microsoft Office Word için Microsoft Office Excel özelliklerini projesinde kullanmak isteyebilirsiniz.  
  
-   Visual Studio'da, Microsoft Office Access gibi ayrılmış projeleri olmayan Microsoft Office uygulamalarını otomatikleştirmek istediğiniz.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-to-a-primary-interop-assembly"></a>Birincil birlikte çalışma derlemesine başvuru eklemek için  
  
1.  Office projenizi açın ve proje adını seçin **Çözüm Gezgini**.  
  
2.  Üzerinde **proje** menüsünde tıklatın **Başvuru Ekle**.  
  
3.  Üzerinde **Framework** sekmesinde, istediğiniz PIA seçin **bileşen adı** listesi. Kullanılabilir Microsoft Office birincil birlikte çalışma derlemeleri hakkında daha fazla bilgi için bkz: [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md).  
  
     Varsa Proje hedefleri [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] veya sonraki sürümlerde, **birlikte çalışma türlerini katıştır** derleme başvurusunun ayarlanmış **True** varsayılan olarak. Bu ayarı kullanarak, son kullanıcı bilgisayarlarında PIA çözümünüzü gerektirmez. Daha fazla bilgi için bkz: [tasarlama ve oluşturma Office çözümleri](../vsto/designing-and-creating-office-solutions.md).  
  
    > [!NOTE]  
    >  Her zaman Office projelerinde kullanarak Office PIA başvuruları ekleyin **.NET** sekmesinde **Başvuru Ekle** iletişim yerine **COM** sekmesi. Daha fazla bilgi için bkz: [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md).  
  
4.  **Tamam**'ı tıklatın.  
  
     Derleme adı görünür **başvuruları** klasöründe **Çözüm Gezgini**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office birincil birlikte çalışma derlemeleri](../vsto/office-primary-interop-assemblies.md)   
 [Office çözümlerinde kod yazma](../vsto/writing-code-in-office-solutions.md)   
 [Office çözümleri geliştirme](../vsto/developing-office-solutions.md)   
 [Nasıl yapılır: Office birincil birlikte çalışma derlemelerini yükleme](../vsto/how-to-install-office-primary-interop-assemblies.md)  
  
  