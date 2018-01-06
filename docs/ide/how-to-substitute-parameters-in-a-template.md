---
title: "Visual Studio Proje ve öğe şablonları adı parametreleri ekleyin | Microsoft Docs"
ms.custom: 
ms.date: 01/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- template parameters
- template parameters, substituting
- Visual Studio templates, using parameters
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ecdd277a36cb1c074653edb2af7f1882e6d25ede
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-substitute-parameters-in-a-template"></a>Nasıl yapılır: şablonda parametreleri ikame etme

Şablon parametreleri, bir dosyayı bir şablondan oluşturulduğunda tanımlayıcıları sınıf adları ve ad alanları, gibi değiştirmek etkinleştirin. Şablon parametreleri için var olan şablonları ekleyebilir veya şablon parametreleri ile kendi şablonlarınızı oluşturabilirsiniz.

Şablon parametreleri biçimi $ yazılır*parametresi*$. Şablon parametreleri tam bir listesi için bkz: [şablon parametreleri](../ide/template-parameters.md).

Aşağıdaki bölümde "güvenli proje adı" bir ad alanı adıyla değiştirmek için bir şablonu nasıl değiştireceğiniz gösterilir.

## <a name="to-use-a-parameter-to-replace-the-namespace-name"></a>Ad alanı adını değiştirmek için bir parametre kullanmak için

1. Bir veya daha fazla şablon kod dosyalarında parametresini ekleyin. Örneğin:

    ```csharp
    namespace $safeprojectname$
    ```

1. Şablon .vstemplate dosyasını bulun `ProjectItem` bu dosyayı içeren öğe.

1. Ayarlama `ReplaceParameters` özniteliğini `true` için `ProjectItem` öğe:

    ```xml
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>
    ```

## <a name="see-also"></a>Ayrıca bkz.

[Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)  
[Şablon Parametreleri](../ide/template-parameters.md)  
[Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)  
[ProjectItem Öğesi (Visual Studio Öğe Şablonları)](../extensibility/projectitem-element-visual-studio-item-templates.md)