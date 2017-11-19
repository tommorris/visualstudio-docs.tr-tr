---
title: "Kodlanmış UI testinin anatomisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: coded UI tests
ms.assetid: 9c5d82fc-3fb7-4bb1-a9ac-ac1fa3a4b500
caps.latest.revision: "23"
ms.author: douge
manager: douge
ms.openlocfilehash: 5eb576be81849215f1413a7b58c6e460479af7f3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="anatomy-of-a-coded-ui-test"></a>Kodlanmış UI Testinin Anatomisi
Kodlanmış UI test projesinde Kodlanmış bir UI testi oluşturduğunuzda, birkaç dosyaları çözümünüze eklenir. Bu konuda, bu dosyaları keşfetmek için bir örnek kodlanmış UI testi kullanacağız.  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
## <a name="contents-of-a-coded-ui-test"></a>Kodlanmış UI testi içeriğini  
 Kodlanmış bir UI testi, oluşturduğunuzda **kodlanmış UI Test oluşturucusunu** test ve ayrıca test yöntemleri, parametreleri ve altındaki tüm testler için onayların kullanıcı arabiriminin bir harita oluşturur. Ayrıca, her test için bir sınıf dosyası oluşturur.  
  
|Dosya|İçindekiler|Düzenlenebilir mi?|  
|----------|--------------|---------------|  
|[UIMap.Designer.cs](#UIMapDesignerFile)|[Bildirimler bölümü](#UIMapDesignerFile)<br /><br /> [UIMap sınıfı](#UIMapClass) (kısmi, otomatik olarak oluşturulan)<br /><br /> [Yöntemleri](#UIMapMethods)<br /><br /> [Özellikleri](#UIMapProperties)|Hayır|  
|[UIMap.cs](#UIMapCS)|[UIMap sınıfı](#UIMapCS) (kısmi)|Evet|  
|[Codeduıtest1.cs](#CodedUITestCS)|[Codeduıtest1 sınıfı](#CodedUITestCS)<br /><br /> [Yöntemleri](#CodedUITestMethods)<br /><br /> [Özellikleri](#CodedUITestProperties)|Evet|  
|[UIMap.uitest](#UIMapuitest)|UI testi için XML eşlemesi.|Hayır|  
  
###  <a name="UIMapDesignerFile"></a>UIMap.Designer.cs  
 Bu dosya tarafından otomatik olarak oluşturulan kodu içerir **kodlanmış UI Test oluşturucusunu** test oluşturulduğunda. Bu dosya Ekle veya Değiştir kodu bir dosya olmaması test değişiklikler, her zaman yeniden oluşturulur.  
  
#### <a name="declarations-section"></a>Bildirimler bölümü  
 Bu bölüm aşağıdaki bildirimler için bir Windows kullanıcı arabirimini içerir.  
  
```csharp  
using System;  
using System.CodeDom.Compiler;  
using System.Collections.Generic;  
using System.Drawing;  
using System.Text.RegularExpressions;  
using System.Windows.Input;  
using Microsoft.VisualStudio.TestTools.UITest.Extension;  
using Microsoft.VisualStudio.TestTools.UITesting;  
using Microsoft.VisualStudio.TestTools.UITesting.WinControls;  
using Microsoft.VisualStudio.TestTools.UnitTesting;  
using Keyboard = Microsoft.VisualStudio.TestTools.UITesting.Keyboard;  
using Mouse = Microsoft.VisualStudio.TestTools.UITesting.Mouse;  
using MouseButtons = System.Windows.Forms.MouseButtons;  
```  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.WinControls> Ad alanı, bir Windows kullanıcı arabirimini (UI) eklenir. Bir Web sayfası kullanıcı Arabirimi için ad alanı olacaktır <xref:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls>; bir Windows Presentation Foundation Arabirimi için ad alanı olacaktır <xref:Microsoft.VisualStudio.TestTools.UITesting.WpfControls>.  
  
####  <a name="UIMapClass"></a>UIMap sınıfı  
 Sonraki bölüm dosyasının <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfı.  
  
```  
[GeneratedCode("Coded UITest Builder", "10.0.21221.0")]  
public partial class UIMap  
```  
  
 Sınıf kodu ile başlayan bir <xref:System.CodeDom.Compiler.GeneratedCodeAttribute> kısmi bir sınıf olarak bildirilmiş sınıfa uygulanır. Bu dosyadaki her sınıfa öznitelik de geçerli fark edeceksiniz. Bu sınıf için daha fazla içerebilecek dosya `UIMap.cs`, hangi ele alınmıştır daha sonra.  
  
 Oluşturulan `UIMap` sınıfı, her yöntem test zaman kaydedildiği belirtilen için kod içerir.  
  
```  
public void LaunchCalculator()  
public void AddItems()  
public void VerifyTotal()  
public void CleanUp()  
```  
  
 Bu bölümü <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfı yöntemleri için gereken her bir özellik için oluşturulan kodu da içerir.  
  
```  
public virtual LaunchCalculatorParams LaunchCalculatorParams  
public virtual AddItemsParams AddItemsParams  
public virtual VerifyTotalExpectedValues VerifyTotalExpectedValues  
public virtual CalculateItemsParams CalculateItemsParams  
public virtual VerifyMathAppTotalExpectedValues   
    VerifyMathAppTotalExpectedValues  
public UIStartMenuWindow UIStartMenuWindow  
public UIRunWindow UIRunWindow  
public UICalculatorWindow UICalculatorWindow  
public UIStartWindow UIStartWindow  
public UIMathApplicationWindow UIMathApplicationWindow  
```  
  
#####  <a name="UIMapMethods"></a>UIMap yöntemleri  
 Her yöntem benzer bir yapıya sahip `AddItems()` yöntemi. Bu kodu daha anlaşılır olması eklemek için satır sonları ile birlikte sunulan altında daha ayrıntılı açıklanmıştır.  
  
```  
/// <summary>  
/// AddItems - Use 'AddItemsParams' to pass parameters into this method.  
/// </summary>  
public void AddItems()  
{  
    #region Variable Declarations  
    WinControl uICalculatorDialog =   
        this.UICalculatorWindow.UICalculatorDialog;  
    WinEdit uIItemEdit =   
        this.UICalculatorWindow.UIItemWindow.UIItemEdit;  
    #endregion  
  
    // Type '{NumPad7}' in 'Calculator' Dialog  
    Keyboard.SendKeys(uICalculatorDialog,   
        this.AddItemsParams.UICalculatorDialogSendKeys,   
        ModifierKeys.None);  
  
    // Type '{Add}{NumPad2}{Enter}' in 'Unknown Name' text box  
    Keyboard.SendKeys(uIItemEdit,   
        this.AddItemsParams.UIItemEditSendKeys,   
        ModifierKeys.None);  
}  
```  
  
 Her bir yöntemin tanımı için Özet açıklama hangi sınıfın bu yöntem için parametre değerleri için kullanılacağını söyler. Bu durumda olan `AddItemsParams` daha sonra dosyasında tanımlanan sınıfı `UIMap.cs` dosya ve ayrıca tarafından döndürülen değer türü olduğu `AddItemsParams` özelliği.  
  
 Kodu yöntemi en üstte bir `Variable Declarations` yerel değişkenler için kullanıcı arabirimini tanımlar bölge nesneleri yöntemi tarafından kullanılır.  
  
 Bu yöntemde her ikisi de `UIItemWindow` ve `UIItemEdit` kullanılarak erişilen özellikleri `UICalculatorWindow` daha sonra dosyasında tanımlanan sınıfı `UIMap.cs` dosya.  
  
 Sonraki özelliklerini kullanarak metin klavyeden hesaplayıcı uygulamaya gönder satırları olan `AddItemsParams` nesnesi.  
  
 `VerifyTotal()` Yöntemi çok benzer bir yapıya sahip ve aşağıdaki onay kodunu içerir.  
  
```  
// Verify that 'Unknown Name' text box's property 'Text' equals '9. '  
Assert.AreEqual(  
    this.VerifyTotalExpectedValues.UIItemEditText,   
    uIItemEdit.Text);  
```  
  
 Windows hesap makinesi uygulama geliştiricisi denetimi için genel kullanıma açık bir ad sağlamadığından metin kutusu adı bilinmeyen olarak listelenir. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=fullName> Yöntem gerçek değer testin başarısız olmasına neden olacağından beklenen değer ile eşit olmadığında başarısız olur. Ayrıca, beklenen değer boşluk bırakarak bir Ondalık ayırıcının içerdiğine dikkat edin. Bu belirli test işlevlerini değiştirmek amacıyla varsa, ondalık ayırıcıdan ve boşluğa izin vermesi gerekir.  
  
#####  <a name="UIMapProperties"></a>UIMap özellikleri  
 Her bir özellik için de sınıfı çok standart kodudur. Aşağıdaki kod `AddItemsParams` özelliği kullanılıyor `AddItems()` yöntemi.  
  
```  
public virtual AddItemsParams AddItemsParams  
{  
    get  
    {  
        if ((this.mAddItemsParams == null))  
        {  
            this.mAddItemsParams = new AddItemsParams();  
        }  
        return this.mAddItemsParams;  
    }  
}  
```  
  
 Özellik adlı özel bir yerel değişken kullanıyor bildirimi `mAddItemsParams` döndürmeden önce değeri tutmak için. Özellik adı ve döndürdüğü nesnesi için sınıf adı aynıdır. Sınıf daha sonra tanımlanan `UIMap.cs` dosya.  
  
 Bir özellik tarafından döndürülen her sınıf benzer şekilde yapılandırılmıştır. Aşağıdaki `AddItemsParams` sınıfı.  
  
```  
/// <summary>  
/// Parameters to be passed into 'AddItems'  
/// </summary>  
[GeneratedCode("Coded UITest Builder", "10.0.21221.0")]  
public class AddItemsParams  
{  
    #region Fields  
    /// <summary>  
    /// Type '{NumPad7}' in 'Calculator' Dialog  
    /// </summary>  
    public string UICalculatorDialogSendKeys = "{NumPad7}";  
  
    /// <summary>  
    /// Type '{Add}{NumPad2}{Enter}' in 'Unknown Name' text box  
    /// </summary>  
    public string UIItemEditSendKeys = "{Add}{NumPad2}{Enter}";  
    #endregion  
}  
```  
  
 Tüm sınıflarda olduğu gibi `UIMap.cs` dosyası, bu sınıf ile başlayan <xref:System.CodeDom.Compiler.GeneratedCodeAttribute>. Bu küçük sınıf bir `Fields` parametreleri olarak kullanılmak üzere dize tanımlayan bölge <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard.SendKeys%2A?displayProperty=fullName> kullanılır yöntemi `UIMap.AddItems()` daha önce bahsedilen yöntemi. Bu parametreleri kullanılan yöntemi çağrılmadan önce bu dize alanlarındaki değerleri değiştirmek üzere kod yazabilirsiniz.  
  
###  <a name="UIMapCS"></a>UIMap.cs  
 Varsayılan olarak, bu dosyayı bir kısmi içeren `UIMap` yöntemleri ya da özellikleri olan sınıfı.  
  
#### <a name="uimap-class"></a>UIMap sınıfı  
 İşlevlerini genişletmek için özel kod oluşturabileceğiniz budur <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfı. Bu dosyada oluşturduğunuz kod tarafından yeniden oluşturulacak değil **kodlanmış UI Test oluşturucusunu** test değiştiren her zaman.  
  
 Tüm parçalarını <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> yöntemleri ve diğer herhangi bir kısmını özelliklerinden kullanabilirsiniz <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> sınıfı.  
  
###  <a name="CodedUITestCS"></a>Codeduıtest1.cs  
 Bu dosya tarafından oluşturulan **kodlanmış UI Test oluşturucusunu**, ancak bu dosya kodda değiştirebilmek için test değiştirildiğinde, her zaman yeniden oluşturulmaz. Dosyanın adını oluşturduğunuz zaman, test için belirttiğiniz addan üretilir.  
  
#### <a name="codeduitest1-class"></a>Codeduıtest1 sınıfı  
 Varsayılan olarak, bu dosya yalnızca bir sınıf için tanım içeriyor.  
  
```  
[CodedUITest]  
public class CodedUITest1  
```  
  
 T:Microsoft.VisualStudio.TestTools.UITesting.CodedUITestAttribute öğesi, bir test uzantısı olarak tanımak test çerçevesi sağlar sınıfına otomatik olarak uygulanır. Ayrıca bu bir parçalı sınıf olmadığına dikkat edin. Tüm sınıf kodu bu dosyada yer alır.  
  
#####  <a name="CodedUITestProperties"></a>Codeduıtest1 özellikleri  
 Sınıfı dosyanın sonunda bulunan iki varsayılan özelliklerini içerir. Bunlar değiştirilmemelidir.  
  
```  
/// <summary>  
/// Gets or sets the test context which provides  
/// information about and functionality for the current test run.  
///</summary>  
public TestContext TestContext  
public UIMap UIMap  
```  
  
#####  <a name="CodedUITestMethods"></a>Codeduıtest1 yöntemleri  
 Varsayılan olarak, sınıfı tek yöntemi içerir.  
  
```  
public void CodedUITestMethod1()  
```  
  
 Bu yöntem her çağırır `UIMap` üzerinde bölümünde açıklanan testinizi kaydettiğiniz zaman belirtilen yöntemi [UIMap sınıfı](#UIMapClass).  
  
 Adlandırılmış bir bölge `Additional test attributes`, kaldırılmamışsa, isteğe bağlı iki yöntem içerir.  
  
```  
// Use TestInitialize to run code before running each test   
[TestInitialize()]  
public void MyTestInitialize()  
{  
    // To generate code for this test, select "Generate Code for Coded   
    // UI Test" from the shortcut menu and select one of the menu items.  
    // For more information on generated code, see   
    // http://go.microsoft.com/fwlink/?LinkId=179463  
  
    // You could move this line from the CodedUITestMethod1() method  
    this.UIMap.LaunchCalculator();  
}  
  
// Use TestCleanup to run code after each test has run  
[TestCleanup()]  
public void MyTestCleanup()  
{  
    // To generate code for this test, select "Generate Code for Coded   
    // UI Test" from the shortcut menu and select one of the menu items.  
    // For more information on generated code, see   
    // http://go.microsoft.com/fwlink/?LinkId=179463  
  
    // You could move this line from the CodedUITestMethod1() method  
    this.UIMap.CloseCalculator();  
}  
```  
  
 `MyTestInitialize()` Yöntemi sahip <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute> , herhangi bir test yöntem önce bu yöntemi çağırmak için test çerçevesi söyler uygulanır. Benzer şekilde, `MyTestCleanup()` yöntemi sahip <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute> uygulanan, bu yöntem tüm diğer test yöntemleri çağırmak için test çerçevesi söyleyen çağrılıp çağrılmadığını. Bu yöntemlerin kullanımı isteğe bağlıdır. Bu test için `UIMap.LaunchCalculator()` yöntemi konumundan çağrılabilir `MyTestInitialize()` ve `UIMap.CloseCalculator()` yöntemi konumundan çağrılabilir `MyTestCleanup()` yerine gelen `CodedUITest1Method1()`.  
  
 Kullanarak daha fazla yöntem bu sınıfa eklerseniz <xref:Microsoft.VisualStudio.TestTools.UITesting.CodedUITestAttribute>, test çerçevesi testin bir parçası her bir yöntemi çağırır.  
  
###  <a name="UIMapuitest"></a>UIMap.uitest  
 Temsil kaydı yapısı kodlanmış UI test XML dosyasını ve tüm bölümleri budur. Bunlar, eylemleri ve sınıfları yöntemleri ve bu sınıfların özelliklerine ek olarak içerir. [UIMap.Designer.cs](#UIMapDesignerFile) dosya kodlanmış UI test yapısı oluşturmaya oluşturucusu tarafından oluşturulur ve test çerçevesi bağlantısı sağlayan kodunu içerir.  
  
 `UIMap.uitest` Dosyası doğrudan düzenlenebilir değil. Ancak, otomatik olarak değiştirir testi değiştirmek için kodlanmış UI Oluşturucusu kullanabilirsiniz `UIMap.uitest` dosya ve [UIMap.Designer.cs](#UIMapDesignerFile) dosya.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.WinControls>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.WpfControls>   
 <xref:System.CodeDom.Compiler.GeneratedCodeAttribute>   
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard.SendKeys%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.CodedUITestAttribute>   
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute>   
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute>   
 [Kodunuzu test etmek için UI otomasyonunu kullanma](../test/use-ui-automation-to-test-your-code.md)   
 [Kodlanmış UI testleri oluşturma](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)   
 [Kodlanmış UI testleri için en iyi yöntemler](../test/best-practices-for-coded-ui-tests.md)   
 [Birden çok UI eşlemesi bulunan büyük uygulamaları sınama](../test/testing-a-large-application-with-multiple-ui-maps.md)   
 [Kodlanmış UI testleri ve eylem kayıtları için desteklenen yapılandırmalar ve platformlar](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
