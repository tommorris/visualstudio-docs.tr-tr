---
title: BeginCapture | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2f9bc573799ddb5fdd094c7c0e571a88c13b5420
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630958"
---
# <a name="begincapture"></a>BeginCapture
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [BeginCapture](https://docs.microsoft.com/visualstudio/debugger/graphics/begincapture).  
  
İle biten bir yakalama aralık başlar `EndCapture`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
void BeginCapture();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yakalama aralığı genellikle bir alt kümesini çizim çağrısı belirli bir tür hakkında yalnızca grafik bilgisi yakalamak istediğinizde gibi bir çerçeve yayılır. Ardından yakalama aralığı sunmak için bir çağrı yayılırsa, grafik bilgilerini iki çerçeve yakalanır. İlk çerçeve çağrı aralığını kapsayan `BeginCapture` ve sunmak için; çağrı ikinci çerçevesi sunmak için çağrısından sonra ilk Direct3D olay çağrısı arasındaki aralık yayılan `EndCapture`.  
  
 Bir aralık yakalamak için grafik bilgilerini yakalama ve kaydetmeye uygulamanızı hazırlama — diğer bir deyişle, çağrısı yapmanız gerekir [Init](../debugger/init.md) örneği üzerinden `VsgDbg` çağırmadan önce sınıfı `BeginCapture` veya `EndCapture`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EndCapture](../debugger/endcapture.md)   
 [CaptureCurrentFrame](../debugger/capturecurrentframe.md)



