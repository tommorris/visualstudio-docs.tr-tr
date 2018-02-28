---
title: Eski dil Service1 uygulama | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language services, managed
ms.assetid: df638f24-166d-4b80-be82-c9c39ca7a556
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 304d99c1ddd5fdfddba0c4df88fc4eeeb9dcb7ac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-a-legacy-language-service"></a>Eski dil hizmeti uygulama
Sözdizimi vurgulama, eşleşen ayraç ve IntelliSense tamamlanma gibi çok çeşitli özellikleri destekleyen bir eski dil hizmet uygulamak için sınıflar yönetilen paket Framework'te (MPF) kullanabilirsiniz.  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Bir dil hizmeti uygulamak için yeni yolu hakkında daha fazla bilgi için bkz: [Düzenleyicisi ve dil hizmeti uzantılarını](../../extensibility/editor-and-language-service-extensions.md).  
  
> [!NOTE]
>  Yeni Düzenleyicisi API mümkün olan en kısa sürede kullanmaya başlamanızı öneriyoruz. Bu dil hizmetinizin performansını ve yeni Düzenleyicisi özelliklerden yararlanmak sağlar.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Eski Dil Hizmetine Genel Bakış](../../extensibility/internals/legacy-language-service-overview.md)  
 MPF içinde desteklenen dil hizmet özelliklerine genel bakış.  
  
 [Eski dil hizmeti uygulama](../../extensibility/internals/implementing-a-legacy-language-service2.md)  
 Bir dil hizmeti MPF kullanarak uygulamak için gereken nedir açıklar.  
  
 [Eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service1.md)  
 Bir dil MPF tabanlı hizmete kaydolmak için gereken adımları açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Eski Dil Hizmeti Ayrıştırıcısı ve Tarayıcısı](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)  
 Bir dil hizmetin tüm özelliklerini MPF kullanarak uygulamak için gereken iki ayrıştırıcıları açıklar.  
  
 [İzlenecek Yol: Eski Dil Hizmeti Oluşturma](../../extensibility/internals/walkthrough-creating-a-legacy-language-service.md)  
 Bir VSPackage MPF dil hizmeti uygulamak için gereken temel adımları sağlar.  
  
 [İzlenecek Yol: Yüklü Kod Parçacıklarının Listesini Alma (Eski Uygulama)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)  
 Yüklü kod parçacıkları listesini alma teknikleri gösterir.  
  
 [Eski dil hizmeti özellikleri](../../extensibility/internals/legacy-language-service-features1.md)  
 Konulara bağlantılar ne MPF kullanarak bir dil hizmetin tüm özelliklerini uygulama yapılmalıdır bu ayrıntı sağlar.