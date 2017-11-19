---
title: "CommandTable öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CommandTable
helpviewer_keywords:
- CommandTable element (VSCT XML schema)
- VSCT XML schema elements, CommandTable
ms.assetid: 15c38159-660a-4ef4-9643-aa6fcfca82a9
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4f1a906f545dcdbaefca7f5a38824a1f3259c97
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="commandtable-element"></a>CommandTable öğesi
CommandTable .vsct dosyasının kök öğesinin ' dir. Bu gerçek düzeni ve bir VSPackage IDE sağlar komutları türünü tanımlayan dosyasıdır. Komutları menü öğeleri, menüler, araç çubukları ve birleşik giriş kutuları içerebilir. Daha fazla bilgi için bkz: [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema" >  
  <Extern>... </Extern>  
  <Include>... </Include>  
  <Define>... </Define>  
  <Commands>... </Commands>  
  <CommandPlacements>... </CommandPlacements>  
  <VisibilityConstraints>... </VisibilityConstraints>  
  <KeyBindings>... </KeyBindings>  
  <UsedCommands... </UsedCommands>  
  <Symbols>... </Symbols>  
</CommandTable>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|xmlns|Gerekli. XML ad alanları:<br /><br /> xmlns = "http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable"<br /><br /> xmlns:XS "http://www.w3.org/2001/XMLSchema" =|  
|dil|İsteğe bağlı. Tüm varsayılan dili belirtmek için dil özniteliği kullanılabilir \<dizeleri > komutu tablodaki öğeler.  Dil belirtilmezse, geçerli işlemin dilinin kullanılacak:<br /><br /> Dil = "en-us"|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Extern öğesi](../extensibility/extern-element.md)|İsteğe bağlı. Derleyicinin önişlemci yönergeleri içerir.|  
|[Öğe dahil](../extensibility/include-element.md)|İsteğe bağlı. Derleme dahil etmek için herhangi bir dosya yolları içerir.|  
|[Öğe tanımlayın](../extensibility/define-element.md)|İsteğe bağlı. Verilen ad ve değer bir simge tanımlar.|  
|[Komutları öğesi](../extensibility/commands-element.md)|İsteğe bağlı. Tüm komutlar için tüm diğer öğeleri içerir VSPackage tanımlama üst öğesi.|  
|[CommandPlacements öğesi](../extensibility/commandplacements-element.md)|İsteğe bağlı. Komut çubuğunda komutları yerleştirilecek nerede tanımlar.|  
|[VisibilityConstraints öğesi](../extensibility/visibilityconstraints-element.md)|İsteğe bağlı. Komutlar ve araç çubuklarını statik görünürlüğünü belirler.|  
|[Taşıyan öğesi](../extensibility/keybindings-element.md)|İsteğe bağlı. Kısayol tuş birleşimleri, komutları belirtir.|  
|[UsedCommands öğesi](../extensibility/usedcommands-element.md)|İsteğe bağlı. İsteğe bağlı olarak ilk olarak diğer VSPackages tarafından desteklenen işlevleri kendi sürümü uygulamak bir VSPackage sağlar.|  
|[Simgeler öğesi](http://msdn.microsoft.com/en-us/f2ddd0aa-c3dd-439e-834d-28f136a27ffa)|İsteğe bağlı. Derleyici için herhangi bir simge verilerini--GUID'ler, kimlikleri ve benzeri--içerir.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Yok.||  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)