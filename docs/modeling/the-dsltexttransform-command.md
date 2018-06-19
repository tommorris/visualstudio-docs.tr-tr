---
title: DslTextTransform Komutu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: db916372691ce5e336e142aeb72288193e1ed807
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947059"
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