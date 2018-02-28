---
title: "Extern öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Extern
helpviewer_keywords:
- VSCT XML schema elements, Extern
- Extern element (VSCT XML schema)
ms.assetid: db6c3ddd-a1ba-450a-897a-bb568a5377fc
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ff198f5c4b574bf3a27ae1ee8fb6ffdd482c7f71
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="extern-element"></a>Extern öğesi
Extern öğesi dış üstbilgi (.h) dosyalarının derleme zamanında .vsct dosyasıyla Birleştir başvurur. Birleştirilecek dosyalar VSCT derleyici verilen ya da başvurduğu INCLUDE yolu olmalıdır bir [INCLUDE öğesi](../extensibility/include-element.md). Dosyaları, diğer .vsct veya C++ üstbilgi dosyaları olabilir.  
  
 Üstbilgi dosyaları tanımlarında biçiminde olmalıdır "# [sembol] [değer] define" önceden tanımlı değilse değer başka bir simge olabilir. Tanımları komutu öğelerinin koşullu ifadeler kullanılabilir. Aslında kullanılan herhangi bir simge atılacak.  
  
 CommandTable öğesi  
Extern öğesi  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Extern href="stdidcmd.h" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|href|Gerekli. Üstbilgi dosyası yolu:<br /><br /> href="stdidcmd.h"|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
|dil|İsteğe bağlı. Tüm varsayılan dil [ \<dizeleri >](../extensibility/strings-element.md) komutu tablodaki öğeler:<br /><br /> Dil = "en-us"|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Yok.|Yok.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CommandTable Öğesi](../extensibility/commandtable-element.md)|Komutları temsil eden tüm öğeleri tanımlar — diğer bir deyişle, menü öğeleri, menüler, araç çubukları ve birleşik giriş kutuları —, bir VSPackage IDE sağlar.|  
  
## <a name="example"></a>Örnek  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-  
  18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <Extern href="C:\VSCore\vscommon\inc\vsshlids.h"/>  
    ...  
  <Commands package="guidMyPackage">  
</CommandTable>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Komutlar, Menüler ve Araç Çubukları](../extensibility/internals/commands-menus-and-toolbars.md)