---
title: "Simge öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Symbols element (VSCT XML schema)
- VSCT XML schema elements, Symbols
ms.assetid: 1cda43d8-42a5-4b1b-a3c8-cf0401c3202f
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4ef5b215e18163b10c8002affc959bd80b586cf0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="symbols-element"></a>Simgeler öğesi
GUID ve diğer VSCT öğeleri tarafından kullanılan kimlikleri tanımlar. Yönetilmeyen kod için bu bilgileri genellikle tarafından belirtilen üstbilgi dosyaları geldiği [Extern öğesi](../extensibility/extern-element.md). Kod kullanan bu bilgileri tanımlamak için simgeler öğesinin alt öğeleri yönetilen.  
  
 Varolan .cto dosyasından .vsct dosyası oluşturursanız, simgeler simgeleri öğesinin alt öğesi olarak oluşturulur. Daha fazla bilgi için bkz: [nasıl yapılır: oluşturmak bir. Mevcut bir kümeden Vsct dosyası. Teknolojiden dosya](../extensibility/internals/how-to-create-a-dot-vsct-file.md#how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file).  
  
 Simgeler öğesi ile karıştırılmamalıdır [tanımlamak öğesi](../extensibility/define-element.md), ad-değer çiftleri önişlemci tarafından kullanılmak üzere tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Symbols>  
  <GuidSymbol>... </GuidSymbol>  
  <GuidSymbol>... </GuidSymbol>  
</Symbols>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Yok.||  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|GuidSymbol|Bir GUID simge tanımlar. GuidSymbol iki gerekli öznitelikler vardır: ad ve değer. Simgenin adını adıdır ve değeri bir dize olarak GUID değeridir.<br /><br /> Örneğin:\<GuidSymbol name = "guidVsPackage1Pkg" value = "{c5f54698-101a-4846-84d3-dc748f9cd848}" / >|  
|IDSymbol|Bir simge tanımlar. IDSymbol iki gerekli öznitelikler vardır: ad ve değer. Simgenin adını adıdır ve değeri bir dize olarak simgenin değeridir.<br /><br /> Örneğin:\<IDSymbol name = "MyMenuGroup" value = "0x1020" / >|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CommandTable öğesi](../extensibility/commandtable-element.md)|.Vsct dosyasının kök öğesinin.|  
  
## <a name="example"></a>Örnek  
  
```  
<Symbols>  
  <GuidSymbol name="guidVsPackage1Pkg" value="{c5f54698-101a-4846-84d3-dc748f9cd848}" />  
  <GuidSymbol name="guidVsPackage1CmdSet" value="{cb9dfd7f-2fcc-4a3e-aae8-f7fe30b1cfac}">  
    <IDSymbol name="MyMenuGroup" value="0x1020" />  
    <IDSymbol name="cmdidMyCommand" value="0x0100" />  
    <IDSymbol name="cmdidMyTool" value="0x0101" />  
  </GuidSymbol>  
</Symbols>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)