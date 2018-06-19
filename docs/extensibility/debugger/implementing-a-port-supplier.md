---
title: Bir bağlantı noktası tedarikçi uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b0743f307dc579f6197880b0b89acaf2db0dda08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31098998"
---
# <a name="implementing-a-port-supplier"></a>Bir bağlantı noktası sağlayıcı uygulama
Bir bağlantı noktası tedarikçi oturum hata ayıklama Yöneticisi'ni (SDM) istek bağlantı noktaları sağlar. Bir bağlantı noktası tedarikçi DCOM olmayan makineye hata ayıklama sırasında veya yeni bir cihaz desteklenecek gerektiğinde uygulanması gerekir. Örneğin, bir cep telefonu hata ayıklama sağlamak için cep telefonunuza (belki de IR veya hücre bağlantı yoluyla) bağlanan ve işlemleri ve telefonda çalışan programlar numaralandırır bağlantı noktaları sağlayan bir bağlantı noktası tedarikçi uygulayabilir.  
  
 Bu durumda, kendi bağlantı noktası tedarikçi uygulamak için gerekli olmasını (uzaktan hata ayıklama dahil) Windows tabanlı makinelere hata ayıklama programları için Visual Studio yerel ve ortak dil çalışma zamanı (CLR) işlemleri, bağlantı noktası tedarikçileri sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Bağlantı Noktası Sağlayıcısı Uygulama ve Kaydetme](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 SDM bağlantı noktalarını ve bağlantı noktası sağlayıcı ile nasıl etkileşim kurduğu açıklanır.  
  
 [Gerekli Bağlantı Noktası Sağlayıcısı Arabirimleri](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 Bir bağlantı noktası tedarikçi almak için uygulanmalı arabirimleri belgeler.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hata Ayıklayıcı Kavramları](../../extensibility/debugger/debugger-concepts.md)  
 Ana hata ayıklama mimari kavramlarını açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Hata Ayıklayıcı Genişletilebilirliği](../../extensibility/debugger/visual-studio-debugger-extensibility.md)