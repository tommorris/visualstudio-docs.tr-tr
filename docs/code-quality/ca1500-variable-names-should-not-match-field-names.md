---
title: 'CA1500: Değişken adları alan adlarıyla eşleşmemelidir | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b2dc3e217d0645d4acc5afaf416c40f2f16f81bc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: Değişken adları alan adlarıyla eşleşmemelidir
|||  
|-|-|  
|TypeName|VariableNamesShouldNotMatchFieldNames|  
|CheckId|CA1500|  
|Kategori|Microsoft.Maintainability|  
|Yeni Değişiklik|Bir alan olarak aynı ada sahip bir parametreyi harekete kullanıldığında:<br /><br /> -Bölünemez - alan ve parametre bildirdiğinden yöntemi derleme dışında görülemeyen, bağımsız olarak, değişiklik.<br />-Sonu - alanın adını değiştirirseniz ve derleme dışında görülebilir.<br />-- Parametrenin adını değiştirirseniz ve onu tanımlandığı yöntemi derleme görülebilir kesiliyor.<br /><br /> Aynı ada sahip bir alan olarak yerel bir değişken harekete kullanıldığında:<br /><br /> Alan yaptığınız değişiklikler bakılmaksızın derleme dışına görülemeyen varsa bölünemez -.<br />Yerel değişken adını değiştirirseniz ve alanın adını değiştirmeyin bölünemez -.<br />-- Alanın adını değiştirirseniz ve derleme dışında görülebilir kesiliyor.|  
  
## <a name="cause"></a>Sebep  
 Örnek yöntemi, bir parametre veya bildiri türü ait bir örnek alanı adıyla eşleşen bir yerel değişken bildirir. Kural ihlal yerel değişkenler yakalamak için test edilmiş hata ayıklama bilgileri kullanarak derlemeyi gerekir ve ilişkili program veritabanı (.pdb) dosyası kullanılabilir olması gerekir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Örnek alanı adını bir parametre veya yerel bir değişken adı eşleştiğinde, örnek alanı kullanılarak erişilir `this` (`Me` içinde [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]), yöntem gövdesi içinde anahtar sözcüğü. Kod korurken bu fark unutursanız ve parametre/yerel değişken hataları müşteri adayları örnek alanı başvurduğu varsayın kolaydır. Bu, özellikle uzun yöntem gövdeleri için geçerlidir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için parametre/değişken veya alan yeniden adlandırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, iki kural ihlalleri gösterir.  
  
 [!code-vb[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/VisualBasic/ca1500-variable-names-should-not-match-field-names_1.vb)]
 [!code-csharp[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/CSharp/ca1500-variable-names-should-not-match-field-names_1.cs)]