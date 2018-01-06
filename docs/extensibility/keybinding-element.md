---
title: "KeyBinding öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, KeyBindings
- KeyBinding element (VSCT XML schema)
ms.assetid: e55a1098-15df-42a9-9f87-e3a99cf437dd
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2019a34e55148007cd75df12212bd4b0a897159c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="keybinding-element"></a>KeyBinding öğesi
KeyBinding öğesi komutları için klavye kısayolları belirtir.  
  
 Komutları tek ve çift anahtar bağlamaları ilişkili olabilir. Tek bir anahtar bağlaması için CTRL + S örneğidir **kaydetmek** komutu. Bir komut tetiklemek için iki ardışık tuş bileşimlerini anahtar çift bağlamalarını gerektirir. CTRL + K, yer işareti ayarlamak için CTRL + K bir çift anahtar bağlama örneğidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Keybinding guid="MyGuid" id="MyId" Editor="MyEditor" key1="B" key2="x" mod1="Control" mod2="Alt" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli.|  
|kimlik|Gerekli.|  
|düzenleyici|Gerekli. GUID Düzenleyicisi bu klavye kısayolunu active olacağı düzenleme bağlamını gösterir. Genel bağlama kapsam "guidVSStd97" değerdir.|  
|key1|Gerekli. Geçerli değerler arasında tüm typable alfasayısal ve iki basamaklı onaltılık değerler 0 x öncesinde ve [VK_constants](https://msdn.microsoft.com/en-us/library/windows/desktop/dd375731.aspx).|  
|Değişiklik1|İsteğe bağlı. Herhangi bir bileşimini CTRL, ALT ve üst karakter boşlukla ayrılmış.|  
|key2|İsteğe bağlı. Geçerli değerler arasında tüm typable alfasayısal ve iki basamaklı onaltılık değerler 0 x öncesinde ve [VK_constants](https://msdn.microsoft.com/en-us/library/windows/desktop/dd375731.aspx).|  
|mod2|İsteğe bağlı. Herhangi bir bileşimini CTRL, ALT ve üst karakter boşlukla ayrılmış.|  
|öykünücüsü|İsteğe bağlı.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Üst||  
|Ek Açıklama||  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[KeyBindings Öğesi](../extensibility/keybindings-element.md)|Grupları KeyBinding öğeleri ve diğer taşıyan gruplandırmaları.|  
  
## <a name="example"></a>Örnek  
  
```  
<KeyBindings>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidUpdateWidget"   
    editor="guidWidgetEditor" key1="VK_F5"/>  
  <KeyBinding guid="guidWidgetPackage" id="cmdidRunWidget"   
    editor="guidWidgetEditor" key1="VK_F5" mod1="Control"/>  
</KeyBindings>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşıyan öğesi](../extensibility/keybindings-element.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
