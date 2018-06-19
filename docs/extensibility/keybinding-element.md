---
title: KeyBinding öğesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, KeyBindings
- KeyBinding element (VSCT XML schema)
ms.assetid: e55a1098-15df-42a9-9f87-e3a99cf437dd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 226a5913cbaa151689a886dc88986f7de8cc29f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139175"
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
