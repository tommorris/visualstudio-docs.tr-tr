---
title: "Button öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Buttons element (VSCT XML schema)
- VSCT XML schema elements, Buttons
ms.assetid: 96dccf51-2b00-4700-9d28-924b34c21ecd
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bd630a2fed94604cb91dc3af7e46f96269f75ad0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="button-element"></a>Düğme öğesi
Kullanıcı ile etkileşim kurabilen bir öğeyi tanımlar. Düğmeleri farklı türde olabilir: düğme, MenuButton ve SplitDropDown.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Button guid="guidMyCommandSet" id="MyCommand" priority="0x102" type="button">  
  <Parent>... </Parent>  
  <Icon>... </Icon>  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</Button>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. GUID/kimliği komut tanımlayıcı GUID.|  
|kimlik|Gerekli. GUID/kimliği komut tanımlayıcısı kimliği.|  
|önceliği|İsteğe bağlı. Önceliğini belirten bir sayısal değer.|  
|türü|İsteğe bağlı. Düğme türünü belirten bir numaralandırılmış değeri.<br /><br /> Verilen değil, düğmesini kullanır.<br /><br /> Düğme<br /> Araç çubuklarında (genellikle bir simge düğmesi olarak), menüleri ve bağlam menülerini görünür standart komutu.<br /><br /> MenuButton<br /> Komut yürütme değil, ancak başka bir menü üreten bir menü öğesi.<br /><br /> SplitDropDown<br /> Microsoft Word standart araç çubuğundaki geri alma ve yineleme düğmeleri gibi denetler.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Üst öğesi](../extensibility/parent-element.md)|İsteğe bağlı. Düğmenin üst öğesi.|  
|[Icon öğesi](../extensibility/icon-element.md)|İsteğe bağlı. İlişkili düğme simgesi.|  
|[Komut bayrağı öğesi](../extensibility/command-flag-element.md)|Gerekli. Düğme için geçerli CommandFlag değerler aşağıdaki gibidir.<br /><br /> -AllowParams<br /><br /> -CommandWellOnly<br /><br /> -DefaultDisabled<br /><br /> -DefaultInvisible<br /><br /> -DontCache<br /><br /> -DynamicItemStart<br /><br /> -DynamicVisibility<br /><br /> -FixMenuController<br /><br /> -IconAndText<br /><br /> -NoButtonCustomize<br /><br /> -NoCustomize<br /><br /> -NoKeyCustomize<br /><br /> -NoShowOnMenuController<br /><br /> -PICT<br /><br /> -PostExec<br /><br /> -ProfferedCmd<br /><br /> -RouteToDocs<br /><br /> -TextCascadeUseBtn<br /><br /> -TextMenuUseButton<br /><br /> -TextChanges<br /><br /> -TextChangesButton<br /><br /> -TextContextUseButton<br /><br /> -TextMenuCtrlUseMenu<br /><br /> -TextMenuUseButton<br /><br /> -TextOnly|  
|[Dizeleri öğesi](../extensibility/strings-element.md)|Gerekli. Alt [■ ButtonText öğesi](../extensibility/buttontext-element.md) tanımlanması gerekir.|  
|Ek Açıklama|İsteğe bağlı bir açıklama.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Düğme öğesi](../extensibility/buttons-element.md)|Düğme öğeleri gruplandırır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir düğme .vsct dosyasında tanımlar.  

 ```xml
<Button guid="guidMenuTextCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
    <Parent guid="guidMenuTextCmdSet" id="MyMenuGroup" />
    <Icon guid="guidImages" id="bmpPic1" />
    <CommandFlag>TextChanges</CommandFlag>
    <Strings>
          <CommandName>cmdidMyCommand</CommandName>
          <ButtonText>My Command name</ButtonText>
    </Strings>
</Button>
 ```
 
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)