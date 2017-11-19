---
title: "Nasıl yapılır: şablonda parametreleri ikame etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- template parameters, substituting
- Visual Studio templates, using parameters
ms.assetid: a62924a7-4ba0-413d-b606-fdbe1fcf2807
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e6e13e704502443c371021c515c7a9578497f829
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-substitute-parameters-in-a-template"></a>Nasıl Yapılır: Şablonda Parametreleri İkame Etme
Şablon parametreleri sınıf adları gibi değiştirebilir ve ad alanları bir şablonu temel alan bir dosya açıldığında oluşturulur. Şablon parametreleri tam bir listesi için bkz: [şablon parametreleri](../ide/template-parameters.md).  
  
## <a name="procedure"></a>Yordam  
 Bu şablona dayalı bir proje oluşturulduğunda bir şablon dosyalarını parametrelerinde değiştirebilir. Bu yordam, şablonu kullanarak yeni bir proje oluşturduğunuzda, bir ad alanı güvenli proje adıyla yerini alan bir şablonun nasıl oluşturulacağını açıklar.  
  
#### <a name="to-use-a-parameter-to-replace-namespace-name-with-the-project-name"></a>Ad alanı adı ile proje adı değiştirmek için bir parametre kullanmak için  
  
1.  Bir veya daha fazla şablon kod dosyalarında parametresini ekleyin. Örneğin:  
  
    ```  
    namespace $safeprojectname$  
    ```  
  
    > [!NOTE]
    >  Şablon parametreleri biçimi $ yazılır*parametresi*$.  
  
2.  Şablon .vstemplate dosyasını bulun `ProjectItem` bu dosyayı içeren öğe.  
  
3.  Ayarlama `ReplaceParameters` özniteliğini `true` için `ProjectItem` öğesi. Örneğin:  
  
    ```  
    <ProjectItem ReplaceParameters="true">Class1.cs</ProjectItem>  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Şablon parametreleri](../ide/template-parameters.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [ProjectItem öğesi (Visual Studio öğe şablonları)](../extensibility/projectitem-element-visual-studio-item-templates.md)