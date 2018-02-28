---
title: "Şerit XML | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VSTO.Ribbon.RibbonXMLItem
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, XML
- customizing the Ribbon, XML
- Ribbon [Office development in Visual Studio], XML
- callback methods
- custom Ribbon, displaying
- custom Ribbon, defining behavior
- XML [Office development in Visual Studio], Ribbon
- customizing the Ribbon, defining behavior
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, displaying
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: e12489431a7496b1d64d5aef93a24fcc239be81a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="ribbon-xml"></a>Şerit XML
  Şerit (XML) öğesi bir Şerit XML kullanarak özelleştirmenize olanak sağlar. Şerit (Görsel Tasarımcı) öğesi tarafından desteklenmeyen bir yolla Şerit'özelleştirmek istiyorsanız Şerit (XML) öğesini kullanın. Her bir öğeyle ne yapabileceğinizi karşılaştırması için bkz: [Şerite Genel Bakış](../vsto/ribbon-overview.md).  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="adding-a-ribbon-xml-item-to-a-project"></a>Projeye Şerit (XML) öğesi ekleme  
 Ekleyebileceğiniz bir **Şerit (XML)** tüm Office projeden öğesine **Yeni Öğe Ekle** iletişim kutusu. Visual Studio, aşağıdaki dosyaları projenize otomatik olarak ekler:  
  
-   Şerit XML dosyası. Bu dosya, Şerit kullanıcı arabirimi (UI) tanımlar. Bu dosya, sekmeler, gruplar ve denetimler gibi kullanıcı Arabirimi öğeleri eklemek için kullanın. Ayrıntılar için bkz [Şerit XML dosya başvurusu](#RibbonDescriptorFile) bu konuda daha sonra.  
  
-   Şerit kod dosyası. Bu dosyayı içeren *Şerit sınıfı*. Bu sınıf için belirtilen ada sahip **Şerit (XML)** öğesi **Yeni Öğe Ekle** iletişim kutusu. Microsoft Office uygulamaları, özel Şerit yüklemek için bu sınıfın örneğini kullanın. Ayrıntılar için bkz [Şerit sınıfı başvurusu](#RibbonExtensionClass) bu konuda daha sonra.  
  
 Varsayılan olarak, bu dosyaları özel bir gruba eklemek **eklentileri** Şerit sekmesindedir.  
  
## <a name="displaying-the-custom-ribbon-in-a-microsoft-office-application"></a>Özel Şerit bir Microsoft Office uygulamasında görüntüleme  
 Eklediğiniz sonra bir **Şerit (XML)** öğesi projeniz için kod eklemelisiniz **ThisAddIn**, **ThisWorkbook**, veya **ThisDocument** sınıfı yöntemini geçersiz kılar ve Şerit XML sınıfını Office uygulamaya döndürür.  
  
 Aşağıdaki kod örneğinde yöntemini geçersiz kılar ve MyRibbon adlı bir Şerit XML sınıf döndürür.  
  
 [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/CSharp/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.cs#1)]
 [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../vsto/codesnippet/VisualBasic/Trin_Ribbon_Custom_Tab_XML_O12/ThisAddIn.vb#1)]  
  
## <a name="defining-the-behavior-of-the-custom-ribbon"></a>Özel Şerit davranışını tanımlama  
 Oluşturarak Şerit üzerindeki bir düğmeye tıklanması gibi kullanıcı eylemleri yanıt verebilirsiniz *geri arama yöntemleri*. Windows Forms denetimlerindeki olaylar geri arama yöntemleri benzer, ancak UI öğesinin XML bir öznitelik tarafından tanımlanır. Şerit sınıfında yöntemler yazmak ve bir denetim öznitelik değeri olarak aynı ada sahip yöntemini çağırır. Örneğin, bir kullanıcı Şerit üzerindeki düğmesine tıkladığında çağrılan bir geri çağırma yöntemi oluşturabilirsiniz. İki adımı, bir geri çağırma yöntemi oluşturmak için gereklidir:  
  
-   Bir geri çağırma yöntemi kodunuzda tanımlayan Şerit XML dosyasındaki bir denetim için bir öznitelik atayın.  
  
-   Geri çağırma yöntemi Şerit sınıfında tanımlayın.  
  
> [!NOTE]  
>  Outlook için ek bir adım gereklidir. Daha fazla bilgi için bkz: [Outlook için Şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md).  
  
 Şerit'ten bir uygulamanın nasıl izlenecek yol için bkz: [izlenecek yol: Şerit XML kullanarak tarafından özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md).  
  
### <a name="assigning-callback-methods-to-controls"></a>Geri arama yöntemleri denetimlere atama  
 Şerit XML dosyasındaki bir denetim için bir geri çağırma yöntemi atamak için geri çağırma yöntemi türünü ve yöntemin adını belirten bir özniteliği ekleyin. Örneğin, aşağıdaki öğeyi sahip iki durumlu düğme tanımlayan bir **eylem anında** adlı geri çağırma yöntemi `OnToggleButton1`.  
  
```  
<toggleButton id="toggleButton1" onAction="OnToggleButton1" />  
```  
  
 **Eylem anında** kullanıcı belirli bir denetim ile ilişkili olan ana görevi gerçekleştirdiğinde olarak adlandırılır. Örneğin, **eylem anında** kullanıcı düğmesini tıklattığında iki durumlu düğme geri arama yöntemi çağrılır.  
  
 Öznitelikte belirttiğiniz yöntemi herhangi bir ad olabilir. Ancak, bu Şerit kod dosyasında tanımladığınız yöntemin adı eşleşmelidir.  
  
 Farklı türlerde Şerit denetimleri atayabilirsiniz geri arama yöntemleri vardır. Her denetim için geri çağırma yöntemlerini tam bir listesi için teknik makalesine bakın [geliştiriciler (Bölüm 3 / 3) için Office (2007) Şerit kullanıcı arabirimi özelleştirme](http://msdn.microsoft.com/en-us/a16c7df5-93f3-4920-baa8-7b7290794c15).  
  
###  <a name="CallBackMethods"></a>Geri arama yöntemleri tanımlama  
 Şerit kod dosyası Şerit sınıfındaki geri arama yöntemleri tanımlar. Bir geri çağırma yöntemi birkaç gereksinimlere sahiptir:  
  
-   Bu genel olarak bildirilmesi gerekir.  
  
-   Şerit XML dosyasındaki bir denetime atanmış bir geri çağırma yöntemi adı adıyla eşleşmelidir.  
  
-   İmzası ilişkili Şerit denetimi için kullanılabilir geri çağırma yöntemi türü imza eşleşmesi gerekir.  
  
 Şerit denetimleri geri arama yöntemi imzalarının tam listesi için teknik makalesine bakın [geliştiriciler (Bölüm 3 / 3) için Office (2007) Şerit kullanıcı arabirimi özelleştirme](http://msdn.microsoft.com/en-us/a16c7df5-93f3-4920-baa8-7b7290794c15). Visual Studio Şerit kod dosyasında oluşturduğunuz geri arama yöntemleri için IntelliSense desteği sağlamaz. Bir geri çağırma yöntemi oluşturursanız, geçerli bir imzası eşleşmiyor, kod derlenir, ancak kullanıcı denetimi tıklattığında hiçbir şey olmaz.  
  
 Tüm geri arama yöntemleri sahip bir <xref:Microsoft.Office.Core.IRibbonControl> denetimi temsil eden yönteminden parametresi. Birden çok denetim için aynı geri çağırma yöntemi yeniden kullanmak için bu parametreyi kullanın. Aşağıdaki kod örneğinde gösteren bir **eylem anında** bağlı olarak, kullanıcı denetimi tıklattığında farklı görevler gerçekleştiren geri çağırma yöntemi.  
  
 [!code-csharp[Trin_RibbonOutlookBasic#2](../vsto/codesnippet/CSharp/Trin_RibbonOutlookBasic/Ribbon1.cs#2)]
 [!code-vb[Trin_RibbonOutlookBasic#2](../vsto/codesnippet/VisualBasic/Trin_RibbonOutlookBasic/Ribbon1.vb#2)]  
  
##  <a name="RibbonDescriptorFile"></a>Şerit XML dosya başvurusu  
 Şerit XML dosyasına, özel bir Şerit ekleme öğeleri ve öznitelikleri tarafından tanımlayabilirsiniz. Varsayılan olarak, aşağıdaki XML Şerit XML dosyası içeriyor.  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<customUI xmlns="http://schemas.microsoft.com/office/2006/01/customui" onLoad="OnLoad">  
  <ribbon>  
    <tabs>  
      <tab idMso="TabAddIns">  
        <group id="MyGroup"  
               label="My Group">  
        </group>  
      </tab>  
    </tabs>  
  </ribbon>  
</customUI>  
```  
  
 Aşağıdaki tabloda Şerit XML dosyasının varsayılan öğeleri açıklanır.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|**customUI**|Özel Şerit VSTO eklenti projesindeki temsil eder.|  
|**Şerit**|Şerit temsil eder.|  
|**sekmeleri**|Şerit Sekmeleri kümesini temsil eder.|  
|**sekmesi**|Tek bir Şerit sekmesini temsil eder.|  
|**Grup**|Şerit sekmesindeki denetimleri grubunu temsil eder.|  
  
 Bu öğeleri görünümünü ve özel Şerit davranışını belirtin özniteliklere sahiptir. Aşağıdaki tabloda Şerit XML dosyasındaki varsayılan öznitelikleri açıklanmaktadır.  
  
|Öznitelik|Üst öğesi|Açıklama|  
|---------------|--------------------|-----------------|  
|**Yüklendiğinde**|**customUI**|Uygulama Şerit yüklediğinde çağrılan bir yöntemi tanımlar.|  
|**idMso**|**sekmesi**|Şerit'i görüntülemek üzere yerleşik bir sekmeyi tanımlar.|  
|**id**|**Grup**|Grubu tanımlar.|  
|**Etiket**|**Grup**|Görüntülenen metni grubunda belirtir.|  
  
 Varsayılan öğeleri ve öznitelikleri Şerit XML dosyasındaki öğeleri ve kullanılabilir özniteliklerinin küçük bir alt kümesidir. Kullanılabilir öğeleri ve öznitelikleri tam listesi için teknik makalesine bakın [geliştiriciler (Kısım 2 / 3) için Office (2007) Şerit kullanıcı arabirimi özelleştirme](http://msdn.microsoft.com/en-us/6b904f55-525f-4520-9b81-a017db65657b).  
  
##  <a name="RibbonExtensionClass"></a>Şerit sınıfı başvurusu  
 Visual Studio Şerit sınıfı Şerit kod dosyasında oluşturur. Şerit üzerindeki denetimleri için geri çağırma yöntemleri bu sınıfına ekleyin. Bu sınıf uygulayan <xref:Microsoft.Office.Core.IRibbonExtensibility> arabirimi.  
  
 Aşağıdaki tabloda bu sınıftaki varsayılan yöntemleri açıklar.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|`GetCustomUI`|Şerit XML dosyasının içeriğini döndürür. Microsoft Office uygulamaları, özel bir Şerit kullanıcı arabiriminin tanımlayan bir XML dizesini elde etmek için bu yöntemi çağırır. Bu yöntem uygulayan <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> yöntemi. **Not:** `GetCustomUI` sadece Şerit XML dosyasının; içeriğini döndürmek için uygulanması VSTO Eklentinizi başlatmak için kullanılmamalıdır. Özellikle, iletişim kutularını veya diğer windows görüntülemeye denemelisiniz değil, `GetCustomUI` uygulaması. Aksi takdirde, özel Şerit doğru çalışmayabilir. VSTO eklentinizi başlatır kodu çalıştırmak varsa, kodu ekleyin `ThisAddIn_Startup` olay işleyicisi.|  
|`OnLoad`|Atar <xref:Microsoft.Office.Core.IRibbonControl> parametresi `ribbon` alan. Özel Şerit yüklediğinizde Microsoft Office uygulamaları bu yöntemi çağırın. Özel Şerit dinamik olarak güncelleştirmek için bu alanı kullanabilirsiniz. Daha fazla bilgi için teknik makalesine bakın [geliştiriciler (Kısım 1 / 3) için Office (2007) Şerit kullanıcı arabirimi özelleştirme](http://msdn.microsoft.com/en-us/a4fd6d18-d4a8-4e64-bd89-f437208573d3).|  
|`GetResourceText`|Tarafından çağrılır `GetCustomUI` Şerit XML dosyasının içeriğini elde etmek için yöntemi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerite Genel Bakış](../vsto/ribbon-overview.md)   
 [İzlenecek yol: Şerit XML kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)   
 [Office Kullanıcı Arabirimini Özelleştirme](../vsto/office-ui-customization.md)  
  
  