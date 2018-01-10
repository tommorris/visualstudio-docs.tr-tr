---
title: "Kodlanmış UI testi denetimlerinizin etkinleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 782a68e61786121095d3bf730dbd053564bad1cf
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="enable-coded-ui-testing-of-your-controls"></a>Denetimlerinizin Kodlanmış UI Testlerini Etkinleştirme
Kodlanmış UI test çerçevesi için destek uygularsanız, denetim daha kolayca sınanabilir. Artan düzeyde destek artımlı olarak ekleyebilirsiniz. Kaydı ve kayıttan yürütme ve özellik doğrulama destekleyerek başlatabilirsiniz. Bu konudaki denetiminizin özel özellikler tanımak kodlanmış UI test derleyicisini izin vermek için oluşturun ve oluşturulan koddan bu özelliklere erişmek için özel sınıflar sağlar. Kodlanmış UI test Oluşturucu yakalama eylemlerini kaydedilen eylem amacı yakın bir şekilde de yardımcı olabilir.

![CUIT &#95; Tam](../test/media/cuit_full.png "CUIT_Full")  
  
##  <a name="recordandplayback"></a>Erişilebilirlik uygulayarak kaydı ve kayıttan yürütme ve özellik doğrulama desteği  
 Kodlanmış UI test derleyicisini kayıt sırasında karşılaştığı ve bu oturuma yeniden yürütme için kod oluşturur denetimleri hakkında bilgi yakalar. Denetim erişilebilirlik desteklemiyorsa, kodlanmış UI test derleyicisini ekran koordinatları kullanarak (fare tıklamaları gibi) eylemleri yakalar. Test geri yürütüldüğünde oluşturulan kod bu fare tıklatma aynı ekran koordinatları ile gönderirsiniz. Testi kayıttan yürütülürken denetiminizi farklı bir yerde ekranda görünürse oluşturulan kod denetiminizde bu eylemi gerçekleştirmek başarısız olur. Testi farklı ekran yapılandırmalarında, farklı ortamlar veya olmuştur sonra UI düzeninde değişiklikler geri çalınırsa, bu hatalarına neden olabilir.  
  
 ![CUIT &#95; RecordNoSupport](../test/media/cuit_recordnosupport.png "CUIT_RecordNoSupport")  
  
 Erişilebilirlik uygularsanız, yine de kodlanmış UI test derleyicisini, bir test kaydeder ve kod oluşturur, denetimi hakkında bilgi yakalamak için kullanır. Testi çalıştırdığınızda, kullanıcı arabiriminde başka bir yere olsa bile, daha sonra oluşturulan kodu karşı denetim olayları kullanılmaya devam. Test yazarları aynı zamanda kurulamayacak oluşturmak denetiminizi temel özelliklerini kullanarak onaylar.  
  
 ![CUIT &#95; Kayıt](../test/media/cuit_record.png "CUIT_Record")  
  
### <a name="to-support-record-and-playback-property-validation-and-navigation-for-a-windows-forms-control"></a>Bir Windows forms denetimi için kayıt ve kayıttan yürütme, özellik doğrulama ve gezinti desteklemek için  
 Aşağıdaki yordamda özetlendiği gibi denetim için erişilebilirlik uygulamak ve ayrıntılı olarak açıklanmıştır <xref:System.Windows.Forms.AccessibleObject>.  
  
 ![CUIT &#95; Erişilebilir](../test/media/cuit_accessible.png "CUIT_Accessible")  
  
1.  Türeyen bir sınıf uygulama <xref:System.Windows.Forms.Control.ControlAccessibleObject>ve geçersiz kılma <xref:System.Windows.Forms.Control.AccessibilityObject%2A> özelliği, sınıfın bir nesnesi döndürür.  
  
    ```csharp  
    public partial class ChartControl : UserControl  
    {  
        // Overridden to return the custom AccessibleObject for the control.  
        protected override AccessibleObject CreateAccessibilityInstance()  
        {  
            return new ChartControlAccessibleObject(this);  
        }  
  
        // Inner class ChartControlAccessibleObject represents accessible information  
        // associated with the ChartControl and is used when recording tests.  
        public class ChartControlAccessibleObject : ControlAccessibleObject  
        {  
            ChartControl myControl;  
            public ChartControlAccessibleObject(ChartControl ctrl)  
                : base(ctrl)  
            {  
                myControl = ctrl;  
            }  
        }  
    }  
    ```  
  
2.  Erişilebilir nesnenin geçersiz kılma <xref:System.Windows.Forms.AccessibleObject.Role%2A>, <xref:System.Windows.Forms.AccessibleObject.State%2A>, <xref:System.Windows.Forms.AccessibleObject.GetChild%2A> ve <xref:System.Windows.Forms.AccessibleObject.GetChildCount%2A> özellikleri ve yöntemleri.  
  
3.  Alt denetimi için başka bir erişilebilirlik nesnesi uygulamak ve alt denetim geçersiz kılma <xref:System.Windows.Forms.Control.AccessibilityObject%2A> özelliği bu erişilebilirlik nesnesi döndürür.  
  
4.  Geçersiz kılma <xref:System.Windows.Forms.AccessibleObject.Bounds%2A>, <xref:System.Windows.Forms.AccessibleObject.Name%2A>, <xref:System.Windows.Forms.AccessibleObject.Parent%2A>, <xref:System.Windows.Forms.AccessibleObject.Role%2A>, <xref:System.Windows.Forms.AccessibleObject.State%2A>, <xref:System.Windows.Forms.AccessibleObject.Navigate%2A>, ve <xref:System.Windows.Forms.AccessibleObject.Select%2A> alt denetimin erişilebilirlik nesnesi için özellikleri ve yöntemleri.  
  
> [!NOTE]
>  Bu konu erişilebilirlik örnek ile başlayan <xref:System.Windows.Forms.AccessibleObject> bu yordamı ve ardından derlemelerde kalan yordamları üzerindeki. Erişilebilirlik örneğinin çalışan bir sürüm oluşturmak istiyorsanız, bir konsol uygulaması oluşturun ve ardından Program.cs kodda örnek kod ile değiştirin. Erişilebilirlik, System.Drawing ve System.Windows.Forms başvuruları eklemeniz gerekir. Değiştirmeniz gerektiğini **birlikte çalışma türlerini katıştır** erişilebilirlik için **False** bir yapı uyarı ortadan kaldırmak için. Proje çıktı türünden için değiştirebileceğiniz **konsol uygulaması** için **Windows uygulaması** böylece bir konsol penceresi görünmüyor çalıştırdığınızda uygulama.  
  
##  <a name="customproprties"></a>Bir özellik sağlayıcısı uygulayarak özel özellik doğrulama desteği  
 Kaydı ve kayıttan yürütme ve özelliği doğrulama için temel destek uyguladık sonra denetiminizin özel özellikler kodlanmış UI testleri için kullanılabilir uygulayarak yapabileceğiniz bir <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> eklentisi. Örneğin, aşağıdaki yordamı grafik denetiminin CurveLegend alt denetimleri State özelliği erişmek kodlanmış UI testleri sağlayan bir özellik sağlayıcısı oluşturur.  
  
 ![CUIT &#95; CustomProps](../test/media/cuit_customprops.png "CUIT_CustomProps")  
  
### <a name="to-support-custom-property-validation"></a>Özel özellik doğrulamayı desteklemek için

![CUIT &#95; Özellik](../test/media/cuit_props.png "CUIT_Props")

1. Eğri gösterge erişilebilir nesnenin geçersiz kılma <xref:System.Windows.Forms.AccessibleObject.Description%2A> özellik açıklama dizesi zengin özellik değerleri geçirmek için noktalı virgülle (;) ana Açıklama (ve birbirlerine birden çok özellik uyguluyorsanız) ayrılmış.  
  
    ```csharp  
    public class CurveLegendAccessibleObject : AccessibleObject  
    {  
        // add the state property value to the description  
        public override string Description  
        {  
            get  
            {  
                // Add ";" and the state value to the end  
                // of the curve legend's description  
                return "CurveLegend; " + State.ToString();  
            }  
        }  
    }  
    ```  

1. Bir UI testi uzantısı paketi denetlemek için bir sınıf kitaplığı projesi oluşturarak oluşturun ve erişilebilirlik, Microsoft.VisualStudio.TestTools.UITesting, Microsoft.VisualStudio.TestTools.UITest.Common, başvurular ekleyin ve Microsoft.VisualStudio.TestTools.Extension. Değişiklik **birlikte çalışma türlerini katıştır** erişilebilirlik için **False**.

1. Türetilmiş bir özellik sağlayıcısı sınıfı ekleme <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>:

    ```csharp
    using System;
    using System.Collections.Generic;
    using Accessibility;
    using Microsoft.VisualStudio.TestTools.UITesting;
    using Microsoft.VisualStudio.TestTools.UITest.Extension;
    using Microsoft.VisualStudio.TestTools.UITesting.WinControls;
    using Microsoft.VisualStudio.TestTools.UITest.Common;

    namespace ChartControlExtensionPackage
    {
        public class ChartControlPropertyProvider : UITestPropertyProvider
        {
        }
    }
    ```

1. Özellik adları ve özellik tanımlayıcıların koyarak özellik sağlayıcısı uygulayan bir <xref:System.Collections.Generic.Dictionary%602>.

1. Geçersiz kılma <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetControlSupportLevel%2A?displayProperty=fullName> derlemenizi denetiminizi ve alt denetim özgü destek sağlar belirtmek için.

1. Kalan Özet yöntemlerini geçersiz kılar<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider?displayProperty=fullName>

1. Türetilmiş bir uzantı paketini sınıfı ekleme <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>.

1. Tanımlamak `UITestExtensionPackage` derleme özniteliği.

1. Uzantı paketini sınıfında geçersiz kılma <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A?displayProperty=fullName> özellik sağlayıcısı istendiğinde özellik sağlayıcısı sınıfı dönün.

1. Kalan Özet yöntemlerini ve özelliklerini geçersiz kılmak <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>.

1. İkili dosyaları oluşturmak ve kopyalamak için **%ProgramFiles%\Common\Microsoft Shared\VSTT\10.0\UITestExtensionPackages**.  

> [!NOTE]
> Bu uzantı paketinin "Metin" türünde herhangi bir denetimi uygulanır. Aynı türde birden çok denetim test ediyorsanız ayrı ayrı test ve testleri kaydettiğinizde hangi uzantı paketleri dağıtılan yönetmek gerekir.

##  <a name="codegeneration"></a>Erişim özel özellikleri sınıfına uygulayarak kod oluşturma desteği

Kodlanmış UI test derleyicisini oturum kaydından kodu oluşturduğunda kullanan <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl> denetimlerinizi erişmek için sınıf.

Denetimin özel özellikler erişim sağlamak için bir özellik sağlayıcısı uyguladık, böylece oluşturulan kod Basitleştirilmiş bu özelliklere erişmek için kullanılan özel bir sınıf ekleyebilirsiniz.

### <a name="to-add-a-specialized-class-to-access-your-control"></a>Denetim erişmek için özel bir sınıf eklemek için

![CUIT &#95; CodeGen](../test/media/cuit_codegen.png "CUIT_CodeGen")  

1. Türetilmiş bir sınıf uygulama <xref:Microsoft.VisualStudio.TestTools.UITesting.WinControls.WinControl> ve denetimin türü oluşturucuda arama özellikleri koleksiyonuna ekleyin.  

1. Denetimin özel özellikler sınıfının özelliklerine uygular.  

1. Özellik sağlayıcınızın geçersiz kılma <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetSpecializedClass%2A?displayProperty=fullName> gösterge alt denetimleri eğri için yeni bir sınıf türü döndürülecek yöntemi.  

1. Özellik sağlayıcınızın geçersiz kılma <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetPropertyNamesClassType%2A> yöntemi yeni sınıf PropertyNames yöntemi türünü döndürür.

##  <a name="intentawareactions"></a>Bir eylem filtresi uygulayarak hedefi algılayan eylemleri destekler  
 Visual Studio test kaydettiğinde, her fare ve klavye olay yakalar. Ancak, bazı durumlarda, fare ve klavye olaylarının serisinde eylemi amacı kaybedilebilir. Örneğin, denetim otomatik tamamlama destekliyorsa, farklı bir ortamda test geri yürütüldüğünde fare ve klavye olaylarının aynı kümesi farklı bir değer sonuçlanabilir. Klavye ve fare olayları dizi tek bir eylem ile değiştiren bir eylem filtresi eklenti ekleyebilirsiniz. Bu şekilde, bir değerin değeri ayarlar tek bir eylemle seçimdeki kaynaklanan fare ve klavye olaylarını dizi değiştirebilirsiniz. Böylece, kodlanmış UI testleri farklılıkları otomatik tamamlama bir ortamdan diğerine önler.  
  
### <a name="to-support-intent-aware-actions"></a>Hedefi algılayan eylemleri desteklemek için

![CUIT &#95; Eylemler](../test/media/cuit_actions.png "CUIT_Actions")  

1. Türetilmiş bir eylem filtresi sınıf uygulama <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>, özelliklerini geçersiz kılma <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> ve <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A>. 

1. Geçersiz kılma <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ProcessRule%2A>. Örnek realpces çift tıklatma eylemi tek bir eylemi buraya tıklayın.

1. Eylem Filtresi Ekle <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A> uzantısı paketinin yöntemi.

1. İkili dosyaları oluşturmak ve bunları %ProgramFiles%\Common Files\Microsoft Shared\VSTT\10.0\UITestExtensionPackages kopyalayın.

> [!NOTE]
> Eylem filtresi erişilebilirlik uygulama veya özellik sağlayıcısı bağlı değildir.

## <a name="debug-your-property-provider-or-action-filter"></a>Özellik sağlayıcısı veya eylem filtresi hata ayıklama

Özellik sağlayıcısı ve eylem filtresi, yüklenen ve kodlanmış UI test derleyicisini uygulamanızdan ayrı bir işlemde tarafından çalıştırılan uzantı paketinin uygulanır.

#### <a name="to-debug-your-property-provider-or-action-filter"></a>Özellik sağlayıcısı veya eylem filtresi hata ayıklamak için  
  
1.  Hata ayıklama sürümü uzantı paketini kopyasının .dll ve %ProgramFiles%\Common Files\Microsoft Shared\VSTT\10.0\UITestExtensionPackages .pdb dosyaları oluşturun.  
  
2.  Uygulamanızı (ayıklayıcıda değil) çalıştırın.  
  
3.  Kodlanmış UI test derleyicisini çalıştırın.  
  
     `codedUITestBuilder.exe  /standalone`  
  
4.  Hata ayıklayıcı codedUITestBuilder işleme iliştirilemiyor.  
  
5.  Kesme noktaları kodunuzda ayarlayın.  
  
6.  Kodlanmış UI test derleyicisini içinde oluşturma özelliği sağlayıcınız çalışma ve eylem filtrelerini çalışma Eylemler kaydetmek için onaylar.  
  
## <a name="external-resources"></a>Dış kaynaklar  
  
### <a name="guidance"></a>Kılavuz  
 [Visual Studio 2012 - bölüm 2 ile sürekli teslimat için test etme: birim testi: iç test etme](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.AccessibleObject>   
 [Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)
