---
title: "Veri bağlama ActiveX denetiminde hata ayıklama | Microsoft Docs"
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
- data-bound controls, ActiveX
- ActiveX controls, debugging
- controls [Visual Studio], ActiveX
ms.assetid: 9f6e1f00-e25b-48a9-8484-7e67a1232461
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 32cbb7bee21b54c932e0c369c46c3b2c3dacd898
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-a-data-bound-activex-control"></a>Veri Bağımlı ActiveX Denetiminde Hata Ayıklama
Bir veri kaynağı denetimine bağlı bir ActiveX denetimi geliştiriyorsanız, kendi kapsayıcı uygulama oluşturabilir ve bu kapsayıcı ActiveX denetiminde hata ayıklama için kullanın.  
  
 Örneğin, bir iletişim tabanlı MFC uygulaması oluşturma ve veri bağlama denetimi ve iletişim kutusundaki veri kaynağı denetimi yerleştirin. Bu MFC uygulaması, veri bağlama ActiveX denetimi hata ayıklama için yürütülebilir kapsayıcı olarak ve çalışma zamanı sınama için kullanabilirsiniz.  
  
## <a name="using-the-test-container"></a>Test kapsayıcısı kullanma  
 Destek ya da denetimindeki çeşitli arabirimler için kolaylıkla değiştirebileceğiniz bir kapsayıcı veya kapsayıcı istiyorsanız, ActiveX Test kapsayıcısı hata ayıklama oturumu için yürütülebilir dosya kullanın. ActiveX Test kapsayıcısı tıklatın **seçenekleri** gelen **kapsayıcı** etkinleştirmek için çeşitli arabirimleri menüsü. Daha fazla bilgi için bkz: [test özellikleri ve olayları Test kapsayıcısı ile](/cpp/mfc/testing-properties-and-events-with-test-container).  
  
 Hata ayıklarken kapsayıcının koda adım gerekirse, kapsayıcı hata ayıklama sürümünü kullanmanız veya ActiveX Test kapsayıcısı hata ayıklama sürümünü kullanın. Daha fazla bilgi için bkz: [TSTCON örnek: ActiveX denetimi Test kapsayıcısı](http://msdn.microsoft.com/en-us/72fa40ef-27d3-400c-813f-10b03236e600).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM ve ActiveX hata ayıklaması](../debugger/com-and-activex-debugging.md)   
 [ActiveX Denetimleri](/cpp/mfc/activex-controls)