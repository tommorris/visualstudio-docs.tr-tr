---
title: 'DA0007: denetim akışı için özel durumlar kullanmaktan kaçının | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAExceptionsThrown
- vs.performance.7
- vs.performance.rules.DA0007
- vs.performance.DA0007
ms.assetid: ee8ba8b5-2313-46c9-b129-3f3a2a232898
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b7f673adc1c5f93c3cf356218c510cad7f8d229
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749872"
---
# <a name="da0007-avoid-using-exceptions-for-control-flow"></a>DA0007: Denetim akışı için özel durumlar kullanmaktan kaçının
|||  
|-|-|  
|Kural Kimliği|DA0007|  
|Kategori|.NET framework kullanımı|  
|Profil oluşturma yöntemleri|Tümü|  
|İleti|Çok sayıda özel durumlar tutarlı bir şekilde durumlar gönderildiğini. Özel durumlar programı mantığındaki kullanımını azaltmayı deneyin.|  
|İleti türü|Uyarı|  
  
 Örnekleme, .NET bellek veya kaynak çakışması yöntemlerini kullanarak profil, bu kural tetiklemek için en az 25 örnekleri toplamanız gerekir.  
  
## <a name="cause"></a>Sebep  
 .NET Framework özel durum işleyicileri yüksek oranda profil oluşturma verileri çağrılır. Oluşturulan özel durum sayısını azaltmak için diğer denetim akışı mantığı kullanmayı düşünün.  
  
## <a name="rule-description"></a>Kural açıklaması  
 Hataları ve program yürütme kesintiye diğer olayları yakalamak için özel durum işleyicilerini kullanmak iyi bir uygulama olsa da, normal program yürütme mantığının parçası olarak özel durum işleyici kullanımını pahalı olabilir ve kaçınılmalıdır. Çoğu durumda, özel durumlar seyrek oluşur ve değil beklenen durumlarda kullanılmalıdır. Özel durumlar programın normal akışının bir parçası değer döndürmek için kullanılmamalıdır. Çoğu durumda, değerlerini doğrulama ve koşullu mantık soruna neden deyimleri yürütülmesini durdurmak için kullanarak özel durumlarını oluşturma önleyebilirsiniz.  
  
 Daha fazla bilgi için bkz: [özel durum yönetimi](http://go.microsoft.com/fwlink/?LinkID=177825) bölümünü **bölüm 5 — yönetilen kod performansı artırma** içinde **artırma .NET uygulama performansı ve ölçeklenebilirliği** hacmi **Microsoft Patterns and Practices** MSDN'deki kitaplığı.  
  
## <a name="how-to-investigate-a-warning"></a>Bir uyarıyı araştırmak nasıl  
 İşaretleri görünümüne gitmek için hata listesi penceresini iletisinde çift tıklayın. İçeren bir sütun Bul **.NET CLR özel durumları (@ProcessInstance)\\Excels durum sayısı / sn** ölçümleri. Olup olmadığını program yürütme belirli aşamaları özel durum işleme diğerlerinden daha sık olduğu belirler. Throw deyimleri tanımlamak ve try/catch blokları sık özel durum oluşturmak örnekleme profili kullanarak deneyin. Gerekirse, catch blokları hangi özel durumların en sık işlendiğini anlamanıza yardımcı olması için mantık ekleyin. Mümkünse, sık çalıştırılan Değiştir throw deyimleri veya basit akış catch blokları mantığı veya doğrulama kodunu denetler.  
  
 Bul olsaydınız Örneğin, uygulamanızın sıfır değerleri olan kesirler denetlemek için program mantığı uygulama performansını iyileştirir ekleme sık DivideByZeroException özel durumların işlenmesi oluştu.