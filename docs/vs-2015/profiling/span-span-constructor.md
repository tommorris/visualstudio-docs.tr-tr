---
title: span::span Oluşturucusu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::span::span
helpviewer_keywords:
- Concurrency::diagnostic::span constructor
ms.assetid: 8b5578aa-5e5c-4ac7-87c7-ce87c4246e2c
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9cd7d787c136f6811fe6bc4c20fe24f736b29e4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686990"
---
# <a name="spanspan-constructor"></a>span::span Oluşturucusu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [span::span Oluşturucusu](https://docs.microsoft.com/visualstudio/profiling/span-span-constructor).  
  
Yeni bir örneğini başlatır `span` sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
span(  
   const marker_series& _Series,  
   _In_ LPCTSTR _Format,  
   ...  
);  
span(  
   const marker_series& _Series,  
   marker_importance _Importance,  
   _In_ LPCTSTR _Format,  
   ...  
);  
span(  
   const marker_series& _Series,  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
span(  
   const marker_series& _Series,  
   marker_importance _Importance,  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Series`  
 Geçerli işaret serisi bağlamı.  
  
 `_Format`  
 Bağımsız değişken listesindeki nesnelere karşılık gelen sıfır veya daha fazla biçim öğeleri ile karıştırılmış, metin içeren bir bileşik biçimlendirme dizesi.  
  
 `_Importance`  
 Önem düzeyi.  
  
 `_Category`  
 Kategori.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** cvmarkersobj.h  
  
 **Namespace:** Concurrency::diagnostic
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [span Sınıfı](../profiling/span-class.md)



