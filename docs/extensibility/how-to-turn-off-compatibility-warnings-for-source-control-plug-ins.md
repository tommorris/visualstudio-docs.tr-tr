---
title: Kaynak denetimi eklentileri için uyumluluk uyarılarını kapatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3e096b52bdf6e3e0065eefbba708d7bda18ab189
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39498054"
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>Nasıl yapılır: kaynak denetimi eklentileri için uyumluluk uyarılarını kapatma
Bir kullanıcı birden fazla uyumluluk uyarılarını görebilirsiniz, kaynak denetiminde yoksayılacaktır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Sunulan uyarılar, kaynak denetimi eklentisi yeteneklerine bağlıdır ve ayrıntılı buraya devre dışı bırakılabilir.  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>Uyarı devre dışı bırakmak için: "Visual Studio ile en iyi kaynak denetimi tümleştirmesi sağlamak için"  
  
-   (Gerekirse değeri ekleyerek) aşağıdaki kayıt defteri girdisini ayarlayın:  
  
     **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = DWORD: 00000001**  
  
     Tüm bu uyarı görüntülenir olmayan[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] eklentiler.  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>Uyarı devre dışı bırakmak için: "kurulan kaynak denetim sağlayıcısı tüm yetenekleri desteklemiyor"  
  
-   (Değer gerekirse ekleme), aşağıdaki iki kayıt defteri değerlerini ayarlayın:  
  
     **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = DWORD: 00000000**  
  
    **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = DWORD: 00000001**  
  
     (Diğer bir deyişle, yalnızca bir dosya ve proje aynı anda denetleyebilir,) kaynak denetimi eklentisi açıkça yeniden giriş için birden çok proje desteklemiyorsa bu uyarı görüntülenir.  
  
     Yeniden giriş desteklemek en iyi (`SCC_CAP_REENTRANT` yeteneği); bunu yapmak kadar bu uyarıyı kaldırmak. Ancak, bu destek mümkün değilse, bu kayıt defteri girişleri ayarlanabilir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Özellik bayrakları](../extensibility/capability-flags.md)