---
title: "-Düzenle (devenv.exe) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /edit switch
- /Edit Devenv swtich
ms.assetid: 02b3d6e7-a2b1-4d83-a747-aa8c2fb758b7
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 34b256a788f2ce8077d7f62921a63565f210139a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="edit-devenvexe"></a>/Edit (devenv.exe)
Mevcut bir örneğini belirtilen dosyayı açar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv /edit [file1[ file2]]  
```  
  
## <a name="arguments"></a>Arguments  
 `file1`  
 İsteğe bağlı. Mevcut bir örneği açmak için dosyaya [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Hiçbir örneği varsa [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yoksa, yeni bir örneğini bir Basitleştirilmiş pencere düzenini ile oluşturulur ve `file1` yeni örneğinde açılır.  
  
 `file2`  
 İsteğe bağlı. Mevcut örneğinde açmak için bir veya daha fazla ek dosyalar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="remarks"></a>Açıklamalar  
 Hiçbir dosya belirtilir ve mevcut bir örneği var. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], var olan örneğinin [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] odağı alır. Hiçbir dosya belirtilir ve hiçbir mevcut örneği [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], yeni bir örneğini [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Basitleştirilmiş pencere düzenini ile oluşturulur.  
  
 Varsa mevcut örneği [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kalıcı, örneğin durumunda, [Seçenekler iletişim kutusu](../../ide/reference/options-dialog-box-visual-studio.md) açık, dosya mevcut açık örnek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kalıcı durumdan çıkar.  
  
## <a name="example"></a>Örnek  
 Bu örnek dosyayı açar `MyFile.cs` varolan örneğindeki [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] veya yeni bir örneğini içinde dosya açılır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] bir zaten mevcut değilse.  
  
```  
devenv /edit MyFile.cs  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)