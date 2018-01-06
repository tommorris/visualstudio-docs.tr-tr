---
title: "AppliesTo öğesi (Visual Studio şablonları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fb1334b-d78c-405f-98b4-786e9f6b58d7
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 35e11a53b2b9b63a71aab2858151721cfdfd7f9c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="appliesto-element-visual-studio-templates"></a>AppliesTo Öğesi (Visual Studio Şablonları)
Bir veya daha fazla yeteneği karşılamak için isteğe bağlı bir ifade belirtir. (bkz: <xref:Microsoft.VisualStudio.Shell.Interop.VsProjectCapabilityExpressionMatcher>). Özellikleri, hiyerarşinin özelliği olarak aracılığıyla proje türleri tarafından sunulur <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID5>. Bu sayede, şablon ortak uygulanabilir yeteneklere sahip birden fazla proje türü tarafından paylaşılabilir.  
  
 Bu öğe isteğe bağlıdır. Bir şablon dosyasında en fazla bir örnek olabilir. Bu öğe yalnızca, o anda seçili etkin projenin yeteneklerine göre bir öğe şablonunun uygulanabilir olarak tercih edilmesini sağlar. Bir öğe şablonunu uygulanamaz yapmak için kullanılamaz. Varsa `AppliesTo` yok ya da ifade başarıyla, ardından kabul değil `TemplateID` veya `TemplateGroupID` şablonun uygulanabilir, olarak önceki ürün sürümleriyle sağlamak için kullanılır.  
  
 Visual Studio 2013 güncelleştirme 2 kullanıma sunuldu. Doğru sürümü başvuru için bkz: [Visual Studio 2013 güncelleştirme 2 SDK teslim başvuran derlemeler](http://msdn.microsoft.com/en-us/42b65c3e-e42b-4c39-98c8-bea285f25ffb).  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<AppliesTo >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<AppliesTo>Capability1</AppliesTo>   
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Şablon kategorilere ayırır.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir. Bu metin projenin yeteneklerini belirtir.  
  
 Geçerli ifade sözdizimi şu şekilde tanımlanır:  
  
-   "(VisualC &#124; gibi yetenek ifade CSharp) + (mstest'i &#124; NUnit) ".  
  
-   "&#124;" OR işleci.  
  
-   "&" Ve "+" karakterlerdir hem ve işleçler.  
  
-   "!" karakteri NOT işlecidir.  
  
-   Parantezler değerlendirme-öncelik sırasını zorlar.  
  
-   Null veya boş ifade bir eşleşme olarak değerlendirilir.  
  
-   Proje özellikleri bu ayrılmış karakterleri dışında herhangi bir karakter olabilir: "'' :;,+-*/\\! ~ &#124; & %$@^()={} [] <>? \t\b\n\r  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, üç farklı şablonu göstermektedir. `Template1`tüm C# proje türleri veya destekleyen herhangi bir proje türü geçerli `WindowsAppContainer` yeteneği. `Template2`tüm C# projelerine herhangi bir türde yöneliktir. `Template3`olmayan C# projelerine yöneliktir `WindowsAppContainer` projeleri.  
  
```xml  
<!--  Template 1 -->  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <AppliesTo>CSharp | WindowsAppContainer</AppliesTo>   
    </TemplateData>  
</VSTemplate>  
  
<!--  Template 2 -->  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <AppliesTo>CSharp</AppliesTo>   
    </TemplateData>  
</VSTemplate>  
  
<!--  Template 1 -->  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <AppliesTo>CSharp_Class + (!WindowsAppContainer)</AppliesTo>   
    </TemplateData>  
</VSTemplate>  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)   
 [Proje ve Öğe Şablonları Oluşturma](../ide/creating-project-and-item-templates.md)