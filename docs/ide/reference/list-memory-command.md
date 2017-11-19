---
title: "Liste belleği komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.listmemory
helpviewer_keywords:
- Debug.ListMemory command
- ListMemory command
- list memory command
ms.assetid: a84de361-a6a6-4f6d-96aa-a0d4a424371e
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ae04c23a986107125edc9be149d6317a05c5b58a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="list-memory-command"></a>Belleği Listele Komutu
Belirtilen aralığı bellek içeriğini görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListMemory [/ANSI|Unicode] [/Count:number] [/Format:formattype]  
[/Hex|Signed|Unsigned] [expression]  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 İsteğe bağlı. Bellek görüntüleme başlayacağı bellek adresi.  
  
## <a name="switches"></a>Anahtarlar  
 / ANSI &#124; Unicode  
 İsteğe bağlı. Bellek, bellek, ANSI veya Unicode bayt için karşılık gelen karakter olarak görüntüleyin.  
  
 / Sayısı:`number`  
 İsteğe bağlı. Kaç tane bayt görüntülemek için bellek başlayarak belirler `expression`.  
  
 / Biçimi:`formattype`  
 İsteğe bağlı. Biçim türü bellek bilgileri görüntülemek için **bellek** olabilir; penceresi OneByte, TwoBytes, FourBytes, EightBytes, Float (32 bit) veya çift (64 bit). OneByte kullanılırsa, `/Unicode` kullanılamıyor.  
  
 /Hex &#124; İmzalı &#124; İmzasız  
 İsteğe bağlı. Numaralarını görüntüleme için kullanılacak biçimi belirtir: olarak imzalanmış, imzasız veya onaltılık.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir tam yazmak yerine **Debug.ListMemory** komutu tüm anahtarlarla çağırmak için belirtilen değerler önceden belirli anahtarları ile önceden tanımlanmış diğer adları kullanarak komutu. Örneğin, girmek yerine:  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
 Şunu yazabilirsiniz:  
  
```  
>df /Count:30 /Unicode  
```  
  
 İşte bir listesi için kullanılabilir diğer adların **Debug.ListMemory** komutu:  
  
|Alias|Komut ve anahtarlar|  
|-----------|--------------------------|  
|**d**|Debug.ListMemory|  
|**da**|Debug.ListMemory /Ansi|  
|**DB**|Debug.ListMemory /Format:OneByte|  
|**DC**|Debug.ListMemory /Format:FourBytes /Ansi|  
|**dd**|Debug.ListMemory /Format:FourBytes|  
|**DF**|Debug.ListMemory /Format:Float|  
|**dq**|Debug.ListMemory /Format:EightBytes|  
|**DU**|Debug.ListMemory / Unicode|  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağrı yığınını Listele komutu](../../ide/reference/list-call-stack-command.md)   
 [İş parçacıklarını Listele komutu](../../ide/reference/list-threads-command.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)