---
title: 'Nasıl yapılır: oluşturma bir. Vsct mevcut bir dosya. Cto dosya | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT files, creating based on a .cto file
ms.assetid: 847717c9-477d-4ac9-8b2c-2da878912478
caps.latest.revision: 11
manager: douge
ms.openlocfilehash: d69ff5d5c3f6434c9230602ff422accbb2f82422
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688147"
---
# <a name="how-to-create-a-vsct-file-from-an-existing-cto-file"></a>Nasıl yapılır: oluşturma bir. Vsct mevcut bir dosya. Cto dosyası
Var olan bir ikili .cto dosyasından bir XML tabanlı .vsct dosyası oluşturabilirsiniz. Bunun yapılması, yeni komut tablosu derleyici biçimi yararlanmak sağlar. Bu işlem, .cto dosya .ctc dosyasından derlenen bile çalışır. Düzenle ve başka bir .cto dosyasına .vsct dosyası derleme.  
  
### <a name="to-create-a-vsct-file-from-a-cto-file"></a>Bir .cto dosyasından .vsct dosyası oluşturmak için  
  
1.  .Cto dosyası ve karşılık gelen .ctsym dosyası bir kopyasını edinin.  
  
2.  Dosyaları vsct.exe derleyici ile aynı dizine koyun.  
  
3.  Visual Studio komut isteminde .cto ve .ctsym dosyaları içeren dizine gidin.  
  
4.  Tür **vsct.exe** *ctofilename *** .cto** * vsctfilename ***.vsct -S***symfilename ***.ctsym**.  
  
     `ctofilename` .cto dosyanın adıdır `vsctfilename` oluşturmak istediğiniz vsct dosya adıdır ve `symfilename` .ctsym dosyanın adıdır.  
  
     Bu işlem yeni bir .vsct XML komut tablosu derleyici dosyası oluşturur. Düzenle ve diğer .vsct dosyası gibi dosya vsct.exe, vsct derleyici ile derleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: oluşturma bir. Vsct dosyası](../extensibility/internals/how-to-create-a-dot-vsct-file.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)