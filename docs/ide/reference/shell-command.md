---
title: Kabuk komutu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tools.shell
helpviewer_keywords:
- exe files
- Shell command
- Tools.Shell command
- executables, running from Visual Studio
- .exe files
- Shell, launching exe files
- Visual Studio, executables from
ms.assetid: 737fda23-b852-45c4-a9fe-41cbce6ba70f
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 7744feca20a14a85c7a035a9b74ed415a43553b3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="shell-command"></a>Kabuk Komutu
İçinden yürütülebilir programları başlatır [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Tools.Shell [/command] [/output] [/dir:folder] path [args]  
```  
  
## <a name="arguments"></a>Arguments  
 `path`  
 Gerekli. Yürütülecek dosya veya belgeyi açmak için yolu ve dosya adı. Belirtilen dosya PATH ortam değişkeni dizinlerde birinde değilse, bir tam yol gereklidir.  
  
 `args`  
 İsteğe bağlı. Çağrılan programın geçirmek için herhangi bir bağımsız değişken.  
  
## <a name="switches"></a>Anahtarlar  
 /CommandWindow [veya] / Command [veya] /c [veya] / cmd  
 İsteğe bağlı. Yürütülebilir dosya için çıktıyı görüntülenir belirtir **komutu** penceresi.  
  
 /dir:`folder` [veya] / d:`folder`  
 İsteğe bağlı. Programını çalıştırdığınızda ayarlamak için çalışma dizini belirtir.  
  
 /OutputWindow [veya] / Output [veya] /out [veya] /o  
 İsteğe bağlı. Yürütülebilir dosya için çıktıyı görüntülenir belirtir **çıkış** penceresi.  
  
## <a name="remarks"></a>Açıklamalar  
 Hemen sonra /dir /o /c anahtarları belirtilmelidir `Tools.Shell`. Hiçbir şey yürütülebilir dosyanın adını komut satırı bağımsız değişken olarak geçirilen sonra belirtilen.  
  
 Önceden tanımlanmış diğer `Shell` yerine kullanılan `Tools.Shell`.  
  
> [!CAUTION]
>  Varsa `path` bağımsız değişkeni, dosya adının yanı sıra dizin yolu sağlayan, tüm yol değişmez değer tırnak içine aldığınızdan ("" "), aşağıdaki gibi:  
  
```  
Tools.Shell """C:\Program Files\SomeFile.exe"""  
```  
  
 Her kümesi üç çift tırnak ("" ") tarafından yorumlanan `Shell` işlemci tek tırnak karakteri olarak. Bu nedenle, önceki örnekte aşağıdaki yol dizesini gerçekten geçirmeden `Shell` komutu:  
  
```  
"C:\Program Files\SomeFile.exe"  
```  
  
> [!CAUTION]
>  Yol dizesi sabit değeri tırnak içine aldığınızdan değil varsa ("" "), Windows yalnızca dize bölümü kadar ilk alanı kullanır. Örneğin, yukarıdaki yol dizesi düzgün tırnak içine alınmış değil, "Program C:\ kök dizininde bulunan" adlı bir dosya için Windows görünür. C:\Program.exe yürütülebilir dosya kullanılabileceğinden, hatta bir yasadışı oynama tarafından yüklenen Windows istenen "c:\Program Files\SomeFile.exe" programın yerine bu program çalıştırma denemesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut dosyasını kopyalamak için xcopy.exe kullanır `MyText.txt` içine `Text` klasör. İkisi de xcopy.exe çıktısı görüntülenir **komut penceresi** ve **çıkış** penceresi.  
  
```  
>Tools.Shell /o /c xcopy.exe c:\MyText.txt c:\Text\MyText.txt  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Çıktı penceresi](../../ide/reference/output-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)