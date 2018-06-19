---
title: Idebugdocumentprovider arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentProvider interface
ms.assetid: 36510acf-1ef9-479c-a430-d3f09502f82c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 262794718e238068cfd9a8e3fae5161b9fe8cc54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794030"
---
# <a name="idebugdocumentprovider-interface"></a>IDebugDocumentProvider Arabirimi
İsteğe bağlı bir belge başlatmasını sağlar.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir belge örneği için bu dolaylı anlamına gelir:  
  
-   Gerektiğinde yüklenecek belgenin sağlar.  
  
-   Hata ayıklayıcı IDE içinde dahil edilmek üzere belge nesnesi sağlar.  
  
-   Aynı belge nesnesi erişmek için birden çok yol sağlar.  
  
 Bu etkin belgeyi kendi sağlayıcıdan ayırır ve ek çalışma zamanı, bağlam bilgilerini taşımak sağlayıcı sağlar.  
  
 Kaynağından devralındı yöntemleri yanı sıra `IDebugDocumentInfo`, `IDebugDocumentProvider` arabirimi aşağıdaki yöntemleri sunar.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDebugDocumentProvider::GetDocument](../../winscript/reference/idebugdocumentprovider-getdocument.md)|Belge zaten yoksa, örneğinin oluşturulması neden olur.|