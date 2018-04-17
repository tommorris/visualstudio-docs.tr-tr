---
title: VisibilityConstraints öğesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VisibilityConstraints
helpviewer_keywords:
- VSCT XML schema elements, VisibilityConstraints
- VisibilityConstraints element (VSCT XML schema)
ms.assetid: d6dcd314-6fe4-4693-a189-91fa026c7b34
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f81ddd40a6de287fb40840c0473e5702d385793d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="visibilityconstraints-element"></a>VisibilityConstraints öğesi
VisibilityConstraints öğesi grupları komutları ve araç çubuklarını statik görünürlüğünü belirler. Görünürlüğü ilk tarafından denetlenen [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage yüklenirken olmadan tümleşik geliştirme ortamı (IDE).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<VisibilityConstraints>  
  <VisibilityConstraint>... </VisibilityConstraint>  
  <VisibilityConstraint>... </VisibilityConstraint>  
</VisibilityConstraint>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[VisibilityItem Öğesi](../extensibility/visibilityitem-element.md)|Komutlar ve araç çubuklarını statik görünürlüğünü belirler.|  
|[VisibilityConstraints](../extensibility/visibilityconstraints-element.md)|Komutlar ve araç çubuklarını grupları statik görünürlüğünü belirler.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CommandTable Öğesi](../extensibility/commandtable-element.md)|IDE bir VSPackage sağlayan komutlar (örneğin, menü öğeleri, menüler, araç çubukları ve birleşik giriş kutuları) temsil eden tüm öğeleri tanımlar.|  
  
## <a name="example"></a>Örnek  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VisibilityItem öğesi](../extensibility/visibilityitem-element.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)