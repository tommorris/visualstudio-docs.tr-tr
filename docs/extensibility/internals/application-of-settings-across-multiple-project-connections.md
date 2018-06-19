---
title: Birden çok proje bağlantılar üzerinden ayarları uygulaması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, application of settings
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0dff30ea80fb2de9bf4d90ffa48cd2f9b3d40756
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129212"
---
# <a name="application-of-settings-across-multiple-project-connections"></a>Birden çok proje bağlantılar üzerinden ayarları uygulama
Kaynak Denetim Eklentisi Kaynak Denetim eklentisi API 1.2 kullanılarak oluşturulan bir toplu işlem birden çok projeleri veya birden çok bağlantı bağlamları arasında aynı kaynak denetimi işlemi yürütmek için kullanabilirsiniz. Toplu kullanılabilir yedek ortadan kaldırmak için her proje için kullanıcı deneyimini iletişim kutularından.  
  
 Bir kullanıcı birden fazla bağlantı kaynak denetim eklentisi API 1.1, (örneğin, iki Web projeleri farklı dosya paylaşımı makinelerde) kullanılarak oluşturulmuş eklenti bir kaynak denetiminde ait birden çok öğe seçer ve bunları denetler, kullanıcı aynı iletişim kutusu görür. sürekli olarak. Kullanıcı olsa bile bu gerçekleşir **tümüne uygula** IDE her bağlantı bağlamı için durumuna sıfırlar çünkü iletişim kutusunda, kutuyu işaretleyin.  
  
## <a name="new-capability-flag"></a>Yeni özellik bayrağı  
 `SccBeginBatch` İşlev kümeleri `SCC_CAP_BATCH` bir toplu işlem devam ediyor belirten bayrak  
  
## <a name="new-functions"></a>Yeni işlevleri  
 Aşağıdaki yeni işlevleri toplu işlem destekler:  
  
-   [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)  
  
-   [SccEndBatch](../../extensibility/sccendbatch-function.md)  
  
 `SCCBeginBatch` İşlevi bir grup kaynak denetimi işlemleri başlatır. `SccEndBatch` Grup kapatır. Grupları bulunmayabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API Sürümü 1.2’deki Yenilikler](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)