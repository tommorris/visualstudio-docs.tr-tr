---
title: "Nasıl yapılır: çıkış sıraları kullanarak şablonlardan şablonlar oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, generating templates from templates
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7d8aeee2588d0f86708bf76f3630fa0d9ecd5bd1
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>Nasıl yapılır: Çıkış Sıraları Kullanarak Şablonlardan Şablon Oluşturma
Başka bir metin şablonu oluşturulan metin çıktısı olarak oluşturan bir metin şablonu oluşturabilirsiniz. Bunu yapmak için metin şablonu etiketleri ayırmak için çıkış sıraları kullanmanız gerekir. Kaçış dizileri kullanmazsanız, oluşturulan metin şablonu önceden tanımlanmış bir anlama sahip olur. Metin şablonlarında çıkış sıraları kullanma hakkında daha fazla bilgi için bkz: [metin şablonlarında çıkış sıraları kullanarak](../modeling/using-escape-sequences-in-text-templates.md).  
  
### <a name="to-generate-a-text-template-from-within-a-text-template"></a>Metin şablonu içindeki bir metin şablonu oluşturmak için  
  
-   Ters eğik çizgi kullanın (\\) metin şablonu yönergeleri, deyimler, ifadeler içinde gerekli biçimlendirme etiketleri oluşturabilir ve Özellikler ayrı metin şablon dosyasına sınıfı için çıkış karakteri olarak.  
  
    ```  
    \<#@ directive \#>  
    \<# statement \#>  
    \<#= expression \#>  
    \<#+ classfeature \#>  
    ```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir metin şablonuna metin şablonundan üretmek için kaçış karakterleri kullanır. `output` Yönergesi metin şablonu dosya türü (.tt) hedef dosya türünü ayarlar.  
  
```csharp  
\<#@ output extension=".tt" \#>  
\<#@ assembly name="System.Xml.dll" \#>  
\<#@ import namespace="System.Xml" \#>  
\<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {\#>  
           \<#= attr.Name \#>  
       \<#}  
     }  
\#>  
```  
  
 Oluşturulan metin çıktısı bir metin şablonudur.  
  
```  
<#@ output extension=".tt" #>  
<#@ assembly name="System.Xml.dll" #>  
<#@ import namespace="System.Xml" #>  
<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {#>  
           <#= attr.Name #>  
       <#}  
     }  
#>  
```