---
title: VSIXLanguagePack öğesi (VSIX Dil Paketi Şeması) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 767f5c22-8b87-49ca-92aa-a7a3f026469f
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf8e55e38ecf16577482955c30ea95c5a5980087
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687900"
---
# <a name="vsixlanguagepack-element-vsix-language-pack-schema"></a>VSIXLanguagePack öğesi (VSIX Dil Paketi Şeması)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [VSIXLanguagePack öğesi (VSIX Dil Paketi Şeması)](https://docs.microsoft.com/visualstudio/extensibility/vsixlanguagepack-element-vsix-language-pack-schema).  
  
Gerekli. VSIX Dil Paketi için kök öğe sağlar. VSIX Dil Paketi, bir VSIX paketi için yerelleştirilmiş yükleme bilgilerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<VSIXLanguagePack>  
  <LocalizedName>...</LocalizedName>  
  <LocalizedDescription>...</LocalizedDescription>  
  <MoreInfoURL>...</MoreInfoURL>  
  <License>...</License>  
</VSIXLanguagePack>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`xmlns`|VSIX Dil Paketi şeması tanımlandığı XML ad alanı.|  
  
## <a name="xmlns-attribute"></a>xmlns özniteliğinin  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`http://schemas.microsoft.com/developer/vsx-schema-lp/2010`|Gerekli. Dil paketleri şemasını tanımlayan dosyasının konumu.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[LocalizedName öğesi](../extensibility/localizedname-element-vsix-language-pack-schema.md)|Gerekli. Uzantının yüklenmesini yerelleştirilmiş adı.|  
|[LocalizedDescription öğesi](../extensibility/localizeddescription-element-vsix-language-pack-schema.md)|Gerekli. Yerelleştirilmiş açıklama uzantısının yüklenmesi.|  
|[MoreInfoURL öğesi](../extensibility/moreinfourl-element-vsix-language-pack-schema.md)|İsteğe bağlı. Yerelleştirilmiş uzantısı hakkında bilgi almak için bir bağlantı.|  
|[Lisans öğesi](../extensibility/license-element-vsix-language-pack-schema.md)|İsteğe bağlı. Uzantının lisans dosyası yerelleştirilmiş bir sürümünü yolu.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Yok.||  
  
## <a name="element-information"></a>Öğe Bilgisi  
  
|||  
|-|-|  
|Ad Alanı|http://schemas.microsoft.com/developer/vsx-schema-lp/2010|  
|Şema adı|VSIX Dil Paketi şeması|  
|Doğrulama dosyası|VSIXLanguagePackSchema.xsd|  
|Boş olabilir.|Hayır|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSX dil paketi Şeması Başvurusu](../extensibility/vsx-language-pack-schema-reference.md)   
 [VSIX paketlerini yerelleştirme](../extensibility/localizing-vsix-packages.md)   
 [VSIX Uzantı Şeması 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)

