---
title: 'Nasıl yapılır: birden çok çözümü açın'
description: Mac için Visual Studio'da birden fazla çözümü açın ve uygulamanın birden fazla örneğini açmayı öğrenin.
author: asb3993
ms.author: amburns
ms.date: 07/19/2018
ms.assetid: 592BA4E3-8DEF-4FCD-8BA0-519A4CEEE03E
ms.openlocfilehash: 85d300c5131dad2d6f4480fceb4770e2e8a126a5
ms.sourcegitcommit: b544e2157ac20866baf158eef9cfed3e3f1d68b9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39391586"
---
# <a name="opening-multiple-solutions-or-instances-of-visual-studio-for-mac"></a>Mac için birden çok çözümlerini veya Visual Studio örneği açma

Mac için Visual Studio da dahil olmak üzere bir Mac bilgisayarda varsayılan olarak, tüm uygulamalardır _Tek Örnekli_ uygulamalar. Bu, kullanmak istediğiniz uygulamayı (dock'taki simgesinin altında "dot" tarafından gösterilen) açıksa, yeniden simgesine tıklayarak yeni bir tane yerine çalışan örneği açılacağı anlamına gelir.  Uygulamanın ek örneklerini gerekiyorsa açıklandığı gibi açmak için sistem isteyebilir [sonraki bölümde](#open-a-second-instance-of-visual-studio-for-mac).

Ayrıca, bir çözümü açtığınızda, yeni bir çalışma alanında çözümü açın ve (gerekirse) geçerli çalışma kapatmak için varsayılan davranışı olan. Geçerli çalışma açıklandığı gibi açık tutarak bu varsayılan davranışı geçersiz kılabilirsiniz [ikinci bir çözüm açın](#open-a-second-solution-inside-a-single-instance) bölümü.

## <a name="open-a-second-instance-of-visual-studio-for-mac"></a>Mac için Visual Studio ikinci bir örneğini açın

IDE ikinci bir örneğini açmak için Aç **Terminal** uygulama ve şu satırı girin:

```bash
open -n "/Applications/Visual Studio.app"
```

## <a name="open-a-second-solution-inside-a-single-instance"></a>Tek bir örnek içinde ikinci bir çözüm açın

İlk çözümünüzü birlikte ikinci bir çözümü açmak için aşağıdaki adımları kullanın:

1. İlk çözümünüzü zaten açıkken, seçin **Dosya > Aç**.
2. Varolan bir çözümü bulmak üzere dosya sisteminde göz atın.
3. Seçin **.sln** dosya ve ENTER tuşuna **seçenekleri** düğmesi:
    
    ![seçenekleri düğmenin konumu](media/open-multiple-solutions-image3.png)
4. Seçimini kaldırın **çalışma alanını Kapat** kutusunda:

    ![Geçerli çalışma alanının ekran görüntüsü](media/open-multiple-solutions-image1.png)

1. Çözüm panelinde ikinci çözümü açmak için Aç düğmesine basın.

**Alternatif olarak**, kısa süre önce çözüm açtıysanız, aşağıdaki adımları kullanabilirsiniz:

1. Dosyaya gidin > son çözümleri menü öğesi:

    ![Son çözümleri menüsünün ekran görüntüsü](media/open-multiple-solutions-image2.png)

1. Basılı **Ctrl** anahtar ve çözümü seçin. Bu birleşim ikinci çözüm çözüm bölmesi açılır.
