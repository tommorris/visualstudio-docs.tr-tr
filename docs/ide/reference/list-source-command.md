---
title: "Liste kaynağı komutu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
caps.latest.revision: "6"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2f94f7bea2f4742fa975948d838e0cb01ce5e11e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="list-source-command"></a>Kaynağı Listele Komutu
Kaynak kodu belirtilen satır görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListSource [/Count:number] [/Current] [/File:filename]  
[/Line:number] [/ShowLineNumbers:yes|no]  
```  
  
## <a name="switches"></a>Anahtarlar  
 / Sayısı:`number`  
 İsteğe bağlı. Görüntülenecek satır sayısını belirtir.  
  
 / Geçerli  
 İsteğe bağlı. Geçerli satır gösterir.  
  
 / Dosyası:`filename`  
 İsteğe bağlı. Gösterilecek dosyasının yolu. Bir dosya adı belirtilmezse, komut satırı geçerli deyimin için kaynak kodunu gösterir.  
  
 / Satır:`number`  
 İsteğe bağlı. Bir satır numarasında gösterir.  
  
 / ShowLineNumbers:`yes|no`  
 İsteğe bağlı. Satır numaraları görüntülenip görüntülenmeyeceğini belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Bu örnekte, kaynak kodu satır numaralarını görünür dosyanın Form1.vb, 4 satırından listelenmiştir.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)