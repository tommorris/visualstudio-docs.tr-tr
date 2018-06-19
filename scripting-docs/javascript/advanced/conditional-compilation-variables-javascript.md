---
title: Koşullu derleme değişkenleri (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional compilation, variables
ms.assetid: d6f9827d-c558-412c-8e68-de04c19c3d9d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 900a44dab0ad418cd2899af6423f78016c90fe2b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788681"
---
# <a name="conditional-compilation-variables-javascript"></a>Koşullu Derleme Değişkenleri (JavaScript)
Aşağıdaki önceden tanımlanmış değişkenler koşullu derleme için kullanılabilirler. Bir değişken değilse **true**, tanımlı değil ve olarak davranır `NaN` erişildiğinde.  
  
> [!WARNING]
>  Koşullu derleme Internet Explorer'ın Internet Explorer 11'den önceki tüm sürümlerinde desteklenir. Internet Explorer 11 standartları modu ve buna başlangıç [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamaları, koşullu derleme desteklenmiyor.  
  
## <a name="variables"></a>Değişkenler  
  
|Değişken|Açıklama|  
|--------------|-----------------|  
|@_win32|Eğer bir Win32 sistemde yürütülüyorsa doğru.|  
|@_win16|Eğer bir Win16 sistemde yürütülüyorsa doğru.|  
|@_mac|Eğer bir Apple Macintosh sistemde yürütülüyorsa doğru.|  
|@_alpha|Eğer bir DEC Alpha işlemci üzerinde yürütülüyorsa doğru.|  
|@_x86|Eğer bir Intel işlemci üzerinde yürütülüyorsa doğru.|  
|@_mc680x0|Eğer bir Motorola 680x0 işlemci üzerinde yürütülüyorsa doğru.|  
|@_PowerPC|Eğer bir Motorola PowerPC işlemci üzerinde yürütülüyorsa doğru.|  
|@_jscript|Her zaman doğru.|  
|@_jscript_build|Yapı sayısını içeren [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyası altyapısı.|  
|@_jscript_version|İçeren [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] major.minor biçiminde sürüm numarası.|