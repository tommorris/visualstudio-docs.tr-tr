---
title: "Özellikleri görüntüle kılavuz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: properties [Visual Studio SDK], grid
ms.assetid: 318e41b0-acf5-4842-b85e-421c9d5927c5
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 88720010c178fb1ca3a4c2425002f5f34e26e777
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-display-grid"></a>Izgarayı özelliklerini görüntüle
**Özellikleri** penceresi bir kılavuz alanlarını görüntüler. Sol sütunda özellik adları içerir; Sağ sütunda özellik değerlerini içerir.  
  
## <a name="working-with-the-grid"></a>Kılavuz ile çalışma  
 İki sütun listesi tasarım zamanı ve geçerli ayarları değiştirilebilir yapılandırma bağımsız özellikleri gösterir. Tüm özellikleri gösterilmez unutmayın. Bir özellik ayarlanabilir gizli olarak, örneğin, uygulama tarafından <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> yöntemi. Özellikle, alt özelliklerine sahip Gizle özellikleri:  
  
1.  Ayarlama `pfDisplay` parametresinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.DisplayChildProperties%2A> için `FALSE`.  
  
2.  Ayarlama `pfHide` parametresinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> için `TRUE`.  
  
 Anında iletme bilgilere **özellikleri** penceresi, IDE kullanır <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>. <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>VSPackages tarafından görüntülenmesini ilgili özellikleri seçilebilir nesneleriyle içeren her bir pencere için çağrılır **özellikleri** penceresi. **Çözüm Gezgini**'s uyarlamasını <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> çağrıları `GetProperty` kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> proje hiyerarşinizdeki hiyerarşideki göz nesneler edinmeye.  
  
 VSPackage desteklemediği varsa <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>, IDE kullanma girişiminde <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> değeri kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> hiyerarşi öğesi veya öğeleri sağlayın.  
  
 VSPackage oluşturmanız gerekmez, projenizin <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> IDE sağlanan penceresi paket, bunu uyguladığı için (örneğin, **Çözüm Gezgini**) oluşturur <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> kendi adına.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>IDE tarafından adında üç yöntem oluşur:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.CountObjects%2A>Görüntülenecek seçilen nesne sayısını içeren **özellikleri** penceresi.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A>döndürür `IDispatch` görüntülenmesini seçili nesneler **özellikleri** penceresi.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A>tarafından döndürülen nesnelerden herhangi birini olanaklı kılar <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A> kullanıcı tarafından seçilmelidir. Bu, kullanıcı arabiriminde görüntülenecek seçimi görsel olarak güncelleştirmek VSPackage sağlar.  
  
 **Özellikleri** penceresi ayıklar bilgilerinden `IDispatch` taranan özelliklerini almak için nesneleri. Özellikler tarayıcısını kullanır `IDispatch` hangi özelliklerin nesne sorulacak sorgulayarak desteklediği `ITypeInfo`, öğesinden elde `IDispatch::GetTypeInfo`. Tarayıcı, bu değerleri doldurmak için sonra kullanır **özellikleri** penceresi ve ayrı ayrı özellikler için değerleri kılavuzda görüntülenen Değiştir. Özellik bilgileri nesnesi içinde korunur.  
  
 Döndürülen nesneleri desteklemediğinden `IDispatch`, çağıran ya da çağırarak nesnenin adı gibi bilgileri edinebilirsiniz `IDispatch::Invoke` veya `ITypeInfo::Invoke` istenilen bilgileri temsil eden bir önceden tanımlanmış gönderme tanımlayıcı (DISPID). Kullanıcı tanımlı tanımlayıcıları ile çakışmadığından emin olmak için bildirilen DISPID değerleri negatiftir.  
  
 **Özellikleri** penceresi alanları özgü özellikleri seçili nesnenin özniteliklerini bağlı olarak farklı türde görüntüler. Bu alanlar düzenleme kutularını, açılan listeleri ve özel Düzenleyici iletişim kutuları bağlantılar içerir.  
  
-   Numaralandırılmış bir listede yer alan değerleri tarafından alınır bir <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.GetObjects%2A> için sorgu `IDispatch`. Alan adı çift tıklatarak ya da değeri tıklatıp yeni değer aşağı açılan listeden seçerek numaralandırılmış bir listeden elde edilen değerleri özellikleri kılavuzunda değiştirilebilir. Önceden tanımlanmış ayarları numaralandırılmış listeleri özellikler için özellik adını özellikler listesinde çift kullanılabilir seçenekleri döngüleri. Önceden tanımlanmış özellikler gibi true/false, yalnızca iki seçenek için seçenekler arasında geçiş yapmak için özellik adına çift tıklayın.  
  
-   Varsa <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HasDefaultValue%2A> olan `false`, gösteren değeri değişti, değer kalın metin olarak görüntülenir. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.CanResetPropertyValue%2A>özgün değer sıfırlanabilir değeri belirlemek için kullanılır. Bu nedenle, değer sağ tıklayıp seçerek varsayılanına değiştirebilirsiniz, **sıfırlama** menüsünde görüntülenir. Aksi halde değer varsayılanına el ile değiştirmeniz gerekir. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>Yerelleştirme ve tasarım sırasında görüntülenen özellik adlarını gizlemek sağlar, ancak çalışma zamanında görüntülenen özellik adları etkilemez.  
  
-   Üç nokta (...) düğmesini tıklatarak kullanıcı (Renk Seçici veya yazı tipi listesi gibi) seçebileceği özellik değerlerinin bir listesini görüntüler. <xref:Microsoft.VisualStudio.Shell.Interop.IProvidePropertyBuilder>Bu değerleri sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellikleri Genişletme](../../extensibility/internals/extending-properties.md)