---
title: Dosyalarda Bul komutu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: edit.findinfiles
helpviewer_keywords:
- Edit.FindInFiles command
- find in files command
ms.assetid: 2fc78bfe-b339-4599-97f9-4cafd8a194d9
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b041772c98fb8466ebc262863638ae5583500ef6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="find-in-files-command"></a>Dosyalarda Bul Komutu
Arama bir alt kümesi üzerinde kullanılabilir seçenekleri kullanarak dosyaları **dosyalarda Bul** sekmesinde **bulma ve değiştirme** penceresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Edit.FindinFiles findwhat [/case] [/ext:extensions]  
[/lookin:searchpath] [/names] [/options] [/reset] [/stop] [/sub]  
[/text2] [/wild|/regex] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Gerekli. Eşleşen metin.  
  
## <a name="switches"></a>Anahtarlar  
 /Case veya /c  
 İsteğe bağlı. Eşleşme ortaya yalnızca büyük ve küçük harfleri tam olarak belirtilen eşleşiyorsa `findwhat` bağımsız değişkeni.  
  
 /ext:`extensions`  
 İsteğe bağlı. Aranacak dosyaların dosya uzantıları belirtir. Bir daha önce girilmiş olması durumunda belirtilmezse, önceki uzantıyı kullanılır.  
  
 /lookin:`searchpath`  
 İsteğe bağlı. Arama dizini. Yol boşluk içeriyorsa, yolun tamamını tırnak işaretleri içine alın.  
  
 /Names veya /n  
 İsteğe bağlı. Eşleşmeleri dosya adlarının bir listesini görüntüler.  
  
 / Options veya /t  
 İsteğe bağlı. Geçerli Bul seçeneği ayarlarını listesini görüntüler ve arama gerçekleştirmez.  
  
 /Regex veya /r  
 İsteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişken olarak değişmez değer karakterleri yerine metin desenlerini göstermek gösterimler. Normal ifade karakter tam bir listesi için bkz: [normal ifadeler](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 / Reset veya /e  
 İsteğe bağlı. Bul seçeneklerini varsayılan ayarlarına geri döndürür ve bir arama gerçekleştirmez.  
  
 / Stop  
 İsteğe bağlı. Devam eden ise geçerli arama işlemini durdurur. Arama, diğer tüm bağımsız değişkenleri göz ardı eder zaman `/stop` belirtilmedi. Örneğin, geçerli aramayı durdurmak için aşağıdaki girmeniz gerekir:  
  
```  
>Edit.FindinFiles /stop  
```  
  
 /Sub veya/s  
 İsteğe bağlı. Alt klasörleri /lookin belirtilen dizin içinde arar:`searchpath` bağımsız değişkeni.  
  
 /text2 veya /2  
 İsteğe bağlı. Arama sonuçlarını Bul sonuçları 2 penceresinde görüntüler.  
  
 /wild veya /l  
 İsteğe bağlı. Önceden tanımlanmış özel karakterleri kullanan `findwhat` bağımsız değişkeni olarak bir karakter ya da bir karakter dizisi temsil etmek için gösterimler.  
  
 /Word veya /w  
 İsteğe bağlı. Yalnızca tam sözcükleri için arama yapar.  
  
## <a name="example"></a>Örnek  
 Bu örnekte "My Visual Studio projeleri" klasöründe bulunan tüm .cls dosyalarında btnCancel arar ve Bul sonuçları 2 penceresinde eşleştirme bilgileri görüntüler.  
  
```  
>Edit.FindinFiles btnCancel /lookin:"c:/My Visual Studio Projects" /ext:*.cls /text2  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyalarda Bul](../../ide/find-in-files.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)