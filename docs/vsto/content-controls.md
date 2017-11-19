---
title: "İçerik denetimleri | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.Toolbox.DropDownListContentControl
- VST.Toolbox.RichTextContentControl
- VST.Toolbox.PlainTextContentControl
- VST.Toolbox.ComboBoxContentControl
- VST.Toolbox.CCBuildingBlockGalleryContentControl
- VST.Toolbox.DatePickerContentControl
- VST.Toolbox.PictureContentControl
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document building blocks [Office development in Visual Studio]
- restricted permissions [Office development in Visual Studio]
- ComboBoxContentControl class
- PictureContentControl class
- PlainTextContentControl class
- Office documents [Office development in Visual Studio], restricted permissions
- RichTextContentControl class
- content controls [Office development in Visual Studio]
- building block gallery [Office development in Visual Studio]
- controls [Office development in Visual Studio], content controls
- GroupContentControl class
- documents [Office development in Visual Studio], restricted permissions
- DropDownListContentControl class
- DatePickerContentControl class
- data binding [Office development in Visual Studio], content controls
- content controls [Office development in Visual Studio], about content controls
- custom XML parts, content controls
- templates [Office development in Visual Studio], content controls
- BuildingBlockGalleryContentControl class
ms.assetid: ed59e522-dd6e-4c82-8d49-f5dbcfcc950d
caps.latest.revision: "65"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5b2950370b35eb8e2f60f15c5de032284c5546f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="content-controls"></a>İçerik Denetimleri
  İçerik denetimleri tasarım belgeleri ve bu özelliklere sahip şablonları sağlamak sizin için bir yol:  
  
-   Form gibi giriş denetlenen bir kullanıcı arabirimi (UI).  
  
-   Kullanıcıların korumalı belge veya şablonun bölümlerini düzenlemesini engellemek kısıtlamaları. Daha fazla bilgi için bkz: [koruma bölümleri belgeler içerik denetimlerini kullanarak tarafından](#Protection).  
  
-   Bir veri kaynağına veri bağlama. Daha fazla bilgi için bkz: [veri içerik denetimlerine bağlama](#DataBinding).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [Word 2007 içerik denetimlerini kullanarak Visual Studio Araçları (3.0) Office sistemi için veri bağlama](http://go.microsoft.com/fwlink/?LinkId=136785).  
  
## <a name="overview-of-content-controls"></a>İçerik denetimlerine genel bakış  
 İçerik denetimleri, her iki kullanıcı giriş ve yazdırma için iyileştirilmiş bir kullanıcı Arabirimi sağlar. İçerik denetimi belgeye eklediğinizde, Denetim kenarlık, başlık ve kullanıcı için yönergeler sağlayan geçici metin tarafından tanımlanır. Kenarlık ve denetim başlık belgenin yazdırılan sürümlerini görünmez.  
  
 Örneğin, bir tarih belgenizi bölümünde girmesini istiyorsanız, belgeye tarih seçici içerik denetimi ekleyebilirsiniz. Standart tarih seçici UI kullanıcılar denetimi tıklattığında görüntülenir. Görüntülenen bölgesel takvimi ayarlamak ve tarih biçimini belirlemek için denetim özelliklerini de ayarlayabilirsiniz. Kullanıcı bir tarih seçtikten sonra denetim UI gizli ve kullanıcı belgeyi yazdırır yalnızca tarih görüntülenir.  
  
 İçerik de Yardım aşağıdakileri denetler:  
  
-   Kullanıcının düzenleme veya bir belge bölümlerini silmesini engeller. Bu, bir belge veya kullanıcıların okuma ancak düzenleyemez açabilmelisiniz şablon bilgileri varsa veya kullanıcıların içerik denetimlerini düzenleyebilir, ancak bunları silmemeniz yapabilmek istiyorsanız kullanışlıdır.  
  
-   Bir belge veya şablon bölümlerini verilere bağlayın. İçerik denetimleri veritabanı alanları, yönetilen nesneleri bağlayabilirsiniz [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)], belge ve diğer veri kaynakları depolanan XML öğeleri.  
  
 Belge düzeyi projelerine içerik denetimlerini belgenize tasarım zamanında veya çalışma zamanında ekleyebilirsiniz. VSTO eklenti projelerinde içerik denetimlerini herhangi bir açık belgeye çalışma zamanında ekleyebilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Word belgelerine içerik denetimlerine ekleme](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
> [!NOTE]  
>  Open XML biçiminde kaydedilen belgelerde içerik denetimleri kullanabilirsiniz. İçerik denetimleri Word 97-2003 belgesi (.doc) biçiminde kaydedilen belgeleri kullanamazsınız.  
  
## <a name="types-of-content-controls"></a>İçerik denetimleri türleri  
 Belgelere ekleme içerik denetimleri dokuz farklı türde vardır. İçerik denetimleri çoğunu olmayan karşılık gelen bir türü <xref:Microsoft.Office.Tools.Word> ad alanı. Genel de kullanabilirsiniz <xref:Microsoft.Office.Tools.Word.ContentControl>, hangi temsil edebilen herhangi bir kullanılabilir içerik denetimini. Her kullanılabilir içerik denetimlerini kullanma izlenecek yol için bkz: [izlenecek yol: bir şablon tarafından kullanarak içerik denetimler oluşturma](../vsto/walkthrough-creating-a-template-by-using-content-controls.md).  
  
### <a name="building-block-gallery"></a>Yapı Taşı Galerisi  
 Yapı Taşı Galerisi listesinden kullanıcıların seçmesine olanak sağlar *belge yapı taşları* bir belgeye eklemek için. Yapı Taşı belgesi yaygın bir kapak sayfası, biçimlendirilmiş bir tablo veya bir üstbilgi gibi birden çok kez kullanılması için oluşturulan içeriği parçasıdır. Daha fazla bilgi için bkz: <xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl> türü. Yapı taşları hakkında daha fazla bilgi için bkz: [Word 2007'de geliştiriciler için Yenilikler](http://msdn.microsoft.com/en-us/74aa6688-65b3-4167-997d-131f26ad8f84).  
  
### <a name="check-box"></a>Onay kutusu  
 Bir onay kutusu ikili durumunu temsil eden bir kullanıcı Arabirimi sağlar: Seçili veya temizlenir.  
  
 İçerik denetimleri, başka türlerde aksine [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] bir onay kutusu içerik denetimi temsil eden belirli bir tür sağlamaz. Diğer bir deyişle, CheckBoxContentControl türü yok. Ancak, bir onay kutusu içerik denetimi genel ekleyerek oluşturabilirsiniz <xref:Microsoft.Office.Tools.Word.ContentControl> belgeye programlı olarak. Daha fazla bilgi için bkz: [onay kutusu içerik denetimleri Word projelerinde](#checkbox).  
  
### <a name="combo-box"></a>Birleşik Giriş Kutusu  
 Birleşik giriş kutusu kullanıcıların seçebileceği öğelerin listesini görüntüler. Aşağı açılan listesinde, birleşik giriş kutusu kullanıcıların kendi öğelerini eklemesine olanak sağlar. Daha fazla bilgi için bkz: <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> türü.  
  
### <a name="date-picker"></a>Tarih Seçici  
 Tarih Seçici bir tarih seçmek için bir takvim kullanıcı Arabirimi sağlar. Son Kullanıcı aşağı açılan okunu denetimi tıklattığında takvim görüntülenir. Bölgesel takvimler ve farklı tarih biçimleri kullanabilirsiniz. Daha fazla bilgi için bkz: <xref:Microsoft.Office.Tools.Word.DatePickerContentControl> türü.  
  
### <a name="drop-down-list"></a>Açılan Liste  
 Aşağı açılan liste kullanıcıların seçebileceği öğelerin listesini görüntüler. Birleşik giriş kutusu, aşağı açılan liste öğeleri ekleme veya düzenleme kullanıcıların izin vermez. Daha fazla bilgi için bkz: <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> türü.  
  
### <a name="group"></a>Grup  
 Bir grup denetimi kullanıcılar düzenleyemeyeceğiniz veya silemeyeceğiniz belgenin korumalı bir bölge tanımlar. Bir grup denetimi metin, tablo, grafik ve diğer içerik denetimleri gibi herhangi bir belge öğesi içerebilir. Daha fazla bilgi için bkz: <xref:Microsoft.Office.Tools.Word.GroupContentControl> türü.  
  
### <a name="picture"></a>Resim  
 Bir resim denetimi bir görüntüsünü görüntüler. Tasarım zamanında resmi belirtin ya da çalışma zamanı veya kullanıcıların belgede eklemek için görüntüyü seçmek için bu denetim tıklatabilirsiniz. Daha fazla bilgi için bkz: <xref:Microsoft.Office.Tools.Word.PictureContentControl> türü.  
  
### <a name="rich-text"></a>Zengin metin  
 Zengin metin denetimi, metin veya tabloları, resimleri veya diğer içerik denetimleri gibi diğer öğeleri içerir. Daha fazla bilgi için bkz: <xref:Microsoft.Office.Tools.Word.RichTextContentControl> türü.  
  
### <a name="plain-text"></a>Düz Metin  
 Düz metin denetimi metni içerir. Düz metin denetimi tabloları, resimleri veya diğer içerik denetimleri gibi diğer öğeler içeremez. Ayrıca, düz metin denetimi metinde tümünün aynı biçimlendirme. Örneğin, bir düz metin denetiminde bir tümcenin bir sözcük italik yaparsanız, denetimin içindeki tüm metni italik. Daha fazla bilgi için bkz: <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> türü.  
  
### <a name="generic-content-control"></a>Genel içerik denetimi  
 Genel bir içerik denetimi bir <xref:Microsoft.Office.Tools.Word.ContentControl> içerik denetimleri kullanılabilir türlerinden herhangi birini temsil eden nesne. Değiştirebileceğiniz bir <xref:Microsoft.Office.Tools.Word.ContentControl> kullanarak farklı türde içerik denetimi gibi davranır nesnesine <xref:Microsoft.Office.Tools.Word.ContentControl.Type%2A> özelliği. Örneğin, oluşturduğunuz bir <xref:Microsoft.Office.Tools.Word.ContentControl> nesne gösteren bir düz metin denetimini, böylece bir birleşik giriş kutusu gibi davranır çalışma zamanında değiştirebilirsiniz.  
  
 Oluşturabileceğiniz <xref:Microsoft.Office.Tools.Word.ContentControl> nesneler yalnızca çalışma zamanında, tasarım zamanında değil. Daha fazla bilgi için bkz: [nasıl yapılır: Word belgelerine içerik denetimlerine ekleme](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
## <a name="common-features-of-content-controls"></a>İçerik denetimleri ortak özellikleri  
 Birçok içerik denetimleri ortak görevleri gerçekleştirmek için kullanabileceğiniz üyelerin kümesini paylaşır. Aşağıdaki tabloda bu üyeleri kullanarak gerçekleştirebileceğiniz görevlerden bazıları açıklanmaktadır.  
  
|Bu görev için:|Bunu yapın:|  
|--------------------|--------------|  
|Alın veya denetimde görüntülenen metni ayarlama.|Kullanım **metin** özelliği. **Not:** <xref:Microsoft.Office.Tools.Word.PictureContentControl> ve <xref:Microsoft.Office.Tools.Word.ContentControl> türleri bu özelliğe sahip değildir.|  
|Alın veya denetimde bir kullanıcı denetimi düzenledikten denetimi bir veri kaynağından doldurulur ya da denetimin içeriği silinir kadar görüntülenen metnin geçici ayarlayın.|Kullanım **PlaceholderText** özelliği. **Not:** <xref:Microsoft.Office.Tools.Word.PictureContentControl> türü bu özelliğe sahip değildir.|  
|Alın veya kullanıcı tıklattığında içerik denetiminin kenarlık görüntülenen Başlık ayarlayın.|Kullanım **başlık** özelliği.|  
|Kullanıcı denetimi düzenledikten sonra denetimi belgeden otomatik olarak kaldırın. (Denetim metinde belgede kalır.)|Kullanım **geçici** özelliği.|  
|Kullanıcı, içerik denetimi tıklattığında veya imleç içerik denetimine programlı olarak taşındığında kodu çalıştırın.|Tanıtıcı <xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering> denetiminin olayı.|  
|Kullanıcı dışında içerik denetimi tıklattığında veya imlecin dışında içerik denetimi programlı olarak taşındığında kodu çalıştırın.|Tanıtıcı <xref:Microsoft.Office.Tools.Word.ContentControlBase.Exiting> denetiminin olayı.|  
|İçerik denetimi yineleme belgeye eklendikten sonra kodu çalıştırmak veya geri alma işlemi.|Tanıtıcı <xref:Microsoft.Office.Tools.Word.ContentControlBase.Added> denetiminin olayı.|  
|İçerik denetimi belgeden yalnızca silinmeden önce kodu çalıştırın.|Tanıtıcı <xref:Microsoft.Office.Tools.Word.ContentControlBase.Deleting> denetiminin olayı.|  
  
##  <a name="Protection"></a>İçerik denetimlerini kullanarak belge bölümlerini koruma  
 Belgenin bir bölümünü koruduğunuzda, değiştirme veya silme belgenin bu bölümü içeriği kullanıcıların engellemiş olursunuz. İçerik denetimlerini kullanarak belge bölümlerini korumak için birkaç yol vardır.  
  
 Korumak istediğiniz alan içerik denetiminin içinde ise, kullanıcıların düzenleme veya silmesini önlemek için içerik denetimi özelliklerini kullanabilirsiniz:  
  
-   **LockContents** özelliği kullanıcılar içeriği düzenlemesini engeller.  
  
-   **LockContentControl** özelliği kullanıcılar silmesini engeller.  
  
 Korumak istediğiniz alan içerik denetiminin içinde değilse veya içerik denetimleri ve diğer içerik türlerine içeren bir alanı korumak istiyorsanız, tüm alanı koyabilirsiniz bir <xref:Microsoft.Office.Tools.Word.GroupContentControl>. Diğer içerik denetimleri farklı bir <xref:Microsoft.Office.Tools.Word.GroupContentControl> kullanıcıya görünen kullanıcı Arabirimi sağlar. Tek amacı, kullanıcılar düzenleyemez bölge tanımlamaktır.  
  
> [!NOTE]  
>  Oluşturursanız, bir <xref:Microsoft.Office.Tools.Word.GroupContentControl> katıştırılmış içerik denetimleri içeren, katıştırılmış içerik denetimleri otomatik olarak korunmaz. Kullanmalısınız **LockContents** her özellik katıştırılmış kullanıcıların içeriklerini düzenlemesini önlemek için denetimi.  
  
 İçerik denetimleri belge parçalarını korumak için nasıl kullanılacağı hakkında daha fazla bilgi için bkz: [nasıl yapılır: korumak bölümleri belgeler kullanarak içerik denetimleri tarafından](../vsto/how-to-protect-parts-of-documents-by-using-content-controls.md).  
  
##  <a name="DataBinding"></a>İçerik denetimlerine veri bağlama  
 İçerik denetimi bir veri kaynağına bağlayarak veri belgeleri görüntüleyebilirsiniz. Veri kaynağı güncelleştirildiğinde, içerik denetimi değişiklikleri yansıtır. Veri kaynağına değişiklikler da kaydedebilirsiniz.  
  
 İçerik denetimleri aşağıdaki veri bağlama seçenekleri sağlar:  
  
-   Windows Forms gibi aynı veri bağlama modelini kullanarak, veritabanı alanları veya yönetilen nesneler için içerik denetimlerini bağlayabilirsiniz.  
  
-   İçerik denetimleri XML parçalarının öğeleri bağlayabilirsiniz (olarak da adlandırılan *özel XML bölümleri*) belgesinde katıştırılmış.  
  
 Konak denetimleri Office çözümlerinde verilere bağlama genel bakış için bkz: [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
### <a name="using-the-windows-forms-data-binding-model"></a>Kullanarak Windows Forms veri bağlama modelini  
 Birçok içerik denetimleri Windows Forms kullanan basit veri bağlama modelini destekler. Basit veri bağlama bir denetimin veri tablosunun bir sütunda bir değer gibi tek bir veri öğesine bağlı olduğu anlamına gelir. Daha fazla bilgi için bkz: [verileri bağlama ve Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
 Belge düzeyi projelerine veri içerik denetimlerini kullanarak bağlayabilirsiniz **veri kaynakları** penceresinde [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Belgelere veri bağlama içerik denetimleri ekleme hakkında daha fazla bilgi için bkz [nasıl yapılır: belgeleri veritabanı verileriyle doldurmak](../vsto/how-to-populate-documents-with-data-from-a-database.md) ve [nasıl yapılır: doldurmak belgeleri nesne verileriyle](../vsto/how-to-populate-documents-with-data-from-objects.md).  
  
 Aşağıdaki tabloda her bir veri türü bağlayabilirsiniz içerik denetimlerini listeler **veri kaynakları** penceresi.  
  
|Veri türü|Varsayılan içerik denetimi|Bu veri türüne bağlı diğer içerik denetimleri|  
|---------------|-----------------------------|----------------------------------------------------------------|  
|<xref:System.Boolean><br /><br /> <xref:System.Byte><br /><br /> <xref:System.Char><br /><br /> <xref:System.Double><br /><br /> <xref:System.Enum><br /><br /> <xref:System.Guid><br /><br /> <xref:System.Int16><br /><br /> <xref:System.Int32><br /><br /> <xref:System.Int64><br /><br /> <xref:System.SByte><br /><br /> <xref:System.Single><br /><br /> <xref:System.String><br /><br /> <xref:System.TimeSpan><br /><br /> <xref:System.UInt16><br /><br /> <xref:System.UInt32><br /><br /> <xref:System.UInt64>|<xref:Microsoft.Office.Tools.Word.PlainTextContentControl>|<xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.DatePickerContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.RichTextContentControl>|  
|<xref:System.DateTime>|<xref:Microsoft.Office.Tools.Word.DatePickerContentControl>|<xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.PlainTextContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.RichTextContentControl>|  
|<xref:System.Drawing.Image><br /><br /> <xref:System.Byte>dizi|<xref:Microsoft.Office.Tools.Word.PictureContentControl>|Yok.|  
  
 Belge düzeyi ve VSTO eklentisi projelerine, içerik denetimi bir veri kaynağına program aracılığıyla kullanarak bağlayabilirsiniz <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> yöntemi <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> denetiminin özelliği. Bunu yaparsanız bir dizeyi geçirmek **metin** için *propertyName* parametresinin <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> yöntemi. **Metin** içerik denetimlerinin varsayılan veri bağlama özelliği bir özelliktir.  
  
 İçerik denetimleri de değişiklikleri denetiminde veri kaynağına güncelleştirilir iki yönlü veri bağlamayı destekler. Daha fazla bilgi için bkz: [nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).  
  
> [!NOTE]  
>  İçerik denetimleri karmaşık veri bağlamayı desteklemez. Bağlarsanız bir <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> veya <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl> denetimi tıklattığınızda bir veri kaynağına Windows Forms veri modelini kullanarak, kullanıcılar yalnızca tek bir değer görürsünüz. Bu denetimler kullanıcıların seçebileceği veri değerleri kümesi bağlamak istiyorsanız, bu denetimlerin özel bir XML parçasına öğeleri bağlayabilirsiniz.  
  
### <a name="binding-content-controls-to-custom-xml-parts"></a>İçerik denetimlerini özel XML bölümlerine bağlama  
 Bazı içerik denetimlerini belgede gömülü özel XML bölümleri bağlayabilirsiniz. Özel XML bölümleri hakkında daha fazla bilgi için bkz: [özel XML bölümlerine genel bakış](../vsto/custom-xml-parts-overview.md).  
  
 İçerik denetimi özel bir XML parçasına bir öğedeki bağlamak için kullanın **XMLMapping** denetiminin özelliği. Aşağıdaki kod örneğinde nasıl bağlanacağını gösterir bir <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> için `Price` öğesinin altında `Product` belgeye zaten eklenmiş özel bir XML parçasına düğümünde.  
  
```vb  
plainTextContentControl1.XMLMapping.SetMapping("/Product/Price")  
```  
  
```csharp  
plainTextContentControl1.XMLMapping.SetMapping("/Product/Price", String.Empty, null);  
```  
  
 İçerik denetimlerini özel XML bölümleri daha ayrıntılı bağlamak nasıl izlenecek yol için bkz: [izlenecek yol: içerik denetimlerini özel XML bölümlerine bağlama](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md).  
  
 İçerik denetimi için özel bir XML parçasına bağlama iki yönlü veri bağlama otomatik olarak etkinleştirilir. Bir kullanıcı denetimi metin düzenlemeleri, karşılık gelen XML öğeleri otomatik olarak güncelleştirilir. Benzer şekilde, özel XML bölümleri öğesi değerleri değiştirdiyseniz, XML öğelerine bağlanmış içerik denetimleri yeni verileri görüntüler.  
  
 İçerik denetimleri aşağıdaki türleri için özel XML bölümleri bağlayabilirsiniz:  
  
-   <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.DatePickerContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.DropDownListContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.PictureContentControl>  
  
-   <xref:Microsoft.Office.Tools.Word.PlainTextContentControl>  
  
### <a name="data-binding-events-for-content-controls"></a>Olayları içerik denetimleri için veri bağlama  
 Tüm içerik denetimleri veri kaynağı güncelleştirilmeden önce bir denetim metinde belirli kriterlere uyan doğrulama gibi veri ilişkili görevler gerçekleştirmek için işleyebilir olayları kümesi sağlar. Aşağıdaki tabloda veri bağlama ile ilgili içerik denetimi olaylarını listeler.  
  
|Görev|Olay|  
|----------|-----------|  
|Yalnızca Word özel bir XML parçasına bağlı bir içerik denetimi metinde otomatik olarak güncelleştirir önce kodu çalıştırın.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.ContentUpdating>|  
|Yalnızca Word bağlı özel bir XML parçasına verileri otomatik olarak güncelleştirir önce kodu çalıştırın içerik (diğer bir deyişle, içerik denetimi metinde değiştikten sonra) denetler.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.StoreUpdating>|  
|Özel ölçütlere göre denetiminin içeriği doğrulamak için kendi kodunuzu çalıştırın.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Validating>|  
|Denetimin içeriği başarıyla doğrulandıktan sonra kodu çalıştırın.|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Validated>|  
  
## <a name="limitations-of-content-controls"></a>İçerik denetimleri sınırlamaları  
 Office projelerinde içerik denetimlerini kullandığınızda, aşağıdaki sınırlamalara dikkat edin.  
  
### <a name="behavior-differences-between-design-time-and-run-time"></a>Tasarım zamanı ve çalışma zamanında arasındaki davranış farklılıkları  
 Microsoft Office Word içerik denetimlerinde çalışma zamanında uygular sınırlamaları çoğunu tasarım zamanında zorunlu değildir. Belge düzeyi çözümde UI tasarlarken [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], içerik denetimlerini çalışma zamanında desteklenen şekilde değiştirdiğinizden emin olun.  
  
 Tasarım zamanında denetimi çalışma zamanında desteklemiyor şekilde içerik denetimi değiştirirseniz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Tasarımcısı değil uyarı desteklenmeyen değişiklikleri. Ancak, hata ayıklama veya proje çalıştırdığınızda veya kaydedin ve projeyi yeniden açın, Word belgeyi onarmak için bir hata iletisi ve istek izni görüntüler. Belgeyi onarmak, Word desteklenmeyen içeriği ve denetimden biçimlendirme kaldırır.  
  
 Örneğin, Word, tabloya ekleme engellemez bir <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> tasarım zamanında. Ancak, çünkü <xref:Microsoft.Office.Tools.Word.PlainTextContentControl> nesneleri çalışma zamanında tabloları içeremez, Word belge açıldığında bir hata iletisi görüntüler.  
  
 Ayrıca içerik denetimleri davranışını tanımlayan birçok özellikleri tasarım zamanında hiçbir etkisi gerektiğini unutmayın. Örneğin, ayarlarsanız **LockContents** içerik denetimi özelliği **True** tasarım zamanında denetiminde metni hala düzenleyebilirsiniz [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Tasarımcısı. Bu özellik, kullanıcıların yalnızca çalışma zamanında denetimi düzenlemesini engeller.  
  
### <a name="event-limitations"></a>Olay sınırlamaları  
 İçerik denetimleri kullanıcı metin veya diğer öğeleri denetiminde değiştirdiğinde bir olayı sağlamaz. Örneğin, bir kullanıcı farklı bir öğe seçtiğinde hiçbir olay yok bir <xref:Microsoft.Office.Tools.Word.DropDownListContentControl> veya <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl>.  
  
 İçerik denetimi içeriğini kullanıcının ne zaman düzenlediğini belirlemek için denetimini özel bir XML parçasına bağlama ve ardından işlemek <xref:Microsoft.Office.Tools.Word.ContentControlBase.StoreUpdating> olay. Kullanıcı için özel bir XML parçasına bağlı bir denetimin içeriğini değiştirdiğinde bu olay tetiklenir. İçerik denetimi için özel bir XML parçasına bağlama nasıl izlenecek yol için bkz: [izlenecek yol: içerik denetimlerini özel XML bölümlerine bağlama](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md).  
  
###  <a name="checkbox"></a>Word projelerinde onay kutusu içerik denetimleri  
 Word 2010 temsil eden bir onay kutusu içerik denetimi yeni bir tür sunmuştur. Ancak, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Office projelerinde kullanabilmeniz için karşılık gelen bir CheckBoxContentControl türü sağlamaz. Bir onay kutusu içerik denetimi oluşturmak için bir [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)] veya Word 2010 proje kullanın, <xref:Microsoft.Office.Tools.Word.ControlCollection.AddContentControl%2A> yöntemi oluşturmak için bir <xref:Microsoft.Office.Tools.Word.ContentControl> nesne ve geçirin <xref:Microsoft.Office.Interop.Word.WdContentControlType.wdContentControlCheckBox> yöntemine bir onay kutusu içerik denetimi belirtmek için değer. Aşağıdaki kod örneğinde bunun nasıl yapılacağı gösterilmektedir.  
  
 [!code-vb[Trin_ContentControlReference#800](../vsto/codesnippet/VisualBasic/trin_contentcontrolreference/checkbox.vb#800)]
 [!code-csharp[Trin_ContentControlReference#800](../vsto/codesnippet/CSharp/trin_wordcontentcontrolreference/checkbox.cs#800)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletilmiş nesneleri kullanarak Word'ü Otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)   
 [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [İzlenecek yol: içerik denetimlerini kullanarak şablon oluşturma](../vsto/walkthrough-creating-a-template-by-using-content-controls.md)   
 [Office çözümlerindeki veriler](../vsto/data-in-office-solutions.md)   
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Konak denetimlerinin ve konak öğelerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
