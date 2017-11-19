---
title: "Nasıl yapılır: hata ayıklama XAML iş akışı Tasarımcısı ile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: c73e053cc3e3dc53101595f00dcd8fd45da8abd7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Nasıl yapılır: XAML iş akışı Tasarımcısı ile hata ayıklama
İş akışı XAML bakımından tanımlanır. İş akışı UI gösterimini iş akışı tanımlama XAML ağaç üzerinde oluşturulmuştur. Hata ayıklama deneyimini akışlarında hata ayıklama için benzer [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Bunlar yaptığınız gibi örneği için XAML ayıklarken yerel öğeler, izleme ve iş parçacıkları windows aynı şekilde çalışır [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] hata ayıklama. Ayrıca, XAML hata ayıklama sırasında çağrı yığını satırı tabanlı hiyerarşik bir görünümü için iş akışı yürütme akışı görünümdür.  
  
> [!NOTE]
>  XAML iş akışı etkinlikleri ile aynı bütünleştirilmiş kodda yer alıyorsa, sınıf adlarının derleme bölümü değildir dahildir. Bu sınıf (etkinlik) adlarını bölümü, çalışma zamanında XAML yüklenemiyor. Ana proje aynı ad alanına etkinlikleri tanımlamak için önerilmez; Aksi takdirde, XAML Tasarımcısı'nda düzenlenmekte sonra el ile düzenleyebilirsiniz olması gerekir.  
  
### <a name="to-debug-workflow-xaml"></a>İş akışı XAML hata ayıklamak için  
  
1.  Bir iş akışı veya etkinlik projeyi açın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
2.  Etkinlik ya da açıklandığı gibi hata ayıklamak istediğiniz etkinlikleri bir kesme noktası belirleyerek [nasıl yapılır: iş akışlarında kesme noktaları ayarlayın](../workflow-designer/how-to-set-breakpoints-in-workflows.md).  
  
3.  Seçin ve iş akışı tanımını içeren .xaml dosyasını sağ tıklatın **görünümü kodu**. Kesme noktasına Tasarım görünümünde Ayarla etkinliğinin XAML öğe bildirimi aynı satırda görüntülenen bir kesme noktası görürsünüz.  
  
4.  Hata ayıklayıcı açıklandığı gibi çağırma [nasıl yapılır: iş akışı hata ayıklayıcı çağırma](../workflow-designer/how-to-invoke-the-workflow-debugger.md).  
  
5.  Kod yürütmeyi noktalarınıza ulaştığında, kesme noktası ile ilişkili XAML öğesi vurgulanır. Sonraki kesme taşımak için kullanın **F10** veya **F11** anahtarı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: iş akışlarında kesme noktalarını ayarlama](../workflow-designer/how-to-set-breakpoints-in-workflows.md)   
 [Nasıl yapılır: iş akışı hata ayıklayıcı çağırma](../workflow-designer/how-to-invoke-the-workflow-debugger.md)