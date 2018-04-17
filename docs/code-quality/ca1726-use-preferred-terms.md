---
title: 'CA1726: tercih edilen terimleri kullanın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- UsePreferredTerms
- CA1726
helpviewer_keywords:
- UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5e37ed041d03e82a63929a7bc525c73ea4062333
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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