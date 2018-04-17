---
title: Bul komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- edit.find
helpviewer_keywords:
- Find command
- Edit.Find command
ms.assetid: f0c705dc-2b97-423d-abbf-5584d4827208
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4f20be9aafaa6002ba329b7dd14c132dbfcab70
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="find-command"></a>Bul Komutu
Bir alt kümesi üzerinde kullanılabilir seçenekleri kullanarak dosyaları arar **dosyalarda Bul** sekmesinde **bulma ve değiştirme** penceresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Edit.Find findwhat [/case] [/doc | /proc | /open | /sel]   
[/markall] [/options] [/reset] [/up] [/wild | /regex] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Gerekli. Eşleşen metin.  
  
## <a name="switches"></a>Anahtarlar  
 /Case veya /c  
 İsteğe bağlı. Eşleşme ortaya yalnızca büyük ve küçük harfleri tam olarak belirtilen eşleşiyorsa `findwhat` bağımsız değişkeni.  
  
 / doc veya /d  
 İsteğe bağlı. Yalnızca geçerli belgede arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 /markall veya /m  
 İsteğe bağlı. Her satırda bir arama eşleşme geçerli belgedeki içeren bir grafik yerleştirir.  
  
 /Open veya /o  
 İsteğe bağlı. Bir belge değilmiş gibi tüm açık belgeleri arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 / Options veya /t  
 İsteğe bağlı. Geçerli Bul seçeneği ayarlarını listesini görüntüler ve arama gerçekleştirmez.  
  
 /proc veya /p  
 İsteğe bağlı. Yalnızca geçerli yordamı arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 / Reset veya /e  
 İsteğe bağlı. Bul seçeneklerini varsayılan ayarlarına geri döndürür ve bir arama gerçekleştirmez.  
  
 /sel veya/s  
 İsteğe bağlı. Yalnızca geçerli seçimi arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 /UP veya /u  
 İsteğe bağlı. Dosya geçerli konumunu başına doğru dosyasında arar. Varsayılan olarak, dosya ve dosyanın sonuna aramaları geçerli konumda aramalar başlar.  
  
 /Regex veya /r  
 İsteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişken olarak değişmez değer karakterleri yerine metin desenlerini göstermek gösterimler. Normal ifade karakter tam bir listesi için bkz: [normal ifadeler](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 /wild veya /l  
 İsteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişkeni olarak bir karakter ya da bir karakter dizisi temsil etmek için gösterimler.  
  
 /Word veya /w  
 İsteğe bağlı. Yalnızca tam sözcükleri için arama yapar.  
  
## <a name="example"></a>Örnek  
 Bu örnek kod şu anda seçili bölümünde "somestring" sözcüğü için büyük küçük harfe duyarlı arama gerçekleştirir.  
  
```  
>Edit.Find somestring /sel /case  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)