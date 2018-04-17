---
title: RequiredPlatformVersion öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 6f0e4986-3157-4bba-aed3-c28413ebe976
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 35a8dc6fa57dbe88ce1e30e9be58105f28fe5641
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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