---
title: Liste kaynağı komutu | Microsoft Docs
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
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ce57d39d609268e2570d588e6863eb1e8b8d3111
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688511"
---
# <a name="list-source-command"></a>Kaynağı Listele Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kaynağı Listele komutu](https://docs.microsoft.com/visualstudio/ide/reference/list-source-command).  
  
  
Belirtilen kaynak kodu satırlarını görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListSource [/Count:number] [/Current] [/File:filename]  
[/Line:number] [/ShowLineNumbers:yes|no]  
```  
  
## <a name="switches"></a>Anahtarlar  
 / Sayısı:`number`  
 İsteğe bağlı. Görüntülenecek satır sayısını belirtir.  
  
 / Geçerli  
 İsteğe bağlı. Geçerli satırı gösterir.  
  
 / Dosya:`filename`  
 İsteğe bağlı. Gösterilecek dosyasının yolu. Dosya adı belirtilmezse, komut satırı geçerli deyimin için kaynak kodunu gösterir.  
  
 / Çizgi:`number`  
 İsteğe bağlı. Belirli bir satır numarasına gösterir.  
  
 / ShowLineNumbers:`yes|no`  
 İsteğe bağlı. Satır numaraları görüntülenip görüntülenmeyeceğini belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Bu örnekte, kaynak kodu satır numaralarını görünür olan Form1.vb, dosyanın 4 satırından listeler.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut Penceresi](../../ide/reference/command-window.md)



