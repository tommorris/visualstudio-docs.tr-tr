---
title: -Command (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b5ab19af1e746bdee9c4ec933507ac3092b0e82a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
Belirtilen komut başlattıktan sonra yürütür [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv /command CommandName  
```  
  
## <a name="arguments"></a>Arguments  
 `CommandName`  
 Gerekli. Tam adını bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komutu ya da çift tırnak işaretleri arasına, diğer ad. Komut ve diğer adı sözdizimi hakkında daha fazla bilgi için bkz: [Visual Studio komutları](../../ide/reference/visual-studio-commands.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Başlatma tamamlandıktan sonra IDE adlandırılmış komutu yürütür. Bu anahtarı kullanırsanız, IDE görüntülenmez [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] başlangıç başlangıç sayfasında.  
  
 Bir eklenti komutu kullanıma sunar, eklenti komut satırından başlatmak için bu anahtarı kullanın. Daha fazla bilgi için bkz: [nasıl yapılır: denetim eklentileri kullanarak Eklenti Yöneticisi](http://msdn.microsoft.com/Library/4f60444a-cb48-4cdb-8df4-941f6419aeeb).  
  
## <a name="example"></a>Örnek  
 Bu örnek başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve makrosu açık sık kullanılan dosyaları otomatik olarak çalıştırır.  
  
```  
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)