---
title: -(Devenv.exe) oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- builds [Team System], command-line
- /build Devenv switch
- Devenv, /build switch
- build Devenv switch
ms.assetid: ced21627-7653-455b-8821-3e31c6a448cf
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d04b927232936e3c1abc82c0334f4c3486457088
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687482"
---
# <a name="build-devenvexe"></a>/Build (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [-(devenv.exe) derleme](https://docs.microsoft.com/visualstudio/ide/reference/build-devenv-exe).  
  
  
Belirtilen çözüm yapılandırma dosyası kullanarak bir çözüm oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv SolutionName /build SolnConfigName [/project ProjName [/projectconfig ProjConfigName]]  
```  
  
## <a name="arguments"></a>Arguments  
 `SolutionName`  
 Gerekli. Çözüm dosyasının adını ve tam yolu.  
  
 `SolnConfigName`  
 Gerekli. Adlı çözümü derlemek için kullanılan çözüm yapılandırması adı `SolutionName`.  
  
 / Project `ProjName`  
 İsteğe bağlı. Çözüm içindeki bir proje dosyasının adı ve yolu. Göreli bir yol girebilirsiniz `SolutionName` klasör proje dosyası veya projenin görünen adı veya tam yolu ve proje dosyasının adı.  
  
 / projectconfig `ProjConfigName`  
 İsteğe bağlı. Bir proje adını derleme oluşturma sırasında kullanılacak yapılandırma `/project` adlı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu anahtar ile aynı işlevi gerçekleştirir **Çözümü Derle** tümleşik geliştirme ortamında (IDE) menü komutu.  
  
 Çift tırnak içine boşluk dizeleri alın.  
  
 Hataları dahil olmak üzere, derlemeler için Özet bilgiler görüntülenebilir **komut** penceresinde veya belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
 Bu komut, yalnızca son derlemeden sonra değiştirilen projeleri oluşturur. Bir çözümdeki tüm projeleri oluşturmak için kullanın [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md).  
  
## <a name="example"></a>Örnek  
 Bu örnek projeyi derler `CSharpConsoleApp`kullanarak `Debug` içinde proje yapı yapılandırmasını `Debug` çözüm yapılandırması `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Projeleri ve Visual Studio çözümleri oluşturma ve temizleme](../../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ (Devenv.exe out)](../../ide/reference/out-devenv-exe.md)



