---
title: "Kopyalama (programlı yakalama) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0b8cb397afd4f1ba58dca30b4314471b4647576
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="copy-programmatic-capture"></a>Kopyalama (Programlı Yakalama)
Etkin Grafikler (.vsglog) günlük dosyasının içeriğini yeni bir dosyaya kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `szNewVSGLog`  
 Yeni grafik günlük dosyasının dosya adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Yeni bir dosyaya grafik bilgilerini kopyalamak için zaten bazı grafik bilgilerini yakalanan gerekir; Aksi takdirde, hiçbir şey olmaz.