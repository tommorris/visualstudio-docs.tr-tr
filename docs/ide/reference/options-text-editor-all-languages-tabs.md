---
title: "Seçenekler, metin düzenleyici, tüm diller, sekmeler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.ResJSON.Tabs
- VS.ToolsOptionsPages.Text_Editor.JavaScript.Tabs
- VS.ToolsOptionsPages.Text_Editor.All_Languages.Tabs
helpviewer_keywords:
- indents, Code Editor
- Code Editor, default behavior
- tabs, setting in Code Editor
- All Languages Text Editor Options dialog box
- editors, Code Editor
- Code Editor, indenting
- Code Editor, tabs
ms.assetid: 7e208e1d-5e3a-4bf7-a27b-4417e3e049c7
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ae28077b52faf97b0ed1005e6fe5474925d197de
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="options-text-editor-all-languages-tabs"></a>Seçenekler, Metin Düzenleyici, Tüm Diller, Sekmeler
Bu iletişim kutusu, Kod Düzenleyicisi'nin varsayılan davranışı değiştirmenizi sağlar. Bu ayarlar üzerinde kod düzenleyicisinde, HTML Tasarımcısı kaynağı görünümü gibi temel diğer düzenleyiciler için de geçerlidir. Bu seçenekleri görüntülemek için seçin **seçenekleri** gelen **Araçları** menüsü. İçinde **metin düzenleyici** klasörünü genişletin **tüm diller** alt ve ardından **sekmeleri**.  
  
> [!CAUTION]
>  Bu sayfayı tüm geliştirme diller için varsayılan seçeneklerini ayarlar. Bu iletişim kutusunda bir seçenek sıfırlama tüm diller sekmeler seçeneklerinde ne olursa olsun seçenekler burada seçilen için sıfırlar olduğunu unutmayın. Metin Düzenleyici seçenekleri yalnızca bir dil için değiştirmek için o dil için alt klasörü genişletin ve seçenek sayfaları seçin.  
  
 Farklı için farklı ayarlar belirli programlama dilleri, ardından "Tek tek metin biçimleri çakışma birbirleriyle girinti ayarlarını" iletisi sekmeleri seçenekleri sayfalarındaki seçtiyseniz görüntülenen **Indenting**seçenekleri; ve farklı için "Sekmesinde ayarları tek tek metin biçimleri çakışması birbirleriyle" iletisi görüntülenir **sekmesini** seçenekleri. Örneğin, bu anımsatıcısı görüntülenir **akıllı girintileme** seçeneği için Visual Basic, ancak **engelleme girintileme** Visual C++ için seçilir.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="indenting"></a>Girintileme  
 Yok.  
 Bu onay kutusu seçildiğinde, yeni satır girintili değil. Ekleme noktasını yeni bir satır ilk sütunda yerleştirilir.  
  
 Blok  
 Bu onay kutusu seçildiğinde, yeni satırlar otomatik olarak girintili. Ekleme noktasını, aynı başlangıç noktasına önceki satır olarak yerleştirilir.  
  
 Akıllı  
 Bu onay kutusu seçildiğinde, yeni satır kod bağlam biçimlendirme ayarları ve geliştirme dilini için IntelliSense kuralları başka bir kod başına uyacak şekilde yerleştirilir. Bu seçenek, tüm geliştirme diller için kullanılamaz.  
  
 Örneğin, bir açılış ayracı ({}) arasında bir kapanış ayracı (}) içine satırları otomatik olarak olabilir ek sekme durağı hizalanmış küme ayraçları konumundan girintili.  
  
## <a name="tabs"></a>Sekmeleri  
 Sekme boyutu  
 Ayarlar sekmesinde arasında boşluk cinsinden uzaklık durdurur. Dört alanları varsayılandır.  
  
 Girinti boyutu  
 Boyutu otomatik girinti boşluklara ayarlar. Dört alanları varsayılandır. Belirtilen boyut doldurmak için sekme karakterleri, boşluk karakterleri ya da her ikisini de eklenir.  
  
 Boşluk Ekle  
 Seçili olduğunda, girinti işlemleri sekme karakterleri yalnızca boşluk karakterleri ekleyin. Varsa **girinti boyutu** ayarlanmış SEKME tuşuna basın her 5, örneğin, daha sonra beş boşluk karakterleri eklenir veya **Girintiyi** düğmesini **biçimlendirme** araç çubuğu.  
  
 Sekmeleri tut  
 Seçili olduğunda, girinti işlemleri mümkün olduğu kadar sekme karakterleri ekleyin. Belirtilen alanları sayısı her sekme karakteri doldurur **sekme boyutu**. Varsa **girinti boyutu** bir çift katı değil **sekme boyutu**, boşluk karakterleri fark doldurmak için eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçenekler, metin düzenleyici, tüm diller](../../ide/reference/options-text-editor-all-languages.md)   
 [Genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md)