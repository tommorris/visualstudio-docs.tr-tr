---
title: DslTextTransform komutu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, commands
ms.assetid: 7d025d0b-6543-4a49-9f6b-8b8cfcad77ee
caps.latest.revision: "30"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: fd45a33b421e889b05fd78eceddc0b05126e4a21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform Komutu
DslTextTransform.cmd TextTransform.exe çağırır ve sık kullanılan seçenekleri ile çalışan bir komut dosyasıdır. DslTextTransformation.cmd gecelik derlemesinde otomatikleştirmek için kullanabileceğiniz, [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] projeleri. Daha fazla bilgi için bkz: [oluşturma dosyalarıyla TextTransform yardımcı programı'nı](../modeling/generating-files-with-the-texttransform-utility.md).  
  
 DslTextTransform.cmd şu dizinde bulunur:  
  
 **\<Visual Studio SDK yükleme yolu > \VisualStudioIntegration\Tools\Bin**  
  
 DslTextTransform.cmd giriş olarak şu bağımsız değişkenleri belirtebilirsiniz:  
  
-   Etki alanı modeli proje çıktı dizini.  
  
-   Tasarımcı tanımı proje çıktı dizini.  
  
-   Metin şablonu dosyasının konumu.  
  
 DslTextTransform.cmd varsayılan yönerge işlemcileri ve derlemeler kullanarak belirtilen metin şablonu dosyasını işler. Özel yönerge işlemcileri oluşturursanız, TextTransform.exe çağıran kendi toplu iş dosyası oluşturabilirsiniz. Bu toplu iş dosyasında derlemeleriniz ve ilişkili özel yönerge işlemcileri belirtebilirsiniz.