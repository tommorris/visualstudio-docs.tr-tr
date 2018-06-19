---
title: Seçenekler, metin düzenleyici, C/C++, Deneysel
ms.date: 08/02/2017
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C/C++.Experimental
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Experimental
- VS.ToolsOptionsPages.Text_Editor.C\C++.Experimental
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- cplusplus
ms.openlocfilehash: 36826a998c579526487b440ebe9d3ddab228daab
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945977"
---
# <a name="options-text-editor-cc-experimental"></a>Seçenekler, metin düzenleyici, C/C++, Deneysel

Bu seçeneklerinde değişiklik yaparak C veya C++ programlama zaman IntelliSense ve gözatma veritabanı ile ilgili davranışı değiştirebilirsiniz. Bu özellikler gerçekten Deneysel ve değiştirilebilir veya sonraki bir sürümde Visual Studio'dan kaldırıldı. Bu konuda yer alan Visual Studio 2017 seçenekler açıklanmaktadır. Visual Studio 2015 için bkz: [seçenekler, metin düzenleyici, C/C++, Experimental](https://msdn.microsoft.com/library/mt591979.aspx)

Bu özellik sayfasında erişmek için basın **Control + Q** etkinleştirmek için `Quick Launch` ve "Deneysel" yazın. Hızlı Başlat Sayfası sonra ilk birkaç harfini bulur. Seçerek için de alabilirsiniz **Araçlar | Seçenekler** ve genişletme **metin düzenleyici**, ardından **C/C++** ve ardından **Experimental**.

Bu özellikler, Visual Studio 2017 yüklemesinde kullanılabilir.

> [!NOTE]
> Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="enable-predictive-intellisense"></a>Tahmine dayalı IntelliSense'i etkinleştirme

Tahmine dayalı IntelliSense bağlam için uygun olan sonuçları görebilmesi için IntelliSense açılır listede gösterilen sonuçları sayısını sınırlar. Örneğin, <code>int x =</code> ve IntelliSense açılır çağırma, yalnızca tamsayı veya tamsayı döndüren işlevler görürsünüz. Tahmine dayalı IntelliSense varsayılan olarak kapalıdır.

## <a name="enable-faster-project-load"></a>Daha hızlı proje yüklemesini etkinleştir

**Visual Studio 2017 15.3 ve sonraki sürümleri**: Bu özellik artık adlı **proje önbelleğe almayı etkinleştir** ve e taşınmıştır [VC ++ proje ayarları](vcpp-project-settings-projects-and-solutions-options-dialog-box.md) özellik sayfası.
Bu seçenek, Visual Studio Proje verileri önbelleğe almak için etkinleştirir sonraki projeyi açtığınızda, proje dosyalarını yeniden hesaplama yerine verileri önbelleğe yükleyebilirsiniz. Önbelleğe alınan verileri kullanarak proje yük zamanı önemli ölçüde hızlandırılabilir.

## <a name="additional-features-in-the-visual-studio-marketplace"></a>Visual Studio Market'te ek özellikler

Ek metin düzenleyicisi özelliklerinde göz atabilirsiniz [Visual Studio Market'te](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=All&sortBy=Downloads). Örnek [C++ hızlı düzeltmeler](https://marketplace.visualstudio.com/items?itemName=VisualCppDevLabs.CQuickFixes2017), aşağıdakileri destekler:

- **Eksik ekleme #include** -ilgili öneren #include ait kodunuzu bilinmeyen sembolleri

- **Kullanarak Ekle simgesi ad/tam olarak nitelemek** - önceki öğeyi gibi ancak ad alanları için

- **Eksik noktalı virgül Ekle**

- **Çevrimiçi Yardım** -arama hata iletileri için çevrimiçi Yardım

- ve daha fazlası...

## <a name="see-also"></a>Ayrıca bkz.

- [Dile Özgü Düzenleyici Seçeneklerini Ayarlama](../../ide/reference/setting-language-specific-editor-options.md)
- [C++ (VC Blog) yeniden düzenleme](http://blogs.msdn.com/b/vcblog/archive/2014/11/14/all-about-c-refactoring-in-visual-studio-2015-preview.aspx)
