---
title: "&#39; teki yeni kaynağındaki eklenti API sürümü 1.3 denetlemek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, what's new in API v1.3
- what's new [Visual Studio SDK], source control plug-ins
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ac92c327a5eb4e51c7e6c22a73fb331843adc99f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="what39s-new-in-the-source-control-plug-in-api-version-13"></a>&#39; teki kaynak denetimi eklenti API sürümü 1.3'deki yenilikler
Kaynak Denetim eklentisi API sürümü 1.3 daha gelişmiş denetimi sağlamak için aşağıdaki yeni işlevleri sunar.  
  
## <a name="changes"></a>Değişiklikler  
 Aşağıdaki işlevleri kaynak denetim eklentisi API sürümü 1.3 için yenidir:  
  
|İşlev|Genel Bakış|  
|--------------|--------------|  
|[SccGetExtendedCapabilities](../../extensibility/sccgetextendedcapabilities-function.md)|Raporlanacak ek yetenek BITS sağlar|  
|[SccEnumChangedFiles](../../extensibility/sccenumchangedfiles-function.md)|Yerel diskteki sürüm denetim veritabanında daha yeni sürümlerde dosyaları incelenmesi sağlar|  
|[SccQueryChanges](../../extensibility/sccquerychanges-function.md)|Belirtilen dosyalar için ad değişiklikleri (yeniden adlandırır, ekleme ve silme işlemleri) durumunu incelenmesi sağlar|  
|[SccPopulateDirList](../../extensibility/sccpopulatedirlist-function.md)|Sürüm denetimi veritabanındaki dizinler ve dosyalar incelenmesi sağlar|  
|[SccAddFilesFromSCC](../../extensibility/sccaddfilesfromscc-function.md)|Belirtilen dosyaların listesini sürüm denetimi veritabanından geçerli projeye ekler.|  
|[SccBackgroundGet](../../extensibility/sccbackgroundget-function.md)|Sessiz "Get" (kullanıcı arabirimi gösterilir) belirtilen dosyaları gerçekleştirir|  
|[SccGetUserOption](../../extensibility/sccgetuseroption-function.md)|Kullanıcıya özgü seçenekleri erişmesini sağlar|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)   
 [Kaynak Denetimi Eklentisi API Sürümü 1.2’deki Yenilikler](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)