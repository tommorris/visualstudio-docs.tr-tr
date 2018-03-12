---
title: "Nasıl yapılır: hata ayıklama XAML iş akışı Tasarımcısı ile | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- uwp
ms.openlocfilehash: 4d17d0a92bf3760e723bfa4ba26b45952634e7e2
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Nasıl yapılır: XAML iş akışı Tasarımcısı ile hata ayıklama
İş akışı XAML bakımından tanımlanır. İş akışı UI gösterimini iş akışı tanımlama XAML ağaç üzerinde oluşturulmuştur. Hata ayıklama deneyimini Windows iş akışı Tasarımcısı'nda iş akışları hata ayıklama için benzer. Bunlar yaptığınız gibi örneği için XAML ayıklarken yerel öğeler, izleme ve iş parçacıkları windows aynı şekilde çalışır [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] hata ayıklama. Ayrıca, XAML hata ayıklama sırasında çağrı yığını satırı tabanlı hiyerarşik bir görünümü için iş akışı yürütme akışı görünümdür.

> [!NOTE]
> XAML iş akışı etkinlikleri ile aynı bütünleştirilmiş kodda yer alıyorsa, sınıf adlarının derleme bölümü değildir dahildir. Bu sınıf (etkinlik) adlarını bölümü, çalışma zamanında XAML yüklenemiyor. Ana proje aynı ad alanına etkinlikleri tanımlamak için önerilmez; Aksi takdirde, XAML Tasarımcısı'nda düzenlenmekte sonra el ile düzenleyebilirsiniz olması gerekir.

### <a name="to-debug-workflow-xaml"></a>İş akışı XAML hata ayıklamak için

1.  Bir iş akışı veya etkinlik projeyi açın [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

2.  Etkinlik ya da açıklandığı gibi hata ayıklamak istediğiniz etkinlikleri bir kesme noktası belirleyerek [nasıl yapılır: iş akışlarında kesme noktaları ayarlayın](../workflow-designer/how-to-set-breakpoints-in-workflows.md).

3.  Seçin ve iş akışı tanımını içeren .xaml dosyasını sağ tıklatın **görünümü kodu**. Kesme noktasına Tasarım görünümünde Ayarla etkinliğinin XAML öğe bildirimi aynı satırda görüntülenen bir kesme noktası görürsünüz.

4.  Hata ayıklayıcı açıklandığı gibi çağırma [nasıl yapılır: iş akışı hata ayıklayıcı çağırma](../workflow-designer/how-to-invoke-the-workflow-debugger.md).

5.  Kod yürütmeyi noktalarınıza ulaştığında, kesme noktası ile ilişkili XAML öğesi vurgulanır. Sonraki kesme taşımak için kullanın **F10** veya **F11** anahtarı.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: İş Akışlarında Kesme Noktası Ayarlama](../workflow-designer/how-to-set-breakpoints-in-workflows.md)
- [Nasıl Yapılır: İş Akışı Hata Ayıklayıcısını Çağırma](../workflow-designer/how-to-invoke-the-workflow-debugger.md)