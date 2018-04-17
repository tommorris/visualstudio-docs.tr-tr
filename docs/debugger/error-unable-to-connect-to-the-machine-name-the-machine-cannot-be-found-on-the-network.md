---
title: 'Hata: Makineye bağlanılamıyor &lt;adı&gt;. Makinenin ağ üzerinde bulunamadı. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.remote.dcom_disabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DCOM, unable to connect error
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf8716602469eccb40dabda15e91d6198fa9b489
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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