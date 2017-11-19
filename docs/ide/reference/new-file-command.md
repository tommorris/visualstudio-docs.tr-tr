---
title: Yeni dosya komutu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: file.newfile
helpviewer_keywords:
- File.NewFile command
- New File command
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9f3b469466080403122484a7b6259c099765edd7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="new-file-command"></a>Yeni Dosya Komutu
Yeni bir dosya oluşturur ve açar. Dosya çeşitli dosyalar klasörü altında görünür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.NewFile [filename] [/t:templatename] [/editor:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 İsteğe bağlı. Dosya adı. Hiçbir adı belirtilirse, varsayılan adı sağlanır. Hiçbir şablon adı listeleniyorsa, bir metin dosyası oluşturulur.  
  
## <a name="switches"></a>Anahtarlar  
 / t:`templatename`  
 İsteğe bağlı. Oluşturulacak dosya türünü belirtir.  
  
 / T:`templatename` bağımsız değişkeni sözdizimi yeni dosya iletişim kutusunda bulunan bilgileri yansıtır. Ardından bir eğik kategori adı girin (`\`) ve şablon adı ve tüm dizeyi tırnak işaretleri içine alın.  
  
 Örneğin, yeni bir oluşturmak için [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] kaynak dosyasını, / t: şunları girersiniz`templatename` bağımsız değişkeni.  
  
```  
/t:"Visual C++\C++ File (.cpp)"  
```  
  
 Yukarıdaki örnekte Visual C++ kategorisinde C++ dosya şablonu altındadır gösterir **yeni dosya** iletişim kutusu.  
  
 / e:`editorname`  
 İsteğe bağlı. Dosya açılacak düzenleyicinin adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı sağlanan **birlikte Aç** iletişim kutusu görüntülenir.  
  
 / E:`editorname` bağımsız değişkeni açık ile iletişim kutusunda tırnak işaretleri içine göründükleri gibi Düzenleyici adları söz dizimini kullanır.  
  
 Örneğin, bir dosyayı kaynak kod düzenleyicisinde açmak için aşağıdaki / e: için girersiniz`editorname` bağımsız değişkeni.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="example"></a>Örnek  
 Bu örnekte yeni bir Web sayfası "test1.htm" oluşturur ve Kaynak Kod Düzenleyicisi'nde açar.  
  
```  
>File.NewFile test1 /t:"General\HTML Page" /e:"Source Code (text) Editor"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Komut penceresi](../../ide/reference/immediate-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komut diğer adları](../../ide/reference/visual-studio-command-aliases.md)