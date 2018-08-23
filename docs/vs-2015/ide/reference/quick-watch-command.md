---
title: Hızlı Bakış komutu | Microsoft Docs
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
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d340f88b83e5dce3054a264a2815fa96707a19f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694945"
---
# <a name="quick-watch-command"></a>Hızlı Bakış Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Hızlı Bakış komutu](https://docs.microsoft.com/visualstudio/ide/reference/quick-watch-command).  
  
  
İfade alanında seçilen veya belirtilen metni görüntüler [QuickWatch iletişim kutusu](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867). Bir değişkenin veya ifadenin hata ayıklayıcı veya bir kaydın içeriğini tarafından tanınan geçerli değerini hesaplamak için bu iletişim kutusunu kullanabilirsiniz. Ayrıca, herhangi bir sabit olmayan değişken değeri veya herhangi bir kayıt içeriğini değiştirebilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.QuickWatchq [text]  
```  
  
## <a name="arguments"></a>Arguments  
 `text`  
 İsteğe bağlı. Eklenecek metin **QuickWatch** iletişim kutusu.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `text` olan atlanırsa, seçili durumdaki metni veya word imlecin İzle penceresine eklenir.  
  
## <a name="example"></a>Örnek  
  
```  
>Debug.QuickWatch  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: QuickWatch iletişim kutusunu kullanın](http://msdn.microsoft.com/library/ffaee1dd-e5ce-4ef2-9401-d28329398867)   
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



