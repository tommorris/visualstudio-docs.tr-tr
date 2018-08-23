---
title: Başlatmış | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4cd66d7329fa4bfc288f3d60879e45cc86ded94e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695659"
---
# <a name="uninit"></a>UnInit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [başlatmış](https://docs.microsoft.com/visualstudio/debugger/graphics/uninit).  
  
Grafik günlük dosyasını sonlandırır kapatılır ve uygulama, etkin bir şekilde grafik bilgilerini kaydetme sırasında kullanılan kaynakları serbest bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
void UnInit();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `UnInit` örneği otomatik olarak çağrılır `VsgDbg` sınıfı yok edildiğinde. Varsa `VsgDbg` örneği etkin bir şekilde kaydetmediğiniz grafik bilgilerini, bu etkiye sahip değildir.  
  
 Sonra `UnInit` örneği üzerinde çağrıldıktan `VsgDbg` sınıfının yeni bir grafik günlük dosyasını çağırarak oluşturulabilir `Init` ve çağrı sonlandırılır `UnInit`. Bu kadar çok kez aynı kullanmak istediğiniz gibi yineleyebilirsiniz `VsgDbg` çeşitli bağımsız grafik günlük dosyaları oluşturmak için örneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Init](../debugger/init.md)



