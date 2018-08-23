---
title: Kopyalama (programlı yakalama) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 171dd04a4f2c933272a7addc787554f611b1449f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687045"
---
# <a name="copy-programmatic-capture"></a>Kopyalama (Programlı Yakalama)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kopyalama (programlı yakalama)](https://docs.microsoft.com/visualstudio/debugger/graphics/copy-programmatic-capture).  
  
Etkin bir grafik günlüğü (.vsglog) dosyasının içeriğini yeni bir dosyaya kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `szNewVSGLog`  
 Yeni grafik günlük dosyasının dosya adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Grafik bilgilerini yeni bir dosya kopyalamak için zaten bazı grafik bilgilerini yakalanan gerekir; Aksi takdirde, hiçbir şey olmaz.



