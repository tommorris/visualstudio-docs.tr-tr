---
title: "Özellikler penceresi düğmelerini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Properties window, buttons
ms.assetid: bdd2e3a7-ae6e-4e88-be1a-e0e3b7ddbbcc
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c4cd83a8d8e72c18f8a6929e8985f7a8635a940d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="properties-window-buttons"></a>Özellikler penceresi düğmeleri
Geliştirme dilini ve ürün türüne bağlı olarak, belirli düğmeleri varsayılan araç çubuğunda görüntülenir **özellikleri** penceresi. Tüm durumlarda **kategoriler**, **Alphabetized**, **özellikleri**, ve **özellik sayfaları** düğmeleri görüntülenir. Visual C# ve Visual Basic **olayları** düğmesini de görüntülenir. Belirli Visual C++ projelerinde **VC ++ iletileri** ve **VC geçersiz kılmaları** düğmeleri görüntülenir. Diğer proje türleri için ek düğmeler görüntülenebilir. Düğmeleri hakkında daha fazla bilgi için **özellikleri** penceresinde bkz [Özellikler penceresini](../../ide/reference/properties-window.md).  
  
## <a name="implementation-of-properties-window-buttons"></a>Özellikler penceresi düğmelerini uygulaması  
 Tıkladığınızda **kategoriler** button, Visual Studio çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties> arabirimi özelliklerini kategoriye göre sıralamak için odağa sahip nesne üzerinde. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>üzerinde uygulanan `IDispatch` için sunulan nesne **özellikleri** penceresi.  
  
 Negatif değerler sahip 11 önceden tanımlanmış bir özelliği kategorisi vardır. Özel kategoriler tanımlayabilirsiniz, ancak bunları önceden tanımlanmış kategorilerden ayırmak için pozitif değerler atamanızı öneririz.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.MapPropertyToCategory%2A> Yöntemi belirtilen özellik için uygun özelliği kategori değeri döndürür. <xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties.GetCategoryName%2A> Yöntemi kategori adı içeren bir dize döndürür. Yalnızca Visual Studio standart özellik kategori değerlerini bildiği için destek özel kategori değerlerini sağlamanız gerekir.  
  
 Tıkladığınızda **Alphabetized** düğmesi özellikleri adına göre alfabetik olarak görüntülenir. Adları tarafından alınır `IDispatch` yerelleştirilmiş bir sıralama algoritması göre.  
  
 Zaman **özellikleri** penceresi açık **özellikleri** düğmesi otomatik olarak gösterilen seçili. Ortamının diğer bölümlerinde aynı düğmesi görüntülenir ve göstermek için tıklayabilirsiniz **özellikleri** penceresi.  
  
 **Özellik sayfaları** düğmesi kullanılamaz olursa `ISpecifyPropertyPages` seçili nesne için uygulanmadı. Çözümler ve projeler genellikle ilişkili görüntü yapılandırmaya bağlı özellikleri özellik sayfaları, ancak bunlar olması da ilişkilendirilebilir proje öğeleri (örneğin, Visual C++'ta).  
  
> [!NOTE]
>  Araç çubuğu düğmelerine ekleyemezsiniz **özellikleri** yönetilmeyen kodu kullanarak penceresi. Araç çubuğu düğmesi eklemek için türetilen yönetilen bir nesne oluşturma <xref:System.Windows.Forms.Design.PropertyTab>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genişletme özellikleri](../../extensibility/internals/extending-properties.md)