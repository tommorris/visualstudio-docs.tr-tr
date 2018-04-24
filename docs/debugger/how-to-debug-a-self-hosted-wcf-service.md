---
title: 'Nasıl yapılır: kendini barındıran WCF hizmetinde hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 19ce90effca21f6079cc7b569fa6e58f94553627
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>Nasıl Yapılır: Kendini Barındıran WCF Hizmetinde Hata Ayıklama
A *kendi kendini barındıran hizmete* WCF hizmet ana bilgisayarı, IIS içinde çalışmaz bir WCF hizmeti veya [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] geliştirme sunucusu. Kendini barındıran WCF hata ayıklamak için en kolay yolu yapılandırmaktır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] seçtiğinizde, istemci ve sunucu başlatmak için **hata ayıklamayı Başlat** üzerinde **hata ayıklama** menüsü.  
  
 WCF hizmeti iç ya da NT hizmeti gibi bu şekilde başlatılamıyor bir işlem kendi kendine barındırıyorsa, bu yöntem kullanamazsınız. Bunun yerine, aşağıdakilerden birini yapabilirsiniz:  
  
-   Elle hata ayıklayıcı barındırma işlemi ekleyin. Daha fazla bilgi için bkz: [eklemek için çalışan işlemler](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
     — veya —  
  
-   İstemci hata ayıklama başlatın ve sonra hizmetine yapılan bir çağrı adımla. Bu app.config dosyasında hata ayıklama etkinleştirmenizi gerektirir. Daha fazla bilgi için [WCF hata ayıklama sınırlamaları](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-start-both-client-and-host-from-visual-studio"></a>Visual Studio'dan hem istemci hem de ana bilgisayarı başlatmak için  
  
1.  Oluşturma bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] istemci ve sunucu projeleri içeren çözüm.  
  
2.  Öğesini seçtiğinizde, istemci ve sunucu işlemlerini başlatmak için çözümünüzü yapılandırma **Başlat** üzerinde **hata ayıklama** menüsü.  
  
    1.  İçinde **Çözüm Gezgini**, çözüm adına sağ tıklayın.  
  
    2.  Tıklatın **başlangıç projelerini ayarlama**.  
  
    3.  İçinde **çözüm \<adı > Özellikler** iletişim kutusunda **birden fazla başlangıç projesi**.  
  
    4.  İçinde **birden fazla başlangıç projesi** sunucu projesi için karşılık gelen satırda kılavuz **eylem** ve **Başlat**.  
  
    5.  İstemci projesine karşılık gelen satırda tıklatın **eylem** ve **Başlat**.  
  
    6.  **Tamam**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WCF hizmetlerinde hata ayıklama](../debugger/debugging-wcf-services.md)   
 [WCE hata ayıklamasında sınırlamalar](../debugger/limitations-on-wcf-debugging.md)   
 [Nasıl yapılır: WCF hizmetleri içine Adımlama](../debugger/how-to-step-into-wcf-services.md)