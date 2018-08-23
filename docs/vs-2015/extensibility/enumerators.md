---
title: Numaralandırıcılar | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6dcbd3dea8ad932aec5890bc085873ce3d20a8f0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691108"
---
# <a name="enumerators"></a>Numaralandırıcılar
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [numaralandırıcılar](https://docs.microsoft.com/visualstudio/extensibility/enumerators).  
  
Bu bölümde, kaynak denetimi eklentisi hakkında bilmeniz gereken kaynak denetimi eklentisi API Numaralandırıcı veri türlerini listeler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Komut kodu](../extensibility/command-code-enumerator.md)  
 Seçeneklerini numaralandırır [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) ve [SccPopulateList](../extensibility/sccpopulatelist-function.md) işlevleri.  
  
 [İleti](../extensibility/message-enumerator.md)  
 Yazdırma geri çağırma için kullanılan bayrakları numaralandırır [LPTEXTOUTPROC](../extensibility/lptextoutproc.md).  
  
 [Dosya durum kodu](../extensibility/file-status-code-enumerator.md)  
 Kaynak denetimi altındaki bir dosyayı durumunu belirten adlandırılmış sabit değerleri içerir.  
  
 [Dizin durum kodu](../extensibility/directory-status-code-enumerator.md)  
 Kaynak denetimi altında bir dizin durumunu belirten adlandırılmış sabit değerleri içerir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Kaynak Denetimi Eklentisi Oluşturma](../extensibility/internals/creating-a-source-control-plug-in.md)  
 Kaynak Denetimi Eklentisi SDK tanımlar ve dahil edilen kaynaklar açıklanır.  
  
 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)  
 Verilen komutu için Gelişmiş Seçenekleri kullanıcıya sorar.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 Bunların geçerli durum için dosyaların listesini inceler. Ayrıca, kullandığı `pfnPopulate` işlevi bir dosya için ölçüt eşleşmediğinde çağrıyı yapana bunu bildirmesi `nCommand`.  
  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 Tarafından kullanılan geri çağırma işlevi açıklar [SccOpenProject](../extensibility/sccopenproject-function.md) kaynak denetimi eklentisi IDE üzerinden alınan iletileri görüntülemek için.  
  
 [Kaynak Denetimi Eklentileri](../extensibility/source-control-plug-ins.md)  
 Kaynak Denetimi Eklentisi API içindeki tüm öğelerin tam listesini sağlar.

