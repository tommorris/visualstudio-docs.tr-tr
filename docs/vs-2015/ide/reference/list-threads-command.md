---
title: Liste komut iş parçacıkları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.listthreads
helpviewer_keywords:
- ListThreads command
- list threads command
- Debug.ListThreads command
ms.assetid: 34b665c0-d46f-4c1a-a066-b678eba5ac54
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cd8e9f96e0f477ba0b83419274d9b2ed0a101195
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694999"
---
# <a name="list-threads-command"></a>İş Parçacıklarını Listele Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [iş parçacıklarını Listele komutu](https://docs.microsoft.com/visualstudio/ide/reference/list-threads-command).  
  
  
Geçerli programdaki iş parçacıklarının listesini görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListThreads [index]  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 İsteğe bağlı. Bir iş parçacığı geçerli iş parçacığı olarak dizine göre seçer.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek belirtildiğinde, `index` bağımsız değişkeni, belirtilen iş parçacığı geçerli iş parçacığı olarak işaretler. Bir yıldız işareti (*), geçerli iş parçacığı yanındaki listede görüntülenir.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.ListThreads   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağrı yığınını Listele komutu](../../ide/reference/list-call-stack-command.md)   
 [Ayrıştırılmış kodu Listele komutu](../../ide/reference/list-disassembly-command.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



