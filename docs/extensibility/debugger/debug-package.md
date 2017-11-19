---
title: "Paket hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: eccd258476f82871732ef7b16f0282d2f945b9ee
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="debug-package"></a>Paket hata ayıklama
Hata ayıklama paketi, Visual Studio Kabuğu'nda çalışır ve tüm UI işler. Visual Studio hata ayıklama arabirimleri tüketir ve oturum hata ayıklama Yöneticisi (SDM) ile iletişim kurar.  
  
 SDM gönderilen sonu olayları kesme modu ve odağı sonu oluştuğu programın değiştirmek için hata ayıklayıcı çalışma modu'den geçiş. Hata ayıklama paket olaylar tarafından gönderilen bilgileri yığın çerçevesi ve iş parçacığı izler.  
  
 Hata ayıklama paket hiçbir dil veya çalışma zamanı ortamı bağımlılıkları vardır. Uygulama veya hata ayıklama paket değiştirmek gerekli değildir.  
  
 Hata ayıklama paket vsdebug.dll tarafından uygulanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Oturum hata ayıklama Yöneticisi](../../extensibility/debugger/session-debug-manager.md)   
 [Yığın çerçeveleri](../../extensibility/debugger/stack-frames.md)   
 [İş parçacıkları](../../extensibility/debugger/threads.md)   
 [Hata ayıklayıcı bileşenleri](../../extensibility/debugger/debugger-components.md)