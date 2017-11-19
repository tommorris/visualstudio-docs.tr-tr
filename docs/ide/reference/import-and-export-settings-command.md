---
title: "İçeri ve dışarı aktarma ayarları komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 61924f7d9430661114f1fecc36d585e2d223604b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="import-and-export-settings-command"></a>Ayarları İçeri ve Dışarı Aktar Komutu
Exports veya sıfırlar alır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]  
```  
  
## <a name="switches"></a>Anahtarlar  
 / Export:`filename`  
 İsteğe bağlı. Geçerli ayarları, belirtilen dosyaya aktarır.  
  
 / import:`filename`  
 İsteğe bağlı. Belirtilen dosya ayarlarında alır.  
  
 / Reset  
 İsteğe bağlı. Geçerli ayarları sıfırlar.  
  
## <a name="remarks"></a>Açıklamalar  
 Olmadan bu komutu çalıştırmak geçer açılır **içeri ve dışarı aktarma ayarları** Sihirbazı. Daha fazla bilgi için bkz: [nasıl yapılır: paylaşım ayarları bilgisayarlar arasında ya da Visual Studio sürümleri](http://msdn.microsoft.com/en-us/1131fb10-35c1-42da-9cd8-91aa3235b882).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komutu geçerli ayarları dosyasına dışa aktarır `MyFile.vssettings`.  
  
```  
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)