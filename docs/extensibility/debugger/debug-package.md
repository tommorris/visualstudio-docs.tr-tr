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
ms.workload: vssdk
ms.openlocfilehash: a2cbb124dcb2d2d7a0bbcba1bc57eb3c704dd770
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
 [Hata Ayıklayıcı Bileşenleri](../../extensibility/debugger/debugger-components.md)