---
title: "Düzenleyici ve dil Hizmetleri genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new -
ms.assetid: 8d04f8db-eda7-4b3e-b6eb-c06df104502a
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8490ddefaca1d170c1dbf379364cdf91b41b7803
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="extending-the-editor-and-language-services"></a>Düzenleyici ve dil Hizmetleri genişletme
Kendi Düzenleyicisi (örneğin, IntelliSense) dil hizmet özellikleri ekleyin ve özelliklerin çoğunu Visual Studio Kod Düzenleyicisi'ni genişletin.  Genişletmek tam listesi için bkz [dil hizmeti ve düzenleyici uzantı noktaları](../extensibility/language-service-and-editor-extension-points.md).  
  
 Yönetilen Genişletilebilirlik Çerçevesi (MEF) kullanarak çoğu Düzenleyicisi özelliklerini genişletir. Örneğin, genişletmek istediğiniz Düzenleyicisi özelliği söz dizimi renklendirme ise, bir MEF yazabilirsiniz *bileşen bölümü* istediğiniz farklı renklendirme ve bunları ele istediğiniz nasıl sınıflandırmalarını tanımlar. Düzenleyicisi ayrıca birden çok uzantı aynı özelliğini destekler.  
  
 Düzenleyici sunu katmanı tabanlı Windows Presentation Framework (WPF). WPF için esnek metin biçimlendirmesini grafik kitaplığını sağlar ve ayrıca grafikleri ve animasyonları gibi görselleştirmeleri sağlar.  
  
 Visual Studio SDK'sı olarak bilinir bağdaştırıcıları sağlar *dolgular* önceki sürümleri için yazılmış VSPackages desteklemek için. Bununla birlikte, varolan bir VSPackage varsa, daha iyi performans ve güvenilirlik elde etmek için yeni teknoloji güncelleştirme öneririz.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Dil hizmeti ve düzenleyici uzantıları ile çalışmaya başlama](../extensibility/getting-started-with-language-service-and-editor-extensions.md)|Uzantı düzenleyiciye oluşturma açıklanmaktadır.|  
|[İçinde Düzenleyicisi](../extensibility/inside-the-editor.md)|Düzenleyici genel yapısını açıklar ve bazı özellikleri listeler.|  
|[Düzenleyicideki Yönetilen Genişletilebilirlik Çerçevesi](../extensibility/managed-extensibility-framework-in-the-editor.md)|Yönetilen Genişletilebilirlik Çerçevesi (MEF) düzenleyiciyle kullanımı açıklanmaktadır.|  
|[Dil hizmeti ve düzenleyici uzantı noktaları](../extensibility/language-service-and-editor-extension-points.md)|Düzenleyicinin uzantı noktaları listeler. Uzantı noktalarını Genişletilebilir Düzenleyicisi özelliklerini temsil eder.|  
|[İzlenecek yol: bir görünüm Adornment, komutları ve ayarları (sütun kılavuzları) oluşturma](../extensibility/walkthrough-creating-a-view-adornment-commands-and-settings-column-guides.md)|İzlenecek yol ve belirli bir ekran genişliği kod sağlamanıza yardımcı olmak için sütun gudie çizgiler çizer bir görünüm adornment oluşturmayı açıklar.  Aynı zamanda okuma ve ayarlarını yazma yanı sıra bildirme ve komut penceresinde çağırabileceği komutları uygulama gösterir.|  
|[Düzenleyici içeri aktarmalar](../extensibility/editor-imports.md)|Uzantı aktarabilirsiniz hizmetleri listeler.|  
|[Eski kod düzenleyicisine uyarlama](../extensibility/adapting-legacy-code-to-the-editor.md)|Eski kod (önceden Visual Studio düzenleyiciyi genişletmek için 2010) uyarlamak için farklı yolları açıklanmaktadır.|  
|[Eski dil hizmetini geçirme](../extensibility/internals/migrating-a-legacy-language-service.md)|Temel VSPackage dil hizmeti geçirme açıklanmaktadır.|  
|[İzlenecek yol: bir içerik türü için bir dosya adı uzantısı bağlama](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)|Bağlantı bir dosya adı uzantısı için bir içerik türü gösterilmektedir.|  
|[İzlenecek yol: bir kenar karakter oluşturma](../extensibility/walkthrough-creating-a-margin-glyph.md)|Simge bir kenar boşluğuna eklemek gösterilmiştir.|  
|[İzlenecek yol: Metni vurgulama](../extensibility/walkthrough-highlighting-text.md)|Nasıl kullanılacağını gösterir *etiketleri* metin vurgulayın.|  
|[İzlenecek yol: anahat oluşturma](../extensibility/walkthrough-outlining.md)|Küme ayraçları belirli türdeki anahat oluşturma ekleme gösterir.|  
|[İzlenecek yol: Eşleşen küme parantezleri görüntüleme](../extensibility/walkthrough-displaying-matching-braces.md)|Eşleşen küme parantezleri vurgulamak gösterilmiştir.|  
|[İzlenecek yol: Quıckınfo araç ipuçlarını görüntüleme](../extensibility/walkthrough-displaying-quickinfo-tooltips.md)|Kod özellikleri, yöntemleri ve olayları gibi öğeleri açıklayan Quıckınfo açılan pencereler görüntülemek nasıl gösterir.|  
|[İzlenecek yol: İmza Yardım görüntüleme](../extensibility/walkthrough-displaying-signature-help.md)|İmza sayısı ve türleri parametreleri hakkında bilgi vermek açılan pencereler görüntülemek nasıl gösterir.|  
|[İzlenecek yol: Deyim tamamlama görüntüleme](../extensibility/walkthrough-displaying-statement-completion.md)|Deyim tamamlama uygulamak gösterilmiştir.|  
|[İzlenecek yol: Kod parçacıkları uygulama](../extensibility/walkthrough-implementing-code-snippets.md)|Kod parçacığı genişletme uygulamak gösterilmiştir.|  
|[İzlenecek yol: ampul önerileri görüntüleme](../extensibility/walkthrough-displaying-light-bulb-suggestions.md)|Ampuller kod önerileri için görüntülenecek gösterilmiştir.|  
|[İzlenecek yol: bir kabuk komut Düzenleyicisi uzantısı ile kullanma](../extensibility/walkthrough-using-a-shell-command-with-an-editor-extension.md)|Bir MEF Bileşeni ile menü komutu bir VSPackage içinde ilişkilendirilecek gösterilmiştir.|  
|[İzlenecek yol: bir kısayol tuşu Düzenleyicisi uzantısı ile kullanma](../extensibility/walkthrough-using-a-shortcut-key-with-an-editor-extension.md)|İle nasıl bir VSPackage menüsünde kısayolu bir MEF Bileşeni ile ilişkilendirildiğini gösterir.|  
|[Yönetilen Genişletilebilirlik Çerçevesi (MEF)](/dotnet/framework/mef/index)|Yönetilen Genişletilebilirlik Çerçevesi'hakkında (MEF) hakkında bilgi sağlar.|  
|[Windows Presentation Foundation](/dotnet/framework/wpf/index)|Windows Presentation Foundation (WPF) hakkında bilgi sağlar.|  
  
## <a name="reference"></a>Başvuru  
 Visual Studio düzenleyicisinde şu ad alanlarından içerir.  
  
 <xref:Microsoft.VisualStudio.Language.Intellisense>  
  
 <xref:Microsoft.VisualStudio.Language.StandardClassification>  
  
 <xref:Microsoft.VisualStudio.Editor>  
  
 <xref:Microsoft.VisualStudio.Text>  
  
 <xref:Microsoft.VisualStudio.Text.Adornments>  
  
 <xref:Microsoft.VisualStudio.Text.Classification>  
  
 <xref:Microsoft.VisualStudio.Text.Differencing>  
  
 <xref:Microsoft.VisualStudio.Text.Document>  
  
 <xref:Microsoft.VisualStudio.Text.Editor>  
  
 <xref:Microsoft.VisualStudio.Text.Editor.OptionsExtensionMethods>  
  
 <xref:Microsoft.VisualStudio.Text.Formatting>  
  
 <xref:Microsoft.VisualStudio.Text.IncrementalSearch>  
  
 <xref:Microsoft.VisualStudio.Text.Operations>  
  
 <xref:Microsoft.VisualStudio.Text.Outlining>  
  
 <xref:Microsoft.VisualStudio.Text.Projection>  
  
 <xref:Microsoft.VisualStudio.Text.Tagging>  
  
 <xref:Microsoft.VisualStudio.Utilities>