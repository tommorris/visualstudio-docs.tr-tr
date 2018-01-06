---
title: "Ayıklanacak bir Program etkinleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], enabling for programs
ms.assetid: 61d24820-0cd9-48b6-8674-6813f7493237
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a581c5a9ae56f52727c011db1de2ad35a5ba3592
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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