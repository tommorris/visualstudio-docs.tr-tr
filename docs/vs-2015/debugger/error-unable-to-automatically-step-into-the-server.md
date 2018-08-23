---
title: 'Hata: Otomatik olarak Adımlanamıyor aktarılacaksa | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- remote debugging, notification error
ms.assetid: 9a370ccc-d358-429c-b285-9b6c0649bc68
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d75ed4ddb42705b95a5ddd834596bc828e0f3ec2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632344"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Hata: Sunucunun İçine Otomatik Olarak Adımlanamıyor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: otomatik olarak adım içine sunucusu alınamıyor](https://docs.microsoft.com/visualstudio/debugger/error-unable-to-automatically-step-into-the-server).  
  
Hata görünür:  
  
 Otomatik olarak adımlanamıyor aktarılacaksa. Hata ayıklayıcı uzak yordam yürütülmesi önce bildirilmedi  
  
 Bir web hizmeti adımlamak çalışırken, bu hata oluşabilir (bkz [Adımlama içine bir XML Web hizmeti](http://msdn.microsoft.com/en-us/8e67de38-bf5f-41cc-a457-1b88ce63d764)). Herhangi bir zamanda gerçekleşebilir [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] düzgün ayarlanmadı.  
  
 Olası nedenler şunlardır:  
  
-   Web.config dosyasında, [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] uygulama ayarlı değil "true" debug (bkz [ASP.NET uygulamalarında hata ayıklama modu](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).  
  
-   Bir sürümünü [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Visual Studio yüklendikten sonra yüklendi. [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] Visual Studio'da daha önce yüklü olması gerekir. Bu sorunu gidermek için Windows kullanın **Denetim Masası**, **programlar ve Özellikler** Visual Studio yüklemenizi onarmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)



