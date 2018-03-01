---
title: "Yeni Öğe Ekle komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- project.addnewitem
helpviewer_keywords:
- Add New Item command
- File.AddNewItem command
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 70290f588fe3fac83a5cf0b0ab0339d5e0741186
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="add-new-item-command"></a>Yeni Öğe Ekle Komutu
Geçerli çözüme bir .htm, .css, .txt veya çerçeve gibi yeni bir çözüm öğesi ekler ve açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.AddNewItem [filename] [/t:templatename] [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 İsteğe bağlı. Çözüme eklenecek öğe yolu ve dosya adı.  
  
## <a name="switches"></a>Anahtarlar  
 / t:`templatename`  
 İsteğe bağlı. Oluşturulacak dosya türünü belirtir. Hiçbir şablon adı belirtilmezse, varsayılan olarak bir metin dosyası oluşturulur.  
  
 / T:`templatename` bağımsız değişken sözdizimi yansıtan içinde bulunan bilgileri **yeni çözüm Öğe Ekle** iletişim kutusu. Kategori adı bir ters eğik çizgi ile olan dosya türünü ayırmak dosya türünü ve ardından tam kategori girmeniz gerekir (`\`) ve tüm dizeyi tırnak işaretleri içine kapsayan.  
  
 Örneğin, yeni bir metin dosyası oluşturmak için / t: şunları girersiniz`templatename` bağımsız değişkeni.  
  
```  
/t:"General\Style Sheet"  
```  
  
 / e:`editorname`  
 İsteğe bağlı. Dosya açılacak Düzenleyicisi adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı sağlanan **birlikte Aç** iletişim kutusu görüntülenir.  
  
 / E:`editorname` bağımsız değişkeni söz dizimini kullanır Düzenleyici adları içinde göründükleri gibi **ile iletişim kutusunu aç**, tırnak işaretleri içindeki kapalı.  
  
 Örneğin, bir stil sayfası kaynak kod düzenleyicisinde açmak için aşağıdaki / e: için girersiniz`editorname` bağımsız değişkeni.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek, geçerli çözüme yeni bir çözüm öğesi olan MyHTMLpg, ekler.  
  
```  
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)