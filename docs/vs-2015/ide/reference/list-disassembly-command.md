---
title: Ayrıştırılmış kodu komut listesi | Microsoft Docs
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
- debug.listdisassembly
helpviewer_keywords:
- Debug.ListDisassembly command
- list disassembly command
ms.assetid: eb363e35-e86a-4121-966f-991210c27e2a
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6834bc8f6c9bc3aacb95ae3705195fde32c4d6cb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689836"
---
# <a name="list-disassembly-command"></a>Ayrıştırılmış Kodu Listele Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ayrıştırılmış kodu Listele komutu](https://docs.microsoft.com/visualstudio/ide/reference/list-disassembly-command).  
  
  
Hata ayıklama işlemini başlatır ve hataların nasıl işleneceğini belirtmenizi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListDisassembly [/count:number] [/endaddress:expression]  
[/codebytes:yes|no] [/source:yes|no] [/symbolnames:yes|no]  
[/linenumbers:yes|no]  
```  
  
## <a name="switches"></a>Anahtarlar  
 Her anahtar, formun tamamını veya bir kısa biçim kullanılarak çağrılabilir.  
  
 / count: `number` [veya] / c: `number` [veya] /length: `number` [veya] / l: `number`  
 İsteğe bağlı. Görüntülenecek yönerge sayısı. Varsayılan değer 8'dir.  
  
 /endaddress: `expression` [veya] / e: `expression`  
 İsteğe bağlı. Ayrıştırılmış kod durdurmak hangi adresi.  
  
 /codebytes:`yes` &#124; `no` [veya] /bytes:`yes` &#124; `no` [veya] / b:`yes`&#124;`no`  
 İsteğe bağlı. Kod baytlarını görüntülenip görüntülenmeyeceğini gösterir. Varsayılan değer `no`.  
  
 / source:`yes` &#124; `no` [veya] / s:`yes`&#124;`no`  
 İsteğe bağlı. Kaynak kodu görüntülenip görüntülenmeyeceğini gösterir. Varsayılan değer `no`.  
  
 /symbolnames:`yes` &#124; `no` [veya] /names:`yes` &#124; `no` [veya] / n:`yes`&#124;`no`  
 İsteğe bağlı. Sembol adları görüntülenip görüntülenmeyeceğini gösterir. Varsayılan değer `yes`.  
  
 [/ lınenumbers:`yes`&#124;`no`]  
 İsteğe bağlı. Kaynak koduyla ilişkili satır numaralarını görüntülemesini sağlar. / Source switch değerini içermelidir. `yes` /linenumbers anahtar kullanacak şekilde.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.ListDisassembly  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağrı yığınını Listele komutu](../../ide/reference/list-call-stack-command.md)   
 [İş parçacıklarını Listele komutu](../../ide/reference/list-threads-command.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



