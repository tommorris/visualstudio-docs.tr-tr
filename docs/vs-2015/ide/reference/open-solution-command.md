---
title: Çözüm komutunu açın | Microsoft Docs
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
- file.opensolution
helpviewer_keywords:
- Open Solution command
- File.OpenSolution command
ms.assetid: 61de76c8-69d7-4cdb-b605-e132f45d05d9
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8c2c93f44ba7c801b31390c411da1d16c1645bf6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628941"
---
# <a name="open-solution-command"></a>Çözümü Aç Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [açık çözüm komut](https://docs.microsoft.com/visualstudio/ide/reference/open-solution-command).  
  
  
Herhangi bir açık çözümü kapatma varolan bir çözümü açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.OpenSolution filename  
```  
  
## <a name="arguments"></a>Arguments  
 `Filename`  
 Gerekli. Çözümü açmak için tam yol ve dosya adı.  
  
 Sözdizimi `filename` bağımsız değişken gerektiriyor boşluk içeren yolları tırnak işaretleri kullanın.  
  
## <a name="remarks"></a>Açıklamalar  
 Otomatik Tamamlama, doğru yol ve dosya adı, türü bulmaya çalışır.  
  
## <a name="example"></a>Örnek  
 Bu örnek Test1.sln çözümü açar.  
  
```  
>File.OpenSolution "c:\MySolutions\Test1\Test1.sln"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



