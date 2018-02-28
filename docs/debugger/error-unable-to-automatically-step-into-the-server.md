---
title: "Hata: Sunucunun otomatik olarak bir adımla kurulamıyor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, notification error
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 890c3e650b656d3c69a574ba477b797ba120c0a6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Hata: Sunucunun İçine Otomatik Olarak Adımlanamıyor
Hata okur:  
  
 Sunucu otomatik olarak bir adımla kurulamıyor. Uzaktan yordam yürütülmeden önce hata ayıklayıcısı bildirildi değil  
  
 Bir web hizmetine adım çalışılırken bu hata oluşabilir (bkz [atlama içine bir XML Web hizmeti](http://msdn.microsoft.com/en-us/8e67de38-bf5f-41cc-a457-1b88ce63d764)). Her oluşabilir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] düzgün ayarlanmadı.  
  
 Olası nedenler şunlardır:  
  
-   Web.config dosyasında, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulama ayarlı değil "true" debug (bkz [ASP.NET uygulamalarında hata ayıklama modunda](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).  
  
-   Bir sürümünü [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Visual Studio yüklendikten sonra yüklendi. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]Visual Studio önce yüklenmesi gerekir. Bu sorunu gidermek için Windows kullanma **Denetim Masası > Programlar ve Özellikler** Visual Studio yüklemenizi onarmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)