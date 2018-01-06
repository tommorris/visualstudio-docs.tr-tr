---
title: "Komutları öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Commands
helpviewer_keywords:
- Commands element (VSCT XML schema)
- VSCT XML schema elements, Commands
ms.assetid: 47cf16a5-d78b-452e-86f6-b5893856dddf
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7c5cce390ad786ad530153e1850850509990b039
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="commands-element"></a>Komutları öğesi
VSPackage araç çubuğundaki komutları koleksiyonunu temsil eder. Koleksiyon en fazla beş alt bölümlerde, aşağıdaki gibi olabilir: menüleri, gruplar, düğmeleri, birleşik ve bit eşlemler.  
  
 Her alt alt öğe, örneğin, \<menü >, bir GUID ve sayısal tanımlayıcı çifti benzersiz komut kimliği tarafından tanımlanır. GUID "komut kümesini" tanımlar ve mantıksal olarak ilgili komutları gruplandırmak için kullanılır. VSPackage diğer VSPackages tarafından tanımlanan komut kimlikleri çakışmaları önlemek için kendi komutunu tanımlamanız gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Commands package="GuidMyPackage" >  
  <Menus>... </Menus>  
  <Groups>... </Groups>  
  <Buttons>... </Buttons>  
  <Combos>... </Combos>  
  <Bitmaps>... </Bitmaps>  
</Commands>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Paket|Komutları sağlar VSPackage tanımlayan bir GUID.<br /><br /> Örneğin, paket "guidVsPackage1Pkg" =.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Menus Öğesi](../extensibility/menus-element.md)|Bir VSPackage uygulayan tüm menüleri tanımlar.|  
|[Groups Öğesi](../extensibility/groups-element.md)|Bir VSPackage komut gruplarını tanımlamak girdiler içeriyor.|  
|[Buttons Öğesi](../extensibility/buttons-element.md)|Düğme öğeleri gruplandırır.|  
|[Bitmaps Öğesi](../extensibility/bitmaps-element.md)|Bit eşlem öğeleri gruplandırır.|  
|[Combos Öğesi](../extensibility/combos-element.md)|Birleşik giriş öğeleri gruplandırır.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CommandTable Öğesi](../extensibility/commandtable-element.md)|Bir VSPackage IDE sağlar komutları temsil eden tüm öğeleri tanımlar. Menü öğeleri, menüler, araç çubukları ve birleşik giriş kutuları Bunun olası öğelerdir.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösteren bir [komutları öğesi](../extensibility/commands-element.md).  
  
```  
<Commands package="guidMyPackage">  
    <Menus>  
      <Menu Condition="'%(DEBUG)' != 'true'"   
        guid="cmdSetGuidMyProductCommands" id="menuIDMainMenu"   
        priority="0x0000" type="Menu">  
        <Annotation>  
          <Documentation>this is an annotation</Documentation>  
          <AppInfo>  
            <CustomData>  
              <CustomSubElement>Some data</CustomSubElement>  
            </CustomData>  
          </AppInfo>  
        </Annotation>  
        <CommandFlag>AlwaysCreate</CommandFlag>  
        <Strings>  
          <ButtonText>MainMenu</ButtonText>  
        </Strings>  
      </Menu>  
  </Menus>  
<Commands>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri VSPackages nasıl eklenir](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Komutlar, Menüler ve Araç Çubukları](../extensibility/internals/commands-menus-and-toolbars.md)