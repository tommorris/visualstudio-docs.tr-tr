---
title: Yeni dosya komutu | Microsoft Docs
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
- file.newfile
helpviewer_keywords:
- File.NewFile command
- New File command
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0e925cee55f0e2c79a02a208a5d792339e6fd86e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686558"
---
# <a name="new-file-command"></a>Yeni Dosya Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yeni dosya komutu](https://docs.microsoft.com/visualstudio/ide/reference/new-file-command).  
  
  
Yeni bir dosya oluşturur ve onu açar. Dosyanın çeşitli dosyalar klasörü altında görünür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.NewFile [filename] [/t:templatename] [/editor:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 İsteğe bağlı. Dosyanın adı. Adı sağlanmazsa, varsayılan adı sağlanır. Hiçbir şablon adı listede yoksa, bir metin dosyası oluşturulur.  
  
## <a name="switches"></a>Anahtarlar  
 / t:`templatename`  
 İsteğe bağlı. Oluşturulacak dosya türünü belirtir.  
  
 / T:`templatename` bağımsız değişkeni sözdizimini yeni dosya iletişim kutusunda bulunan bilgileri yansıtır. Ardından bir eğik kategori adı girin (`\`) ve şablon adı ve tüm dizeyi tırnak içine alın.  
  
 Örneğin, yeni bir [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] kaynak dosyası, / t: şunları girersiniz`templatename` bağımsız değişken.  
  
```  
/t:"Visual C++\C++ File (.cpp)"  
```  
  
 Yukarıdaki örnekte C++ dosyası şablonu Visual C++ kategorisi altında bulunduğunu gösterir **yeni dosya** iletişim kutusu.  
  
 / e:`editorname`  
 İsteğe bağlı. Dosyanın açılmasını düzenleyicinin adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı verilmesi, **birlikte Aç** iletişim kutusu görüntülenir.  
  
 / E:`editorname` bağımsız değişkeni sözdizimini açık ile iletişim kutusunda tırnak işaretleri arasına göründükleri gibi Düzenleyicisi adları kullanır.  
  
 Örneğin, bir dosya kaynak kod Düzenleyicisi'nde açmak için / e: şunları girersiniz`editorname` bağımsız değişken.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek, yeni bir Web sayfası "test1.htm" oluşturur ve Kaynak Kod Düzenleyicisi'nde açılır.  
  
```  
>File.NewFile test1 /t:"General\HTML Page" /e:"Source Code (text) Editor"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Komut penceresi](../../ide/reference/immediate-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



