---
title: Visual Studio Proje ve öğe şablonları Name parametrelerini ekleyin
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- template parameters
- template parameters, substituting
- Visual Studio templates, using parameters
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 26802b7b5293fd43eb1546290560c5300c360003
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-substitute-parameters-in-a-template"></a>Nasıl yapılır: şablonda parametreleri ikame etme

Şablon parametreleri tanımlayıcıları sınıf adları ve ad alanları gibi bir dosya bir şablondan oluşturulduğunda değiştirmenizi sağlar. Şablon parametreleri için var olan şablonları ekleyebilir veya şablon parametreleri ile kendi şablonlarınızı oluşturabilirsiniz.

Şablon parametreleri biçimi $ yazılır*parametresi*$. Şablon parametreleri tam bir listesi için bkz: [şablon parametreleri](../ide/template-parameters.md).

Aşağıdaki bölümde "güvenli proje adı" bir ad alanı adıyla değiştirmek için bir şablonu nasıl değiştireceğiniz gösterilir.

## <a name="to-use-a-parameter-to-replace-the-namespace-name"></a>Ad alanı adını değiştirmek için bir parametre kullanmak için

1. Bir veya daha fazla şablon kod dosyalarında parametresini ekleyin. Örneğin:

    ```csharp
    namespace $safeprojectname$
    ```

1. İçinde *vstemplate* için şablon dosyası, bulun `ProjectItem` bu dosyayı içeren öğe.

1. Ayarlama `ReplaceParameters` özniteliğini `true` için `ProjectItem` öğe:

    ```xml
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>
    ```

## <a name="see-also"></a>Ayrıca bkz.

- [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)
- [Şablon parametreleri](../ide/template-parameters.md)
- [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)
- [ProjectItem öğesi (Visual Studio öğe şablonları)](../extensibility/projectitem-element-visual-studio-item-templates.md)