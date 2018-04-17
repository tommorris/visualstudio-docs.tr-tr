---
title: Geçiş kesme komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.togglebreakpoint
helpviewer_keywords:
- ToggleBreakpoint command
- Debug.ToggleBreakPoint command
- Toggle Breakpoint command
ms.assetid: d50dfadb-ce79-4d5e-9c09-1cfddd57876d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8ddbcf2cb47c5e83f2ce23833e3a206b7aaf7fe4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="toggle-breakpoint-command"></a>Kesim Noktasını Değiştir Komutu
Dosya geçerli konumda geçerli durumuna bağlı olarak açmak veya kapatmak kesme noktası etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ToggleBreakpoint [text]  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 İsteğe bağlı. Metin belirtilirse, satır adlandırılmış bir kesme noktası işaretlenir. Aksi takdirde, satır F9 tuşuna bastığınızda olanlar için benzer olduğu adsız bir kesme noktası işaretlenir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, geçerli kesme noktası değiştirir.  
  
```  
>Debug.ToggleBreakpoint  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)