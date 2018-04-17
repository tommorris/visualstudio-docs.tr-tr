---
title: DslTextTransform komutu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 11fb12f3716fe9f8b5fee13a7eecd88ee107ff45
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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