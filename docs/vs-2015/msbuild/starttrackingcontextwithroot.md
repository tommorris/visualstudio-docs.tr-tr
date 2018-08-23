---
title: StartTrackingContextWithRoot | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- StartTrackingContextWithRoot
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2c713b9f2b285bee56303b7d2142837d9afc62b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634107"
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [StartTrackingContextWithRoot](https://docs.microsoft.com/visualstudio/msbuild/starttrackingcontextwithroot).  
  
  
Bir kök işaret belirten bir yanıt dosyası kullanarak bir izleme bağlamına başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `intermediateDirectory`  
 İzleme günlüğü depolanacağı dizin.  
  
 [in] `taskName`  
 İzleme bağlamı tanımlar. Bu ad, günlük dosyası adı oluşturmak için kullanılır.  
  
 [in] `rootMarkerResponseFile`  
 Bir kök işaret içeren bir yanıt dosyasının yol adı. Kök adı, tüm izleme için bir bağlam birlikte gruplandırmak için kullanılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 [HRESULT] (<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->) [başarılı] ile (<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) izleme bağlamına oluşturulduysa biti ayarlanmamış.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** FileTracker.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)



