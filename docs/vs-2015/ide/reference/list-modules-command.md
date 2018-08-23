---
title: Liste modülleri komutu | Microsoft Docs
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
- debug.listmodules
helpviewer_keywords:
- Debug.ListModules command
- ListModules command
- list modules command
ms.assetid: 3cb73774-6ac0-43b2-b781-75ed47175bfd
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1593879f59642347f58d9c8229aac7d2a9d70261
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694652"
---
# <a name="list-modules-command"></a>Modülleri Listele Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [modülleri Listele komutu](https://docs.microsoft.com/visualstudio/ide/reference/list-modules-command).  
  
  
Geçerli işlem için modülleri listeler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListModules [/Address:yes|no] [/Name:yes|no] [/Order:yes|no]  
[/Path:yes|no] [/Process:yes|no] [/SymbolFile:yes|no]  
[/SymbolStatus:yes|no] [/Timestamp:yes|no] [/Version:yes|no]  
```  
  
#### <a name="parameters"></a>Parametreler  
 / Adres:`yes|no`  
 İsteğe bağlı. Modül bellek adresleri gösterilip gösterilmeyeceğini belirtir. Varsayılan değer `yes`.  
  
 / Name:`yes|no`  
 İsteğe bağlı. Modül adlarını gösterilip gösterilmeyeceğini belirtir. Varsayılan değer `yes`.  
  
 / Order:`yes|no`  
 İsteğe bağlı. Modüller sırasını gösterilip gösterilmeyeceğini belirtir. Varsayılan değer `no`.  
  
 / Yolu:`yes|no`  
 İsteğe bağlı. Modül yolları gösterilip gösterilmeyeceğini belirtir. Varsayılan değer `yes`.  
  
 / Process:`yes|no`  
 İsteğe bağlı. Modüller işlemlerinin gösterilip gösterilmeyeceğini belirtir. Varsayılan değer `no`.  
  
 / SymbolFile:`yes|no`  
 İsteğe bağlı. Sembol dosyaları modüllerinin gösterilip gösterilmeyeceğini belirtir. Varsayılan değer `no`.  
  
 / SymbolStatus:`yes|no`  
 İsteğe bağlı. Modül sembolü durumları gösterilip gösterilmeyeceğini belirtir. Varsayılan değer `yes`.  
  
 / Zaman damgası:`yes|no`  
 İsteğe bağlı. Zaman damgaları modüllerinin gösterilip gösterilmeyeceğini belirtir. Varsayılan değer `no`.  
  
 / VERSION:`yes|no`  
 İsteğe bağlı. Modül sürümlerini gösterilip gösterilmeyeceğini belirtir. Varsayılan değer `no`.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Bu örnekte, modül adlarını, adresleri ve geçerli işlem için zaman damgalarını listeler.  
  
```  
Debug.ListModules /Address:yes /Name:yes /Order:no /Path:no /Process:no /SymbolFile:no /SymbolStatus:no /Timestamp:yes /Version:no  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Nasıl yapılır: modüller penceresini kullanma](../../debugger/how-to-use-the-modules-window.md)



