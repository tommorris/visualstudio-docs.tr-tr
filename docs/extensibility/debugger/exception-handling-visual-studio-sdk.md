---
title: "Özel durum işleme (Visual Studio SDK) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], exception handling
ms.assetid: 7279dc16-db14-482c-86b8-7b3da5a581d2
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 88a862c26dad97eecdb5f372f41a76d7886f32be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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
  
         veya  
  
         Yöntem S_FALSE, program döndürüyorsa ayıklanacak özel durumu işlemek için ikinci bir şans verilir.  
  
6.  Ayıklanacak program bir saniye fırsat özel durum için hiçbir işleyici varsa DE gönderir bir `IDebugExceptionEvent2` SDM için **EVENT_SYNC_STOP**.  
  
7.  Hata ayıklama paket ilk fırsat özel durum iletişim kutusunu açarak özel durum işleme kullanıcıya sorar.  
  
8.  Hata ayıklama paket çağrıları [IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md) ne kullanıcıya sunmak üzere seçeneklerini belirlemek için.  
  
9. Hata ayıklama paket ikinci fırsat özel durum iletişim kutusunu açarak özel durum işleme kullanıcıya sorar.  
  
10. Yöntem S_OK döndürüyorsa, çağıran `IDebugExceptionEvent2::PassToDebuggee`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)