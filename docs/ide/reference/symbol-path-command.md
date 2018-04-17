---
title: Sembol yolu komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b1b35c5d55eed31111746f2e2dbf9befb4fb7591
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="symbol-path-command"></a>Sembol Yolu Komutu
Simgelerini aramak hata ayıklayıcı için dizinler listesinde ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.SymbolPath pathname1;pathname2;... pathnameN  
```  
  
## <a name="arguments"></a>Arguments  
 `pathname`  
 İsteğe bağlı. Noktalı virgülle ayrılmış yollar simgelerini aramak hata ayıklayıcı için listesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Öyle değilse `pathname` belirtilmemişse, komut geçerli simgesi yolları listeler.  
  
## <a name="example"></a>Örnek  
 Bu örnek iki yolu simgesi dizinleri listesine ekler.  
  
```  
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek, geçerli simgesi yolları noktalı virgülle ayrılmış listesini görüntüler.  
  
```  
Debug.SymbolPath  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)