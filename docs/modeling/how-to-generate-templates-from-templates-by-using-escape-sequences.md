---
title: "Nasıl yapılır: çıkış sıraları kullanarak şablonlardan şablonlar oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, generating templates from templates
ms.assetid: 4126156a-7cea-48b8-925e-7790806cfe6c
caps.latest.revision: "35"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 421b8a8bde2bb383889bcb58915fa8a3acb027cf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
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