---
title: 'CA1500: Değişken adları alan adlarıyla eşleşmemelidir | Microsoft Docs'
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
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: fc900de76f0ae31cb3dc770fec681c1b7bed8213
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632090"
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: Değişken adları alan adlarıyla eşleşmemelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2017 ile ilgili en son belgeler için bkz. [CA1500: değişken adları alan adları değil eşleşmelidir](https://docs.microsoft.com/visualstudio/code-quality/ca1500-variable-names-should-not-match-field-names) docs.microsoft.com'da.  
  
|||  
|-|-|  
|TypeName|VariableNamesShouldNotMatchFieldNames|  
|CheckId|CA1500|  
|Kategori|Microsoft.Maintainability|  
|Yeni Değişiklik|Bir alan olarak aynı ada sahip bir parametreyi tetiklendiğinde:<br /><br /> -Hataya neden olmayan - varsa alan ve parametre bildirir yöntemi derlemenin dışından görülemeyen bağımsız olarak, değişiklik.<br />-Bozucu - alanın adını değiştirip derlemesi dışında görülebilir.<br />-- Parametrenin adını değiştirirseniz ve onu bildiren yöntemin, derlemenin dışından görülebilir kesiliyor.<br /><br /> Bir alan olarak aynı ada sahip yerel bir değişken üzerinde tetiklendiğinde:<br /><br /> Alanın yaptığınız değişiklikler ne olursa olsun derlemenin dışından görülemeyen, hataya neden olmayan -.<br />Yerel değişken adını değiştirin ve alan adını değiştirmeyin hataya neden olmayan -.<br />-- Alanın adını değiştirip derlemesi dışında görülebilir kesiliyor.|  
  
## <a name="cause"></a>Sebep  
 Bir örnek yöntemi, bir parametre veya bildirim türü bir örnek alan adı ile eşleşen yerel bir değişken bildirir. Kural ihlal yerel değişkenler yakalamak için test edilen derleme hata ayıklama bilgileri kullanarak oluşturulması gereken ve ilişkili bir program veritabanı (.pdb) dosyası kullanılabilir olmalıdır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Örnek alan adı, parametre veya yerel bir değişken adı eşleştiğinde, örnek alanı kullanılarak erişilen `this` (`Me` içinde [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]), yöntem gövdesi içindeki anahtar sözcüğü. Kod muhafaza ederken, bu fark aklınızdan çıkarın ve parametre/yerel değişkeni hataları müşteri adayları örneği alanına başvuruyor varsayar daha kolaydır. Bu, özellikle uzun metot gövdeleri için geçerlidir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için parametre/değişkeni veya alanı yeniden adlandırın.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iki kural ihlalleri gösterir.  
  
 [!code-csharp[FxCop.Maintainability.VarMatchesField#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Maintainability.VarMatchesField/cs/FxCop.Maintainability.VarMatchesField.cs#1)]
 [!code-vb[FxCop.Maintainability.VarMatchesField#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Maintainability.VarMatchesField/vb/FxCop.Maintainability.VarMatchesField.vb#1)]

