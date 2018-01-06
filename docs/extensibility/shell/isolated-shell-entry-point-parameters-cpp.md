---
title: "Yalıtılmış Kabuk giriş noktası parametreleri (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shell [Visual Studio], isolated mode, Start entry point
- Visual Studio shell, isolated mode, Start entry point
ms.assetid: 18f4b18b-2173-4afa-ba0a-42fe33e61118
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 78993e12c1ab4098e20aad243faaa487ff0ea35b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="isolated-shell-entry-point-parameters-c"></a>Yalıtılmış Kabuk giriş noktası parametreleri (C++)
Visual Studio Kabuğu tabanlı bir uygulama başladığında Visual Studio Kabuğu'nu başlangıç giriş noktasını çağırır. Aşağıdaki ayarlar, kabuk başlangıç giriş noktası çağrısında geçersiz kılınabilir. Her bir ayarın bir açıklaması için bkz: [. Pkgdef dosyaları](modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md).  
  
-   AddinsAllowed  
  
-   AllowsDroppedFilesOnMainWindow  
  
-   AppName  
  
-   CommandLineLogo  
  
-   DefaultHomePage  
  
-   DefaultProjectsLocation  
  
-   DefaultSearchPage  
  
-   DefaultUserFilesFolderRoot  
  
-   DisableOutputWindow  
  
-   HideMiscellaneousFilesByDefault  
  
-   HideSolutionConcept  
  
-   NewProjDlgInstalledTemplatesHdr  
  
-   NewProjDlgSlnTreeNodeTitle  
  
-   SolutionFileCreatorIdentifier  
  
-   SolutionFileExt  
  
-   UserFilesSubFolderName  
  
-   UserOptsFileExt  
  
 Visual Studio Shell yalıtılmış şablonu bir kaynak dosyası oluşturur *solutionName*.cpp, burada *solutionName* uygulama için çözüm adıdır. Bu dosya, uygulama, _tWinMain işlevi için ana giriş noktası tanımlar. Bu işlev, kabuk başlangıç giriş noktası çağırır.  
  
 Uygulama başlatıldığında, bu ayarların değiştirilmesi uygulamanın davranışı değiştirebilirsiniz.  
  
## <a name="parameters"></a>Parametreler  
 Visual Studio Kabuğu'nu başlangıç giriş noktasını beş parametrelerini tanımlar. İlk dört parametre değiştirmeyin. Beşinci parametre ayarlarını geçersiz kılma listesini alır. Kabuk başlangıç giriş noktası, uygulamanın ana giriş noktasından adı verilir.  
  
 Kabuk başlangıç giriş noktası aşağıdaki imza içeriyor.  
  
```  
typedef int (__cdecl *STARTFCN)(LPSTR, LPWSTR, int, GUID *, WCHAR *pszSettings);  
```  
  
 İstemediğiniz tüm uygulama ayarlarını geçersiz kılmak için ayarları değerini bırakın parametresi null işaretçi olarak geçersiz kılın.  
  
 Bir veya daha fazla ayarlarını geçersiz kılmak için geçersiz kılınacak ayarları içeren bir UNICODE dizesi geçirin. Dize ad-değer çifti noktalı virgülle ayrılmış bir listesidir. Her bir çifti ayarını uygulamak için değer arkasından eşittir (=) ve ardından geçersiz kılmak için ayar adını içerir.  
  
> [!NOTE]
>  Boşluk, Unicode dizeleri dahil etmeyin.  
  
 Boole ayarları için aşağıdaki dizeleri true değerini temsil eder; Tüm diğer dizeleri false değerini temsil eder. Bu dizeler büyük/küçük harfe duyarsızdır.  
  
-   \+  
  
-   1.  
  
-   -1  
  
-   on  
  
-   true  
  
-   Evet  
  
## <a name="example"></a>Örnek  
 Eklentileri devre dışı bırakın ve uygulamanız için varsayılan projeleri konumu değiştirmek için "AddinsAllowed=false;DefaultProjectsLocation=%USERPROFILE%\temp" Son parametre ayarlayabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış Kabuk özelleştirme](customizing-the-isolated-shell.md)   
 [. Pkgdef dosyaları](modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)