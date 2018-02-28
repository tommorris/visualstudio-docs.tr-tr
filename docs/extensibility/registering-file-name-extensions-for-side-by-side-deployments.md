---
title: "Yan yana dağıtımlar için dosya adı uzantılarını kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- file extensions, registering for side-by-side
ms.assetid: 9ab046a2-147d-4167-aa14-7d661b1eaaa5
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 457f9e5303c71d73467815b581c091dc239c1b63
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="registering-file-name-extensions-for-side-by-side-deployments"></a>Yan yana dağıtımlar için dosya adı uzantılarını kaydetme
Yan yana bir ortamda dağıtılan VSPackages için dosyaların doğru sürümü ile ilişkilendirmek için dosya adı uzantılarını kaydetmelisiniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Sürüme özgü dosya adı uzantısı kullanmıyorsanız, kullanıcıların projenizi açın ve uygun sürümünü öğesi dosyalarında proje kaydını etkinleştirir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Dosya Adı Uzantıları Hakkında](../extensibility/about-file-name-extensions.md)  
 Dosya adı uzantılarını nasıl kaydedildiği açıklanır.  
  
 [Dosya Adı Uzantıları için Dosya İşleyicileri Belirtme](../extensibility/specifying-file-handlers-for-file-name-extensions.md)  
 Açabilirsiniz uygulamalar, düzenleme ve benzeri, belirli dosya adı uzantısı kaydetme hakkında bilgi sağlar.  
  
 [Dosya Adı Uzantıları için Fiil Kaydetme](../extensibility/registering-verbs-for-file-name-extensions.md)  
 Fiiller nasıl ele alınmaktadır.  
  
 [Yan Yana Dosya İlişkilendirmelerini Yönetme](../extensibility/managing-side-by-side-file-associations.md)  
 Yan yana yüklemeler kaydedileceği nasıl ele alınacağını açıklar belirli bir sürümü [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir dosyayı açmaya çağrılmalıdır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Visual Studio'nun Birden Çok Sürümünü Destekleme](../extensibility/supporting-multiple-versions-of-visual-studio.md)  
 Birden çok sürümleri için ilgili sorunlar anlatılmaktadır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ve geliştirme ve son kullanıcılar için dağıtım sırasında VSPackage.