---
title: "Çağrı yığınını komutu listesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: debug.listcallstack
helpviewer_keywords:
- list call stack command
- Debug.ListCallStack command
ms.assetid: a8b20bf2-81d2-4069-aea8-23e6b15b4347
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 178f219cf25ccddea0121d6c565cb5f9e99d3b33
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="list-call-stack-command"></a>Çağrı Yığınını Listele Komutu
Geçerli çağrı yığını görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListCallStack [/Count:number] [/ShowTypes:yes|no]  
[/ShowNames:yes|no] [/ShowValues:yes|no] [/ShowModule:yes|no]  
[/ShowLineOffset:yes|no] [/ShowByteOffset:yes|no]  
[/ShowLanguage:yes|no] [/IncludeCallsAcrossThreads:yes|no]  
[/ShowExternalCode:yes|no] [Thread:n] [index]  
```  
  
## <a name="arguments"></a>Arguments  
 `index`  
 İsteğe bağlı. Geçerli yığın çerçevesini ayarlar ve hiçbir çıktı görüntüler.  
  
## <a name="switches"></a>Anahtarlar  
 Her anahtar, formun tamamını veya bir kısa süreli kullanılarak çağrılabilir.  
  
 / Sayısı:`number` [veya] / c:`number`  
 İsteğe bağlı. Çağrı yığınları görüntülenecek maksimum sayısı. Sınırsız varsayılan değerdir.  
  
 / ShowTypes:`yes`&#124;`no` [veya] / t:`yes`&#124;`no`  
 İsteğe bağlı. Parametre türleri görüntülenip görüntülenmeyeceğini belirtir. Varsayılan değer `yes`.  
  
 / ShowNames:`yes`&#124;`no` [veya] / n:`yes`&#124;`no`  
 İsteğe bağlı. Parametre adları görüntülenip görüntülenmeyeceğini belirtir. Varsayılan değer `yes`.  
  
 / ShowValues:`yes`&#124;`no` [veya] v:`yes`&#124;`no`  
 İsteğe bağlı. Parametre değerleri görüntülenip görüntülenmeyeceğini belirtir. Varsayılan değer `yes`.  
  
 / ShowModule:`yes`&#124;`no` [veya] / m:`yes`&#124;`no`  
 İsteğe bağlı. Modül adı görüntülenip görüntülenmeyeceğini belirtir. Varsayılan değer `yes`.  
  
 / ShowLineOffset:`yes`&#124;`no` [veya] /#:`yes`&#124;`no`  
 İsteğe bağlı. Satır uzaklığı görüntülenip görüntülenmeyeceğini belirtir. Varsayılan değer `no`.  
  
 / ShowByteOffset:`yes`&#124;`no` [veya] / b:`yes`&#124;`no`  
 İsteğe bağlı. Bayt uzaklığı görüntülenip görüntülenmeyeceğini belirtir. Varsayılan değer `no`.  
  
 / ShowLanguage:`yes`&#124;`no` [veya] / l:`yes`&#124;`no`  
 İsteğe bağlı. Dil görüntülenip görüntülenmeyeceğini belirtir. Varsayılan değer `no`.  
  
 / IncludeCallsAcrossThreads:`yes`&#124;`no` [veya] / i:`yes`&#124;`no`  
 İsteğe bağlı. Çağrıları ya da diğer iş parçacıklarından dahil edilip edilmeyeceğini belirtir. Varsayılan değer `no`.  
  
 / ShowExternalCode:`yes`&#124;`no`  
 İsteğe bağlı. Çağrı yığını için sadece kendi kodumu görüntülenip görüntülenmeyeceğini belirtir. Sadece kendi kodumu kapalıyken, tüm kullanıcı olmayan kodu görüntülenir. Sadece kendi kodumu açık olduğunda, kullanıcı olmayan kod olarak gösterilen `[external]` çağrı yığını çıkışı.  
  
 İş parçacığı:`n`  
 İsteğe bağlı. İş parçacığı için çağrı yığını görüntüler `n`. Hiçbir iş parçacığı belirtilirse, diplays geçerli iş parçacığı için çağrı yığını.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken veya anahtarları yapılan değişiklikler için bu komutun gelecekteki etkinleştirmeleri uygulanır. Debug.ListCallStackby kendisini dağıttığınız tüm çağrı yığını görüntüler. Bir dizin örneğin belirtirseniz,  
  
```  
Debug.ListCallStack 2  
```  
  
 ardından bu çerçevede (Bu durumda, ikinci çerçevesi) için geçerli yığın çerçevesini ayarlayın.  
  
 Ayrıca, önceden tanımlanmış diğer adı kullanarak bu komutu yazabilirsiniz kb. Örneğin, girin  
  
```  
kb 2  
```  
  
 Geçerli yığın çerçevesi ikinci çerçevesi ayarlamak için.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.CallStack /Count:4 /ShowTypes:yes  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ayrıştırılmış kodu Listele komutu](../../ide/reference/list-disassembly-command.md)   
 [İş parçacıklarını Listele komutu](../../ide/reference/list-threads-command.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)