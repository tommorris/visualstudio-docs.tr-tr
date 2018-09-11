---
title: 64-bit uygulamalar için önkoşulları dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], 64-bit
- 64-bit [Visual Studio]
- 64-bit programming [Visual Studio]
- 64-bit applications [Visual Studio]
ms.assetid: 87399e20-5510-41e4-b5b7-4a87c5773f21
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 10a5883e655fc5ee8a37bbe61f531b6b266ebb55
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44281903"
---
# <a name="deploy-prerequisites-for-64-bit-applications"></a>64-bit uygulamalar için önkoşulları dağıtma
ClickOnce dağıtımı, 64-bit platformlarda uygulamaların yüklenmesini destekler. Hedef platformlar **x86** 32-bit platformları için **x64** AMD64 ve EM64T komut kümelerini destekleyen makineler için ve **Itanium** 64-bit Itanium işlemcisi için.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Aşağıdaki tabloda, 64-bit uygulamanızın kurulum için önkoşul olarak kullanabileceğiniz yeniden dağıtılabilir dosyaları listeler.  
  
 64-bit bileşen yok. bir önkoşul seçerseniz, seçilen paketleri 64-bit platformu için kullanılabilir olmadığını belirten bir uyarı görebilirsiniz.  
  
|Yeniden dağıtılabilir|x64 desteği|IA64 desteği|  
|---------------------|-----------------|------------------|  
|[!INCLUDE[vsto_runtime](../deployment/includes/vsto_runtime_md.md)]|Evet|Hayır|  
|Visual C++ 2010 Çalışma zamanı kitaplıkları (IA64)|Hayır|Evet|  
|Visual C++ 2010 Çalışma zamanı kitaplıkları (x64)|Evet|Hayır|  
|Microsoft .NET Framework 4 (x86 ve x64)|Evet||  
|Microsoft .NET Framework 4 istemci profili (x86 ve x64)|Evet||  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Uygulamaları, hizmetleri ve bileşenleri dağıtma](../deployment/deploying-applications-services-and-components.md)   
 [Nasıl yapılır: ClickOnce uygulamasıyla Önkoşulları Yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [64-bit uygulamalar](/dotnet/framework/64-bit-apps)