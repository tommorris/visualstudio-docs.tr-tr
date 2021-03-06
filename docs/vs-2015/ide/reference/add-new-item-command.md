---
title: Yeni Öğe Ekle komutu | Microsoft Docs
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
- project.addnewitem
helpviewer_keywords:
- Add New Item command
- File.AddNewItem command
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8f380a11440ed413871d2c80603148aa7cc77390
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687635"
---
# <a name="add-new-item-command"></a>Yeni Öğe Ekle Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yeni öğe komut Ekle](https://docs.microsoft.com/visualstudio/ide/reference/add-new-item-command).  
  
  
Geçerli çözüme .htm, .css, .txt veya frameset gibi yeni bir çözüm öğesi ekler ve onu açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.AddNewItem [filename] [/t:templatename] [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 İsteğe bağlı. Çözüme eklenecek öğe yolu ve dosya adı.  
  
## <a name="switches"></a>Anahtarlar  
 / t: `templatename`  
 İsteğe bağlı. Oluşturulacak dosya türünü belirtir. Hiçbir şablon adı belirtilmezse, varsayılan olarak bir metin dosyası oluşturulur.  
  
 / T:`templatename` bağımsız değişken söz dizimi içinde bulunan bilgileri yansıtır **yeni çözüm Öğe Ekle** iletişim kutusu. Dosya türü kategori adı bir ters eğik çizgi dosya türünü ayırmak, ardından tam kategori girmeniz gerekir (`\`) ve tırnak dizenin tamamını kapsayan.  
  
 Örneğin, yeni bir metin dosyası oluşturmak için / t: şunları girersiniz`templatename` bağımsız değişken.  
  
```  
/t:"General\Style Sheet"  
```  
  
 / e: `editorname`  
 İsteğe bağlı. Dosyanın açılmasını Düzenleyicisi adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı verilmesi, **birlikte Aç** iletişim kutusu görüntülenir.  
  
 / E:`editorname` bağımsız değişkeni sözdizimini kullanan Düzenleyicisi adları gibi görünürler **ile iletişim kutusunu açma**tırnak işareti içine alınan.  
  
 Örneğin, bir stil sayfası Kaynak Kod Düzenleyicisi'nde açmak için / e: şunları girersiniz`editorname` bağımsız değişken.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek, yeni bir çözüm öğesi MyHTMLpg, geçerli çözüme ekler.  
  
```  
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



