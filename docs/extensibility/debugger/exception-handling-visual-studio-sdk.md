---
title: Özel durum işleme (Visual Studio SDK) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], exception handling
ms.assetid: 7279dc16-db14-482c-86b8-7b3da5a581d2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 646479184061b093d5d84f81827a4106bd3cda47
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100796"
---
# <a name="exception-handling-visual-studio-sdk"></a>Özel durum işleme (Visual Studio SDK)
Aşağıdaki özel durumlar oluşan işlemini açıklar.  
  
## <a name="exception-handling-process"></a>Özel durum işleme işlemi  
  
1.  İlk özel durum, ancak ayıklanacak programı özel durum işleyici tarafından işlenen önce hata ayıklama altyapısı (DE) gönderir bir [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md) durdurma olayı olarak oturum hata ayıklama yöneticisine (SDM). `IDebugExceptionEvent2` Kullanıcının üzerinde ilk fırsat özel durum bildirimleri durdurmak istediği (hata ayıklama paket özel durumlar iletişim kutusunda belirtilen) özel durum için ayarları belirtin yalnızca gönderilir.  
  
2.  SDM çağrıları [IDebugExceptionEvent2::GetException](../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) özel durum özelliği alınamadı.  
  
3.  Hata ayıklama paket çağrıları [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) ne kullanıcıya sunmak üzere seçeneklerini belirlemek için.  
  
4.  Hata ayıklama paket ilk fırsat özel durum iletişim kutusunu açarak özel durum işleme kullanıcıya sorar.  
  
5.  SDM kullanıcı devam etmek seçerse, çağıran [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md).  
  
    -   Yöntem S_OK döndürüyorsa, çağıran [IDebugExceptionEvent2::PassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md).  
  
         -veya-  
  
         Yöntem S_FALSE, program döndürüyorsa ayıklanacak özel durumu işlemek için ikinci bir şans verilir.  
  
6.  Ayıklanacak program bir saniye fırsat özel durum için hiçbir işleyici varsa DE gönderir bir `IDebugExceptionEvent2` SDM için **EVENT_SYNC_STOP**.  
  
7.  Hata ayıklama paket ilk fırsat özel durum iletişim kutusunu açarak özel durum işleme kullanıcıya sorar.  
  
8.  Hata ayıklama paket çağrıları [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) ne kullanıcıya sunmak üzere seçeneklerini belirlemek için.  
  
9. Hata ayıklama paket ikinci fırsat özel durum iletişim kutusunu açarak özel durum işleme kullanıcıya sorar.  
  
10. Yöntem S_OK döndürüyorsa, çağıran `IDebugExceptionEvent2::PassToDebuggee`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)