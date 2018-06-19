---
title: Ayıklanacak bir Program etkinleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], enabling for programs
ms.assetid: 61d24820-0cd9-48b6-8674-6813f7493237
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3f8dc37e5d59738e6ef326be71e773c1e4e57351
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100536"
---
# <a name="enabling-a-program-to-be-debugged"></a>Ayıklanacak bir Program etkinleştirme
Hata ayıklama altyapınız (DE) bir programı ayıklayabilirsiniz önce öncelikle DE başlatın veya varolan bir program eklemek gerekir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Bağlantı Noktası Alma](../../extensibility/debugger/getting-a-port.md)  
 Ayıklanacak bir programı etkinleştirmek için ilk adım olarak bir bağlantı noktası alınacağını açıklar.  
  
 [Program Kaydetme](../../extensibility/debugger/registering-the-program.md)  
 Ayıklanacak bir program etkinleştirme bir sonraki adım açıklar: bağlantı noktası ile kaydediliyor. Kaydedildikten sonra programı hata ayıklaması yapılabilir ya da ekleme veya tam zamanında (JIT) hata ayıklama işlemi.  
  
 [Programa Ekleme](../../extensibility/debugger/attaching-to-the-program.md)  
 Sonraki adımda açıklanmaktadır: hata ayıklayıcı programa ekleniyor.  
  
 [Başlatma tabanlı ekleme](../../extensibility/debugger/launch-based-attachment.md)  
 Otomatik başlatma SDM ile bağlı bir program başlatma tabanlı eki açıklar.  
  
 [Gerekli Olayları Gönderme](../../extensibility/debugger/sending-the-required-events.md)  
 Hata ayıklama altyapısı (DE) oluştururken gerekli olayları adımları ve bir programa ekleniyor.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Özel Hata Ayıklama Altyapısı Oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Hata ayıklama altyapısı (DE) tanımlar ve Aygıtların arabirimleri ve belirleyerek, ne hata ayıklayıcısı farklı işletimsel modlar arasında geçiş için bir neden aracılığıyla uygulanan hizmetlerini açıklar.