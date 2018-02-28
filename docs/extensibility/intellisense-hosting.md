---
title: "IntelliSense barındırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - IntelliSense hosting
ms.assetid: 20c61f8a-d32d-47e2-9c67-bf721e2cbead
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9727b6fcbe3c552273ca521e8fd14ab5e5181eb7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="intellisense-hosting"></a>IntelliSense barındırma
Visual Studio IntelliSense barındırma sağlar. Sağlar barındırma IntellSense Visual Studio Metin Düzenleyicisi barındırılmayan kodu için IntelliSense sağlar.  
  
## <a name="intellisense-hosting-usage"></a>IntelliSense barındırma kullanımı  
 Visual Studio'da tamamlama kümesi ve bir metin arabelleği erişimi olan herhangi bir kod IntelliSense windows yerden elde edebilirsiniz kullanıcı arabiriminde (UI). Tamamlanmasında bu bazı örnek senaryolar verilmiştir **izleme** penceresi veya bir kesme noktası özellikleri penceresinin koşul alanında.  
  
### <a name="implementation-interfaces"></a>Uygulama arabirimleri  
  
#### <a name="ivsintellisensehost"></a>IVsIntellisenseHost  
 IntelliSense açılır pencereleri barındıran herhangi bir kullanıcı Arabirimi bileşeni desteklemelidir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> arabirimi. Varsayılan çekirdek düzenleyici metin görünümü hisse içerir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> arabirim uygulaması geçerli IntelliSense işlevi korur. Çoğunlukla, yöntemlerinin <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> bir alt kümesini ne uygulandığını temsil arabirim <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> arabirimi. Alt IntelliSense UI işleme, düzeltme işareti ve seçim işleme ve basit bir metin değiştirme işlevselliği içerir. Ayrıca, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> arabirimi, ayrı IntelliSense "subject" ve "context" doğrudan bağlam için kullanılan metin arabelleği yok konular için IntelliSense sağlanan böylece sağlar.  
  
#### <a name="ivsintellisensehostgethostflags"></a>IVsIntellisenseHost.GetHostFlags  
 Bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> arabirimi sağlayıcısı uygulanmalı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetHostFlags%2A> ne tür bir IntelliSense konak özellikleri belirlemek bir istemci etkinleştirmek için yöntemi destekler.  
  
 İçinde tanımlı ana bilgisayar bayrakları [IntelliSenseHostFlags](../extensibility/intellisensehostflags.md), aşağıda özetlenmiştir.  
  
|IntelliSense konak bayrağı|Açıklama|  
|----------------------------|-----------------|  
|IHF_READONLYCONTEXT|Bağlamı arabelleğine bu bayrağı anlamına gelir ayarı salt okunur ve düzenleme yalnızca konu metni içinde gerçekleşir.|  
|IHF_NOSEPERATESUBJECT|Bu bayrak anlamına gelir, var. hiçbir ayrı IntelliSense konu ayardır. Konu bağlamı arabelleğinde gibi geleneksel var. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> IntelliSense sistem.|  
|IHF_SINGLELINESUBJECT|Konu değil bayrağı deyişle ayarı çok satırlı özelliği, tek bir satır olduğu gibi düzenleme **izleme** penceresi.|  
|IHF_FORCECOMMITTOCONTEXT|Bu bayrağı ayarlarsanız ve bağlamı arabelleğine güncelleştirilmelidir konağı yok sayılacak bağlamı arabelleğine salt okunur bayrağı ve devam etmek için düzenlemeleri etkinleştirir.|  
|IHF_OVERTYPE|(Konu veya bağlam) düzenleme üzerine yazma modunda yapılması gerekir.|  
  
#### <a name="ivsintellisensehostbeforecompletorcommit-and-ivsintellisensehostaftercompletorcommit"></a>IVsIntellisenseHost.BeforeCompletorCommit ve IVsIntellisenseHost.AfterCompletorCommit  
 Bu geri çağırma yöntemleri tarafından tamamlama penceresi önce ve sonra metin ön işleme ve sonrası işlemesi etkinleştirmek için kaydedilmiş denir.  
  
#### <a name="ivsintellisensecompletor"></a>IVsIntellisenseCompletor  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseCompletor> Birlikte creatable sürüm tümleşik geliştirme ortamı (IDE) tarafından kullanılan standart tamamlama penceresinin bir arabirimdir. Tüm <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> arabirimi hızla uygulayabilirsiniz IntelliSense bu completor arabirimini kullanarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop>