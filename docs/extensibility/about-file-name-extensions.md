---
title: Dosya adı uzantıları hakkında | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2c940319cd0ce3204f6dd9bb62e731de49b8baac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="about-file-name-extensions"></a>Dosya adı uzantıları hakkında
Dosya uzantısına sahip bir VSPackage kaydederken bunu bir sürümü ile ilişkilendirmeniz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Bu önemli IF bundan daha yüksek bir sürümü olan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir bilgisayarda yüklü.  
  
 Dosya uzantıları VSPackages için ilişkili programlı tanımlayıcısına (ProgID) işaret eden varsayılan bir değerle HKEY_CLASSES_ROOT anahtarı altında kaydedilir.  
  
 .Vcproj dosya uzantısı için kayıt bilgilerinin bir örnek verilmiştir:  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)=" VisualStudio.vcproj.8.0"   
```  
  
 İle ilişkili dosyalar [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sürümü tutulan ProgID gibi olmalıdır `VisualStudio.vcproj.8.0`yan yana yüklemeler ürün sürümleri arasında dosya uzantısı ilişkilendirmeyi korumak için ürün izin vermek için. Sürüme özgü ProgID ayrıca gibi açık, düzenleme ve benzeri üzerine veya diğer uygulamalar veya sürümleri tarafından üzerine yazılmasını sorun olmadan standart fiillerin sayesinde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 Bazı durumlarda, bir dosya uzantısıyla ilişkili ProgID değiştirilmemelidir. Örneğin, ProgID .htm dosya uzantısı için (ProgID htmlfile =) işletim sisteminde basamak sayısını kodlanmış zordur ve yaygın olarak bilinen ve kullanılan .htm ve .html dosyalarla ilişkidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan yana dağıtımlar için dosya adı uzantılarını kaydetme](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [Dosya Adı Uzantıları için Dosya İşleyicileri Belirtme](../extensibility/specifying-file-handlers-for-file-name-extensions.md)