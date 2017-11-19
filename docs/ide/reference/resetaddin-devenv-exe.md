---
title: -ResetAddin (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8f54e50e62b7f7f8f6dd1610904b66c82da02380
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="resetaddin-devenvexe"></a>/ResetAddin (devenv.exe)
Komutları ve komut belirtilen eklenti ilişkili UI kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv /ResetAddin AddIn  
```  
  
## <a name="arguments"></a>Arguments  
 `AddIn`  
 İsteğe bağlı. Komut adı eklenti.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, eklenti komut adını eşittir  *\<AddInSolutionName >*. Bağlantı*.\< AddInSolutionName >*ve Connect.cs görünür `commandName` parametresinin `Exec` yöntemi. Komut adı, Visual Studio komutları penceresine adını yazmanız başlangıç ve kalan doldurmak için IntelliSense kullanarak da doğrulayabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek Visual Studio başlatır ve engeller `MyAddin` eklentisinden başlangıçta çalıştırma.  
  
```  
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md)   
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)