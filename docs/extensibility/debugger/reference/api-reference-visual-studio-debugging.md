---
title: "API Başvurusu (Visual Studio hata ayıklama) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], API reference
ms.assetid: e4e429da-3667-41f7-9158-a8207d13e91a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9f6e3110ca4988fcc12e547f3bcd82c1026f3aeb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="api-reference-visual-studio-debugging"></a>API Başvurusu (Visual Studio hata ayıklama)
Başvuru bölümünde, API, sözdizimi ve kullanımı tüm API öğeleri için gösteren bir kılavuz kavramsal genel bakış ve bir sınıflama, kod örnekleri içerir. Tüm başvurular kategoriye göre alfabetik olarak listelenir.  
  
 Aşağıdaki tabloda ortak gösterilmektedir `HRESULT` yöntemleri tarafından döndürülen değer.  
  
|Ad|Açıklama|Değer|  
|----------|-----------------|-----------|  
|S_OK|Başarılı.|0x00000000|  
|E_UNEXPECTED|Beklenmeyen hata oluştu.|0x8000FFFF|  
|E_NOTIMPL|Henüz uygulanmadı.|0x80004001|  
|E_OUTOFMEMORY|İşlemi tamamlamak için yeterli bellek yok.|0x8007000E|  
|E_INVALIDARG|Bir veya daha fazla bağımsız değişken geçersiz.|0x80070057|  
|E_NOINTERFACE|Böyle bir arabirim desteklenmiyor.|0x80004002|  
|E_POINTER|Geçersiz bir işaretçi.|0x80004003|  
|E_HANDLE|Geçersiz tanıtıcı.|0x80070006|  
|E_ABORT|İşlem iptal edildi.|0x80004004|  
|E_FAIL|Beklenmeyen hata oluştu.|0x80004005|  
|E_ACCESSDENIED|Genel erişim reddedildi hatası.|0x80070005|  
  
> [!NOTE]
>  Zaman bir [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] yöntemi hata ayıklama döndürür `S_OK`, varsayılır her şeyi parametre işaretçileri geçerli olduğundan ve diğer bir deyişle, bir doğrulama üzerinde parametresi işaretçileri yürütülür zaman `S_OK` döndürülür.  
  
> [!NOTE]
>  Geçersiz veya `NULL` [out] parametreleri IDE çökmesine neden olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimleri](../../../extensibility/debugger/reference/interfaces-visual-studio-debugging.md)   
 [Numaralandırmalar](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Yapılar ve birleşimleri](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [Hata ayıklama için SDK Yardımcıları](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Visual Studio Hata Ayıklayıcı Genişletilebilirliği](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)