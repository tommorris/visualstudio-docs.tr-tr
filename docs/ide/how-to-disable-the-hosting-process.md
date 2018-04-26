---
title: 'Nasıl yapılır: barındırma sürecini devre dışı bırakma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- hosting process, disabling
- vshost.exe, disabling the hosting process
ms.assetid: 9157488d-737f-454b-8d8d-36f99de38bb0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f7970ff97c7aec42f8798da07cf2a4a2b6c8bea8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-disable-the-hosting-process"></a>Nasıl yapılır: barındırma sürecini devre dışı bırakma

Barındırma işlemi etkinleştirildiğinde, belirli API çağrıları etkilenebilir. Bu durumlarda, doğru sonuçlar döndürecek şekilde barındırma işlemini devre dışı bırakmak gereklidir.

## <a name="to-disable-the-hosting-process"></a>Barındırma işlemini devre dışı bırakmak için

1.  Yürütülebilir bir Proje Aç [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Yürütülebilir dosyalar (örneğin, sınıf kitaplığı veya hizmet projeleri) üretmez projeleri bu seçeneği yok.

2.  Üzerinde **proje** menüsünde tıklatın **özellikleri**.

3.  Tıklatın **hata ayıklama** sekmesi.

4.  Clear **barındırma işlemi Visual Studio'nun** onay kutusu.

 Barındırma işlemini devre dışı bırakıldığında, birkaç hata ayıklama özelliği kullanılamıyor veya düşük performansla karşılaşabilirsiniz. Daha fazla bilgi için bkz: [hata ayıklama ve barındırma işlemi](../debugger/debugging-and-the-hosting-process.md).

 Genel olarak, ne zaman barındırma işlemini devre dışı bırakılır:

-   Hata ayıklama başlamak için gereken süre [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] uygulamaları artar.

-   Tasarım zamanı ifade değerlendirmesi kullanılamaz.

-   Kısmi güven hata ayıklama kullanılamıyor.

## <a name="see-also"></a>Ayrıca bkz.

- [Hata ayıklama ve barındırma işlemi](../debugger/debugging-and-the-hosting-process.md)
- [Barındırma süreci (vshost.exe)](../ide/hosting-process-vshost-exe.md)