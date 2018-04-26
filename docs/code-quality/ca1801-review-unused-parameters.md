---
title: 'CA1801: Kullanılmayan parametreleri gözden geçir'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUnusedParameters
- CA1801
- ReviewUnusedParameters
helpviewer_keywords:
- CA1801
- ReviewUnusedParameters
ms.assetid: 5d73545c-e153-4b7c-a7b2-be6bf5aca5be
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 142ed6bca0513022b8edd1a062c443aa50d08191
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1801-review-unused-parameters"></a>CA1801: Kullanılmayan parametreleri gözden geçir
|||
|-|-|
|TypeName|ReviewUnusedParameters|
|CheckId|CA1801|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Üye yaptığınız değişiklikler bakılmaksızın derleme dışına görünür değilse olmayan sonu -.<br /><br /> Üye parametre kendi gövdesi içinde kullanmak üzere değiştirirseniz olmayan sonu -.<br /><br /> -Parametresini kaldırın ve derleme dışında görünür ise kesiliyor.|

## <a name="cause"></a>Sebep
 Yöntem imzası, yöntemin gövdesinde kullanılmayan bir parametre içerir. Bu kural, aşağıdaki yöntemlerden inceleyin değil:

-   Temsilci tarafından başvurulan yöntemleri.

-   Olay işleyicileri olarak kullanılan yöntemleri.

-   Yöntemleri bildirilen ile `abstract` (`MustOverride` Visual Basic'te) değiştiricisi.

-   Yöntemleri bildirilen ile `virtual` (`Overridable` Visual Basic'te) değiştiricisi.

-   Yöntemleri bildirilen ile `override` (`Overrides` Visual Basic'te) değiştiricisi.

-   Yöntemleri bildirilen ile `extern` (`Declare` Visual Basic'de deyimini) değiştiricisi.

## <a name="rule-description"></a>Kural Tanımı
 Yöntem gövdesinde hiçbir doğruluk bunlara erişmek için hatayı çözebilirsiniz olduğundan emin olmak için kullanılmayan sanal olmayan yöntemler parametreleri gözden geçirin. Kullanılmayan parametreleri Bakım ve performans maliyetler doğurur.

 Bazı durumlarda bu kuralı ihlal yöntemin bir uygulaması hata işaret edebilir. Örneğin, parametre yöntemi gövdesinde kullanılmış. Geriye dönük uyumluluk nedeniyle bulunmasını parametresi varsa, bu kural için uyarıları gizler.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlal düzeltmek için kullanılmayan parametresini (önemli bir değişiklik) kaldırın veya yöntem gövdesi (bölünemez değiştirin) parametresini kullanın.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bir düzeltme önemli bir değişiklik olacak önceden sevk edilen kodu için bu kuraldan gizlemek güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnekte, iki yöntem gösterilmektedir. Bir yöntem kuralını ihlal ediyor ve başka bir yöntem kuralı karşılar.

 [!code-csharp[FxCop.Usage.ReviewUnusedParameters#1](../code-quality/codesnippet/CSharp/ca1801-review-unused-parameters_1.cs)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1811: Çağrılmayan özel kodlardan kaçının](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: Örneklendirilmemiş iç sınıflardan kaçının](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1804: Kullanılmayan yerel öğeleri kaldırın](../code-quality/ca1804-remove-unused-locals.md)