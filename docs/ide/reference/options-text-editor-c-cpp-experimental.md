---
title: "Seçenekler, metin düzenleyici, C/C++, Deneysel | Microsoft Docs"
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C/C++.Experimental
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Experimental
- VS.ToolsOptionsPages.Text_Editor.C\C++.Experimental
ms.assetid: b9e9dda2-350c-460d-b368-37d6c5342eee
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: d67907a99851e09bf384c96b6ff6b87b4882cd30
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="options-text-editor-cc-experimental"></a>Seçenekler, metin düzenleyici, C/C++, Deneysel
Bu seçeneklerinde değişiklik yaparak C veya C++ programlama zaman IntelliSense ve gözatma veritabanı ile ilgili davranışı değiştirebilirsiniz. Bu özellikler gerçekten Deneysel ve değiştirilebilir veya sonraki bir sürümde Visual Studio'dan kaldırıldı. Bu konuda yer alan Visual Studio 2017 seçenekler açıklanmaktadır. Visual Studio 2015 için bkz: [seçenekler, metin düzenleyici, C/C++, Experimental](https://msdn.microsoft.com/library/mt591979.aspx) 
  
 Bu özellik sayfasında erişmek için basın **Control + Q** etkinleştirmek için `Quick Launch` ve "Deneysel" yazın. Hızlı Başlat Sayfası sonra ilk birkaç harfini bulur. Seçerek için de alabilirsiniz **Araçlar | Seçenekler** ve genişletme **metin düzenleyici**, ardından **C/C++**ve ardından **Experimental**.  

 Bu özellikler, Visual Studio 2017 yüklemesinde kullanılabilir.  
  
> [!NOTE]
>  Bilgisayarınız, aşağıdaki yönergelerde yer alan Visual Studio kullanıcı arabirimi öğelerinden bazıları için farklı adlar veya konumlar gösterebilir. Sahip olduğunuz Visual Studio sürümü ve kullandığınız ayarlar bu öğeleri belirler. Bkz: [Visual Studio IDE'yi kişiselleştirme](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="enable-predictive-intellisense"></a>Tahmine dayalı IntelliSense'i etkinleştirme
Tahmine dayalı IntelliSense bağlam için uygun olan sonuçları görebilmesi için IntelliSense açılır listede gösterilen sonuçları sayısını sınırlar. Örneğin, <code>int x =</code> ve IntelliSense açılır çağırma, yalnızca tamsayı veya tamsayı döndüren işlevler görürsünüz. Tahmine dayalı IntelliSense varsayılan olarak kapalıdır.

## <a name="enable-faster-project-load"></a>Daha hızlı proje yüklemesini etkinleştir 
**Visual Studio 2017 15.3 ve sonraki sürümleri**: Bu özellik artık adlı **proje önbelleğe almayı etkinleştir** ve e taşınmıştır [VC ++ proje ayarları](vcpp-project-settings-projects-and-solutions-options-dialog-box.md) özellik sayfası.
Bu seçenek, Visual Studio Proje verileri önbelleğe almak için etkinleştirir sonraki projeyi açtığınızda, proje dosyalarını yeniden hesaplama yerine verileri önbelleğe yükleyebilirsiniz. Önbelleğe alınan verileri kullanarak proje yük zamanı önemli ölçüde hızlandırılabilir.  

## <a name="additional-features-in-the-visual-studio-gallery"></a>Visual Studio Galerisi ek özellikleri
Visual Studio Galerisi içinde ek bir metin Düzenleyicisi özellikleri için listesine bakın [burada](http://go.microsoft.com/fwlink/?LinkId=692016). Örnek [C++ hızlı düzeltmeler](https://visualstudiogallery.msdn.microsoft.com/be91feef-8dc3-4f7a-ac9f-f34e7ca5918f), aşağıdakileri destekler:  
  
-   **Eksik ekleme #include** -ilgili öneren #include ait kodunuzu bilinmeyen sembolleri  
  
-   **Kullanarak Ekle simgesi ad/tam olarak nitelemek** - önceki öğeyi gibi ancak ad alanları için  
  
-   **Eksik noktalı virgül Ekle**  
  
-   **MSDN Yardım** -arama MSDN hata iletileri  
  
Her iki vurgulu bir ampul almak veya varsayılan klavye kısayolu Ctrl + nokta (Ctrl +.) kullanmak üzere bir dalgalı olabilir. Klavye kısayolu için düzeltme işareti belirli bir hata ya da belirtecinde konumlandırılması gerektiğini değil unutmayın; yalnızca o satırdaki her şey için öneriler çağrılacak hata aynı satır üzerinde olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dile özgü Düzenleyici seçeneklerini ayarlama](../../ide/reference/setting-language-specific-editor-options.md)   
 [C++ (VC Blog) yeniden düzenleme](http://blogs.msdn.com/b/vcblog/archive/2014/11/14/all-about-c-refactoring-in-visual-studio-2015-preview.aspx)
