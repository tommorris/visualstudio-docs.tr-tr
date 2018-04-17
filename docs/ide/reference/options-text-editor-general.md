---
title: Seçenekler, metin düzenleyici, genel | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VS.TOOLSOPTIONSPAGES.TEXT_EDITOR.SQL_SERVER_TOOLS.GENERAL
- VS.ToolsOptionsPages.Text_Editor.All_Languages.General
- VS.ToolsOptionsPages.Text_Editor.RDL_Expression.General
- VS.ToolsOptionsPages.Text_Editor.SQL.General
- vs.toolsoptionspages.text_editor
- VS.ToolsOptionsPages.Text_Editor.XML.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL80.General
- VS.ToolsOptionsPages.Text_Editor.CSS
- VS.ToolsOptionsPages.Text_Editor.Plain_Text.General
- VS.ToolsOptionsPages.Text_Editor.SQL_Script.General
- VS.ToolsOptionsPages.Text_Editor.CSharp.General
- VS.ToolsOptionsPages.Text_Editor.All_Languages
- VS.ToolsOptionsPages.Text_Editor.T-SQL7.General
- VS.ToolsOptionsPages.Text_Editor.Basic.General
- VS.ToolsOptionsPages.Text_Editor.T-SQL.General
- VS.ToolsOptionsPages.Text_Editor.F#.Tabs
- VS.ToolsOptionsPages.Text_Editor.F#
- VS.ToolsOptionsPages.Text_Editor.PL/SQL.General
- VS.ToolsOptionsPages.Text_Editor.C/C++.General
- VS.ToolsOptionsPages.Text_Editor.Plain_Text
- VS.ToolsOptionsPages.Text_Editor.HTML
- VS.ToolsOptionsPages.Text_Editor.XAML.General
- VS.ToolsOptionsPages.Text_Editor
- VS.ToolsOptionsPages.Text_Editor.F#.General
- VS.ToolsOptionsPages.Text_Editor.XOML.General
- VS.ToolsOptionsPages.Text_Editor.SQL
- vs.toolsoptionspages.text_editor.c/c++
- VS.ToolsOptionsPages.Text_Editor.SQL_Script
- VS.ToolsOptionsPages.Text_Editor.T-SQL90.General
- VS.ToolsOptionsPages.Text_Editor.General
- VS.ToolsOptionsPages.Text_Editor.CSharp
- VS.ToolsOptionsPages.Text_Editor.Python
- VS.ToolsOptionsPages.Text_Editor.R
helpviewer_keywords:
- Text Editor Options dialog box
- Code Editor
- Text Editor [Visual Studio]
- editors, global settings
ms.assetid: 4ac21e48-3243-4141-9058-7eaf12b3cde7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d215503d182078196337e6ad1110e41b0e888865
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="options-text-editor-general"></a>Seçenekler, Metin Düzenleyici, Genel

Bu iletişim kutusunu Visual Studio kod ve Metin Düzenleyicisi için genel ayarları değiştirmenize olanak verir. Bu iletişim kutusunu görüntülemek için seçin **seçenekleri** üzerinde **Araçları** menüsünde genişletin **metin düzenleyici** klasörünü ve ardından **genel**.

> [!NOTE]
> Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="settings"></a>Ayarlar

### <a name="drag-and-drop-text-editing"></a>Sürükle ve bırak metin düzenleme

Seçili olduğunda, seçerek ve geçerli belge veya herhangi bir açık belgeye içinde başka bir konuma fareyle sürükleyerek metin taşımanızı sağlar.

### <a name="automatic-delimiter-highlighting"></a>Otomatik sınırlayıcı vurgulama

Seçili olduğunda, parametreleri veya öğesi-değer çiftleri yanı sıra, eşleşen küme parantezleri ayrı sınırlayıcı karakterleri vurgulanır.

### <a name="track-changes"></a>Değişiklikleri İzle

Kod Düzenleyicisi seçildiğinde, dikey sarı bir çizgi dosyanın en son kaydedilişinden değişti kodu işaretlemek için Seçim kenar görünür. Değişiklikleri kaydetmek, dikey çizgileri yeşil olur.

### <a name="auto-detect-utf-8-encoding-without-signature"></a>UTF-8 kodlamasını imza olmadan otomatik olarak algıla

Varsayılan olarak, bayt sırası işaretleri veya charset etiketleri için arama yaparak kodlama Düzenleyicisi algılar. Hiçbiri geçerli belgede bulunursa, Kod düzenleyicisinde bayt dizileri tarayarak UTF-8 kodlaması otomatik algıla dener. Kodlama otomatik algılama devre dışı bırakmak için bu seçeneği temizleyin.

## <a name="display"></a>Ekran

### <a name="selection-margin"></a>Seçim kenar boşluğu

Seçili olduğunda düzenleyici metin alanı sol kenarı boyunca dikey boşluğu görüntüler. Bir metin satırının tamamına seçin veya tıklatın ve ardışık satırlık metin seçmek için sürükleyin bu kenar tıklatabilirsiniz.

|Seçim kenar boşluğu|Seçim kenar devre dışı|
|-------------------------|--------------------------|
|![HTMLpageSelectionMarginOn ekran görüntüsü](../../ide/reference/media/vxselmaron.gif "vxSelmaron")|![HTMLpageSelectionMarginOff ekran görüntüsü](../../ide/reference/media/vxselmaroff.gif "vxSelmaroff")|

### <a name="indicator-margin"></a>Gösterge Boşluğu

Seçili olduğunda, metin alanı düzenleyicinin sol kenarı dışında dikey boşluğu görüntüler. Bu kenar boşluğunda tıklattığınızda, bir simge ve metin için ilgili araç ipucu görünür. Örneğin, kesme noktası ya da görev listesi kısayollarını göstergesi kenar boşluğunda görünür. Gösterge kenar boşluğu bilgileri yazdırma değil.

### <a name="vertical-scroll-bar"></a>Dikey kaydırma çubuğu

Seçili olduğunda, görünüm öğelerine Düzenleyicisi görüntüleme alanı dışında kalan yukarı ve aşağı kaydırma olanak tanıyan dikey bir kaydırma çubuğu görüntüler. Dikey kaydırma çubukları kullanılabilir değilse, Page Up, Page Down ve imleci anahtarları kaydırmak için kullanabilirsiniz.

### <a name="horizontal-scroll-bar"></a>Yatay kaydırma çubuğu

Seçili olduğunda, görünüm öğelerine Düzenleyicisi görüntüleme alanı dışında kalan yan yana kaydırma olanak tanıyan bir yatay kaydırma çubuğu görüntüler. Yatay kaydırma çubukları kullanılamıyorsa, kaydırmak için imleç tuşlarını kullanabilirsiniz.

### <a name="highlight-current-line"></a>Geçerli satırı vurgulayın

Seçili olduğunda, imlecin bulunduğu kod satırı çevresinde gri bir kutu görüntüler.

## <a name="see-also"></a>Ayrıca bkz.

- [Seçenekler, metin düzenleyici, tüm diller](../../ide/reference/options-text-editor-all-languages.md)
- [Seçenekler, metin düzenleyici, tüm diller, sekmeler](../../ide/reference/options-text-editor-all-languages-tabs.md)
- [Seçenekler, metin düzenleyici, dosya uzantısı](../../ide/reference/options-text-editor-file-extension.md)
- [Klavye Kısayollarını Tanımlama ve Özelleştirme](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)
- [Düzenleyiciyi Özelleştirme](../../ide/customizing-the-editor.md)
- [IntelliSense Kullanma](../../ide/using-intellisense.md)