---
title: -ResetSettings (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 52d01cfc3ae6a453330c2dda5da137f449ff5cbd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)
Geri yükler [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] varsayılan ayarları ve otomatik olarak başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. İsteğe bağlı olarak belirtilen .vssettings dosyasına ayarlarını sıfırlar.  
  
 Varsayılan ayarları olan profili tarafından belirlenir işaretlendiğinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] önce başlatıldı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv /ResetSettings SettingsFile  
```  
  
## <a name="arguments"></a>Arguments  
 `SettingsFile`  
 Tam yolunu ve uygulamak için .vssettings dosyasının adı [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Genel Geliştirme Ayarları profili geri yüklemek için kullanmak `General`.  
  
## <a name="remarks"></a>Açıklamalar  
 Öyle değilse `SettingsFile` belirtilirse, başlatmanız istenecek sonraki başlatışınızda ayarlar varsayılan koleksiyonu seçmek için [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını dosyasında depolanan ayarları uygular `MySettings.vssettings`.  
  
```  
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md)   
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)