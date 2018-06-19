---
title: Numaralandırmalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 84102435092096b7154a46100e9d857a31537482
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127247"
---
# <a name="enumerators"></a>Numaralandırmalar
Bu bölümde, kaynak denetim eklentisi hakkında bilmeniz gereken kaynak denetim eklentisi API'sindeki Numaralandırıcı veri türleri listelenmektedir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Komut kodu](../extensibility/command-code-enumerator.md)  
 Seçeneklerini numaralandırır [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) ve [SccPopulateList](../extensibility/sccpopulatelist-function.md) işlevleri.  
  
 [İleti](../extensibility/message-enumerator.md)  
 Yazdırma geri arama için kullanılan bayrakları numaralandırır [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).  
  
 [Dosya durum kodu](../extensibility/file-status-code-enumerator.md)  
 Kaynak denetimi altındaki bir dosyaya durumunu belirtin adlandırılmış sabit değerleri içerir.  
  
 [Dizin durum kodu](../extensibility/directory-status-code-enumerator.md)  
 Kaynak denetimi altında bir dizin durumunu belirtin adlandırılmış sabit değerleri içerir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kaynak Denetimi Eklentisi Oluşturma](../extensibility/internals/creating-a-source-control-plug-in.md)  
 Kaynak Denetim eklentisi SDK'sı tanımlar ve bulunan kaynaklar açıklanır.  
  
 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)  
 Verilen komut için Gelişmiş Seçenekleri kullanıcıya sorar.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 Bunların geçerli durum için dosyaları listesi inceler. Ayrıca, kullanır `pfnPopulate` işlevi çağıran bir dosya için ölçüt eşleşmediğinde bildirmek için `nCommand`.  
  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 Tarafından kullanılan geri çağırma işlevini açıklar [SccOpenProject](../extensibility/sccopenproject-function.md) IDE'yi eklenti kaynak denetiminden iletileri görüntülemek için.  
  
 [Kaynak Denetimi Eklentileri](../extensibility/source-control-plug-ins.md)  
 Kaynak Denetim eklentisi API'ndaki tüm öğelerin listesi sağlar.