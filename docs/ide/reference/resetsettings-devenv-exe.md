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
ms.openlocfilehash: c4f65035e1030406ced4c5f0c98ebd1d1e66c5d2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)