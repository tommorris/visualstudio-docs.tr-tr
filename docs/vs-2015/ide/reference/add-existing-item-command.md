---
title: Varolan öğeyi Ekle komutu | Microsoft Docs
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
- project.addexistingitem
helpviewer_keywords:
- File.AddExistingItem command
- Add Existing Item command
ms.assetid: 41f56131-d4c7-4f81-83b7-bdac713ea870
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 67ee390c55ba9aed0a67990b23d1fd979c1bbc24
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697502"
---
# <a name="add-existing-item-command"></a>Varolan Öğeyi Ekle Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [var olan öğe komut Ekle](https://docs.microsoft.com/visualstudio/ide/reference/add-existing-item-command).  
  
  
Geçerli çözüme var olan bir dosya ekler ve onu açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.AddExistingItem filename [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Gerekli. Tam yol ve dosya adı, geçerli çözüme eklenecek öğe uzantısına sahip. Dosya yolu veya dosya adı boşluk içeriyorsa, yolun tamamını tırnak içine alın.  
  
## <a name="switches"></a>Anahtarlar  
 / e: `editorname`  
 İsteğe bağlı. Dosyanın açılmasını düzenleyicinin adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı verilmesi, **birlikte Aç** iletişim kutusu görüntülenir.  
  
 / E:`editorname` bağımsız değişkeni sözdizimini kullanan Düzenleyicisi adları gibi görünürler **ile iletişim kutusunu açma**tırnak işareti içine alınan. Örneğin, bir stil sayfası Kaynak Kod Düzenleyicisi'nde açmak için / e: şunları girersiniz`editorname` bağımsız değişken.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Otomatik Tamamlama, doğru yol ve dosya adı, türü bulmaya çalışır.  
  
## <a name="example"></a>Örnek  
 Bu örnek dosyayı Form1.frm, geçerli çözüme ekler.  
  
```  
>File.AddExistingItem "C:\public\solution files\Form1.frm"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



