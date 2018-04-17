---
title: Doğrudan bir programını ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, attaching to programs
ms.assetid: ad2b7db8-821c-440c-ba07-c55c6a395e0f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6885cb0dea801ab95e2e88e3f8168c139fea0e0c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="attaching-directly-to-a-program"></a>Doğrudan bir programını ekleme
Programlar genellikle çalışan zaten bir işlemde hata ayıklamak istediğiniz kullanıcılar bu süreci izleyin:  
  
1.  IDE içinde seçin **hata ayıklama işlemleri** komutunu **Araçları** menüsü.  
  
     **İşlemleri** iletişim kutusu görüntülenir.  
  
2.  Bir işlem seçin ve'ı tıklatın **Attach** düğmesi.  
  
     **Ekleme işlemi için** iletişim kutusu görüntülenirse, makinede yüklü tüm hata ayıklama altyapılar (DEs) listesi.  
  
3.  Seçili işlemde hata ayıklamak ve ardından kullanmak için DEs belirtin **Tamam**.  
  
 Hata ayıklama paket bir hata ayıklama oturumu başlatır ve DEs listesi geçirir. Hata ayıklama oturumu sırayla seçili işlem için bir geri çağırma işlevini yanı sıra bu listeyi geçirir ve çalışan programları listeleme işlemi sorar.  
  
 Program aracılığıyla, isteğine yanıt olarak kullanıcı, hata ayıklama paket oturum hata ayıklama Yöneticisi'ni (SDM) oluşturur ve seçili DEs listesi geçirir. Listenin yanı sıra, hata ayıklama paket SDM geçirir bir [IDebugEventCallback2](../../extensibility/debugger/reference/idebugeventcallback2.md) arabirimi. Hata ayıklama paket DEs listesi seçili işlem çağırarak geçirir [IDebugProcess2::Attach](../../extensibility/debugger/reference/idebugprocess2-attach.md). SDM sonra çağırır [IDebugProcess2::EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) işlemde çalışan programlar numaralandırmak için bağlantı noktası.  
  
 Bu noktadan itibaren bir program tam olarak içinde ayrıntılı her hata ayıklama altyapısı iliştirildiği [ekleme sonra bir başlatma](../../extensibility/debugger/attaching-after-a-launch.md), iki özel durum dışında.  
  
 Verimlilik için bir adres alanı SDM ile paylaşmak için uygulanması DEs gruplandırılır böylece her DE onu bağlanacağı programlar kümesi vardır. Bu durumda, [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) çağrıları [IDebugEngine2::Attach](../../extensibility/debugger/reference/idebugengine2-attach.md) ve programların eklemek için bir dizi geçirir.  
  
 Zaten çalışan bir program ekleme SE tarafından gönderilen başlangıç olayları giriş noktası olay genellikle içermez ikinci istisnadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlangıç olayları başlatma gönderme](../../extensibility/debugger/sending-startup-events-after-a-launch.md)   
 [Hata Ayıklama Görevleri](../../extensibility/debugger/debugging-tasks.md)