---
title: Liste kaynağı komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d21a18a58832918b566e925c7c3898988740a1a7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [Komut Penceresi](../../ide/reference/command-window.md)