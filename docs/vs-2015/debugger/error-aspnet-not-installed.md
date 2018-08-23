---
title: 'Hata: ASP.NET yüklü değil | Microsoft Docs'
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
- vs.debug.error.http_not_supported
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
ms.assetid: 6286dd3d-3e2b-4edd-959d-81e0ed45500b
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0617f5200a69809afc86fe9405dc3ea9bd8fcda0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685778"
---
# <a name="error-aspnet-not-installed"></a>Hata: ASP.NET Yüklü Değil
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: ASP.NET yüklü değil](https://docs.microsoft.com/visualstudio/debugger/error-aspnet-not-installed).  
  
Bu hata oluştuğunda, [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] doğru hata ayıklamaya çalıştığınız bilgisayarda yüklü değil. Bu gelebilir [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] hiç yüklenmemiş ya da [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] ilk yüklenen ve IIS daha sonra yüklendi.  
  
### <a name="to-reinstall-aspnet"></a>ASP.NET yeniden yüklemek için  
  
1.  Bir komut istemi penceresinden aşağıdaki komutu çalıştırın:  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     Burada *sürüm* v1.0.370 gibi bilgisayarınızda yüklü .NET Framework sürüm numarasını temsil eder. Framework sürümü bakarak belirleyebilirsiniz `\WINDOWS\Microsoft.NET\Framework` dizin.  
  
    > [!NOTE]
    >  Windows Server 2003 ile yükleyebileceğiniz [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] kullanarak **Program Ekle veya Kaldır** Denetim Masası'nda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web uygulamalarında hata ayıklama: Hatalar ve sorun giderme](../debugger/debugging-web-applications-errors-and-troubleshooting.md)



