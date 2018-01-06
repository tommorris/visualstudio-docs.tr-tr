---
title: "Geçerli işlem ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: eb673db29a4bb106aa4c9c4d9022293367e8ed4f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="set-current-process"></a>Geçerli Süreci Ayarla
Belirtilen işlem etkin işlem hata ayıklayıcı olarak ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.SetCurrentProcess index  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Gerekli. İşlem dizini.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama yaptığınız ancak herhangi bir anda yalnızca bir işlem dubber etkin olduğu durumlarda, birden çok işlem ekleyebilirsiniz. Kullanabileceğiniz `SetCurrentProcess` etkin işlem ayarlamak için komutu.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.SetCurrentProcess 1  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)