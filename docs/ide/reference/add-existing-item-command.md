---
title: "Varolan öğeyi Ekle komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- project.addexistingitem
helpviewer_keywords:
- File.AddExistingItem command
- Add Existing Item command
ms.assetid: 41f56131-d4c7-4f81-83b7-bdac713ea870
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a94546b8e480a661c175f946cc376fa92b30cbf8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="add-existing-item-command"></a>Varolan Öğeyi Ekle Komutu
Varolan bir dosyayı geçerli çözüme ekler ve açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.AddExistingItem filename [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Gerekli. Tam yol ve dosya adı, geçerli çözüme eklemek için öğesinin uzantısına sahip. Dosya yolu veya dosya adı boşluk içeriyorsa, yolun tamamını tırnak işaretleri içine alın.  
  
## <a name="switches"></a>Anahtarlar  
 / e:`editorname`  
 İsteğe bağlı. Dosya açılacak düzenleyicinin adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı sağlanan **birlikte Aç** iletişim kutusu görüntülenir.  
  
 / E:`editorname` bağımsız değişkeni söz dizimini kullanır Düzenleyici adları içinde göründükleri gibi **ile iletişim kutusunu aç**, tırnak işaretleri içindeki kapalı. Örneğin, bir stil sayfası kaynak kod düzenleyicisinde açmak için aşağıdaki / e: için girersiniz`editorname` bağımsız değişkeni.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Otomatik Tamamlama doğru yolun ve dosya adı, türü bulmaya çalışır.  
  
## <a name="example"></a>Örnek  
 Bu örnek, geçerli çözüme Form1.frm, dosyanın ekler.  
  
```  
>File.AddExistingItem "C:\public\solution files\Form1.frm"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)