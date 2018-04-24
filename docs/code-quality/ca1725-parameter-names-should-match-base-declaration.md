---
title: 'CA1725: Parametre adları taban yöntem ile eşleşmelidir'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f0f7899d54f2b1598530d199d49ee1ea7e38fea0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725: Parametre adları taban yöntem ile eşleşmelidir
|||
|-|-|
|TypeName|ParameterNamesShouldMatchBaseDeclaration|
|CheckId|CA1725|
|Kategori|Microsoft.Naming|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir harici olarak görünür yöntemi geçersiz kılma içindeki bir parametre adı yönteminin temel bildiriminde ya da yönteminin arabirim bildirimindeki parametresinin adı parametresinin adı eşleşmiyor.

## <a name="rule-description"></a>Kural Tanımı
 Parametreyi geçersiz kılma hiyerarşisinde tutarlı adlandırma yöntemini geçersiz kılmaları kullanılabilirliği artırır. Temel bildirim alanındaki addan farklı türetilmiş yöntem parametre adı taban yöntemini geçersiz kılma veya yeni aşırı yöntemin yöntem olup olmadığı hakkında karışıklığa neden olabilir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için parametre temel bildirimi eşleşecek şekilde yeniden adlandırın. COM görünür yöntemleri için önemli bir değişiklik açıklanmıştır.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural daha önce gönderilen kitaplıklarında COM görünür yöntemleri dışında bir uyarıdan engelleme.