---
title: Kaynak Denetim Eklentileri için uyumluluk uyarılarını devre dışı bırakma | Microsoft Docs
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
ms.openlocfilehash: 2d3cffbd6a8b6c21aa6e958495b88eb51a5724a5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>Nasıl yapılır: kaynak denetimi eklentiler için uyumluluk uyarılarını devre dışı bırakma
Bir kullanıcı kaynak denetiminde kullanan zaman birkaç uyumluluk uyarısı görebilirsiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Sunulan uyarılar eklenti kaynak denetimi özelliklerine bağlıdır ve ayrıntılı burada devre dışı bırakılabilir.  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>Uyarıyı devre dışı bırakmak için: "... Visual Studio ile en iyi kaynak denetimi tümleştirmesinin emin olmak için"  
  
-   (Gerekirse değeri ekleyerek) aşağıdaki kayıt defteri girdisini ayarlayın:  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = DWORD: 00000001  
  
     Bu uyarı tüm görüntülenir olmayan[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] eklentileri.  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>Uyarıyı devre dışı bırakmak için: "yüklü kaynak denetimi sağlayıcısı olanaklarına... desteklemiyor."  
  
-   (Gerekirse değerleri ekleyerek) aşağıdaki iki kayıt defteri değerlerini ayarlayın:  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = DWORD: 00000000  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = DWORD: 00000001  
  
     (Diğer bir deyişle, yalnızca bir dosya ve proje aynı anda denetleyebilir varsa) eklentisi kaynak denetimi açıkça yeniden giriş için birden çok proje desteklemiyorsa, bu uyarı görüntülenir.  
  
     Yeniden giriş desteklemek en iyisidir (`SCC_CAP_REENTRANT` yeteneği); bunun nedenle kaldırılır bu uyarı. Ancak, bu desteği mümkün değilse, bu kayıt defteri girişleri ayarlanabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik Bayrakları](../extensibility/capability-flags.md)