---
title: Çözüm komutunu açmak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- file.opensolution
helpviewer_keywords:
- Open Solution command
- File.OpenSolution command
ms.assetid: 61de76c8-69d7-4cdb-b605-e132f45d05d9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e97fa5265550222b4df9143a900419a0994f9129
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="open-solution-command"></a>Çözümü Aç Komutu
Herhangi bir açık çözümleri kapatma varolan bir çözümü açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.OpenSolution filename  
```  
  
## <a name="arguments"></a>Arguments  
 `Filename`  
 Gerekli. Çözüm açmak için tam yol ve dosya adı.  
  
 Sözdizimi `filename` bağımsız değişken gerektiriyor boşluk içeren yollar tırnak işaretleri kullanın.  
  
## <a name="remarks"></a>Açıklamalar  
 Otomatik Tamamlama doğru yolun ve dosya adı, türü bulmaya çalışır.  
  
## <a name="example"></a>Örnek  
 Bu örnek Test1.sln çözüm açar.  
  
```  
>File.OpenSolution "c:\MySolutions\Test1\Test1.sln"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)