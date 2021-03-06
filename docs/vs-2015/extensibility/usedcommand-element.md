---
title: UsedCommand öğesi | Microsoft Docs
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
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 78ab46c4524bb25563d407514aa0590e75feffaa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697337"
---
# <a name="usedcommand-element"></a>UsedCommand Öğesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [UsedCommand öğesi](https://docs.microsoft.com/visualstudio/extensibility/usedcommand-element).  
  
VSPackage'ı başka bir .vsct dosyası içinde tanımlanan bir komutuna erişmek üzere etkinleştirir. Örneğin, standart, VSPackage'ı kullanıyorsa, **kopyalama** tanımlanan komutu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] shell ekleyebileceğiniz komut bir menü veya araç yeniden uygulamadan.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|GUID|Gerekli. Komut tanımlayan GUID kimliği çiftinin GUID.|  
|kimlik|Gerekli. Komut tanımlayan GUID kimliği çifti kimliği.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|Yok.||  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[UsedCommands Öğesi](../extensibility/usedcommands-element.md)|UsedCommand öğeleri gruplandırır ve diğer UsedCommands gruplandırmaları.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir komutu ekleyerek `<UsedCommands>` öğesi, bir VSPackage'ı bilgilendirir [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ortam VSPackage komutu gerektirir. Eklemeniz bir `<UsedCommand>` paketinizi gerektiren herhangi bir komutun öğesi, değil tüm sürümleri ve yapılandırmaları Visual Studio'nun içinde bulunabilir. Paketiniz Visual C++ için belirli bir komut çağırırsa, eklemediğiniz sürece Örneğin, komut Visual Web Developer kullanıcılara kullanılamaz bir `<UsedCommand>` komutu için öğesi.  
  
## <a name="example"></a>Örnek  
  
```  
<UsedCommands>  
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>  
</UsedCommands>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [UsedCommands öğesi](../extensibility/usedcommands-element.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

