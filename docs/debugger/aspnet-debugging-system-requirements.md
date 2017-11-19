---
title: "ASP.NET hata ayıklama: Sistem gereksinimleri | Microsoft Docs"
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
- debugging ASP.NET Web applications, system requirements
- debugging ASP.NET Web applications, security requirements
ms.assetid: 7810b9b2-debf-4271-8fc7-1df031123255
caps.latest.revision: "38"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 30ac9c68104423c559ad3bfa8712426b67a4c734
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="aspnet-debugging-system-requirements"></a>ASP.NET Hata Ayıklama: Sistem Gereksinimleri
Bu konu için yazılım ve güvenlik gereksinimlerini açıklar [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] senaryoları hata ayıklama:  
  
-   Yerel, içinde hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve aynı bilgisayarda çalışan Web uygulaması. Bu senaryo iki sürümü vardır:  
  
    -   [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Kodu dosya sisteminde yer alıyor.  
  
    -   [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Kod bir IIS Web sitesinde yer alıyor.  
  
-   Uzaktan, içinde hata ayıklama [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir istemci bilgisayar üzerinde çalışır ve bir uzak sunucu bilgisayarda çalışan bir Web uygulaması debugs.  
  
## <a name="security-requirements"></a>Güvenlik Gereksinimleri  
 Uzaktan hata ayıklama için yerel ve uzak bilgisayarlar bir etki alanı kurulumu veya bir çalışma grubu kurulumu olması gerekir.  
  
 Hata ayıklama için [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] (bir uygulama havuzu tarafından barındırılan) çalışan işlemi, bu işlemde hata ayıklamak için izni olmalıdır. Varsayılan olarak, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] IIS 6.0 öncesinde uygulamaları çalıştırmak olarak **ASPNET** kullanıcı. IIS 6.0 ve IIS 7. 0'da, **ağ hizmeti** varsayılan hesaptır. Çalışan işlem olarak çalışıyorsa, **ASPNET**, veya as **ağ hizmeti**, hata ayıklamak için yönetici ayrıcalıklarına sahip olmalıdır.

 > [!IMPORTANT]
 > Windows Server 2008 R2 ile başlayarak, kullanılmasını öneririz [ApplicationPoolIdentity](https://docs.microsoft.com/en-us/iis/manage/configuring-security/application-pool-identities) her bir uygulama havuzu kimliği olarak.
  
 Adını [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi senaryo hata ayıklama ve IIS sürümü göre değişir. Daha fazla bilgi için bkz: [nasıl yapılır: ASP.NET işleminin adını bulma](../debugger/how-to-find-the-name-of-the-aspnet-process.md).  
  
 Kullanıcı değiştirebilir, hesap [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] altında çalışan IIS çalıştıran sunucuda machine.config dosyasını düzenleyerek çalışan işlemi. Bunu yapmak için en iyi yolu kullanmaktır **Internet Information Services (IIS) Yöneticisi'ni**. Daha fazla bilgi için bkz: [nasıl yapılır: çalışan işlemin altında bir kullanıcı hesabı çalıştırmak](../debugger/how-to-run-the-worker-process-under-a-user-account.md).  
  
 Değiştirirseniz [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] kendi kullanıcı hesabı altında çalışacak şekilde çalışan işlemi IIS çalıştıran sunucuda yönetici olmanız gerekmez.  
  
> [!CAUTION]
>  Değiştirmeden önce [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] farklı bir hesap ile çalıştırmak için çalışan işlemi, olası sonuçları düşünün [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] çalışan işlemi izinsiz giriş bu hesap altında çalışırken. ASP.NET ve ağ hizmeti kullanıcı hesapları işlemi izinsiz giriş varsa olası hasar azaltma en az izinlerle çalıştırın. Değiştirmeniz gerekiyorsa [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] büyük izinlerine sahip bir hesap altında çalıştırmak için çalışan işlemi potansiyel hasarı büyüktür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ASP.NET uygulamalarında hata ayıklama](../debugger/how-to-enable-debugging-for-aspnet-applications.md)   
 [Nasıl yapılır: bir kullanıcı hesabı altında çalışan işlem çalıştırma](../debugger/how-to-run-the-worker-process-under-a-user-account.md)