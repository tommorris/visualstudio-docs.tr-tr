---
title: "UsedCommand öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2b3974c9103a385badc56fda759ee95ef3a40a93
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="usedcommand-element"></a>UsedCommand öğesi
Başka bir .vsct dosyasında tanımlanan bir komutuna erişmek bir VSPackage sağlar. Örneğin, standart, VSPackage kullanıyorsa, **kopya** tarafından tanımlanan komut [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] shell ekleyebileceğiniz komut menü veya araç çubuğuna yeniden uygulamadan.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. Komut tanımlar GUID kimliği çifti GUID.|  
|kimlik|Gerekli. Komut tanımlar GUID kimliği çifti kimliği.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Yok.||  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[UsedCommands öğesi](../extensibility/usedcommands-element.md)|Grupları UsedCommand öğeleri ve diğer UsedCommands gruplandırmaları.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir komutu ekleyerek `<UsedCommands>` öğesi, bir VSPackage bildirir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ortamı VSPackage komutu gerektirir. Eklemeniz gereken bir `<UsedCommand>` öğesi paketinizi gerektiren herhangi bir komut için değil tüm sürümleri ve yapılandırmaları Visual Studio içinde bulunabilir. Paketinizi Visual C++ için özel bir komut çağırırsa eklemediğiniz sürece Örneğin, komut Visual Web Developer kullanıcılara kullanılamaz bir `<UsedCommand>` öğesi için komutu.  
  
## <a name="example"></a>Örnek  
  
```  
<UsedCommands>  
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>  
</UsedCommands>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [UsedCommands öğesi](../extensibility/usedcommands-element.md)   
 [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)