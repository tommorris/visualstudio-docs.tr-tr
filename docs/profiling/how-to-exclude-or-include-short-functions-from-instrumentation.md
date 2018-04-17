---
title: 'Nasıl yapılır: Exclude veya kısa işlevleri izlemeden Include | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling tools, instrument events
- profiling tools, include short functions
- profiling tools, exclude short functions
ms.assetid: eaeead79-aafe-4490-86ff-6ed4cad9c15f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 864d4ccf6f211469b876b3452e69c23caceccd7e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-exclude-or-include-short-functions-from-instrumentation"></a>Nasıl yapılır: Kısa İşlevleri İzlemeden Hariç Tutma veya Dahil Etme
Profil oluşturma araçları varsayılan olarak, dışarıda *küçük işlevleri* izlemeden. İşlev çağrıları yapma kısa işlevleri küçük işlevlerdir. Bu kısa işlevleri dışlama araçları tarafından yükü daha azdır için sağlar ve bu nedenle araçları hızı geliştirilmiş. Kısa işlevleri dışlama de performans profil oluşturma veri dosyası (.vsp) boyutu ve çözümleme için gereken süreyi azaltır. Küçük işlevler hariç, küçük işlevlerde geçen süre üst işlevleriyle özel ve kapsayıcı zaman karşı sayar. Küçük işlevler hariç veya Araçları'nda, aşağıdaki yordamda açıklandığı gibi dahil.  
  
### <a name="to-exclude-or-include-short-functions-from-instrumentation"></a>Hariç tutma veya kısa işlevleri izlemeden eklemek için  
  
1.  İçinde **performans Gezgini**seçin **Performans oturumunu** ve ardından sağ tıklatın ve seçin **özellikleri**.  
  
     **Özellik sayfaları** iletişim kutusu görüntülenir.  
  
2.  İçinde **özellik sayfaları**, tıklatın **Araçları** özellikleri.  
  
3.  Kısa işlevleri izleme hariç tutmak için işaretleyin **araçları kısa işlevleri dışlama**. Varsayılan ayar budur.  
  
     -veya-  
  
     Kısa işlevleri de araçları içerecek şekilde temizleyin **araçları kısa işlevleri dışlama**.  
  
4.  **Tamam**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri toplama denetimi](../profiling/controlling-data-collection.md)   
 [Performans oturum özellikleri](../profiling/performance-session-properties.md)