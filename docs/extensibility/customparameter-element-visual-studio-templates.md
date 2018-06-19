---
title: CustomParameter öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CustomParameter
helpviewer_keywords:
- CustomParameters element [Visual Studio project templates]
ms.assetid: 743c4489-74ac-403a-bbaa-eed7d785a3ac
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 154586701386f5f8f56c128920e12ca3147deb6b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100575"
---
# <a name="customparameter-element-visual-studio-templates"></a>CustomParameter Öğesi (Visual Studio Şablonları)
Özel parametre adı ve şablonu bir proje veya öğesi oluşturulurken kullanılacak bir değer içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<CustomParameter Name="name" Value="value">  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli. Parametrenin adı. Parametreler için biçimidir $*adı*$.|  
|`Value`|Gerekli. Parametre değiştirme değeri.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CustomParameters](../extensibility/customparameters-element-visual-studio-templates.md)|Sihirbaz parametre değişiklik yaptığında için Şablon Sihirbazı'nı geçirilecek özel parametreler gruplandırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir şablon içerdiğinde `CustomParameter` öğeleri, her örneği `Name` özniteliği ile değiştirilir `Value` oluşturulan proje veya öğesi dosya özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir şablonda birden fazla özel parametreler kullanmayı gösterir. Bir proje veya öğesi oluşturulduğunda aşağıdaki özel parametrelerle, tüm örneklerinin bir şablondan `$color1$` ve `$color2$` şablonda dosyaları ile değiştirilecek `Red` ve `Blue`sırasıyla.  
  
```  
<CustomParameters>  
    <CustomParameter Name="$color1$" Value="Red"/>  
    <CustomParameter Name="$color2$" Value="Blue "/>  
</CustomParameters>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CustomParameters öğesi (Visual Studio şablonları)](../extensibility/customparameters-element-visual-studio-templates.md)   
 [Şablon parametreleri](../ide/template-parameters.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)