---
title: "Hata: Makineye bağlanılamıyor &lt;adı&gt;. Makinenin ağ üzerinde bulunamadı. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.remote.dcom_disabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: DCOM, unable to connect error
ms.assetid: b584b5db-ef52-45ed-8561-1314da3cc5b8
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e8ed30ca3baeb29f92c4d5f02b64c581ef9a37a7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>Hata: Makineye bağlanılamıyor &lt;adı&gt;. Makinenin ağ üzerinde bulunamadı.
Aşağıdaki koşullardan biri doğru olduğunda bu davranış oluşur:  
  
-   Uzak bilgisayarla bağlantınız kesildi.  
  
-   Kullanıcı hesabınızın uzak bilgisayarda devre dışıdır.  
  
-   Uzak bilgisayarda parolanızın süresi doldu.  
  
### <a name="to-resolve-this-behavior"></a>Bu davranışı gidermek için  
  
-   Yerel bilgisayar ve uzak bilgisayar aynı ağda olduğundan emin olun. Bunu yapmak için uzak bilgisayara erişmek için denemek için Microsoft Windows Explorer'ı (veya dosya Gezgini'ni) kullanın.  
  
     — ve —  
  
-   Uzak bilgisayara bağlanmak için kullandığınız kullanıcı hesabının etkin olduğundan emin olun.  
  
     — ve —  
  
-   Uzak bilgisayara bağlanmak için kullandığınız parola geçerli değil ve süresi geçmemiş emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)   
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)