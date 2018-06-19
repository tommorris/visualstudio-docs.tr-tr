---
title: GuidSymbol öğesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, GuidSymbol
- GuidSymbol element (VSCT XML schema)
ms.assetid: 11fb3545-8974-4776-9a54-6b6e7739ae31
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d5e3a3f4d33e166d344669dbeb4bc1a877335f0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128074"
---
# <a name="guidsymbol-element"></a>GuidSymbol öğesi
`GuidSymbol` Ögesinin GUID GUID:ID çiftinin menü, Grup veya komutu temsil eder. Kimliği geldiği bir `IDSymbol` öğesinde `GuidSymbol` öğesi. `GuidSymbol` Öğeye sahip bir `name` bulunan GUID için kolay bir ad sağlar özniteliği `value` özniteliği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<GuidSymbol name="guidMyCommandSet" value="{xxxxxxxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx}">  
  <IDSymbol>... </IDSymbol>  
  <IDSymbol>... </IDSymbol>  
</GuidSymbol>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|name|Gerekli. GUID sembol adı.|  
|value|Gerekli. GUID simgenin GUID.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[IDSymbol Öğesi](../extensibility/idsymbol-element.md)|Menü, Grup veya komut temsil eden GUID:ID çifti Kimliğini içerir.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Symbols Öğesi](../extensibility/symbols-element.md)|Grupları `GuidSymbol` .vsct dosyasındaki öğeleri.|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, bir .vsct dosyası üç içeren `GuidSymbol` öğelerinde kendi `Symbols` bölümü, paket için bir, komut kümesini (menüler, grupları ve paket kullanılabilmesini komutları koleksiyonu) için bir ve sağlamak bit eşlemler için bir düğmelerin ve diğer görsel bileşenleri için simgeler. Her `IDSymbol` öğesinde bir verilen `GuidSymbol` öğesinin benzersiz olmalı `value`. Ancak, `IDSymbol` farklı üst sahip oldukları sürece, aynı değerlere sahip öğeleri bir pakette bulunabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)