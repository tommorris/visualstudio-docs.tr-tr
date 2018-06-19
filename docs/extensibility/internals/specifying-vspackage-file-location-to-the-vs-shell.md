---
title: VS Kabuğu VSPackage dosya konumunu belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, file location
- VSPackages, managed package file location
ms.assetid: beb8607a-4183-4ed2-9ac8-7527f11513b1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7a4270fbd723e6c5aa6f16066066e0ca4ac74e5d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132008"
---
# <a name="specifying-vspackage-file-location-to-the-vs-shell"></a>VS Kabuğu VSPackage dosya konumunu belirtme
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackage yüklemek için DLL derleme bulabilir olması gerekir. Bu çeşitli şekillerde aşağıdaki tabloda açıklandığı şekilde bulabilir.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|CodeBase kayıt defteri anahtarını kullanın.|CodeBase anahtarı yönlendirmek için kullanılabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] herhangi bir tam dosya yolu VSPackage derlemesi yüklenemedi. Anahtarın değerini dll Dosyasının dosya yolu olmalıdır. Bunu sağlamak için en iyi yoludur [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] paket derlemenizi yükleyin. Bu teknik bazen "CodeBase/özel yükleme dizini teknik." adlandırılır Kayıt sırasında bir örneği üzerinden kayıt öznitelik sınıfları codebase değerini geçirilen <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.RegistrationContext> türü.|  
|DLL içine yerleştirin **PrivateAssemblies** dizini.|Derlemede yerleştirin **PrivateAssemblies** alt [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] dizin. Derlemeleri bulunan **PrivateAssemblies** otomatik olarak algılanır ancak görünmez **Başvuru Ekle** iletişim kutusu. Arasındaki farkı **PrivateAssemblies** ve **PublicAssemblies** derlemeler olan içinde **PublicAssemblies** bölümünde açıklanan **Başvuru Ekle**  iletişim kutusu. "CodeBase/özel yükleme dizini" tekniği kullanmayı seçtiğiniz sonra içine yüklemelidir **PrivateAssemblies** dizini.|  
|Tanımlayıcı adlı bir derleme ve derleme kayıt defteri anahtarını kullanın.|Derleme anahtarı açıkça yönlendirmek için kullanılabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackage derleme adlı bir güçlü yüklenemiyor. Anahtarın değerini derleme tanımlayıcı adı olmalıdır.|  
|DLL içine yerleştirin **PublicAssemblies** dizini.|Son olarak, derleme de içine yerleştirilebilir **PublicAssemblies** alt dizin. Derlemeleri bulunan **PublicAssemblies** otomatik olarak algılanır ve ayrıca görünür **Başvuru Ekle** iletişim kutusunda [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].<br /><br /> VSPackage derlemeler yalnızca yerleştirilmelidir içinde **PublicAssemblies** bunlar içeriyorsa, dizin yönetilen diğer VSPackage geliştiriciler tarafından yeniden kullanılması amaçlanan bileşenleri. Derlemeleri çoğunu, bu ölçütü karşılamıyor.|  
  
> [!NOTE]
>  Tanımlayıcı adlı, imzalı derlemeler tüm bağımlı derlemeleriniz için kullanın. Bu derlemeler de dizininizin veya genel derleme önbelleği (GAC) yüklenmesi gerekir. Bu zayıf ad bağlama olarak bilinen aynı temel dosya adına sahip bir derleme çakışıyor korur.