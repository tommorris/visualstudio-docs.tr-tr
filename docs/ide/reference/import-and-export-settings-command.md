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
ms.workload: multiple
ms.openlocfilehash: d4337a5755a58c03c827849417412885f42127a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
 [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)