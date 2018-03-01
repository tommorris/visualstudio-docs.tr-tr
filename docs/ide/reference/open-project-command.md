---
title: "Aç proje komutunu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- file.openproject
helpviewer_keywords:
- op command
- File.OpenProject command
- Open Project command
ms.assetid: baa85f86-041b-49f4-9ced-0c397dc180e1
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6ae2b8f0c9f0a17f29bf42a8a2893f8671df4cd6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="open-project-command"></a>Proje Aç Komutu
Varolan projeyi açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.OpenProject filename  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Gerekli. Projenin açmak için tam yol ve dosya adı.  
  
 Sözdizimi `filename` bağımsız değişken gerektiriyor boşluk içeren yollar tırnak işaretleri kullanın.  
  
## <a name="remarks"></a>Açıklamalar  
 Otomatik Tamamlama doğru yolun ve dosya adı, türü bulmaya çalışır.  
  
 Bu komutu hata ayıklama sırasında kullanılamaz.  
  
## <a name="example"></a>Örnek  
 Bu örnek açar [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] proje, Test1.  
  
```  
>File.OpenProject "C:\My Projects\Test1\Test1.vbproj"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)