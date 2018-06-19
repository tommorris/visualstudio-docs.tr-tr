---
title: 'CA1725: Parametre adları taban yöntem ile eşleşmelidir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: d3564f3713dd24488e71703e902ae63f09b6aa74
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31914347"
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