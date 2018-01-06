---
title: "XAML Tasarımcısı'nda nesnelere animasyon ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 57aa814ac458fc3c893f8a2d557840d936ed033b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="animate-objects-in-xaml-designer"></a>XAML Tasarımcısı’nda nesnelere animasyon ekleme
Nesneleri taşıma kısa animasyon oluşturma veya içeri ve dışarı silinerek.  
  
 Başlamak için Oluştur bir *film şeridi*. Bir veya daha fazla film şeridi içeren *zaman çizelgelerini*. Ayarlama *ana kare* özellik değişikliklerini işaretlemek için bir zaman çizelgesi üzerinde. Ardından, animasyonun çalıştırdığınızda, harmanlama özellik değişikliklerini belirlenen süre ilişkilendirileceğini. Sorunsuz bir geçiş sonucudur. Bir nesneye ait olduğu herhangi bir özelliği animasyon, görsel olmayan özellikler bile.  
  
 Adlı bir film şeridi aşağıda gösterilmiştir **MoveUp**. Zaman Çizelgesi dikdörtgen X ve Y konumunu işaretlemek ana kare içerir. Bu animasyon çalıştığında, dikdörtgen bir konumdan diğerine sorunsuz taşır.  
  
 ![](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png "982f031a-74a3-414a-abc2-a0f41a741075")  
  
 Videoları izleyerek animasyonları oluşturmayı öğrenin.  
  
|Kısa bir video izleyin:|Bilgi nasıl yapılır:|  
|--------------------------|-------------------|  
|![Yüklenen özellikleri yapılandırmak](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [zaman çizelgelerini oluşturma](http://www.popscreen.com/v/6A4eF/Microsoft-Expression-Blend-Creating-Timelines)|Bir zaman çizelgesi oluşturma ve zaman çizelgesi nesneleri ile çalışma.|  
|![Yüklenen özellikleri yapılandırmak](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [ana kareleri eklemek ve animasyon yineleyin](http://www.popscreen.com/v/6A4fi/Microsoft-Expression-Blend-Adding-Keyframes-and-Repeating-an-Animation)|Ana kare ekleyin ve her ana kare özellikleri ayarlayın. Ardından animasyon ve izleme nesnelerini sorunsuz geçiş aralarında çalıştırın.|  
|![Yüklenen özellikleri yapılandırmak](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [etkileşim için olay tetikleyicileri ekleyin](http://www.popscreen.com/v/6A4e4/Microsoft-Expression-Blend-Adding-Event-Triggers-for-Interactivity)|Bir olay gerçekleştiğinde bir animasyon başlatın. Örneğin, pencerenin yüklediğinde birini başlatın.|  
|![Yüklenen özellikleri yapılandırmak](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [renkleri animasyon ekleme](http://www.popscreen.com/v/6A4gv/Microsoft-Expression-Blend-Animating-Colors)|Bir nesnenin rengini değiştirmek için bir animasyon kullanın.|  
|![Yüklenen özellikleri yapılandırmak](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [oluşturma hareket yolları ve değiştirme](http://www.popscreen.com/v/6A4fX/Microsoft-Expression-Blend-Creating-and-Modifying-Motion-Paths)|Bir yol boyunca nesnelere animasyon ekleme.|  
|![Yüklenen özellikleri yapılandırmak](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [ana kare kolaylaştırır](http://www.popscreen.com/v/6A4dM/Microsoft-Expression-Blend-Easing-Keyframes)|Hızlandırma veya animasyonun başına yanında aşağı yavaş (*içinde hareket hızı*) ya da sona (*hareket hızı çıkış*) animasyonun.|  
|![Yüklenen özellikleri yapılandırmak](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [düğmesi animasyon ekleme](http://www.popscreen.com/v/6A4fK/Microsoft-Expression-Blend-Animating-a-Button)|Kullanıcı için işaret ettiğinde görünür ilginç efektler bir düğme oluşturun.|  
|![Yüklenen özellikleri yapılandırmak](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [animasyon oluşturma ve kolaylaştırma ile çalışma](https://www.youtube.com/watch?v=mAJXYrwxGYo)|Bir kullanıcı bir hesaplayıcı görüntüde düğmesini basılı bastığında görüntülenen efektler animasyon.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio için Blend’i kullanarak kullanıcı arabirimi oluşturma](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)