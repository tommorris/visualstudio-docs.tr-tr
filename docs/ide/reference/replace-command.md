---
title: "Değiştir komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- edit.replace
helpviewer_keywords:
- Edit.Replace command
- Replace command
ms.assetid: a15767f1-5a3d-44f5-8c77-7b0f1157f340
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ea63db35d5bb1eeca08f3e948ffcf5183259ef1c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="replace-command"></a>Değiştir Komutu
Bir alt kümesi üzerinde kullanılabilir seçenekleri kullanarak dosyaları metinde değiştirir **dosyalarda Değiştir** sekmesinde **bulma ve değiştirme** penceresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Edit.Replace findwhat replacewith [/all] [/case]  
[/doc|/proc|/open|/sel] [/hidden] [/options] [/reset] [/up]  
[/wild|/regex] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Gerekli. Eşleşen metin.  
  
 `replacewith`  
 Gerekli. Eşleşen metin için alternatif metin.  
  
## <a name="switches"></a>Anahtarlar  
 / all veya /a  
 İsteğe bağlı. Arama metni tüm oluşumlarını değiştirme metni ile değiştirir.  
  
 /Case veya /c  
 İsteğe bağlı. Eşleşme ortaya yalnızca zaman büyük ve küçük harfleri tam olarak belirtilen eşleşiyorsa `findwhat` bağımsız değişkeni.  
  
 / doc veya /d  
 İsteğe bağlı. Yalnızca geçerli belgede arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 / Gizli veya /h  
 İsteğe bağlı. Tasarım zamanı denetimi, gizli bir bölge anahatları belirlenmiş bir belge veya bir daraltılmış sınıfı ya da yöntemi meta verileri gibi gizli bilgiler ve daraltılmış metin arar.  
  
 /Open veya /o  
 İsteğe bağlı. Bir belge değilmiş gibi tüm açık belgeleri arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 / Options veya /t  
 İsteğe bağlı. Geçerli Bul seçeneği ayarlarını listesini görüntüler ve arama gerçekleştirmez.  
  
 /proc veya /p  
 İsteğe bağlı. Yalnızca geçerli yordamı arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 /Regex veya /r  
 İsteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişken olarak değişmez değer karakterleri yerine metin desenlerini göstermek gösterimler. Normal ifade karakter tam bir listesi için bkz: [normal ifadeler](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 / Reset veya /e  
 İsteğe bağlı. Bul seçeneklerini varsayılan ayarlarına geri döndürür ve bir arama gerçekleştirmez.  
  
 /sel veya/s  
 İsteğe bağlı. Yalnızca geçerli seçimi arar. Kullanılabilir arama kapsamlar yalnızca birini belirtin `/doc`, `/proc`, `/open`, veya `/sel`.  
  
 /UP veya /u  
 İsteğe bağlı. Dosyanın en üstüne doğru dosyayı geçerli konumundan arar. Varsayılan olarak, dosya ve dosyanın sonuna doğru İlerle geçerli konumda aramalar başlar.  
  
 /wild veya /l  
 İsteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişkeni olarak bir karakter ya da bir karakter dizisi temsil etmek için gösterimler.  
  
 /Word veya /w  
 İsteğe bağlı. Yalnızca tam sözcükleri için arama yapar.  
  
## <a name="example"></a>Örnek  
 Bu örnek değiştirir `btnSend` ile `btnSubmit` tüm belgeleri açın.  
  
```  
>Edit.Replace btnSend btnSubmit /open  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin bulma ve değiştirme](../../ide/finding-and-replacing-text.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)