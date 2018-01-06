---
title: "VS Kabuğu VSPackage dosya konumunu belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed VSPackages, file location
- VSPackages, managed package file location
ms.assetid: beb8607a-4183-4ed2-9ac8-7527f11513b1
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 35bd935683f8ace47536389ebc65f34311e9fcfd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-vspackage-file-location-to-the-vs-shell"></a>VS Kabuğu VSPackage dosya konumunu belirtme
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]VSPackage yüklemek için DLL derleme bulabilir olması gerekir. Bu çeşitli şekillerde aşağıdaki tabloda açıklandığı şekilde bulabilir.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|CodeBase kayıt defteri anahtarını kullanın.|CodeBase anahtarı yönlendirmek için kullanılabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] herhangi bir tam dosya yolu VSPackage derlemesi yüklenemedi. Anahtarın değerini dll Dosyasının dosya yolu olmalıdır. Bunu sağlamak için en iyi yoludur [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] paket derlemenizi yükleyin. Bu teknik bazen "CodeBase/özel yükleme dizini teknik." adlandırılır Kayıt sırasında bir örneği üzerinden kayıt öznitelik sınıfları codebase değerini geçirilen <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.RegistrationContext> türü.|  
|DLL içine yerleştirin **PrivateAssemblies** dizini.|Derlemede yerleştirin **PrivateAssemblies** alt [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] dizin. Derlemeleri bulunan **PrivateAssemblies** otomatik olarak algılanır ancak görünmez **Başvuru Ekle** iletişim kutusu. Arasındaki farkı **PrivateAssemblies** ve **PublicAssemblies** derlemeler olan içinde **PublicAssemblies** bölümünde açıklanan **Başvuru Ekle**  iletişim kutusu. "CodeBase/özel yükleme dizini" tekniği kullanmayı seçtiğiniz sonra içine yüklemelidir **PrivateAssemblies** dizini.|  
|Tanımlayıcı adlı bir derleme ve derleme kayıt defteri anahtarını kullanın.|Derleme anahtarı açıkça yönlendirmek için kullanılabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackage derleme adlı bir güçlü yüklenemiyor. Anahtarın değerini derleme tanımlayıcı adı olmalıdır.|  
|DLL içine yerleştirin **PublicAssemblies** dizini.|Son olarak, derleme de içine yerleştirilebilir **PublicAssemblies** alt dizin. Derlemeleri bulunan **PublicAssemblies** otomatik olarak algılanır ve ayrıca görünür **Başvuru Ekle** iletişim kutusunda [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].<br /><br /> VSPackage derlemeler yalnızca yerleştirilmelidir içinde **PublicAssemblies** bunlar içeriyorsa, dizin yönetilen diğer VSPackage geliştiriciler tarafından yeniden kullanılması amaçlanan bileşenleri. Derlemeleri çoğunu, bu ölçütü karşılamıyor.|  
  
> [!NOTE]
>  Tanımlayıcı adlı, imzalı derlemeler tüm bağımlı derlemeleriniz için kullanın. Bu derlemeler de dizininizin veya genel derleme önbelleği (GAC) yüklenmesi gerekir. Bu zayıf ad bağlama olarak bilinen aynı temel dosya adına sahip bir derleme çakışıyor korur.