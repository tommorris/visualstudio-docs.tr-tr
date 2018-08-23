---
title: Üst öğe | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Parent
- Parent element (VSCT XML schema)
ms.assetid: e4624ac8-1b9a-4940-910a-528a661cefad
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b16aa3e3d6542130b449196de92e795e464ab0e9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684341"
---
# <a name="parent-element"></a>Üst Öğe
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [üst öğe](https://docs.microsoft.com/visualstudio/extensibility/parent-element).  
  
Bir düğme veya birleşik giriş kutusunun üst yalnızca bir grup olabilir. Bir menü veya grubun üst herhangi bir menü veya grup olabilir. İçinde bir [CommandPlacement öğesi](../extensibility/commandplacement-element.md), bu öğe gereklidir; diğer tüm durumlarda isteğe bağlıdır. Bu öğe atlanırsa, üst `Group_Undefined:0` kapsanan.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Parent guid="guidMyCommandSet" id="MyParentGroupOrMenu" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. GUID GUID/kimliği komut tanımlayıcısı.|  
|kimlik|Gerekli. Kimliği GUID/kimliği komut tanımlayıcısı.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CommandTable Öğesi](../extensibility/commandtable-element.md)|VSPackage sağlayan komutlar tümleşik geliştirme ortamı (IDE) temsil eden tüm öğeleri tanımlar. Örneğin, menü öğeleri, menüler, araç çubukları ve birleşik giriş kutuları.|  
|[Buttons Öğesi](../extensibility/buttons-element.md)|Grupları [Button öğesi](../extensibility/button-element.md) öğeleri.|  
|[Menus Öğesi](../extensibility/menus-element.md)|VSPackage'ı uygulayan tüm menüleri tanımlar.|  
|[Groups Öğesi](../extensibility/groups-element.md)|VSPackage komut gruplarını tanımlar girişleri içerir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

