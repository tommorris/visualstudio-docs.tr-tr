---
title: "Visual Studio statik kod analizi kullanarak UWP uygulamaları Visual Basic ve C# kod kalitesini çözümleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.propertypages.csvb.express
ms.assetid: cab553fc-19a9-4cbf-858e-8200258ffe50
caps.latest.revision: "14"
author: erickson-doug
ms.author: douge
manager: douge
ms.openlocfilehash: e61f307872f60da316480d3654507b5225588f41
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2017
---
# <a name="analyze-visual-basic-and-c-code-quality-in-uwp-apps-using-visual-studio-static-code-analysis"></a>Visual Studio statik kod analizi kullanarak UWP uygulamaları Visual Basic ve C# kod kalitesini çözümleme
![Windows ve Windows Phone için geçerlidir](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Visual Studio Express kod çözümleme aracı kodunuz ortak kusurları kümesi ve iyi bir programlama uygulama ihlalleri için inceler. Kod çözümleme aracı, geçerli olan, ancak hala siz veya kodunuzu kullanan diğer kişiler için sorunlarına neden olabilir belirli kod düzenleri arar çünkü kod analizi uyarıları derleyici hataları ve Uyarıları farklılık gösterir. Kod çözümleme kodunuzda sınama aracılığıyla bulmak zordur kusurları da bulabilirsiniz. Kod çözümleme aracı geliştirme sürecinde düzenli aralıklarla çalışan tamamlanan uygulama kalitesini geliştirebilirsiniz.  
  
> [!NOTE]
>  Visual Studio Ultimate, Visual Studio Premium ve Visual Studio Professional, Kod Analizi tam işlevselliğini kullanabilirsiniz. Bkz: [kod çözümleme araçları ile uygulama kalitesini analiz etme](http://msdn.microsoft.com/library/dd264897.aspx) MSDN Kitaplığı'nda.  
  
## <a name="in-this-topic"></a>Bu konuda  
 Hakkında bilgi alabilirsiniz:  
  
 [Çalışan kod çözümleme](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Run)  
  
 [Çözümleme ve Kod Analizi uyarıları çözümleme](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Analyze)  
  
 [Kod çözümleme uyarıları gizleme](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Suppress)  
  
 [Arama ve kod çözümleme sonuçlarını filtreleme](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Search)  
  
 [Visual Basic ve C# Kod Analizi uyarıları](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Warnings)  
  
##  <a name="BKMK_Run"></a>Çalışan kod çözümleme  
 Visual Studio çözümünüzü Kod Analizi çalıştırmak için:  
  
-   Üzerinde **yapı** menüsünde seçin **çalıştırmak Kod Analizi çözüm üzerinde**.  
  
 Kod çözümleme her zaman otomatik olarak çalıştırmak için bir proje oluşturun:  
  
1.  Çözüm Gezgini'nde proje adına sağ tıklayın ve ardından **özellikleri**.  
  
2.  Proje özellik sayfası seçin **Kod Analizi** ve ardından **etkinleştirme kodu (tanımlar CODEANALYSIS sabiti) çözümleme yapı**.  
  
 Çözüm derlenir ve Kod Analizi çalıştırır. Sonuçları Kod Analizi penceresinde görüntülenir.  
  
 ![Kod çözümleme penceresi](../test/media/ca_managed_collapsed.png "CA_Managed_Collapsed")  
  
##  <a name="BKMK_Analyze"></a>Çözümleme ve Kod Analizi uyarıları çözümleme  
 Belirli bir uyarı çözümlemek için Kod Analizi penceresinde uyarı başlığını tıklatın. Sorun hakkında ayrıntılı bilgileri görüntülemek için uyarı genişletir.  
  
 ![Kod çözümleme uyarısı Genişletilmiş](../test/media/ca_managed_callouts.png "CA_Managed_Callouts")  
  
 Bir uyarı genişlettiğinizde, uyarıya neden olan kod satırı Visual Studio Kod Düzenleyicisi'nde vurgulanır.  
  
 ![Kod çözümleme metni vurgulama](../test/media/ca_managed_sourceline.png "CA_Managed_SourceLine")  
  
 Sorunu anlamasına sonra kodunuzda çözebilirsiniz. Ardından uyarı artık Kod Analizi penceresinde görüntülenir ve yeni uyarılar gerçekleşti, düzeltme henüz emin olmak için Kod Analizi yeniden çalıştırın.  
  
> [!TIP]
>  Kod çözümleme Kod Analizi penceresinden yeniden çalıştırabilirsiniz. Tıklatın **Çözümle** düğmesine tıklayın ve analiz kapsamını seçin. Analiz çözümün tamamında veya seçili bir proje üzerinde yeniden çalıştırabilirsiniz.  
  
##  <a name="BKMK_Suppress"></a>Kod çözümleme uyarıları gizleme  
 Kod çözümleme uyarısı düzeltme değil zaman karar verebilirsiniz zamanlar vardır. Uyarı çözümleme sorunu kodunuzu herhangi bir gerçek uygulaması içinde çıkabilecek olasılık ile ilgili çok fazla değiştirilemeyen gerektirir karar verebilirsiniz. Veya uyarıda kullanılan analiz belirli bağlam için uygun olduğunu düşünüyorsanız. Kod Analizi penceresinde artık görünecekleri bireysel uyarıları gizleyebilirsiniz.  
  
 Bir uyarıyı gizlemek için:  
  
1.  Ayrıntılı bilgi görüntülenmiyorsa genişletmek için uyarı başlığını tıklatın.  
  
2.  Seçin **Eylemler** uyarı sonundaki bağlantı.  
  
3.  İşaret **bastırmak ileti** ve ya da seçin **içinde kaynak** veya **gizleme dosyasını**.  
  
    -   **Kaynağındaki** ekler bir `SuppressMessage` uyarı oluşturulduğu yöntemi yukarıdaki kaynak dosya özniteliği. Bu, gizleme daha bulunabilmesini sağlar.  
  
    -   **Gizleme dosyasındaki** ekler bir `SuppressMessage` özniteliğini **GlobalSuppressions.cs** projenin dosya. Bu suppressions Yönetimi kolaylaştırabilir. Unutmayın `SuppressMessage` eklenen öznitelik **GlobalSuppression.cs** ayrıca uyarı oluşturan yöntemi hedefler. Uyarı engelleme genel.  
  
     Kararınızı kaynak dosya ya da gizleme dosyanın uyarısı engellenip engellenmeyeceğini, kodlama stili ve gereksinimlerine bağlıdır.  
  
##  <a name="BKMK_Search"></a>Arama ve kod çözümleme sonuçlarını filtreleme  
 Uyarı iletilerini uzun listeler arayabilir ve birden çok proje çözümü uyarıları filtreleyebilirsiniz.  
  
 ![Arama ve Kod Analizi penceresi filtre](../test/media/ca_searchfilter.png "CA_SearchFilter")  
  
 İçinde [!INCLUDE[vs_dev11_expwin_long](../misc/includes/vs_dev11_expwin_long_md.md)], tüm kod çözümleme uyarıları olan uyarı önem derecesi.  
  
##  <a name="BKMK_Warnings"></a>Visual Basic ve C# Kod Analizi uyarıları  
 Kod çözümleme aşağıdaki uyarıları başlatır:  
  
 [CA1001: atılabilir alanlara sahip olan türler atılabilir olmalıdır](http://msdn.microsoft.com/library/ms182172.aspx)  
  
 [CA1821: Boş Sonlandırıcıları kaldırın](http://msdn.microsoft.com/library/bb264476.aspx)  
  
 [CA2213: Atılabilen alanlar atılmalıdır](http://msdn.microsoft.com/library/ms182328.aspx)  
  
 [CA2229: Serileştirme oluşturucularını uygulayın](http://msdn.microsoft.com/library/ms182343.aspx)  
  
 [CA2231: ValueType.Equals geçersiz kılma üzerinde aşırı işleci eşittir.](http://msdn.microsoft.com/library/ms182359.aspx)
