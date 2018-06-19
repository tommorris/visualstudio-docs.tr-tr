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
ms.openlocfilehash: ed3ffb52e73be1f86b9ae4be67d130807fc7e238
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31566010"
---
# <a name="deploying-prerequisites-for-64-bit-applications"></a>64 bit Uygulamalar için Önkoşulları Dağıtma
ClickOnce dağıtımı 64 bit platformlarda uygulamaların yüklenmesini destekler. Hedef platformlar **x86** 32-bit platformu için **x64** AMD64 ve EM64T yönerge kümeleri destekleyen makineler için ve **Itanium** 64-bit Itanium işlemci için.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Aşağıdaki tabloda, 64-bit uygulamanızın yüklemesi için önkoşulların olarak kullanabileceğiniz yeniden dağıtılabilir öğeleri listeler.  
  
 64-bit bileşenleri sahip olmayan bir önkoşul seçerseniz, seçilen paketleri 64-bit platformu için kullanılabilir olmadığını bildiren bir uyarı görebilirsiniz.  
  
|Yeniden dağıtılabilir|x64 desteği|IA64 desteği|  
|---------------------|-----------------|------------------|  
|[!INCLUDE[vsto_runtime](../deployment/includes/vsto_runtime_md.md)]|Evet|Hayır|  
|Visual C++ 2010 Çalışma zamanı kitaplıkları (IA64)|Hayır|Evet|  
|Visual C++ 2010 Çalışma zamanı kitaplıkları (x64)|Evet|Hayır|  
|Microsoft .NET Framework 4 (x86 hem x64)|Evet||  
|Microsoft .NET Framework 4 istemci profili (x86 hem x64)|Evet||  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulamaları, hizmetleri ve bileşenleri dağıtma](../deployment/deploying-applications-services-and-components.md)   
 [Nasıl yapılır: ClickOnce uygulamasıyla Önkoşulları Yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [64 bit Uygulamalar](http://msdn.microsoft.com/Library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)