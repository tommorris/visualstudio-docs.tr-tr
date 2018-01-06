---
title: "CA1726: tercih edilen terimleri kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UsePreferredTerms
- CA1726
helpviewer_keywords: UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 63a27c62f46343ac840a550ccbefd30f20e9f06a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1726-use-preferred-terms"></a>CA1726: Tercih edilen terimleri kullanın
|||  
|-|-|  
|TypeName|UsePreferredTerms|  
|CheckId|CA1726|  
|Kategori|Microsoft.Naming|  
|Yeni Değişiklik|Derlemelerini harekete sonu-<br /><br /> Tür parametreleri harekete zaman bölünemez-|  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünen bir tanımlayıcının adı, tercih edilen terim varolduğunda alternatif olarak bir terim içerir. Alternatif olarak, ad bayrağı veya bayrak terimi içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural bir tanımlayıcı belirteçlere ayrıştırır. Her tek belirteç ve her bitişik çift belirteci birleşimi kural ve özel sözlükler kullanım dışı bölümünde yerleşik koşulları karşılaştırılır. Aşağıdaki tabloda, kural ve bunların tercih edilen alternatifleri yerleşik terimleri gösterir.  
  
|Artık kullanılmayan terimi|Tercih edilen terim|  
|-------------------|--------------------|  
|değil|Gereksinim yoktur|  
|İptal Edildi|İptal edildi|  
|Yapılamıyor|Olamaz|  
|ComPlus|EnterpriseServices|  
|Couldnt|CouldNot|  
|Didnt|DidNot|  
|Doesnt|Bilgilerine|  
|Engelle|DoNot|  
|Bayrağı veya bayrakları|Değiştirme koşulu yoktur. Kullanmayın.|  
|yüklediniz|HadNot|  
|Tamamlanmadı|HasNot|  
|henüz|HaveNot|  
|Dizinler|Dizinler|  
|değil|IsNot|  
|Oturum açma|Oturum açma|  
|Oturum kapatma|Oturumu Kapat|  
|Shouldnt|ShouldNot|  
|Oturum açma|Oturum açma|  
|Oturumu Kapat|SignOut|  
|Wasnt|WasNot|  
|doğru|WereNot|  
|Yapmıyor|Olmadı|  
|Wouldnt|Görmeyecektir|  
|Yazılabilir|Yazılabilir|  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için tercih edilen alternatif terimiyle terimi değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Tanımlayıcı adı yalnızca kasıtlı ise ve tercih edilen terim yerine özgün terim özellikle ilgili bir uyarı bu kuraldan engelleyin.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [Adlandırma Uyarıları](../code-quality/naming-warnings.md)