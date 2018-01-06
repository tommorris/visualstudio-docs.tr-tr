---
title: "RequiredPlatformVersion öğesi (Visual Studio şablonları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f0e4986-3157-4bba-aed3-c28413ebe976
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 818405e6c7df6466208db325a7417e0b5b9387e2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="requiredplatformversion-element-visual-studio-templates"></a>RequiredPlatformVersion Öğesi (Visual Studio Şablonları)
Proje şablonu düzgün çalışması için gerekli olan işletim sisteminin en düşük sürümünü belirtir. Bu öğe oluşturma proje şablonları için kullanılan [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] uygulamalar.  
  
 `RequiredPlatformVersion` Değeri doğrudan işletim sistemi sürümü ile karşılaştırılan. Varsa `RequiredPlatformVersion` işletim sistemi sürümünden daha yüksek olan şablon görünmez **yeni proje** iletişim kutusu. İçin bir şablon belirtmek için [!INCLUDE[win8](../debugger/includes/win8_md.md)] veya daha yüksek, ayarlanmış `RequiredPlatformVersion` 6.2.0 için. İçin bir şablon belirtmek için [!INCLUDE[win81](../debugger/includes/win81_md.md)] ya da daha yüksek, ayarlanmış RequiredPlatformVersion 6.3.0 için.  
  
 Belirten şablonları `RequiredPlatformVersion`= 8 önceki müşteriyle uyumlu [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] şablonları.  
  
 VSTemplate  
TemplateData  
..... TargetPlatformName  
RequiredPlatformVersion  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<RequiredPlatformVersion> OperatingSystem </RequiredPlatformVersion>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Yok.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplatePlatformName](../extensibility/templatedata-element-visual-studio-templates.md)|Platform belirtir, proje şablonu hedefler.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu metin şablonu için gerekli en düşük işletim sistemi sürümünü belirtir.  
  
## <a name="example"></a>Örnek  
 Bu örnek belirleyen proje şablonu hedefleri [!INCLUDE[win8](../debugger/includes/win8_md.md)] veya sonraki bir sürümü.  
  
```xml  
<VSTemplate Type="Project" Version="3.0.0"    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <TargetPlatformName>Windows</TargetPlatformName>  
            <RequiredPlatformVersion>6.3.0</RequiredPlatformVersion>  
  
    </TemplateData>  
    <TemplateContent>  
  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TargetPlatformName öğesi (Visual Studio şablonları)](../extensibility/targetplatformname-element-visual-studio-templates.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)