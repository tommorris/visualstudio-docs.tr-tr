---
title: 'Hata: Sunucunun otomatik olarak bir adımla kurulamıyor | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a8c79669da0e20bc7376d68c4ea782d280eb6df3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Hata: Sunucunun İçine Otomatik Olarak Adımlanamıyor
Hata okur:  
  
 Sunucu otomatik olarak bir adımla kurulamıyor. Uzaktan yordam yürütülmeden önce hata ayıklayıcısı bildirildi değil  
  
 Bir web hizmetine adım çalışılırken bu hata oluşabilir (bkz [atlama içine bir XML Web hizmeti](http://msdn.microsoft.com/en-us/8e67de38-bf5f-41cc-a457-1b88ce63d764)). Her oluşabilir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] düzgün ayarlanmadı.  
  
 Olası nedenler şunlardır:  
  
-   Web.config dosyasında, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] uygulama ayarlı değil "true" debug (bkz [ASP.NET uygulamalarında hata ayıklama modunda](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).  
  
-   Bir sürümünü [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Visual Studio yüklendikten sonra yüklendi. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Visual Studio önce yüklenmesi gerekir. Bu sorunu gidermek için Windows kullanma **Denetim Masası > Programlar ve Özellikler** Visual Studio yüklemenizi onarmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)