---
title: "Üst öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Parent
- Parent element (VSCT XML schema)
ms.assetid: e4624ac8-1b9a-4940-910a-528a661cefad
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fc66e193b13ac6baf9d6089483a1281c2d6a59ef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="parent-element"></a>Üst Öğe
Bir düğme veya birleşik giriş kutusu üst yalnızca bir grup olabilir. Menü veya grubun üst herhangi bir menü veya grup olabilir. İçinde bir [CommandPlacement öğesi](../extensibility/commandplacement-element.md), bu öğe gereklidir; diğer tüm durumlarda isteğe bağlıdır. Bu öğe girilmezse, üst öğesinin `Group_Undefined:0` kapsanan.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Parent guid="guidMyCommandSet" id="MyParentGroupOrMenu" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. GUID, GUID/kimliği komut tanımlayıcısı.|  
|kimlik|Gerekli. GUID/ID komut tanımlayıcısı.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CommandTable öğesi](../extensibility/commandtable-element.md)|Tümleşik geliştirme ortamı (IDE) bir VSPackage sağlar komutları temsil eden tüm öğeleri tanımlar. Örneğin, menü öğeleri, menüler, araç çubukları ve birleşik giriş kutuları.|  
|[Düğme öğesi](../extensibility/buttons-element.md)|Grupları [Button öğesi](../extensibility/button-element.md) öğeleri.|  
|[Menü öğesi](../extensibility/menus-element.md)|Bir VSPackage uygulayan tüm menüleri tanımlar.|  
|[Öğe grupları](../extensibility/groups-element.md)|Bir VSPackage komut gruplarını tanımlamak girdiler içeriyor.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)