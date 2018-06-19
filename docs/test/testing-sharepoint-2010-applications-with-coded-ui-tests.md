---
title: Visual Studio'da kodlanmış UI testleriyle SharePoint uygulamaları sınama
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 5a23ed3a56c0d4b8daf8086e07ae04206c52ac4a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31979457"
---
# <a name="test-sharepoint-applications-with-coded-ui-tests"></a>Kodlanmış UI testleriyle SharePoint uygulamaları sınama

Kodlanmış UI testleri bir SharePoint uygulama da dahil olmak üzere, kendi kullanıcı Arabirimi denetimlerini dahil olmak üzere tüm uygulama düzgün çalıştığını doğrulamak olanak tanır. Kodlanmış UI testleri, değerler ve kullanıcı arabirimi mantığı da doğrulayabilirsiniz.

Kodlanmış UI testleri kullanmanın avantajları hakkında daha fazla bilgi için bkz: [kodunuzu test etmek için kullanım UI Otomasyonu](../test/use-ui-automation-to-test-your-code.md).

**Gereksinimler**

- Visual Studio Enterprise

## <a name="create-a-coded-ui-test-for-a-sharepoint-app"></a>Bir SharePoint uygulaması için kodlanmış UI testi oluşturma

[Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md) SharePoint uygulamalarınız için uygulamalarının diğer türleri için testler oluşturma ile aynıdır. Kaydı ve kayıttan yürütme Web düzenleme arabirimi tüm denetimler için desteklenir. Kategoriler ve web bölümleri seçme arabirimi olan tüm standart web denetimleri.

![SharePoint web bölümleri](../test/media/cuit_sharepoint.png)

> [!NOTE]
> Eylem kaydı yapıyorsanız, kod oluşturmadan önce eylemleri doğrulayın. Bazı davranışları fare vurgulu ile ilişkili olduğundan, varsayılan olarak açıktır. Yedek gezinen kodlanmış UI testleri kaldırmak dikkatli olun. Test için kodu düzenleme veya kullanarak bunu yapabilirsiniz [kodlanmış UI Test Düzenleyicisi](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).

## <a name="test-office-controls-within-a-sharepoint-app"></a>Bir SharePoint uygulama içinde test Office denetimleri

Bazı office web bölümleri SharePoint uygulamanızda otomasyonunu sağlamak için bazı küçük kod değişiklikler yapmanız gerekir.

> [!NOTE]
> Bir SharePoint uygulamasında Visio ve PowerPoint denetimleri sınama desteklenmiyor.

### <a name="excel-cell-controls"></a>Excel hücre denetimleri

Excel hücre denetimleri eklemek için kodlanmış UI testin kodda bazı değişiklikler yapmanız gerekir.

> [!WARNING]
> Ok anahtar eylemi tarafından izlenen tüm Excel hücresindeki metin girerek doğru kaydetmez. Hücreleri seçmek için fareyi kullanın.

Boş bir hücre eylemleri kaydediyorsanız çift tıklayarak hücreyi tıklayarak ve kümesi metin işlemi gerçekleştirme kodu değiştirmeniz gerekir. Tüm klavye eylemi tarafından izlenen hücre tıklama etkinleştirir olduğundan bu gereklidir `textarea` hücre içinde. Yalnızca kaydı bir `setvalue` üzerinde boş bir hücre arama `editbox` hücre tıklattınız kadar var olmayan. Örneğin:

```csharp
Mouse.DoubliClick(uiItemCell,new Point(31,14));
uiGridKeyboardInputEdit.Text=value;
```

Boş olmayan hücre eylemleri kaydı sonra çünkü kaydı biraz daha karmaşık alır bir hücreye metin ekleme şu anda yeni bir \<div > denetimi hücrenin bir alt öğesi olarak eklenir. Yeni \<div > Denetim girdiğiniz metni içerir. Kaydedici eylemleri yeni kaydetmek gereken \<div > kontrol; ancak, çünkü olamaz yeni \<div > Denetim yok kadar test girildikten sonra. Bu sorunu uyum sağlamak için aşağıdaki kod değişiklikleri el ile yapmalısınız.

1. Hücre başlatma gidin ve olun `RowIndex` ve `ColumnIndex` birincil özellikleri:

    ```csharp
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. RowIndex] = "3";
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. ColumnIndex] = "3";
    ```

2. Bul `HtmlDiv` hücrenin alt:

    ```csharp
    private UITestControl getControlToDoubleClick(HtmlCell cell)
    {
         if (String.IsNullOrEmpty(cell.InnerText)) return cell;
         HtmlDiv pane = new HtmlDiv(cell);
         pane.FilterProperties[HtmlDiv.PropertyNames.InnerText] = cell.InnerText;
         // Class is an important property in finding pane
         pane.FilterProperties[HtmlDiv.PropertyNames.Class] = "cv-nwr";
         UITestControlCollection panes = pane.FindMatchingControls();
         return panes[0];
    }
    ```

3. Fare çift için eylem kodu ekleyin `HtmlDiv`:

    ```csharp
    Mouse.DoubleClick(uIItemPane, new Point(31, 14)); )
    ```

4. Metni ayarlamak için kod ekleme `TextArea`:

    ```csharp
    uIGridKeyboardInputEdit.Text = value; }
    ``

## See also

- [Use UI Automation To Test Your Code](../test/use-ui-automation-to-test-your-code.md)
- [Create SharePoint Solutions](/office-dev/office-dev/create-sharepoint-solutions)
- [Verifying and Debugging SharePoint Code](/office-dev/office-dev/verifying-and-debugging-sharepoint-code)
- [Building and Debugging SharePoint Solutions](/office-dev/office-dev/building-and-debugging-sharepoint-solutions)
- [Profiling the Performance of SharePoint Applications](/office-dev/office-dev/profiling-the-performance-of-sharepoint-applications)
