---
redirect_url: shell/distributing-isolated-shell-applications
title: "Yalıtılmış kabuk uygulamaları dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c503a985-d67a-4ef8-9123-7744a78f2f17
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 250f1d7769f6035e015eeb7247c439b27f913b78
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="distributing-isolated-shell-applications"></a>Yalıtılmış kabuk uygulamaları dağıtma
Yalıtılmış Kabuk uygulama oluşturmak için Visual Studio ve Visual Studio SDK'yı yüklemeniz gerekir. Diğer kullanıcıları veya müşterileri makinelere uygulamasını dağıtmak için yalıtılmış Kabuk için özel bir yeniden dağıtılabilir paketi eklemeniz gerekir.  
  
## <a name="prerequisites-for-distributing-isolated-shell-applications"></a>Yalıtılmış Kabuk uygulamalarını dağıtmak için Önkoşullar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|Visual Studio SDK|Geliştirmek ve uzantılarını test etmek için sahip SDK [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. SDK, Visual Studio yalıtılmış Kabuk kendi örneğini oluşturmak için de kullanabilirsiniz.<br /><br /> Visual Studio SDK'sı için bir önkoşuldur.|  
|Microsoft Visual Studio yalıtılmış Kabuk yeniden dağıtılabilir|Yeniden dağıtılabilir Visual Studio Araçları ortamda derlerken Kurulum programınıza dahil shell yalıtılmış. Yalıtılmış Kabuk yeniden dağıtılabilir paketi .NET Framework 4.5 içerir.|  
  
## <a name="creating-an-installation-program-for-the-application"></a>Uygulama için bir yükleme programı oluşturma  
 Tümleşik veya yalıtılmış Kabuk uygulamanız için bir özel yükleme programı oluşturmanız gerekir. Daha fazla bilgi için bkz: [yalıtılmış Kabuk uygulama yükleme](../extensibility/installing-an-isolated-shell-application.md).  
  
## <a name="allowing-for-updates-to-your-application"></a>Güncelleştirmeleri, uygulamanız için izin verme  
 Yükleme programı uygulamanız, Microsoft Güncelleştirmeleri veya şirketinizin güncelleştirmeleri göre güncelleştirilir, olasılığı için izin vermelidir. Güncelleştirmeleri hakkında daha fazla bilgi için bkz: [yalıtılmış kabuk uygulamaları için bakım yönergeleri](../extensibility/servicing-guidelines-for-isolated-shell-applications.md).