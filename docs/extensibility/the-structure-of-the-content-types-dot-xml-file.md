---
title: '[Content_types] .xml dosyasının yapısı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- content_types
- content types
- opc
- vsix
ms.assetid: 9c399598-b9fa-4da7-84b5-defbf82e9335
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 38e65f484411abcfb2acd78b124b77ff3f2c49cd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144573"
---
# <a name="the-structure-of-the-contenttypesxml-file"></a>[Content_types] .xml dosyasının yapısı
VSIX paketi içerik türleri hakkında bilgi içerir. Paketi yüklemek için Visual Studio [Content_Types] .xml dosyası kullanır, ancak dosya yüklemez.  
  
> [!NOTE]
>  Bu konu, VSIX paketlerinde kullanılan [Content_Type] .xml dosyaları uygulanır [Content_Types] .xml dosya türü bir parçası olsa da *açık paketleme kuralları (OPC)* standart. Daha fazla bilgi için bkz: [OPC: A yeni standart için paketleme verilerinizi](http://go.microsoft.com/fwlink/?LinkID=148207) MSDN Web sitesinde.  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Aşağıdaki bölümlerde, kök öğe ve öznitelikler ve alt öğeleri açıklanmaktadır.  
  
### <a name="root-element"></a>Kök öğesi  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`Types`|VSIX paketi dosya türlerinde listeleme alt öğeleri içerir.|  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Xmlns`|(Gerekli) Bu [Content_Types] .xml dosyası için kullanılan şema konumu.|  
  
### <a name="attribute-name-attribute"></a>{Öznitelik adı} Özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|http://schemas.openformats.org/package/2006/content-types|İçerik türleri şema konumu.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 `Types` Öğesi, herhangi bir sayıda içerebilir `Default` öğeleri.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`Default`|Bir içerik türü VSIX paketi açıklar. Her dosya türü paketindeki kendi olmalıdır `Default` öğesi.|  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Extension`|VSIX paketi bir dosyanın dosya adı uzantısı.|  
|`ContentType`|Dosya adı uzantısıyla ilişkili içerik türü açıklanmaktadır.|  
  
### <a name="attribute-name-attribute"></a>{Öznitelik adı} Özniteliği  
 Visual Studio tanıdığı aşağıdaki `ContentType` ilişkili değerleri `Extension` türleri.  
  
|Uzantısı|ContentType|  
|---------------|-----------------|  
|txt|Metin/düz|  
|pkgdef|Metin/düz|  
|XML|metin/xml|  
|vsixmanifest|metin/xml|  
|htm veya html|metin/html|  
|RTF|Uygulama/rtf|  
|PDF|Uygulama/pdf|  
|gif|Görüntü/gif|  
|JPG veya jpeg|Görüntü/jpg|  
|TIFF|Görüntü/TIFF|  
|vsix|Uygulama/posta|  
|Zip|Uygulama/posta|  
|dll|application/octet-stream|  
|diğer tüm dosya türleri|application/octet-stream|  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki [Content_Types] .xml dosyası tipik VSIX paketi açıklar.  
  
### <a name="code"></a>Kod  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types">  
    <Default Extension="vsixmanifest" ContentType="text/xml" />   
    <Default Extension="dll" ContentType="application/octet-stream" />   
    <Default Extension="png" ContentType="application/octet-stream" />   
    <Default Extension="txt" ContentType="text/plain" />   
    <Default Extension="pkgdef" ContentType="text/plain" />   
</Types>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSIX paketi anatomisi](../extensibility/anatomy-of-a-vsix-package.md)   
 [VSIX uzantı şema 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [OPC: Verilerinizi paketlemek için yeni bir standart](http://go.microsoft.com/fwlink/?LinkID=148207)