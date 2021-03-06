---
title: -Proje (devenv.exe) | Microsoft Docs
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
- /project Devenv switch
- projects [Visual Studio], rebuilding
- projects [Visual Studio], building
- deployment projects, specifying
- project Devenv switch (/project)
- Devenv, /project switch
- projects [Visual Studio], cleaning
ms.assetid: 8b07859c-3439-436d-9b9a-a8ee744eee30
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4ffef1cdcc0b192e2e950e02b28dff2682936d87
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695014"
---
# <a name="project-devenvexe"></a>/Project (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [-proje (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/project-devenv-exe).  
  
  
Tek bir proje oluşturmak, temizlemek, yeniden oluşturmak veya dağıtmak için belirtilen çözüm yapılandırması içindeki tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName   
[/project ProjName] [/projectconfig ProjConfigName]   
```  
  
## <a name="arguments"></a>Arguments  
 / Build  
 Tarafından belirtilen projeyi derler `/project` `ProjName`.  
  
 / clean  
 Tüm ara dosyaları ve derleme sırasında oluşturulan çıktı dizini temizler.  
  
 / Rebuild  
 Temizler ve ile belirtilen projeyi oluşturur `/project` `ProjName`.  
  
 / deploy  
 Proje derleme veya yeniden sonra dağıtılması belirtir.  
  
 `SolnConfigName`  
 Gerekli. Adlı çözüm için uygulanacak çözüm yapılandırması adı `SolutionName`.  
  
 `SolutionName`  
 Gerekli. Çözüm dosyasının adını ve tam yolu.  
  
 / Project `ProjName`  
 İsteğe bağlı. Çözüm içindeki bir proje dosyasının adı ve yolu. Göreli bir yol girebilirsiniz `SolutionName` klasör proje dosyası veya projenin görünen adı veya tam yolu ve proje dosyasının adı.  
  
 / projectconfig `ProjConfigName`  
 İsteğe bağlı. Bir proje adını yapı uygulanacak yapılandırma `/project` adlı.  
  
## <a name="remarks"></a>Açıklamalar  
  
-   Kullanılmalıdır parçası olan bir `devenv /build`, /`clean`, `/rebuild`, veya `/deploy` komutu.  
  
-   Çift tırnak içine boşluk dizeleri alın.  
  
-   Hataları dahil olmak üzere, derlemeler için Özet bilgiler görüntülenebilir **komut** penceresinde veya belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
## <a name="example"></a>Örnek  
 Bu örnek projeyi derler `CSharpConsoleApp`kullanarak `Debug` içinde proje yapı yapılandırmasını `Debug` çözüm yapılandırması `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ ProjectConfig (devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)   
 [/ Derleme (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ (Devenv.exe) dağıtma](../../ide/reference/deploy-devenv-exe.md)   
 [/ (Devenv.exe out)](../../ide/reference/out-devenv-exe.md)



