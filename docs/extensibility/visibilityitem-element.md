---
title: "VisibilityItem öğesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VisibilityItem element (VSCT XML schema)
- VSCT XML schema elements, VisibilityItem
ms.assetid: 0932f551-972d-4194-84bb-426e3e4375e4
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: db041f839e9b7e8ad3268175829ecfee9380e736
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visibilityitem-element"></a>VisibilityItem öğesi
`VisibilityItem` Öğesi komutlar ve araç çubuklarını statik görünürlüğünü belirler. Her giriş, bir komut veya menü ve ayrıca bir ilişkili komut UI bağlamı tanımlar. Visual Studio komutları, menüleri ve araç çubukları ve bunların görünürlük tanımlamadan VSPackages yüklemeden algılar. IDE kullanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> komutu UI bağlam etkin olup olmadığını belirlemek amacıyla yöntemi.  
  
 VSPackage yüklendikten sonra Visual Studio tarafından VSPackage belirlenecek komutu görünürlük bekliyor yerine `VisibilityItem`. Komutunuzu 's görünürlük belirlemek için ya da uygulayabileceğiniz <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> olay işleyicisi veya <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> komutunuzu nasıl uyguladık bağlı olarak yöntemi.  
  
 Bir komut veya sahip menü bir `VisibilityItem` öğe yalnızca ilişkili bağlam etkin olduğunda görüntülenir. Her komut bağlam bileşimi için bir giriş ekleyerek bir veya daha fazla komut UI bağlamlarla tek bir komut, menü veya araç ilişkilendirebilirsiniz. Bir komut veya menü birden çok komut UI bağlamları ile ilişkili ise, ilişkili komut UI bağlamları herhangi biri etkin olduğunda sonra komut veya menü görünür olur.  
  
 `VisibilityItem` Öğesi uygulandığı yalnızca komutları, menüleri ve araç çubuklarını, grupları uygulanmaz. İlgili olmayan bir öğe `VisibilityItem` öğesi, kendi üst menü etkin olduğunda görülebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<VisibilityItem  
  guid ="="cmdGuidMyProductCommands"  
  id=="cmdidAddWidget"  
  context="guidNotViewSourceMode"/>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. GUID/kimliği komut tanımlayıcı GUID.|  
|kimlik|Gerekli. GUID/kimliği komut tanımlayıcısı kimliği.|  
|bağlam|Gerekli. Komut görülebilir UI bağlamı.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[VisibilityConstraints öğesi](../extensibility/visibilityconstraints-element.md)|`VisibilityConstraints` Öğesi grupları komutları ve araç çubuklarını statik görünürlüğünü belirler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Standart Visual Studio kullanıcı Arabirimi bağlamları tanımlanan *Visual Studio SDK yükleme yolu*\VisualStudioIntegration\Common\Inc\vsshlids.h dosyasında da olarak <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids> ve <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> sınıfları. UI bağlamları daha eksiksiz bir kümesini tanımlanan <xref:Microsoft.VisualStudio.VSConstants> sınıfı.  
  
## <a name="example"></a>Örnek  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>   
 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>   
 <xref:Microsoft.VisualStudio.VSConstants>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>   
 [VisibilityConstraints öğesi](../extensibility/visibilityconstraints-element.md)   
 [Visual Studio komut tablosu (. Vsct) dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)