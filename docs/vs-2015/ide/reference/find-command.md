---
title: Bul komutu | Microsoft Docs
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
- edit.find
helpviewer_keywords:
- Find command
- Edit.Find command
ms.assetid: f0c705dc-2b97-423d-abbf-5584d4827208
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6deea29955bac41fb9714f094456775862259b40
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686578"
---
# <a name="find-command"></a>Bul Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Bul komutu](https://docs.microsoft.com/visualstudio/ide/reference/find-command).  
  
  
Dosyaları bulunan seçenekler kümesini kullanarak arar **dosyalarda Bul** sekmesinde **Bul ve Değiştir** penceresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Edit.Find findwhat [/case] [/doc | /proc | /open | /sel]   
[/markall] [/options] [/reset] [/up] [/wild | /regex] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Gerekli. Eşleştirilecek metin.  
  
## <a name="switches"></a>Anahtarlar  
 /Case veya /c  
 İsteğe bağlı. Eşleşme gerçekleşmesi yalnızca büyük ve küçük harfleri tam olarak belirtilen platformlarla eşleşen `findwhat` bağımsız değişken.  
  
 / doc veya /d  
 İsteğe bağlı. Yalnızca geçerli belgede arar. Kullanılabilir arama kapsamları yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 /markall veya /m  
 İsteğe bağlı. Geçerli belge içinde bir arama eşleşme içeren her satırda bir grafik yerleştirir.  
  
 /Open veya /o  
 İsteğe bağlı. Bir belge değilmiş gibi tüm açık belgeleri arar. Kullanılabilir arama kapsamları yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 / Options veya /t  
 İsteğe bağlı. Geçerli bulma seçeneği ayarları listesini görüntüler ve arama yapmaz.  
  
 /proc veya /p  
 İsteğe bağlı. Yalnızca geçerli yordamı arar. Kullanılabilir arama kapsamları yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 Reset veya /e  
 İsteğe bağlı. Bulma seçenekleri varsayılan ayarlarına geri döndürür ve bir arama yapmaz.  
  
 /sel veya /s  
 İsteğe bağlı. Yalnızca geçerli seçimi arar. Kullanılabilir arama kapsamları yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 /UP veya /u  
 İsteğe bağlı. Dosyanın başına doğru dosyasındaki geçerli konumda arar. Varsayılan olarak geçerli konumda dosyanın sonuna doğru arar ve dosya aramaları başlar.  
  
 /Regex veya /r  
 İsteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişken olarak sabit karakterleriyle yerine metin desenleri temsil eden gösterimler. Normal ifade karakterleri tam bir listesi için bkz. [normal ifadeler](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 /wild veya/l  
 İsteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişken olarak bir karakter ya da dizi karakteri temsil etmek için gösterimler.  
  
 /Word veya /w  
 İsteğe bağlı. Yalnızca için tam sözcükleri arar.  
  
## <a name="example"></a>Örnek  
 Bu örnek, şu anda seçili kod bölümünde "somestring" sözcüğü için büyük küçük harfe duyarlı bir arama gerçekleştirir.  
  
```  
>Edit.Find somestring /sel /case  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



