---
title: DslTextTransform komutu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 24a3f292633b915678bad232a4a671c7906e15cb
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
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