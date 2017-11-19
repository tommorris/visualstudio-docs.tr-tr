---
title: "Nasıl yapılır: WCF hizmetleri içine Adımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging
ms.assetid: 9893ad01-54af-499f-85a6-9d1cfe6eb640
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6aeaba831bb82731ae7d3e62cbff5190bb474357
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-step-into-wcf-services"></a>Nasıl Yapılır: WCF Hizmetleri İçine Adımlama
İçinde [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], WCF hizmetine geçebilirsiniz. WCF hizmeti aynı değilse [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] çözüm istemci olarak kesme noktaları WCF hizmeti içinde ulaştı.  
  
 Çalışmak için atlama için hata ayıklama app.config veya Web.config dosyasında etkin olması gerekir. Hata ayıklamayı etkinleştirmek ve WCF hizmetleri içine Adımlama sınırlamalar görmek hakkında bilgi için [WCF hata ayıklama sınırlamaları](../debugger/limitations-on-wcf-debugging.md).  
  
### <a name="to-step-into-a-wcf-service"></a>Bir WCF hizmetine adım  
  
1.  Oluşturma bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] WCF istemcisi ve WCF Hizmeti projeleri içeren çözüm.  
  
2.  Çözüm Gezgini'nde, WCF istemci projesine sağ tıklayın ve ardından **başlangıç projesi olarak ayarla**.  
  
3.  App.config veya web.config dosyasında hata ayıklamayı etkinleştir. Daha fazla bilgi için bkz: [WCF hata ayıklama sınırlamaları](../debugger/limitations-on-wcf-debugging.md).  
  
4.  İstemci projesinde adımlamaya başlamak istediğiniz konumda bir kesme noktası ayarlayın. Genellikle, bu yalnızca WCF hizmeti çağrısı önce olacaktır.  
  
5.  Kesme noktasına çalıştırın, sonra atlama başlar. Hata ayıklayıcı hizmetine otomatik olarak adım.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WCF hizmetlerinde hata ayıklama](../debugger/debugging-wcf-services.md)   
 [WCE hata ayıklamasında sınırlamalar](../debugger/limitations-on-wcf-debugging.md)   
 [Nasıl yapılır: kendini barındıran WCF hizmetinde hata ayıklama](../debugger/how-to-debug-a-self-hosted-wcf-service.md)