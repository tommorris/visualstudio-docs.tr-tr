---
title: Veri bağlama ActiveX denetiminde hata ayıklama | Microsoft Docs
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
- data-bound controls, ActiveX
- ActiveX controls, debugging
- controls [Visual Studio], ActiveX
ms.assetid: 9f6e1f00-e25b-48a9-8484-7e67a1232461
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: df11571bb1e37d458fd647ce1524f67432617b8f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31474297"
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