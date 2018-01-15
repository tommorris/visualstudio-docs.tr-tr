---
title: DslTextTransform komutu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 47b64bf5049baf981cbf85ec5bfeba4f5f796636
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
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