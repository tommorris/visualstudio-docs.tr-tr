---
title: Birleşik giriş öğesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Combos element (VSCT XML schema)
- VSCT XML schema elements, Combos
ms.assetid: 392e3063-f0a0-4130-9583-23bd2aa3fa36
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ca91102467755610144e4d24405e89ace5a013b7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100945"
---
# <a name="combo-element"></a>Birleşik giriş öğesi
Açılan kutuda görünür komutları tanımlar. Birleşik giriş kutuları, dört tür vardır: aşağı açılan, DynamicCombo, IndexCombo ve MRUCombo.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<combo guid="guidMyCommandSet" id="MyCommand" defaultWidth="20" idCommandList="MyCommandListID" priority="0x102" type="DropDownCombo">  
  <Parent>... </Parent  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</combo>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. GUID/kimliği komut tanımlayıcı GUID.|  
|kimlik|Gerekli. GUID/kimliği komut tanımlayıcısı kimliği.|  
|defaultWidth|Gerekli. Birleşik giriş kutusu için bir piksel genişliği belirten bir tamsayı.|  
|idCommandList|Gerekli. Etkin komut hedef açılan kutusunda görüntülenecek öğeleri listesini almak için gönderilen bir kimliği. Kimliği denetimi aynı GUID kapsamı olacaktır.|  
|önceliği|İsteğe bağlı. Önceliğini belirten bir sayısal değer.|  
|türü|İsteğe bağlı. Düğmenin türü belirten bir numaralandırılmış değeri.<br /><br /> Verilen değil, düğmesini kullanır.<br /><br /> Aşağı açılan<br /> Bu birleşik giriş kutusu için içerik doldurma için VSPackage sorumludur. Kullanıcı hiçbir şey bu açılan metin kutusuna yazamazsınız.<br /><br /> DynamicCombo<br /> Bu birleşik giriş kutusu içerikte doldurmak için VSPackage sorumludur. Kullanıcı bu birleşik düzenleyebilir ve öğeleri de seçin.<br /><br /> IndexCombo<br /> DynamicCombo onun dışında aynı metin yerine öğenin dizinini başlatır.<br /><br /> MRUCombo<br /> VSPackage adına tümleşik geliştirme ortamı (IDE) tarafından doldurulur.  Kullanıcı Bu kutudaki düzenleyebilirsiniz. Birleşik giriş kutusu başına son 16 girişi kadar IDE hatırlıyor.<br /><br /> Kullanıcı bir şey açılan kutuda seçer veya yeni bir şey girerse, IDE uygun VSPackage size bildirir.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Üst|İsteğe bağlı. Düğmenin üst öğesi.|  
|CommandFlag|Gerekli. Bkz: [komut bayrağı öğesi](../extensibility/command-flag-element.md). Düğme için geçerli CommandFlag değerler aşağıdaki gibidir.<br /><br /> -CaseSensitive<br /><br /> -CommandWellOnly<br /><br /> -DefaultDisabled<br /><br /> -DefaultInvisible<br /><br /> -DynamicVisibility<br /><br /> -Süzme<br /><br /> -IconAndText<br /><br /> -NoAutoComplete<br /><br /> -NoButtonCustomize<br /><br /> -NoCustomize<br /><br /> -NoKeyCustomize<br /><br /> -StretchHorizontally|  
|Dizeler|Gerekli. Bkz: [dizeleri öğesi](../extensibility/strings-element.md). Alt ■ ButtonText öğesi tanımlanmış olması gerekir.|  
|Ek Açıklama|İsteğe bağlı bir açıklama.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Commands Öğesi](../extensibility/commands-element.md)|VSPackage araç çubuğundaki komutları koleksiyonunu temsil eder.|  
  
## <a name="example"></a>Örnek  
  
```  
<Combo guid="guidWidgetPackage" id="cmdidInsertOptions"  
  defaultWidth="100" idCommandList="cmdidGetInsertOptionsList">  
  <CommandFlag>DynamicVisibility</CommandFlag>  
  <Strings>  
    <ButtonText>Select Insert Options</ButtonText>  
  </Strings>  
</Combo>  
  
<Combo guid="guidWidgetPackage" id="cmdidInsertOptions"  
  priority="0x0500" type="DropDownCombo" defaultWidth="100"  
  idCommandList="cmdidGetInsertOptionsList">  
  <Parent guid="cmdSetGuidWidgetCommands" id="groupIDFileEdit">  
  <CommandFlag>DynamicVisibility</CommandFlag>  
  <Strings>  
    <ButtonText>Select Insert Options</ButtonText>  
  </Strings>  
</Combo>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)