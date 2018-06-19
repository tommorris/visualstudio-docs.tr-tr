---
title: 'İş Akışı Tasarımcısı - nasıl yapılır: XAML iş akışı Tasarımcısı ile hata ayıklama'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: eac6294861080614cbdd46e6ac1cc9a05d7124ff
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31969902"
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>Nasıl yapılır: XAML iş akışı Tasarımcısı ile hata ayıklama

İş akışı XAML bakımından tanımlanır. İş akışı UI gösterimini iş akışı tanımlama XAML ağaç üzerinde oluşturulmuştur. Hata ayıklama deneyimini Windows iş akışı Tasarımcısı'nda iş akışları hata ayıklama için benzer. İş Akışı Tasarımcısı hata ayıklama yaptığınız gibi örneği için XAML ayıklarken yerel öğeler, izleme ve iş parçacıkları windows aynı şekilde çalışır. Ayrıca, XAML hata ayıklama sırasında çağrı yığını satırı tabanlı hiyerarşik bir görünümü için iş akışı yürütme akışı görünümdür.

> [!NOTE]
> XAML iş akışı etkinlikleri ile aynı bütünleştirilmiş kodda yer alıyorsa, sınıf adlarının derleme bölümü değildir dahildir. Bu sınıf (etkinlik) adlarını bölümü, çalışma zamanında XAML yüklenemiyor. Ana proje aynı ad alanına etkinlikleri tanımlamak için önerilmez; Aksi takdirde, XAML Tasarımcısı'nda düzenlenmekte sonra el ile düzenleyebilirsiniz olması gerekir.

## <a name="to-debug-workflow-xaml"></a>İş akışı XAML hata ayıklamak için

1.  Bir iş akışı veya etkinlik projesini Visual Studio'da açın.

2.  Etkinlik ya da açıklandığı gibi hata ayıklamak istediğiniz etkinlikleri bir kesme noktası belirleyerek [nasıl yapılır: iş akışlarında kesme noktaları ayarlayın](../workflow-designer/how-to-set-breakpoints-in-workflows.md).

3.  Seçin ve iş akışı tanımını içeren .xaml dosyasını sağ tıklatın **görünümü kodu**. Kesme noktasına Tasarım görünümünde Ayarla etkinliğinin XAML öğe bildirimi aynı satırda görüntülenen bir kesme noktası görürsünüz.

4.  Hata ayıklayıcı açıklandığı gibi çağırma [nasıl yapılır: iş akışı hata ayıklayıcı çağırma](../workflow-designer/how-to-invoke-the-workflow-debugger.md).

5.  Kod yürütmeyi noktalarınıza ulaştığında, kesme noktası ile ilişkili XAML öğesi vurgulanır. Sonraki kesme taşımak için kullanın **F10** veya **F11** anahtarı.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: İş Akışlarında Kesme Noktası Ayarlama](../workflow-designer/how-to-set-breakpoints-in-workflows.md)
- [Nasıl Yapılır: İş Akışı Hata Ayıklayıcısını Çağırma](../workflow-designer/how-to-invoke-the-workflow-debugger.md)