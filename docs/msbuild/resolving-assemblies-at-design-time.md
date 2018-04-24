---
title: Tasarım zamanında derlemeleri çözme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild
ms.assetid: 20dae076-733e-49c1-a2e9-b336757ae21d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1df70002bf2d69e6d8d41abab5007209b5caf3ef
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="resolving-assemblies-at-design-time"></a>Tasarım Zamanında Derlemeleri Çözme
Bir derleme başvurusu Ekle iletişim kutusunun .NET sekmesi aracılığıyla başvuru eklediğinizde, başvuru Ara başvuru bütünleştirilmiş türü ve imza tüm bilgileri içeren, ancak, mutlaka içermediğinden bir derlemeyi başka bir deyişle, gösterir. kod. .NET sekmesi, .NET Framework çalışma zamanı derlemeleri karşılık başvuru derlemeleri listeler. Ayrıca, çalışma zamanı derlemeleri üçüncü taraflar tarafından kullanılan kayıtlı AssemblyFoldersEx klasörlerde karşılık başvuru derlemeleri listeler.  
  
## <a name="multi-targeting"></a>Çoklu Sürüm Desteği  
 [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)] Hedef üzerinde ortak dil çalışma zamanı (CLR) sürüm 2.0 ya da çalıştırmak .NET Framework sürümleri veya sürüm imkan tanıyan 4. Bu, .NET Framework sürüm 2.0, 3.0, 3.5, 4, 4.5 ve 4.5.1 ve Silverlight sürümleri 1.0, 2.0 ve 3.0 içerir. Yeni bir .NET Framework sürüm varsa CLR Version 2.0 sürümü tabanlı veya sürüm 4 yayımlanır, Framework hedefleme pack kullanılarak yüklenebilir ve onu otomatik olarak Visual Studio bir hedef olarak görünür.  
  
## <a name="how-type-resolution-works"></a>Tür Çözümlemesi Nasıl Çalışır?  
 Çalışma zamanında, bin dizinini GAC ve yoklama yollar bakarak CLR derlemesi türlerini çözümler. Bu fusion yükleyicisi tarafından işlenir. Ancak fusion yükleyicisi ne onu aradığı nasıl biliyor? Bu, uygulamanın ne zaman yerleşik tasarım zamanında yapılan bir çözüm bağlıdır.  
  
 Derleme sırasında derleyici uygulama türleri başvuru derlemeleri kullanarak çözümler. .NET Framework yüklendiğinde, .NET Framework sürümlerinde 2.0, 3.0, 3.5, 4, 4.5 ve 4.5.1, başvuru derlemeleri yüklenir.  
  
 Başvuru derlemeleri karşılık gelen .NET Framework SDK sürümüyle birlikte gelen hedefleme paketi tarafından sağlanır. Framework çalışma zamanı derlemeleri sağlar. Uygulamaları oluşturmak için .NET Framework ve karşılık gelen .NET Framework SDK'yı yüklemeniz gerekir.  
  
 Belirli bir .NET Framework hedeflediğinizde, yapı sistem tüm türleri başvuru derlemeleri hedefleme paketinde kullanarak çözümler. Çalışma zamanında fusion yükleyicisi bu aynı tür GAC içinde genellikle bulunan çalışma zamanı derlemeleri çözümler.  
  
 Başvuru derlemeleri kullanılabilir değilse, yapı sistem çalışma zamanı derlemeleri kullanarak derleme türlerini çözümler. Çalışma zamanı derlemeleri GAC'de göre alt sürüm numaralarını ayrılırlar değil çünkü çözümleme için yanlış derleme yapılan mümkündür. .NET Framework sürüm 3.5 sunulan yeni bir yöntem sürüm 3.0 hedefleme sırasında başvurulan Bu, örneğin, olabilir. Yapı başarılı olur ve uygulama yapı makinesinde çalışır, ancak sürüm 3.5 yüklü olmayan bir makineye dağıtıldığında başarısız olur.  
  
 Şimdi .NET Framework SDK ile birlikte gelen hedefleme paketi yeniden dağıtımı (redist) listesi adlı Framework'ün bu sürümünde tüm çalışma zamanı derlemeleri listesini içerir. Derlemenin sürümü yanlış türleriyle çözmek derleme sistem mümkün kılar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş kavramlar](../msbuild/msbuild-advanced-concepts.md)