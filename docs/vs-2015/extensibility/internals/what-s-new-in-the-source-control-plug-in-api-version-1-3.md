---
title: Hangi&#39;da kaynak denetimi eklentisi API sürümü 1.3 | Microsoft Docs
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
- source control plug-ins, what's new in API v1.3
- what's new [Visual Studio SDK], source control plug-ins
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d5e8e5fd761cbd8c1baf2b75160010f19a8430cc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673758"
---
# <a name="what39s-new-in-the-source-control-plug-in-api-version-13"></a>Hangi&#39;da kaynak denetimi eklentisi API sürümü 1.3
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ne&#39;kaynak denetimi eklentisi API sürümü 1.3 yeni s](https://docs.microsoft.com/visualstudio/extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3).  
  
Kaynak Denetimi Eklentisi API sürümü 1.3 daha gelişmiş bir denetim sağlamak için aşağıdaki yeni işlevler sunar.  
  
## <a name="changes"></a>Değişiklikler  
 Aşağıdaki işlevleri, kaynak denetimi eklentisi API sürümü 1.3 için yenidir:  
  
|İşlev|Genel Bakış|  
|--------------|--------------|  
|[SccGetExtendedCapabilities](../../extensibility/sccgetextendedcapabilities-function.md)|Ek özellik BITS bildirilmesini sağlar.|  
|[SccEnumChangedFiles](../../extensibility/sccenumchangedfiles-function.md)|Sürüm denetimi veritabanı yerel diskteki yeni sürümlere sahip dosyalar incelenmesi sağlar|  
|[SccQueryChanges](../../extensibility/sccquerychanges-function.md)|Ad değişiklikleri (yeniden adlandırma, ekleme ve silme işlemleri) durumunu incelenmesi için belirtilen dosyaları sağlar.|  
|[SccPopulateDirList](../../extensibility/sccpopulatedirlist-function.md)|Dizinleri ve dosyaları incelenmesi sürüm denetim veritabanındaki sağlar|  
|[SccAddFilesFromSCC](../../extensibility/sccaddfilesfromscc-function.md)|Belirtilen dosyaların listesini sürüm denetim veritabanından geçerli projeye ekler.|  
|[SccBackgroundGet](../../extensibility/sccbackgroundget-function.md)|Sessiz "Al" (kullanıcı arabirimi gösterilir) belirtilen dosyaları gerçekleştirir|  
|[SccGetUserOption](../../extensibility/sccgetuseroption-function.md)|Kullanıcıya özgü seçenekleri erişmesini sağlar|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışmaya başlama](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)   
 [Kaynak Denetimi Eklentisi API Sürümü 1.2’deki Yenilikler](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)

