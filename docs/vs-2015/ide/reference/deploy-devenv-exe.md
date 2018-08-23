---
title: -(Devenv.exe) dağıtma | Microsoft Docs
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
- Devenv, /deploy switch
- deploy Devenv switch
- deploying applications [Visual Studio], after build
- /deploy Devenv switch
ms.assetid: e47c8723-df08-4645-aa2d-0c956e7ccca2
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4bed834524c159d42b2193857c805fab7628fe0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628170"
---
# <a name="deploy-devenvexe"></a>/Deploy (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [-(devenv.exe) dağıtma](https://docs.microsoft.com/visualstudio/ide/reference/deploy-devenv-exe).  
  
  
Bir çözüm oluşturma veya yeniden oluşturma sonra dağıtır. Yalnızca yönetilen kod projeleri için geçerlidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv SolutionName /deploy SolnConfigName [/project ProjName] [/projectconfig ProjConfigName] [/out LogFileName]  
```  
  
## <a name="arguments"></a>Arguments  
 `SolnConfigName`  
 Gerekli. Adlı çözümü derlemek için kullanılan çözüm yapılandırması adı `SolutionName`.  
  
 `SolutionName`  
 Gerekli. Çözüm dosyasının adını ve tam yolu.  
  
 / Project `ProjName`  
 İsteğe bağlı. Çözüm içindeki bir proje dosyasının adı ve yolu. Göreli bir yol girebilirsiniz `SolutionName` klasör proje dosyası veya projenin görünen adı veya tam yolu ve proje dosyasının adı.  
  
 / projectconfig `ProjConfigName`  
 İsteğe bağlı. Bir proje adını derleme oluşturma sırasında kullanılacak yapılandırma `/project` adlı.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen projeyi bir dağıtım projesi olmalıdır. Derlenen proje dağıtılacak geçirildiğinde belirtilen projeyi bir dağıtım projesi değil ise, bir hata ile başarısız olur.  
  
 Çift tırnak içine boşluk dizeleri alın.  
  
 Hataları dahil olmak üzere, derlemeler için Özet bilgiler görüntülenebilir **komut** penceresinde veya belirtilen herhangi bir günlük dosyasını `/out` geçin.  
  
## <a name="example"></a>Örnek  
 Bu örnek projesini dağıtır `CSharpConsoleApp`kullanarak `Release` içinde proje yapı yapılandırmasını `Release` çözüm yapılandırması `MySolution`.  
  
```  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /deploy Release /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Release   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)   
 [/ Derleme (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ (Devenv.exe out)](../../ide/reference/out-devenv-exe.md)



