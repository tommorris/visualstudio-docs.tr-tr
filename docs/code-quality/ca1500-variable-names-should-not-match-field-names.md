---
title: "CA1500: Değişken adları alan adlarıyla eşleşmemelidir | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7825078ff4d53ad5d90cdd8765f6f4120805b60f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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