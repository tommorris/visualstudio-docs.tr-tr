---
title: "Nasıl yapılır: kod çalıştırmadan Office çözümlerini açma | Microsoft Docs"
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
- Office solutions [Office development in Visual Studio], opening
- opening Office solutions
- bypassing assemblies
- solutions [Office development in Visual Studio], opening
- assemblies [Office development in Visual Studio], bypassing
- Office documents [Office development in Visual Studio, opening without running code
- documents [Office development in Visual Studio], opening without running code
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: bd7a401ab96cbb196d97b2e210b3ede0a624deb8
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-open-office-solutions-without-running-code"></a>Nasıl Yapılır: Kod Çalıştırmadan Office Çözümlerini Açma
  Yönetilen kod uzantıları ile oluşturulan bir Microsoft Office çözümü, son kullanıcının Office uygulamasında güvenlik ayarı Yüksek olarak ayarlansa bile çalışır. .NET derleme kod güvenliği Microsoft Office tarafından değil, Microsoft .NET Framework tarafından yönetilen olmasıdır.  
  
 Ancak, ne zaman bir belgeyi kod çalıştırmadan açma isteyebilirsiniz zamanlar vardır. Örneğin, belge açıldığında çalışan kod içeriği değiştirebilir, ancak belgeyi önce kod değişiklikleri görünüyor şekilde güncelleştirmek istediğiniz. Veya belirli bilgileri belgeyle içinde göndermek isteyebilirsiniz ve kod çalıştırın ve muhtemelen içeriği değiştirmesini istiyor musunuz.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Bir belge veya bütünleştirilmiş kodu çalıştırmadan yönetilen kod uzantıları içeren çalışma kitabını açmak için birkaç yolu vardır.  
  
### <a name="to-bypass-the-assembly-by-using-the-shift-key"></a>SHIFT tuşunu kullanarak derlemeyi atlamak için  
  
-   Açık belgeler ve çalışma kitaplarından **dosya** Word ve Excel belge açılırken başlatma olaylar oluşturma önlemek için SHIFT tuşunu basılı tutarken menüsü.  
  
    > [!NOTE]  
    >  Bir belge veya çalışma kitabından açarsanız **Başlarken** görev bölmesi, SHIFT tuşunu basılı tutarak kod atlama değil. Ayrıca, SHIFT tuşunu basılı tutarak olayları belge açıldıktan sonra gerçekleştirilen engellemez.  
  
     Bu yöntem, çalıştırma ve belgeyi değiştirmeden kodu olmadan değişiklik yapmak için bir belgeyi açmak istiyorsanız kullanışlıdır.  
  
### <a name="to-bypass-an-assembly-by-renaming-or-removing-it"></a>Yeniden adlandırma veya kaldırmadan bir derlemeyi atlamak için  
  
-   Derleme bulunduğu bilgisayarda gerekli izinlere sahipseniz, yeniden adlandırın veya belge veya çalışma kitabı bulunamıyor derleme kaldırın. Bu, Office belgesi her açıldığında gerçekleştirilen bir hatayla sonuçlanır.  
  
     Çözüm birden çok kişi tarafından kullanılıyorsa, bu yöntem çözümü için bunların tümünün çalışmasını engeller. Bir sorun kodu veya başvurulmuş sunucuda bulunan ve tüm kullanıcıların, yürütülmekte durdurmak istiyorsanız, bu bağlantı yararlı olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümleri güvenliğini sağlama](../vsto/securing-office-solutions.md)   
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office Çözümlerinde Uygulama ve Dağıtım Bildirimleri](../vsto/application-and-deployment-manifests-in-office-solutions.md)  
  
  