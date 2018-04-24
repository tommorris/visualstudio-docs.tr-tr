---
title: 'CA1300: MessageBoxOptions belirtme'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d2d0b28d804dc6932e66de9dcd758fd05fc888f7
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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
 <xref:System.Resources.ResourceManager?displayProperty=fullName> [Masaüstü uygulamalarındaki kaynaklar](/dotnet/framework/resources/index)