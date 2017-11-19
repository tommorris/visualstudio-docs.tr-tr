---
title: 'CA1300: MessageBoxOptions belirtme | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e4ce736aa64cba9d66d770f3c4297c1685d690f6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300: MessageBoxOptions belirtme
|||  
|-|-|  
|TypeName|SpecifyMessageBoxOptions|  
|CheckId|CA1300|  
|Kategori|Microsoft.Globalization|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir aşırı yüklemesini bir yöntemi çağırır <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> değil sürer yöntemi bir <xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName> bağımsız değişkeni.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Doğru bir sağdan sola okuma düzeni kullanan kültürler için bir ileti kutusu görüntülemek için <xref:System.Windows.Forms.MessageBoxOptions> ve <xref:System.Windows.Forms.MessageBoxOptions> üyeleri <xref:System.Windows.Forms.MessageBoxOptions> numaralandırma geçirilen, için <xref:System.Windows.Forms.MessageBox.Show%2A> yöntemi. İncelemek <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName> bir sağdan sola okuma sırası kullanıp kullanmayacağınızı belirlemek için içeren denetiminin özelliği.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için bir aşırı yüklemesini çağırın <xref:System.Windows.Forms.MessageBox.Show%2A> yönteminin alan bir <xref:System.Windows.Forms.MessageBoxOptions> bağımsız değişkeni.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Kod kitaplığı sağdan sola okuma düzeni kullanan bir kültür için yerelleştirilen değil olduğunda bir uyarı bu kuraldan bastırmak güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kültürü okuma sırası için uygun seçenekleri içeren bir ileti kutusu görüntüler bir yöntemi gösterir. Görünmeyen bir kaynak dosyası örneği oluşturmak için gereklidir. Kaynak dosyası olmadan örneği oluşturmak ve sağdan sola özelliği test etmek için örnekte açıklamaları izleyin.  
  
 [!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
 [!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Resources.ResourceManager?displayProperty=fullName>   
 [Masaüstü uygulamalarındaki kaynaklar](/dotnet/framework/resources/index)