---
title: Geçerli işlemi Ayarla | Microsoft Docs
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
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5281d1c0d926d8d6acdedf323649216c74a4cab9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689538"
---
# <a name="set-current-process"></a>Geçerli Süreci Ayarla
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [geçerli işlemi Ayarla](https://docs.microsoft.com/visualstudio/ide/reference/set-current-process).  
  
  
Belirtilen işlemi Hata ayıklayıcıdaki etkin işlem olarak ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.SetCurrentProcess index  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 Gerekli. İşlem dizini.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama, ancak yalnızca bir işlem dublajcı içerisinde belirli bir zamanda birden çok işleme iliştirebilirsiniz. Kullanabileceğiniz `SetCurrentProcess` etkin işlemi ayarlamak için komutu.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.SetCurrentProcess 1  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



