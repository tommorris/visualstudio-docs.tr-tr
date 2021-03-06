---
title: Bir bağlantı noktası sağlayıcısı uygulama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5d14c2642d30ee46df0cd1b766540ae0b135e4d4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687751"
---
# <a name="implementing-a-port-supplier"></a>Bağlantı Noktası Sağlayıcısı Uygulama
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [bir bağlantı noktası sağlayıcısı uygulama](https://docs.microsoft.com/visualstudio/extensibility/debugger/implementing-a-port-supplier).  
  
Bağlantı noktası sağlayıcısı oturum hata ayıklama Yöneticisi (SDM) istek bağlantı noktaları sağlar. Bağlantı noktası sağlayıcısı, DCOM olmayan bir makineye hata ayıklama sırasında veya yeni bir cihaz desteklenmesi gerektiğinde uygulanması gerekir. Örneğin, bir cep telefonu için hata ayıklama sağlamak için cep telefonunuza (belki de IR veya bir hücre bağlantı yoluyla) bağlanan ve bir telefonda çalışan programlar ve işlemleri numaralandırır bağlantı noktaları sağlayan bir bağlantı noktası sağlayıcısı uygulayabilir.  
  
 Bu gibi durumlarda kendi bağlantı noktası sağlayıcısı uygulama gerekmez. Bu nedenle Windows tabanlı makineler (uzaktan hata ayıklama dahil) üzerinde hata ayıklama programları için bağlantı noktası sağlayıcıları için yerel ve ortak dil çalışma zamanı (CLR) işlemleri, Visual Studio sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Bağlantı Noktası Sağlayıcısı Uygulama ve Kaydetme](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md)  
 SDM bağlantı noktalarını ve bağlantı noktası sağlayıcısı ile nasıl etkileşim kurduğu açıklanır.  
  
 [Gerekli Bağlantı Noktası Sağlayıcısı Arabirimleri](../../extensibility/debugger/required-port-supplier-interfaces.md)  
 Bağlantı noktası sağlayıcısı edinmek için uygulanması gereken arabirimleri belgeler.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Hata Ayıklayıcı Kavramları](../../extensibility/debugger/debugger-concepts.md)  
 Hata ayıklama ana mimari kavramlarını açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Hata Ayıklayıcı Genişletilebilirliği](../../extensibility/debugger/visual-studio-debugger-extensibility.md)

