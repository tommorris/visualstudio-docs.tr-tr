---
title: 'CA2103: Kesinlik temelli güvenliği gözden geçirin | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2103
- ReviewImperativeSecurity
helpviewer_keywords:
- CA2103
- ReviewImperativeSecurity
ms.assetid: d24fde71-bdf6-46c0-8965-9a73dc33c1aa
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6aa27379c7fc505c1eddf8ad0518693f5e9930a0
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900219"
---
# <a name="ca2103-review-imperative-security"></a>CA2103: Kesinlik temelli güvenliği gözden geçirin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2103: kesinlik temelli güvenliği gözden geçirin](https://docs.microsoft.com/visualstudio/code-quality/ca2103-review-imperative-security).

|||
|-|-|
|TypeName|ReviewImperativeSecurity|
|CheckId|CA2103|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir yöntem zorunlu güvenliği kullanır ve durum bilgileri veya dönüş değerlerini kullanarak izin oluşturursa, izin talebi etkin durumdayken değişebilir.

## <a name="rule-description"></a>Kural Tanımı
 Kesinlik temelli güvenlik izinleri ve güvenlik eylemleri bildirime dayalı güvenlik öznitelikleri, Eylemler ve izinler meta verileri depolamak için kullandığı karşılaştırıldığında kod yürütülürken belirtmek için yönetilen nesneleri kullanır. Kesinlik temelli güvenlik çok esnektir çünkü bir izin nesnesi durumunu ayarlamak ve çalışma zamanına kadar kullanılabilir olmayan bilgileri kullanarak güvenlik eylemleri seçin. İle birlikte esneklik eylemin yürürlükte olduğu sürece, bir izin durumu değil kalan belirlemek için kullandığınız çalışma zamanı bilgileri değişmeden riskini ortaya çıktı.

 Bildirime dayanan güvenliği mümkün olduğunca kullanın. Bildirim temelli talepleri anlamak kolaydır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Kesinlik temelli güvenlik taleplerini izin durumu izni kullanılmakta olduğu sürece, değiştirebileceğiniz hakkında bilgi kullanmayan emin olmak için gözden geçirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Değişen veri iznini kullanmayan varsa bu kuraldan bir uyarıyı bastırmak güvenlidir. Ancak, bildirim temelli eşdeğerine kesinlik temelli talep değiştirmek iyidir.

## <a name="see-also"></a>Ayrıca Bkz.
 [Güvenli kodlama yönergeleri](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177) [veri ve modelleme](http://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6)



