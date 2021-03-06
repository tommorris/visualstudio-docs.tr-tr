---
title: VsgDbg sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6722263c-ccef-40c7-a0ae-87a863fbab00
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 927990cb8fb21dfeaf25a681cfb0a222ecc3c8ed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627919"
---
# <a name="vsgdbg-class"></a>VsgDbg Sınıfı
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [VsgDbg sınıfı](https://docs.microsoft.com/visualstudio/debugger/graphics/vsgdbg-class).  
  
Grafik tanılama uygulama bileşeninin programlı denetim için bir arabirimi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
class VsgDbg;  
```  
  
## <a name="members"></a>Üyeler  
 `VsgDbg` Sınıfı aşağıdaki üyelere destekler.  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VsgDbg::VsgDbg (Oluşturucu)](../debugger/vsgdbg-vsgdbg-constructor.md)|Örneği oluşturur `VsgDbg` sınıfı ve isteğe bağlı olarak etkin bir şekilde yakalayıp grafik bilgilerini kaydetmek için grafik tanılama uygulama bileşeninin hazırlar.|  
|[VsgDbg::~VsgDbg (Yok Edici)](../debugger/vsgdbg-tilde-vsgdbg-destructor.md)|Örneğini yok eder `VsgDbg` sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[AddMessage](../debugger/addmessage.md)|Grafik tanılama baş üstü (baş yukarı görüntüleme) için özel bir ileti ekler.|  
|[BeginCapture](../debugger/begincapture.md)|İle biten bir yakalama aralık başlar `EndCapture`.|  
|[CaptureCurrentFrame](../debugger/capturecurrentframe.md)|Geçerli kare grafik günlük dosyasına geri kalanında yakalar.|  
|[Kopyalama (Programlı Yakalama)](../debugger/copy-programmatic-capture.md)|Etkin bir grafik günlüğü (.vsglog) dosyasının içeriğini yeni bir dosyaya kopyalar.|  
|[EndCapture](../debugger/endcapture.md)|İle başlatılan bir yakalama zaman aralığı sona `BeginCapture`.|  
|[Init](../debugger/init.md)|Etkin bir şekilde yakalayıp grafik bilgilerini kaydetmek için grafik tanılama uygulama bileşeninin hazırlar.|  
|[ToggleHUD](../debugger/togglehud.md)|Grafik tanılama baş üstü katmana açıp değiştirir.|  
|[UnInit](../debugger/uninit.md)|Grafik günlük dosyasını sonlandırır kapatılır ve uygulama, etkin bir şekilde grafik bilgilerini kaydetme sırasında kullanılan kaynakları serbest bırakır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `VsgDbg` Sınıfı, grafik tanılama özelliklerine program aracılığıyla denetlemek için kullanabileceğiniz bir arabirimi temsil eder. Bazı özellikler bile, aktif yakalama ve grafik bilgilerini kaydetme kullanabilirsiniz; Bu içerir `AddMessage` üye işlevi ve `ToggleHUD` üye işlevi. Diğer üye işlevlerini başlatmak veya durdurmak etkin grafik bilgilerini yakalama için grafik tanılama uygulama bileşeninin hazırlama veya uygulamayı etkin bir şekilde yakalama ve grafik bilgilerini bir grafik günlük dosyasına kaydını çağrılmalıdır.



