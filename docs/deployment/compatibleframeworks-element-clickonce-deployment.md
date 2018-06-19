---
title: '&lt;compatibleFrameworks&gt; öğesi (ClickOnce dağıtımı) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d406ecf058bf1c570b57ed8f50815cc3d9378cbe
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31560784"
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt; öğesi (ClickOnce dağıtımı)
Burada bu uygulamayı yükleyip çalıştırabileceği .NET Framework sürümleri tanımlar.  
  
> [!NOTE]
>  [MageUI.exe](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client) desteklemediği `compatibleFrameworks` bir uygulama bildirimi kaydedilirken öğesi zaten açtığı sertifika kullanarak [MageUI.exe](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client). Bunun yerine, kullanmanız gereken [Mage.exe](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<compatibleFrameworks  
      SupportUrl>   
   <framework  
      targetVersion  
      profile  
      supportedRuntime  
   />   
</ compatibleFrameworks>  
```  
  
## <a name="elements-and-attributes"></a>Öğeleri ve öznitelikleri  
 `compatibleFrameworks` Öğesi gereklidir hedefleyen dağıtım bildirimleri [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] çalışma zamanı tarafından sağlanan [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] veya sonraki bir sürümü. `compatibleFrameworks` Öğesi içeren bir veya daha fazla `framework` bu uygulamayı çalıştırabilirsiniz .NET Framework sürümlerini belirten öğeler. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Çalışma zamanı ilk uygulamanın çalışacağı kullanılabilir `framework` bu listede.  
  
 Özniteliği aşağıdaki tabloda, `compatibleFrameworks` öğesi destekler.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`S``upportUrl`|İsteğe bağlı. Tercih edilen uyumlu .NET Framework sürümü indirdiğiniz bir URL belirtir.|  
  
## <a name="framework"></a>çerçeve  
 Gerekli. Aşağıdaki tabloda öznitelikleri listeler, `framework` öğesi destekler.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`targetVersion`|Gerekli. Hedef .NET Framework sürüm numarasını belirtir.|  
|`profile`|Gerekli. Hedef .NET Framework'ün profilini belirtir.|  
|`supportedRuntime`|Gerekli. Hedef .NET Framework ile ilişkili çalışma zamanı sürüm numarasını belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterildiği kod bir `compatibleFrameworks` öğesinde bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtım bildirimi. Bu dağıtım üzerinde çalışabilir [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]. Ayrıca çalıştırılacağı [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] bir alt kümesi olduğundan [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)].  
  
```  
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
  <framework   
      targetVersion="4.0"   
      profile="Client"   
      supportedRuntime="4.0.30319" />  
</compatibleFrameworks>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Dağıtım Bildirimi](../deployment/clickonce-deployment-manifest.md)