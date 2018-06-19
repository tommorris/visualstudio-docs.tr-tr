---
title: Paket hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], packages
ms.assetid: 99947fd4-fb87-4c69-b26c-65634e17d285
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6ca438b7ed8c9b6a4b84693f975144040f998f01
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31110035"
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