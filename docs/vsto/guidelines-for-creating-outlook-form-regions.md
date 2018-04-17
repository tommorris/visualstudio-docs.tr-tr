---
title: Outlook oluşturma yönergeleri Form bölgeleri | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], guidelines
- icons [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: dae7f03c49223c9919dc67b1c6a13768c597698d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="guidelines-for-creating-outlook-form-regions"></a>Outlook Form Bölgeleri Oluşturma Yönergeleri
  Aşağıdaki bilgiler, form bölgeleri en iyi duruma getirme ve olası sorunları önlemenize yardımcı olabilir:  
  
-   [Form bölgesi adlarını kullanma](#UsingFormRegions).  
  
-   [Form bölgesi devralmayı devre dışı bırakarak](#DisablingInheritance).  
  
-   [Sınıf adları türlerini anlama ve ileti](#ClassNames).  
  
-   [Okuma Bölmesi için bitişik form bölgeleri tasarlama](#ReadingPane).  
  
-   [En iyi simgesi boyutlarını kullanarak](#UsingOptimal).  
  
 Form bölgeleri hakkında daha fazla bilgi için bkz: [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
##  <a name="UsingFormRegions"></a> Form bölgesi adlarını kullanma  
 Form bölgesini tanımlamak için kullanılan birkaç adları vardır. Bu adları ve form bölgesini nasıl etkilediklerini arasındaki farkı anlamak önemlidir. Aşağıdaki tabloda her bir adı açıklanmaktadır.  
  
|Form bölgesi adı|Açıklama|  
|----------------------|-----------------|  
|Form bölgesi öğesi adı|İçin belirttiğiniz ad **Outlook Form bölgesi** öğesi **Yeni Öğe Ekle** iletişim kutusu. Görünür form bölgesi kod dosyası adıdır **Çözüm Gezgini**.|  
|<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> Özelliği|Bu adı belirtmeyin **açıklayıcı metin sağlayın ve görüntüleme tercihlerini seçin** sayfasında **yeni Outlook Form bölgesi** Sihirbazı. Bu ad olarak görünür **FormRegionName** özelliğinde **özellikleri** penceresi.<br /><br /> Kullanım <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> özelliği form bölgesini Outlook kullanıcı arabiriminde (UI) tanımlayan etiketi belirtin. Ayrı form bölgeleri için bu ad Outlook öğesinin Şerit üzerindeki bir düğme olarak görünür.<br /><br /> Bitişik form bölgeleri için bu ad form bölgesini yukarıda üstbilgi metni olarak görünür.|  
|Microsoft.Office.Tools.Outlook.FormRegionName özniteliği|Eklediğinizde bir **Outlook Form bölgesi** öğe projeye, Visual Studio bu özelliğe form bölgesini tam adını ayarlar. Varsayılan tam VSTO eklenti adı noktayla form bölgesini adına bağlı adıdır — örneğin, `OutlookAddIn1.FormRegion1`.<br /><br /> Bu tam adı, form bölgesi üretici sınıfı üstündeki özniteliği olarak görünür.<br /><br /> Form bölgesini tüm Outlook VSTO eklentileri arasında benzersiz şekilde tanımlamak için Microsoft.Office.Tools.Outlook.FormRegionName özniteliğini kullanın. Form bölgesi öğesi yeniden adlandırma veya değiştirerek Microsoft.Office.Tools.Outlook.FormRegionName özniteliğinin değeri değiştirilemiyor <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> özelliği. Bu adı değiştirmek için form bölgesi kod dosyasında Microsoft.Office.Tools.Outlook.FormRegionName özniteliğini değiştirmeniz gerekir.|  
  
##  <a name="DisablingInheritance"></a> Form bölgesi devralma devre dışı bırakma  
 Varsayılan olarak, özel bir ileti sınıfı temel ileti sınıfının tüm form bölgesi ilişkilendirmelerini devralır. Örneğin, bir ileti sınıfı adlı `IPM.Task.Contoso` IPM türer. Görev. Bu nedenle, `IPM.Task.Contoso` IPM form bölgesi ilişkilendirmelerini devralır. Görev.  
  
 Türetilen ileti sınıflarından ile ilişkilendirilmesi için form bölgesi istemiyorsanız ayarlamak <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A> form bölgesine özelliğinin **doğru**. Örneğin, bitişik bir form bölgesi IPM ile ilişkilendirir. Görev ve ayarlayın <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A> özelliğine **doğru**, form bölgesini yalnızca standart görev form sonuna eklenir. Form bölgesini özelleştirilmiş bir standart görev form sürümlerini altına eklenmemiş.  
  
##  <a name="ClassNames"></a> Türlerini anlama ve ileti sınıf adları  
 Bir Outlook öğesi tür adını bir Outlook öğesi ileti sınıfı adından farklıdır. Örneğin, bir RSS öğesinin tür adı Microsoft.Office.Interop.Outlook.PostItem ' dir. İleti sınıfı bir RSS öğesinin IPM addır. Post.RSS.  
  
 Koddaki bir Outlook öğesine başvurmak için tür adı kullanın. Tür adları listesi için bkz: [Form bölgesini Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md).  
  
 Outlook öğelerinde ileti sınıf adını kullanmak **yeni Outlook Form bölgesi** öğesi form bölgesini ile ilişkilendirmek için Sihirbazı. Geçerli ileti sınıfı adlarının bir listesi için bkz: [Form bölgesini Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md).  
  
##  <a name="ReadingPane"></a> Form bölgeleri için Okuma Bölmesi bitişik tasarlama  
 Outlook okuma bölmesi, bir Outlook öğesi öğeyi açmadan önizlemek için kullanabilirsiniz. Okuma bölmesi yalnızca okumak için tasarlanmıştır. Bu nedenle, bir metin kutusu gibi bitişik bir form bölgesi ekleme giriş denetimlerini ne zaman beklendiği gibi davranabilir olmayan öğe ve form bölgesi Okuma Bölmesi'nde açın.  
  
 Örneğin, bitişik bir form bölgesi sahip bir öğe Okuma Bölmesi'nde açık ise, aşağıdaki durum mümkündür:  
  
1.  Form bölgesi üzerinde olan bir metin kutusuna bir metin seçin.  
  
2.  DELETE tuşuna basın.  
  
3.  Tüm posta öğesi metni metin kutusuna yerine silinir.  
  
 Giriş denetimlerini içeren bitişik bir form bölgesi tasarlama, düzgün çalıştığından emin olmak için Okuma Bölmesi'nde denetimleri sınayın. Beklendiği gibi davranır değil denetimleri devre dışı bırakan özel kod eklemeyi düşünün.  
  
 Alternatif olarak, ayarlayabileceğiniz <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ShowInspectorRead%2A> form bölgesine özelliğinin **False**. Böylece form bölgesi Okuma Bölmesi'nde kullanılamaz.  
  
##  <a name="UsingOptimal"></a> En iyi simge boyutunu kullanma  
 Hangi simgeleri simgesi özellik ayarlayarak görüntülemek için form bölgesi istediğinizi belirtebilirsiniz **simgeleri** özelliği grup **özellikleri** penceresi. En iyi görsel kalite elde etmek için aşağıdaki kılavuzları kullanın:  
  
-   İçin **sayfa** simgesi, Taşınabilir Ağ Grafikleri (PNG) dosyası kullanın.  
  
-   **Pencere** simgeleri 32 x 32 piksel olmalıdır.  
  
-   Diğer tüm simgeler 16 x 16 piksel olmalıdır.  
  
 **Sayfa** ayrı, değiştirme veya tümünü değiştir form bölgeleri olan öğeler için Inspector şeridinde simgesi görünür.  
  
 **Penceresi** simgesi, bildirim alanında ve Değişim veya tümünü değiştir form bölgelerini görüntüleyen açık öğeler için ALT + SEKME iletişim kutusunda görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Form bölgesine çalışma zamanında erişme](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook Form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)   
 [İzlenecek yol: Outlook Form Bölgesi Tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Nasıl yapılır: Outlook eklenti projesine Form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Form Bölgesini Outlook İleti Sınıfıyla İlişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md)  
  
  