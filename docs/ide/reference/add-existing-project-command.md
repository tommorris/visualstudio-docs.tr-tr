---
title: Varolan projeyi Ekle komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- file.addexistingproject
helpviewer_keywords:
- Add Existing Project command
- File.AddExistingProject
ms.assetid: 71cf3e31-c76b-405b-ad6a-1b1bc654bd40
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 278ed3e13f29746aab963129418dc07f1dcf5234
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="add-existing-project-command"></a>Varolan Projeyi Ekle Komutu
Varolan projeyi geçerli çözüme ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.AddExistingProject filename  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 İsteğe bağlı. Tam yol ve proje adı, çözüme eklemek için projenin uzantısına sahip.  
  
 Varsa `filename` bağımsız değişkeni alanları içerir, tırnak işaretleri içine alınmalıdır.  
  
 Bir dosya adı belirtilirse, bu kullanıcının bir proje seçebileceği şekilde komutu dosya iletişim kutusu açılır.  
  
## <a name="remarks"></a>Açıklamalar  
 Otomatik Tamamlama doğru yolun ve dosya adı, türü bulmaya çalışır.  
  
## <a name="example"></a>Örnek  
 Bu örnek, [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] proje olan geçerli çözüme TestProject1,.  
  
```  
>File.AddExistingProject "c:\visual studio projects\TestProject1.vbproj"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)