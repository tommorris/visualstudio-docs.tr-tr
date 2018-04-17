---
title: Derleme bilgileri iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vb.ProjectPropertiesAssemblyInfo
helpviewer_keywords:
- Assembly Information dialog box
ms.assetid: 8f1f6449-e03d-4a5b-9076-d3b1f84ada48
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 07c81e392a4513ffa97a384e9aa60147c3a71290
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="assembly-information-dialog-box"></a>Derleme Bilgileri İletişim Kutusu
**Derleme bilgilerini** iletişim kutusu değerleri belirtmek için kullanılan [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] projenizi ile otomatik olarak oluşturulan AssemblyInfo dosyasında depolanan genel derleme öznitelikleri. İçinde **Çözüm Gezgini**, dosya bulunan **My proje** düğümünde [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] (tıklatın **tüm dosyaları göster** görüntülemek için); altında bulunan  **Özellikler** içinde [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]. Derleme özniteliklerinin hakkında daha fazla bilgi için bkz: [öznitelikleri](http://msdn.microsoft.com/Library/ae334cee-d96c-4243-a5e3-06dd7fcaf205).  
  
 Bu iletişim kutusunu erişmek için bir proje düğümünde seçin **Çözüm Gezgini**ve ardından **proje** menüsünde tıklatın **özellikleri**. Zaman **Proje Tasarımcısı** görünen tıklatın **uygulama** sekmesi. Üzerinde **uygulama** sayfasında, **derleme bilgilerini** düğmesi.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Başlık**  
 Derleme bildirimi için bir başlık belirtir. Karşılık gelen <xref:System.Reflection.AssemblyTitleAttribute>.  
  
 **Açıklama**  
 Derleme bildirimi için isteğe bağlı bir açıklama belirtir. Karşılık gelen <xref:System.Reflection.AssemblyDescriptionAttribute>.  
  
 **Şirket**  
 Derleme bildirimi için bir şirket adı belirtir. Karşılık gelen <xref:System.Reflection.AssemblyCompanyAttribute>.  
  
 **Ürün**  
 Derleme bildirimi ürün adını belirtir. Karşılık gelen <xref:System.Reflection.AssemblyProductAttribute>.  
  
 **Telif Hakkı**  
 Derleme bildirimi için telif hakkı uyarısı belirtir. Karşılık gelen <xref:System.Reflection.AssemblyCopyrightAttribute>.  
  
 **Ticari marka**  
 Derleme bildirimi için bir ticari marka belirtir. Karşılık gelen <xref:System.Reflection.AssemblyTrademarkAttribute>.  
  
 **Derleme sürümü**  
 Derlemenin sürümünü belirtir. Karşılık gelen <xref:System.Reflection.AssemblyVersionAttribute>.  
  
 **Dosya sürümü**  
 Belirli bir sürümü için Win32 dosya sürümü kaynak kullanmak için derleyiciye sürüm numarasını belirtir. Karşılık gelen <xref:System.Reflection.AssemblyFileVersionAttribute>.  
  
 **GUID**  
 Derleme tanımlayan benzersiz bir GUID. Bir proje oluşturduğunuzda, Visual Studio derleme için bir GUID oluşturur. Karşılık gelen <xref:System.Guid>.  
  
 **Dilden**  
 Hangi derleme destekler kültür belirtir. Karşılık gelen <xref:System.Resources.NeutralResourcesLanguageAttribute>. Varsayılan değer **(hiçbiri)**.  
  
 **Derlemeyi COM görünür yap**  
 Derlemedeki türleri COM'a olup olmadığını belirtir Karşılık gelen <xref:System.Runtime.InteropServices.ComVisibleAttribute>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama sayfası, Proje Tasarımcısı (Visual Basic)](../../ide/reference/application-page-project-designer-visual-basic.md)   
 [Öznitelikler](http://msdn.microsoft.com/Library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)