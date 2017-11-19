---
title: "Liste modülleri komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.listmodules
helpviewer_keywords:
- Debug.ListModules command
- ListModules command
- list modules command
ms.assetid: 3cb73774-6ac0-43b2-b781-75ed47175bfd
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 081f57f441da17578735317e2d6f8352cd31d30d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="list-modules-command"></a>Modülleri Listele Komutu
Geçerli işlem için modüllerini listeler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListModules [/Address:yes|no] [/Name:yes|no] [/Order:yes|no]  
[/Path:yes|no] [/Process:yes|no] [/SymbolFile:yes|no]  
[/SymbolStatus:yes|no] [/Timestamp:yes|no] [/Version:yes|no]  
```  
  
#### <a name="parameters"></a>Parametreler  
 / Adresi:`yes|no`  
 İsteğe bağlı. Bellek adreslerini modüllerin gösterilip gösterilmeyeceğini belirler. Varsayılan değer `yes`.  
  
 / Adı:`yes|no`  
 İsteğe bağlı. Modül adlarını gösterilip gösterilmeyeceğini belirler. Varsayılan değer `yes`.  
  
 / Order:`yes|no`  
 İsteğe bağlı. Modülleri sırasını gösterilip gösterilmeyeceğini belirler. Varsayılan değer `no`.  
  
 / Yolu:`yes|no`  
 İsteğe bağlı. Modülleri yollarını gösterilip gösterilmeyeceğini belirler. Varsayılan değer `yes`.  
  
 / İşlemi:`yes|no`  
 İsteğe bağlı. Modülleri işlemlerinin gösterilip gösterilmeyeceğini belirler. Varsayılan değer `no`.  
  
 / SymbolFile:`yes|no`  
 İsteğe bağlı. Simge dosyaları modüllerin gösterilip gösterilmeyeceğini belirler. Varsayılan değer `no`.  
  
 / SymbolStatus:`yes|no`  
 İsteğe bağlı. Sembol durumları modüllerin gösterilip gösterilmeyeceğini belirler. Varsayılan değer `yes`.  
  
 / Zaman damgası:`yes|no`  
 İsteğe bağlı. Zaman damgaları modüllerin gösterilip gösterilmeyeceğini belirler. Varsayılan değer `no`.  
  
 / Sürümü:`yes|no`  
 İsteğe bağlı. Modülleri sürümleri gösterilip gösterilmeyeceğini belirler. Varsayılan değer `no`.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Bu örnek modül adlarını, adreslerini ve geçerli işlem için zaman damgalarını listeler.  
  
```  
Debug.ListModules /Address:yes /Name:yes /Order:no /Path:no /Process:no /SymbolFile:no /SymbolStatus:no /Timestamp:yes /Version:no  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Nasıl yapılır: modüller penceresini kullanma](../../debugger/how-to-use-the-modules-window.md)