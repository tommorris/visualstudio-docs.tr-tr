---
title: Seçenekler sayfası, metin düzenleyici düğümü özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Tools Options settings, Text Editor node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 19438302-0677-4f4d-9720-5667e6a22ab2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6678901da33593f8a73b9a0af42eabe721bf91d9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="options-page-text-editor-node-properties"></a>Seçenekler Sayfası, Metin Düzenleyici Düğümü Özellikleri
Bazı sayfaları (veya özellikleri koleksiyonları) Bu belgede açıklanan ile ilişkili **metin düzenleyici** kategorisi, `DTE.Properties("TextEditor", <Property Page>)`, **seçenekleri** iletişim kutusu. Her alt bölüm başlığı kullanılan çağrıdır erişimi `Properties` toplama ve her alt tabloda bir koleksiyondaki özellikleri listeler.  
  
 Visual Basic makroları [denetleyen seçenekler ayarları](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d) geçerli seçeneklerini ve her sayfasının değerlerini görüntülemek nasıl göstermek **seçenekleri** iletişim kutusu.  
  
## <a name="general"></a>Genel  
 `DTE.Properties("TextEditor", "General")`  
  
|Özellik Öğesi Adı|Değer|Açıklama|  
|------------------------|-----------|-----------------|  
|GoToAnchorAfterEscape|Get/Set (Boole)|Varsa `True`, seçim modundayken kaçış tuşuna basarak seçimi oluşturulan eylem başlatıldığı taşımak ekleme noktasını neden olur. `False` ekleme noktasını seçimi diğer ucundaki taşır.|  
|DragNDropTextEditing|Get/Set (Boole)|Seçilen bir metin bölümünü, kopyala veya kes/yapıştır işlemleri için belge içinde bir yerden başka bir yere sürükleyip sürükleyemeyeceğinizi belirler.|  
|HorizontalScrollBar|Get/Set (Boole)|Düzenleyici pencerelerinde yatay kaydırma çubuğu olup olmadığını belirler.|  
|VerticalScrollBar|Get/Set (Boole)|Düzenleyici pencerelerinde dikey kaydırma çubuğu olup olmadığını belirler.|  
|SelectionMargin|Get/Set (Boole)|Metin bölmesinin solunda özel seçim işlemleri, kesme noktası çizimleri vs. için boşluk olup olmadığını belirler.|  
|MarginIndicatorBar|Get/Set (Boole)|Metin bölmesinin sol kenar boşluğunu metin bölmesinin ana gövdesinden ayıran bir dikey çizgi olup olmadığını belirler.|  
|UndoCaretActions|Get/Set (Boole)|Varsa `True`. geri alma işlemleri ekleme noktası hareket, seçim komutları ve benzeri arabellek değiştirme eylemlerini düzenleme yanı sıra içerir.|  
|AutoDelimiterHighlighting|Get/Set (Boole)|Kapanış sınırlayıcısı girmenin, düzenleyicinin açılış sınırlayıcısını vurgulamasına neden olup olmayacağını belirler. Bu özelliğin değerinden bağımsız olarak, düzenleyici açık sınırlayıcıyı her zaman kalın yapar.|  
|EditorEmulation|Get/Set (Enum)||  
|DetectUTF8WithoutSignature|Get/Set (Boole)|Bir dosyanın kodlama imzası olmadığında, UTF-8 kodlaması kullanıp kullanmadığını belirler.|  
|TrackChanges|Get/Set (Boole)||  
  
## <a name="plain-text"></a>Düz Metin  
 `DTE.Properties("TextEditor", "PlainText")`  
  
 `PlainText` Düzenleyici Seçenekleri metin dosyaları düzenlendiğinde Düzenleyici ayarlarını etkiler. Her programlama dili ve [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] paketi varsa, kendi özel **metin düzenleyici** ayarlar. Örneğin, görüntüleme veya değiştirme için [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] Düzenleyicisi aynı ayarları kullanan `DTE.Properties("TextEditor", "CSharp") or DTE.Properties("TextEditor", "CSharp-Specific")`. İçin **SQL komut dosyası** Düzenleyicisi aynı ayarları kullanan `DTE.Properties("TextEditor", "SQL ")`.  
  
|Özellik Öğesi Adı|Değer|Açıklama|  
|------------------------|-----------|-----------------|  
|AutoListMembers|Get/Set (Boole)|Kullanıcı, bir değişken başvurusunun ardından nokta girdiğinde, kullanılabilir üye listesinin otomatik olarak görünüp görünmeyeceğini belirler.|  
|AutoListParams|Get/Set (Boole)|Kullanıcılar bir işlev adının ardından "(" girdiğinde, bağımsız değişken listesi açıklamasının otomatik olarak görüntülenip görüntülenmeyeceğini belirler.|  
|HideAdvancedMembers|Get/Set (Boole)|Deyim tamamlama özelliğinin tüm üyeleri mi, yoksa sadece sık kullanılanları mı listeleyeceğini belirler.|  
|VirtualSpace|Get/Set (Boole)|Boşluk karakterlerinin grafik olarak görüntülenip görüntülenmeyeceğini belirler. Bu ayar `true` neden `WordWrap` özelliği ayarlamak için (Bu listede) öğesi `false`.|  
|WordWrap|Get/Set (Boole)|Görünümün, uzun satırları sözcük sınırlarından kaydırıp kaydırmayacağını belirler. Bu ayar `true` neden `VirtualSpace` özelliği ayarlamak için (Bu listede) öğesi `false`.|  
|WordWrapGlyphs|Get/Set (Boole)|Satırın sonunda bir karakter (glif) görüntüler; bu da satırın bir sonraki satıra kaydırılacağını gösterir.|  
|EnableLeftClickForURLs|Get/Set (Boole)|Düzenleyicinin URL'lerin altını çizip çizmeyeceğini ve tek sol tıklamanın ilgili URL'yi sistemde kayıtlı Web tarayıcısında açmayı sağlayıp sağlamayacağını belirler.|  
|IndentStyle|Get/Set (<xref:EnvDTE.vsIndentStyle>)|Girintilendirme stilini belirler: Varsayılan, Akıllı veya Yok.|  
|TabSize|Get/Set (Long)|Bir sekmeye eşit gelen boşluk sayısını temsil eder. 1 ila 60 aralığı (sınırlar dahil) dışında bir tamsayı ayarlanması hata verir.|  
|InsertTabs|Get/Set (Boole)|Varsa `True`, sekme karakterleri girintileme yapılırken kullanılır.|  
|IndentSize|Get/Set (Long)|Tek bir girinti düzeyine eşit boşluk sayısını temsil eder. 1 ila 60 aralığı (sınırlar dahil) dışında bir tamsayı değeri ayarlanması hata verir.|  
|ShowLineNumbers|Get/Set (Boole)|Çekirdek düzenleyici belge görünümünün, sol kenar boşluğu boyunca satır numaraları görüntüleyip görüntülemeyeceğini belirler.|  
|ShowNavigationBar|Get/Set (Boole)|Düzenleyici pencerelerinin en üstünde açılan listeler ve düğmeler görünüp görünmeyeceğini belirler.|  
|CutCopyBlankLines|Get/Set (Boole)|Seçildiklerinde, boş satırları keser veya kopyalar:|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçeneklerini denetleme](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Seçenekler sayfalarında özellik öğelerinin adlarını belirleme](http://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Seçenekler sayfası, ortam düğümü özellikleri](../../ide/reference/options-page-environment-node-properties.md)   
 [Seçenekler Sayfası, Yazı Tipleri ve Renkler Düğümü Özellikleri](../../ide/reference/options-page-fonts-and-colors-node-properties.md)