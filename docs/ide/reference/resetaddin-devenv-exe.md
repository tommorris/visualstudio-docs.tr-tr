---
title: -ResetAddin (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 36b003f4890b16a7b69f7f66f8b0ef83a0ade7ac
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2018
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
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)