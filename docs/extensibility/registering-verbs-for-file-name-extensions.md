---
title: Dosya adı uzantıları için fiil kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- verbs, registering
ms.assetid: 81a58e40-7cd0-4ef4-a475-c4e1e84d6e06
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8004176fb64244aecde276226683a53c013d3b31
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39513139"
---
# <a name="registering-verbs-for-file-name-extensions"></a>Dosya Adı Uzantıları için Fiil Kaydetme
Bir uygulama bir dosya adı uzantısı ilişkilendirme genellikle bir kullanıcı bir dosyayı çift tıkladığında gerçekleşen tercih edilen bir eylem vardır. Bu eyleme karşılık gelen bir fiil, örneğin açık eylem bağlandığı tercih edilir.  
  
 HKEY_CLASSES_ROOT bulunan Kabuk anahtarı kullanarak bir uzantı için bir programlı tanımlayıcısı (ProgID) ile ilişkili olan fiiller kaydedebilirsiniz\\*ProgID*\shell. Daha fazla bilgi için [dosya türleri](/windows/desktop/shell/fa-file-types).  
  
## <a name="registering-standard-verbs"></a>Standart fiiller kaydediliyor  
 İşletim sistemi, aşağıdaki standart fiiller tanır:  
  
-   Open  
  
-   Düzenle  
  
-   Yürütme  
  
-   Yazdırma  
  
-   Önizleme  
  
 Mümkün olduğunda, standart bir fiil kaydedin. Açık bir fiil en yaygın seçenektir. Dosyayı açıp dosyayı düzenlemeye arasında NET bir fark varsa düzenleme fiili kullanın. Bir .htm dosyasının düzenleme bir HTML Düzenleyicisi başlatılır ancak örneğin, bir .htm dosyasının açma tarayıcı içinde görüntüler. Standart fiiller ile işletim sistemi yerel yerelleştirilmiştir.  
  
> [!NOTE]
>  Standart fiiller kaydederken açık anahtar için varsayılan değer ayarlı değil. Varsayılan değer menüsünde görüntü dizesini içerir. Bu dize standart fiiller için işletim sistemi sağlar.  
  
 Proje dosyaları, yeni bir örneğini başlatmak için kaydedilmelidir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] dosya açıldığında bir kullanıcı. Standart fiili kayıt için aşağıdaki örnekte bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] proje.  
  
```  
[HKEY_CLASSES_ROOT\.csproj]  
@="VisualStudio.csproj.8.0"  
  
[HKEY_CLASSES_ROOT\.csproj\OpenWithList]  
[HKEY_CLASSES_ROOT\.csproj\OpenWithList\VSLauncher.exe]  
@=""  
  
[HKEY_CLASSES_ROOT\.csproj\OpenWithProgids]  
"VisualStudio.csproj.8.0"=""  
  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe]  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell]  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell\Open]  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell\Open\Command]  
@="C:\\Program Files\\Common Files\\Microsoft Shared\\MSEnv\\VSLauncher.exe \"%1\""  
  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0]  
@="C# Project file"  
  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\DefaultIcon]  
@="C:\\VisualStudioPath\\VC#\\VCSPackages\\csproj.dll,0"  
  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell]  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell\Open]  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell\Open\Command]  
@="\"C:\\Program Files\\Common Files\\Microsoft Shared\\MSEnv\\VSLauncher.exe\" \"%1\""  
```  
  
 Mevcut bir örneğini içinde bir dosyayı açmaya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], DDEEXEC anahtarını kaydedin. Standart fiili kayıt için aşağıdaki örnekte bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] .cs dosyası.  
  
```  
[HKEY_CLASSES_ROOT\.cs]  
@="VisualStudio.cs.8.0"  
  
[HKEY_CLASSES_ROOT\.cs\OpenWithList]  
[HKEY_CLASSES_ROOT\.cs\OpenWithList\devenv.exe]  
@=""  
  
[HKEY_CLASSES_ROOT\.cs\OpenWithProgids]  
"VisualStudio.cs.8.0"=""  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0]  
@="C# Source file"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\DefaultIcon]  
@="C:\\VisualStudioPath\\VC#\\VCSPackages\\csproj.dll,1"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell]  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open]  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\Command]  
@="\"C:\\VisualStudioPath\\Common7\\IDE\\devenv.exe\" /dde \"%1\""  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec]  
@="Open(\"%1\")"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec\Application]  
@="VisualStudio.8.0"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec\Topic]  
@="system"  
```  
  
## <a name="setting-the-default-verb"></a>Varsayılan fiili ayarlama  
 Varsayılan fiili bir kullanıcı bir dosyayı Windows Gezgini'nde çift tıkladığında çalıştırılan bir eylemdir. Varsayılan fiili HKEY_CLASSES_ROOT için varsayılan değer olarak belirtilen eylem olan\\*ProgID*\Shell anahtarı. Hiçbir değer belirtilmemişse, varsayılan fiili HKEY_CLASSES_ROOT içinde belirtilen ilk fiil olan\\*ProgID*\Shell anahtar listesi.  
  
> [!NOTE]
>  Varsayılan fiil için uzantı yan yana dağıtım olarak değiştirmeyi planlıyorsanız, yükleme ve kaldırma üzerindeki etkisini göz önünde bulundurun. Yükleme sırasında özgün varsayılan değerin üzerine yazılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Yana Dosya İlişkilendirmelerini Yönetme](../extensibility/managing-side-by-side-file-associations.md)