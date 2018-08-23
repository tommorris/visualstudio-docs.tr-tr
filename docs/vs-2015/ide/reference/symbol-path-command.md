---
title: Sembol yolu komutu | Microsoft Docs
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
- debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b21a745177722160b100d0bbad770c3a74c40ca3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630547"
---
# <a name="symbol-path-command"></a>Sembol Yolu Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [sembol yolu komutu](https://docs.microsoft.com/visualstudio/ide/reference/symbol-path-command).  
  
  
Hata ayıklayıcının simge araması dizinler listesini ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.SymbolPath pathname1;pathname2;... pathnameN  
```  
  
## <a name="arguments"></a>Arguments  
 `pathname`  
 İsteğe bağlı. Noktalı virgül hata ayıklayıcının simge araması yolları bir listesidir.  
  
## <a name="remarks"></a>Açıklamalar  
 Hayır ise `pathname` belirtilirse, komut geçerli simge yollarını listeler.  
  
## <a name="example"></a>Örnek  
 Bu örnek simge dizinleri listesine iki yol ekler.  
  
```  
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek, geçerli simge yollarının noktalı virgülle ayrılmış bir liste görüntüler.  
  
```  
Debug.SymbolPath  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Visual Studio Komutları](../../ide/reference/visual-studio-commands.md)



