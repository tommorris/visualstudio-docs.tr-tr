---
title: "XAML Tasarımcısı seçenekler sayfası | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ToolsOptionsPages.XAMLDesigner
ms.assetid: ad3820b2-0d95-4807-a75c-c3467ed973a3
caps.latest.revision: "1"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 459642fde4d695317a453e223edd54f223569603
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-designer-options-page"></a>XAML Tasarımcısı Seçenekleri sayfası
Kullanım **XAML Tasarımcısı** öğeleri ve özniteliklerinin XAML belgelerinizi nasıl biçimlendirileceğini belirtmek için seçenekler sayfası. Bu sayfayı açmak için seçin **Araçları** menü ve ardından **seçenekleri**. Erişim için **XAML Tasarımcısı** özellik sayfasında, **XAML Tasarımcısı** düğümü. Belgeyi açtığında XAML Tasarımcısı için ayarları uygulanır. Bu nedenle ayarlarında değişiklik yaparsanız, değişiklikleri görmek için Visual Studio'yu kapatıp gerekir.

> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  

## <a name="enable-xaml-designer"></a>XAML Tasarımcısı etkinleştir
Bu ayar seçildiğinde, XAML Tasarımcısı'nı etkinleştirir. XAML Tasarımcısı visual çalışma alanı XAML belgeleri düzenlemesine olanak sağlar. Visual Studio'da, kaynakları ve veri bağlamayı için IntelliSense gibi bazı işlevleri XAML Tasarımcısı etkin olmasını gerektirir.

Aşağıdaki ayarlar yalnızca XAML Tasarımcısı etkinleştirildiğinde geçerlidir. Bu seçenek değiştirirseniz, Visual Studio ayarın etkili olması için yeniden başlatmanız gerekir.

## <a name="default-document-view"></a>Varsayılan belge görünümü
XAML belgeleri yüklendiğinde Tasarım görünümünde görünür olup olmadığını denetlemek için bu ayarı kullanın.

|||  
|-|-|  
|**Kaynak Görünümü**|Yalnızca XAML kaynağı XAML görünümünde görüntülenip görüntülenmeyeceğini belirtir. Bu, büyük belgeleri yüklenirken kullanışlıdır.|  
|**Tasarım görünümü**|Yalnızca bir görsel XAML görünümünde XAML Tasarımcısı görüntülenip görüntülenmeyeceğini belirtir.|  
|**Bölünmüş Görünümü**|Visual XAML Tasarımcısı ve XAML kaynağı başka yanındaki XAML görünümünde görünüp görünmeyeceğini belirtir (konum temel alarak **bölünmüş yönlendirmesini** ayarı).|  

## <a name="split-orientation"></a>Bölünmüş yönü
XAML Tasarımcısı XAML belge düzenlerken görüntülendiği zaman ve nasıl denetlemek için bu ayarı kullanın. Bu ayarlar yalnızca geçerli **varsayılan belge görünümü** ayarlanır **Bölünmüş Görünüm**.

|||  
|-|-|  
|**Dikey**|XAML kaynağı XAML görünümü sol tarafında görünür ve XAML Tasarımcısı diğer tarafında görünür.|  
|**Yatay**|XAML Tasarımcısı XAML görünüm üst kısmında görünür ve XAML kaynağı altında görünür.|  
|**Default**|XAML belge belgenin projenin hedeflediği platform için önerilen bölünmüş yönlendirmesi kullanır. Çoğu platformda bu eşdeğer olan **yatay**.|  

## <a name="zoom-by-using"></a>Kullanarak Yakınlaştır
Yakınlaştırma XAML belge düzenlerken şeklini belirlemek için bu ayarı kullanın.

|||  
|-|-|  
|**Fare tekerleği**|XAML Tasarımcısı'nda, fare tekerleği kaydırarak Yakınlaştır.|  
|**CTRL + fare tekerleği**|XAML Tasarımcısı'nda, fare tekerleğinin kaydırma sırasında CTRL tuşuna basarak Yakınlaştır.|  
|**Alt + fare tekerleği**|XAML Tasarımcısı'nda, fare tekerleğinin kaydırma sırasında ALT tuşuna basarak Yakınlaştır.|  

XAML belge düzenlerken Tasarımcısı davranışı Bu ayarlar belirler.

|||  
|-|-|  
|**Otomatik olarak ad etkileşimli öğeleri oluşturma**|Tasarımcı birine eklediğinizde, yeni bir etkileşimli öğesi için bir varsayılan ad sağlanıp sağlanmayacağını belirtir.|  
|**Öğesi oluşturma sırasında yerleşim özellikleri otomatik olarak Ekle**|Tasarımcı birine eklediğinizde yerleşim özellikleri için yeni bir öğe sağlanan olup olmadığını belirtir.|  
|**Dörtgen Bölümlü temel düzenini kullanın**|Seçili denetimi en yakın üst öğe kapsayıcısı kenarlarına hizalar olup olmadığını belirtir. Bu onay kutusu işaretli değilse, Denetim hizalamaları bir taşıma işlemi sırasında değiştirmeyin veya oluşturma işlemi.|  
|**Araç kutusu öğelerini otomatik olarak doldurma**|Kullanıcı denetimleri ve özel denetimler geçerli çözümde araç kutusunda otomatik olarak gösterilip gösterilmeyeceğini belirler.|  

## <a name="settings-blend-only"></a>Ayarları (yalnızca karışım)
Harmanlama kullanarak XAML dosyalarını düzenlerken ayarlarını belirlemek için bu seçenekleri kullanın.

|||  
|-|-|  
|**Kullanarak Yakınlaştır**|XAML Tasarımcısı'nda, fare tekerleğinin kaydırma ya da fare tekerleğinin kaydırma sırasında CTRL ya da ALT tuşuna basarak Yakınlaştır.|  
|**Tür birimleri**|Ölçümleri tasarımcısında noktaları veya piksel göre belirtir. Evrensel Windows uygulamaları noktaları desteklenmediği birimleri otomatik olarak piksel varsa dönüştürülür **noktaları** seçilir.|  

## <a name="artboard-blend-only"></a>Çalışma yüzeyi (yalnızca karışım)
Blend'de XAML belgeleri düzenlerken XAML Tasarımcısı davranışını belirlemek için bu ayarları kullanın.

### <a name="snapping"></a>Tutturma

|||  
|-|-|  
|**Ek Kılavuzu Göster**|Bu seçenek belirlendiğinde, kılavuz çizgileri denetimleri hizalamanıza yardımcı olmak için Tasarımcısı'nda görünür. Bu kılavuz çizgileri için tasarımcı ek eklenen denetimler zaman **Daya için kılavuz çizgilerini** seçeneği işaretlidir.|  
|**Kılavuz çizgileri için Daya**|Eklenen ya da Tasarımcısı taşınmış denetimleri için kılavuz çizgilerini ek bileşen.|  
|**Kılavuz çizgisi aralığı**|Kılavuz çizgilerinin piksel veya noktaları arasındaki boşluğu belirtir (tarafından belirlenen **yazın birimleri** ayarı).|  
|**Dayama çizgileri için Daya**|Denetimler için dayama çizgileri birleştirilip birleştirilmeyeceğini belirtir.|  
|**Varsayılan kenar boşluğu**|Zaman **Daya dayama çizgileri için** etkinleştirildiğinde, piksel veya noktaları denetim ve dayama çizgileri arasındaki boşluğu belirtir (tarafından belirlenen **yazın birimleri** ayarı).|  
|**Varsayılan doldurma**|Zaman **Daya dayama çizgileri için** etkinleştirildiğinde, Denetim ve dayama çizgileri arasında ek boşluk piksel veya noktalarını belirtir (tarafından belirlenen **yazın birimleri** ayarı).|  

### <a name="animation"></a>Animasyon
Animasyon grubunda etkinleştirilip (Hızlandırılmış olmayan) bağlı olduğunda bir uyarı görünür olup olmadığını belirlemek için bu ayarı kullanın.

### <a name="effects"></a>Etkiler
XAML Tasarımcısı'nda dosyaları XAML düzenleme etkileri Blend kullanarak işlenip işlenmeyeceğini belirlemek için bu ayarları kullanın.

|||  
|-|-|  
|**Efektler Oluştur**|Efektler XAML Tasarımcısı'nda XAML dosyaları düzenlerken Blend kullanarak işlenip işlenmeyeceğini belirtir.|  
|**Yakınlaştırma eşiği**|Yakınlaştırma yüzdesini belirler hangi efektler ne zaman Oluştur içinde **işlemek etkileri** onay kutusunun seçili. Bu ayar ötesinde yakınlaştırma, efektler XAML Tasarımcısı'nda artık oluştur.|  

## <a name="see-also"></a>Ayrıca Bkz.  
 [WPF'de XAML](/dotnet/framework/wpf/advanced/xaml-in-wpf)   
 [Nasıl yapılır: XAML görünümü ayarları değiştirme](http://msdn.microsoft.com/en-us/aee87c79-ca01-4f84-8fb7-a9e47048ee47)   
 [XAML ve kod izlenecek yollar](http://msdn.microsoft.com/en-us/b3ff41a0-a2a3-4f61-b698-ac88ec8f799c)
