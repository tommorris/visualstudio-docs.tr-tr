---
title: -Proje (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 06d788e672cbda254ad95b2b36c650e59d3a3314
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="project-devenvexe"></a>/Project (devenv.exe)
Yapı, temizleme, yeniden oluşturun veya dağıtmak için belirtilen çözüm yapılandırma içinde tek bir proje tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv SolutionName {/build|/clean|/rebuild|/deploy} SolnConfigName   
[/project ProjName] [/projectconfig ProjConfigName]   
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
  
-   Kullanılması gereken parçası bir `devenv /build`, /`clean`, `/rebuild`, veya `/deploy` komutu.  
  
-   Çift tırnak işaretleri boşluk dizeler alın.  
  
-   Derlemeleri hatalar dahil olmak üzere, ilgili özet bilgileri görüntülenebilir **komutu** penceresinde veya ile belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
## <a name="example"></a>Örnek  
 Bu örnek proje derlemeler `CSharpConsoleApp`kullanarak `Debug` Proje yapı yapılandırması içinde `Debug` çözüm yapılandırmasını `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ ProjectConfig (devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)   
 [/ Yapı (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ (Devenv.exe) dağıtma](../../ide/reference/deploy-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)