---
title: "CommandPlacement öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 2cbd7ac8-c55a-43d8-a26d-713b3d790016
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 71a53dfcb7ae7cca5b360d2e115c34909ca32f86
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="commandplacement-element"></a>CommandPlacement öğesi
CommandPlacement öğesi düğmeleri, grupları ve menüleri birden fazla grup veya menü eklenmesini sağlar. CommandPlacement öğesini kullanarak, bir kullanıcı arabirimi görünümünü değiştirmek için bu öğeler tamamen yeniden tanımlamanız gerekmez.  
  
 Daha fazla bilgi için bkz: [, yeniden kullanılabilir grupları düğmeler oluşturma](../extensibility/creating-reusable-groups-of-buttons.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<CommandPlacement guid=guidMyCommandSet" id="MyCommand" priority="0x001" >  
  <Parent>... </Parent>  
</CommandPlacement>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. ' Da tanımlandığı gibi komut kümesini GUID [simgeleri öğesi](../extensibility/symbols-element.md).|  
|kimlik|Gerekli. Menü, Grup veya tanımlandığı şekilde yerleştirilmesini komut kimliğini `Symbols Element`.|  
|önceliği|Gerekli. Üst öğesi görsel öğe konumunu belirler.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Üst|Gerekli. Menü veya yerleştirilecek öğesi barındıran grup.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CommandPlacements öğesi](../extensibility/commandplacements-element.md)|Grupları CommandPlacements ve CommandPlacement öğelerinin belirtir.|  
  
## <a name="example"></a>Örnek  
  
```  
<CommandPlacements>  
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0300">  
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>  
  </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CommandPlacements öğesi](../extensibility/commandplacements-element.md)   
 [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)