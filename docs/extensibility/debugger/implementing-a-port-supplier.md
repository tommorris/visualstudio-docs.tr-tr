---
title: "Bir bağlantı noktası tedarikçi uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: aa70e2a6019a97c248e6d4b411dacc222be59a1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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