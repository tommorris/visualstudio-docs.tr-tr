---
title: "Liste iş parçacıkları komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.listthreads
helpviewer_keywords:
- ListThreads command
- list threads command
- Debug.ListThreads command
ms.assetid: 34b665c0-d46f-4c1a-a066-b678eba5ac54
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4499bd11e60aba81b37f13f5ce95e8a17412e2d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="list-threads-command"></a>İş Parçacıklarını Listele Komutu
İş parçacıklarının geçerli programa görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListThreads [index]  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 İsteğe bağlı. Bir iş parçacığı geçerli iş parçacığının olmasını dizinini tarafından seçer.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtildiğinde, `index` bağımsız değişkeni belirtilen iş parçacığı geçerli iş parçacığı olarak işaretler. Bir yıldız işareti (*), geçerli iş parçacığının yanında listesinde görüntülenir.  
  
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