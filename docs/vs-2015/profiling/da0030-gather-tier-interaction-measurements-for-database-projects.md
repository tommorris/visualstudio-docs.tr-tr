---
title: 'DA0030: Veritabanı projeleri için katman etkileşim ölçümlerini Topla | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.DA0030
- vs.performance.rules.DA0030
- vs.performance.30
ms.assetid: 42b2f69d-0cfa-4854-82c4-589c3d8b4557
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ce25d1ba654ee610f5a9bfa227409b7582a9d32
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688828"
---
# <a name="da0030-gather-tier-interaction-measurements-for-database-projects"></a>DA0030: Veritabanı projeleri için Katman Etkileşim ölçümlerini topla
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [DA0030: veritabanı projeleri için toplama katman etkileşim ölçümlerini](https://docs.microsoft.com/visualstudio/profiling/da0030-gather-tier-interaction-measurements-for-database-projects).  
  
Kural Kimliği | DA0030 |  
| Kategori | Profil oluşturma araçları kullanım |  
| Profil oluşturma yöntemi | Örnekleme |  
| İleti | Çok katmanlı uygulamalar için etkileşim ölçümleri toplamayı veritabanı kullanım modellerini ve anahtar veri anlamanıza yardım gecikmeler erişir. Katman etkileşim profili oluşturma seçeneği etkin uygulamayı yeniden profil oluşturmayı deneyin. |  
| Kural türü | Bilgi |  
  
## <a name="cause"></a>Sebep  
 Çağrılar <xref:System.Data> yöntemlerdir profil oluşturma verilerinin önemli bir kısmı ve profil oluşturma çalışması katman etkileşim verileri toplanan değil. Katman etkileşim verileri ekleme ve yeniden profil oluşturmayı göz önünde bulundurun.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Dahil olmak üzere System.Data ad alanlarında bulunan işlevlerinde önemli bir etkinlik olduğunda bu kural tetikler <xref:System.Data.Linq> <xref:System.Data.Linq>.  
  
 Çok katmanlı uygulamaların katmanlı Hizmetleri, sunu ve veri katmanları için kullanın. Genellikle veri katmanı, bir veritabanı yönetim sistemi gibi Microsoft Sql Server çalıştıran ayrı bir işlemdir. Veri katmanı da ayrı bir makinede uygulama geri kalanından çalışıyor olabilir. Örnekleme profil işlevleri ve işlem dışı çalışan hizmetler küçük bir anlayış sağlayın veya uzaktan.  
  
 Profil oluşturma araçları, çok katmanlı uygulamaların, zaman uyumsuz çağrıları ADO.NET hizmetleri kullanarak bir Microsoft Sql Server veri katmanı ile etkileşim için zamanlama bilgilerini toplayabilirsiniz. Katman etkileşim profili oluşturma açıkça etkinleştirmeniz gerekir. Varsayılan olarak açık değildir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural yalnızca bilgi amaçlıdır ve düzeltici eylem gerekli değil.  
  
 Visual Studio IDE içinden veri profil oluşturma için katman etkileşim verileri ekleme hakkında daha fazla bilgi için bkz: [katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md). Komut satırından katman etkileşim verileri ekleme hakkında daha fazla bilgi için bkz: [katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md).



