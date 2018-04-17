---
title: 'Hata: ASP.NET yüklü değil | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.http_not_supported
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Web applications, errors
- debugger, Web application errors
- error messages, ASP.NET
- ASP.NET, installation error messages
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 41d2804ce3cab18acf697333ee9950b4717f9500
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="error-aspnet-not-installed"></a>Hata: ASP.NET Yüklü Değil
Bu hata oluştuğunda, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] doğru hata ayıklamaya çalıştığınız bilgisayarda yüklü değil. Bu, anlamına gelebilir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] hiç yüklenmemiştir veya [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] ilk olarak yüklendiği ve IIS daha sonra yüklendi.  
  
### <a name="to-reinstall-aspnet"></a>ASP.NET yeniden yüklemek için  
  
1.  Bir komut istemi penceresinden aşağıdaki komutu çalıştırın:  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     Burada *sürüm* v1.0.370 gibi bilgisayarınızda yüklü .NET Framework sürüm numarasını temsil eder. Framework sürümü bakarak belirleyebilirsiniz `\WINDOWS\Microsoft.NET\Framework` dizin.  
  
    > [!NOTE]
    >  Windows Server 2003, yüklediğiniz [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] kullanarak **Program Ekle veya Kaldır** Denetim Masası'nda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Web uygulamalarında hata ayıklama: Hatalar ve sorun giderme](../debugger/debugging-web-applications-errors-and-troubleshooting.md)