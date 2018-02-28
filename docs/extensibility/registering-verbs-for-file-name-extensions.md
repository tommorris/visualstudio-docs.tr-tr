---
title: "Fiiller için dosya adı uzantılarını kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- verbs, registering
ms.assetid: 81a58e40-7cd0-4ef4-a475-c4e1e84d6e06
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ff1902689524dd980c8223ca83863238254df448
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="registering-verbs-for-file-name-extensions"></a>Fiiller için dosya adı uzantılarını kaydetme
Bir uygulama bir dosya adı uzantısı ilişkilendirmesini genellikle bir kullanıcı bir dosyayı tıklattığında oluşan tercih edilen bir eylem vardır. Bu eylem için eylem karşılık gelen bir fiil, örneğin açık bağlantılı tercih edilir.  
  
 HKEY_CLASSES_ROOT bulunan Kabuk anahtarını kullanarak bir uzantı için bir program tanıtıcısı (ProgID) ile ilişkili olan fiiller kaydedebilirsiniz\\*ProgID*\shell. Daha fazla bilgi için bkz: [dosya türlerini](http://msdn.microsoft.com/library/windows/desktop/cc144148\(v=vs.85\).aspx).  
  
## <a name="registering-standard-verbs"></a>Standart fiillerin kaydetme  
 İşletim sistemi aşağıdaki standart fiillerin tanır:  
  
-   Open  
  
-   Düzenle  
  
-   Yürüt  
  
-   Yazdırma  
  
-   Önizleme  
  
 Mümkün olduğunda, standart bir fiil kaydedin. En yaygın açık fiil seçimdir. Yalnızca dosyayı açıp dosya düzenleme arasında düz bir fark ise düzenleme fiil kullanın. Bir HTML düzenleyicisi bir .htm dosyasının düzenlemeye başlar ancak örneğin, bir .htm dosyasının açma tarayıcıda gösterir. Standart fiiller ile işletim sistemi yerel yerelleştirilmiştir.  
  
> [!NOTE]
>  Standart fiillerin kaydederken, açık anahtar için varsayılan değeri ayarlı değil. Varsayılan değer menüsünde görünen dize içeriyor. İşletim sistemini standart fiiller için bu dize sağlar.  
  
 Proje dosyaları, yeni bir örneğini başlatmaya kaydedileceğini [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kullanıcı dosyayı açtığında. Aşağıdaki örnek için bir standart fiil kaydı gösterilmektedir bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projesi.  
  
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
  
 Mevcut bir örneği bir dosyayı açmaya [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], DDEEXEC anahtarını kaydedin. Aşağıdaki örnek için bir standart fiil kaydı gösterilmektedir bir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] .cs dosyası.  
  
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
  
## <a name="setting-the-default-verb"></a>Varsayılan fiil ayarlama  
 Varsayılan fiili bir kullanıcı bir dosyayı Windows Gezgini'nde tıklattığında çalıştırılan eylemdir. Varsayılan fiili HKEY_CLASSES_ROOT için varsayılan değer olarak belirtilen eylem olduğunda\\*ProgID*\Shell anahtarı. Herhangi bir değer belirtilirse, varsayılan fiil HKEY_CLASSES_ROOT belirtilen ilk fiili olduğunda\\*ProgID*\Shell anahtar listesi.  
  
> [!NOTE]
>  Yan yana dağıtım bir uzantı için varsayılan fiil Değiştir planlıyorsanız, yükleme ve kaldırma üzerindeki etkisini göz önünde bulundurun. Yükleme sırasında özgün varsayılan değerin üzerine yazılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Yana Dosya İlişkilendirmelerini Yönetme](../extensibility/managing-side-by-side-file-associations.md)