---
title: "Numaralandırmalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7929ead4ced01561adb8c11dcaa56bc97f57884b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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