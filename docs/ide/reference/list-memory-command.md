---
title: Liste belleği komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- debug.listmemory
helpviewer_keywords:
- Debug.ListMemory command
- ListMemory command
- list memory command
ms.assetid: a84de361-a6a6-4f6d-96aa-a0d4a424371e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 141754e9b298885266aee6d90850b4f0a5c159aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 / ANSI&#124;Unicode  
 İsteğe bağlı. Bellek, bellek, ANSI veya Unicode bayt için karşılık gelen karakter olarak görüntüleyin.  
  
 / Sayısı:`number`  
 İsteğe bağlı. Kaç tane bayt görüntülemek için bellek başlayarak belirler `expression`.  
  
 / Biçimi:`formattype`  
 İsteğe bağlı. Biçim türü bellek bilgileri görüntülemek için **bellek** olabilir; penceresi OneByte, TwoBytes, FourBytes, EightBytes, Float (32 bit) veya çift (64 bit). OneByte kullanılırsa, `/Unicode` kullanılamıyor.  
  
 / Onaltılık&#124;imzalı&#124;imzalanmamış  
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
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)