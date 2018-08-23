---
title: -ResetAddin (devenv.exe) | Microsoft Docs
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
- disable addin
- addin state
- reset addin
ms.assetid: 9e339c8d-d768-4d86-8f45-2f479fc8255b
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f306e6952b5cf0d41901b85e554cfc3f444dbb00
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630690"
---
# <a name="resetaddin-devenvexe"></a>/ResetAddin (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [- ResetAddin (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/resetaddin-devenv-exe).  
  
  
Komutlar ve komut belirtilen eklenti ilişkili UI kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv /ResetAddin AddIn  
```  
  
## <a name="arguments"></a>Arguments  
 `AddIn`  
 İsteğe bağlı. Eklentinin komut adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, eklentinin komut adı eşittir  *\<AddInSolutionName >*. Connect *.\< AddInSolutionName >* ve olarak Connect.CS'de görünür `commandName` parametresinin `Exec` yöntemi. Visual Studio'da komutlar penceresine adını yazmaya başlayarak ve geri kalanı doldurmak için IntelliSense kullanarak da komut adını doğrulayabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, Visual Studio başlatılır ve engeller `MyAddin` başlangıçta çalışan eklentiden.  
  
```  
Devenv.exe /ResetAddin MyAddin.Connect.MyAddin  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)



