---
title: -ProjectConfig (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- /projectconfig Devenv switch
- configurations, rebuilding
- deployment projects, creating
- configurations, cleaning
- deployment projects, specifying
- deployment projects, adding
- build configurations, specifying
- Devenv, /projectconfig switch
- projectconfig Devenv switch (/projectconfig)
- projects [Visual Studio], build configuration
- projects [Visual Studio], cleaning
ms.assetid: 6b54ef59-ffed-4f62-a645-1279ede97ebf
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6069ed9b15ed49f2f7c7a5113f1377cebdd031fc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="projectconfig-devenvexe"></a>/ProjectConfig (devenv.exe)
Yapı, temizleme, yeniden oluşturun veya adlı projeyi dağıtmak uygulanacak bir proje derleme yapılandırmasını belirten `/project` bağımsız değişkeni.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName [/project ProjName] [/projectconfig ProjConfigName]  
```  
  
## <a name="arguments"></a>Arguments  
 / BUILD  
 Tarafından belirtilen proje derlemeler `/project` `ProjName`.  
  
 / clean  
 Tüm aracı dosyaları ve yapılandırma sırasında oluşturulan çıktı dizinleri temizler.  
  
 / Rebuild  
 Temizler sonra tarafından belirtilen proje derlemeler `/project` `ProjName`.  
  
 / deploy  
 Proje derleme veya yeniden sonra dağıtılması belirtir.  
  
 `SolnConfigName`  
 Gerekli. Adlı çözüm için uygulanan çözüm yapılandırmasının adı `SolutionName`.  
  
 `SolutionName`  
 Gerekli. Tam yol ve çözüm dosyasının adı.  
  
 / Project`ProjName`  
 İsteğe bağlı. Yol ve çözüm içinde proje dosyasının adı. Gelen göreli bir yol girin `SolutionName` klasörü proje dosyası veya projenin görünen adı veya tam yolunu ve proje dosyasının adı.  
  
 / projectconfig`ProjConfigName`  
 İsteğe bağlı. Bir proje adını derleme uygulanacak yapılandırma `/project` adlı.  
  
## <a name="remarks"></a>Açıklamalar  
  
-   İle birlikte kullanılmalıdır `/project` geçiş parçası olarak bir `devenv /build`, /`clean`, `/rebuild`, veya `/deploy` komutu.  
  
-   Çift tırnak işaretleri boşluk dizeler alın.  
  
-   Derlemeleri hatalar dahil olmak üzere, ilgili özet bilgileri görüntülenebilir **komutu** penceresinde veya ile belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
## <a name="example"></a>Örnek  
 Bu örnek proje derlemeler `CSharpConsoleApp`kullanarak `Debug` Proje yapı yapılandırması içinde `Debug` çözüm yapılandırmasını `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)   
 [/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ (Devenv.exe) dağıtma](../../ide/reference/deploy-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)