---
title: ■ ButtonText öğesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2fca0fbb22bf51353eeaa64f519face53bfb23c8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="buttontext-element"></a>■ ButtonText öğesi
Bu alan çeşitli menülerde görüntülenen metni belirtmenize olanak sağlar. Varsayılan olarak, `ButtonText` öğe menü denetleyicileri görüntülenir. `ButtonText` Öğesi bir metin alanları boş ise varsayılan de olur. `ButtonText` Diğer metin alanları belirtilmese bile öğesi boş olamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<ButtonText>My Command</ButtonText>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Strings Öğesi](../extensibility/strings-element.md)|Metin öğeleri gibi gruplar `ButtonText` ve `CommandName`.|  
  
## <a name="text-value"></a>Metin Değeri  
 Metin değerini `ButtonText` öğesi menü öğeleri, birleşik ve görünür metne sahip diğer kullanıcı arabirimi (UI) öğeleri için görüntülenen metin sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)