---
title: "Nasıl yapılır: .NET Framework kaynağında hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugging, .NET Framework source
ms.assetid: fc12e472-ac6a-4e77-8e22-a769e13a03b8
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9da2cd7b8a99d750692a69be406c9c8f82c461d1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-net-framework-source"></a>Nasıl Yapılır: .NET Framework Kaynağında Hata Ayıklama
En son sürümünü [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yeni özellikler için sağladığı [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hata ayıklama. Hata ayıklama için [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] kaynak, hata ayıklama simgeleri kodu için erişimi olması gerekir. Ayrıca içine Adımlama etkinleştirmeniz gerekiyor [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] kaynak.  
  
 Etkinleştirebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] atlama ve içinde indirme simgesi **seçenekleri** iletişim kutusu. Sembol indirme etkinleştirdiğinizde, simgeler hemen indirin ya da daha sonra yükleme seçeneği yalnızca etkinleştirebilirsiniz seçebilirsiniz. Simgeler hemen yüklemeyin simgeleri uygulamanızın hatalarını ayıklama başlangıç sonraki saati indirilir. El ile yükleme yoluyla da yapabilirsiniz **modülleri** penceresi veya **çağrı yığını** penceresi.  
  
### <a name="to-enable-net-framework-source-debugging"></a>.NET Framework kaynak hata ayıklamayı etkinleştirmek için  
  
1.  Üzerinde **Araçları** menüsünde tıklatın **seçeneği**s.  
  
2.  İçinde **seçenekleri** iletişim kutusu, tıklatın **hata ayıklama** kategorisi.  
  
3.  İçinde **genel** kutusunda, ayarlamak **etkinleştirmek .NET Framework** kaynak atlama.  
  
    1.  Etkin sadece kendi kodumu olsaydı, bir uyarı iletişim kutusu, sadece kendi kodumu şimdi devre dışı olduğunu bildirir. **Tamam**'ı tıklatın.  
  
    2.  Ayarlanmış bir simge önbellek konumu yok, başka bir uyarı iletişim kutusunda varsayılan bir simge önbellek konumu şimdi ayarlandığını söyler. **Tamam**'ı tıklatın.  
  
4.  Altında **hata ayıklama** kategorisini tıklatın **simgeleri**.  
  
5.  Simgeler önbellek konumunu değiştirmek istiyorsanız:  
  
    1.  Açık **hata ayıklama** kutunun sol düğümünde.  
  
    2.  Altında **hata ayıklama** düğümünü tıklatın **simgeleri**.  
  
    3.  Konumda Düzenle **önbelleğe simge sunucuları sembolleri bu dizine** veya **Gözat** bir konum seçmek için.  
  
6.  Simgeler hemen karşıdan yüklemek istiyorsanız, **yük simgeleri konumları kullanarak**.  
  
     Bu düğme, Tasarım modunda kullanılamaz.  
  
     Simgeleri şimdi indirmek seçmezseniz simgeleri programınızı hata ayıklamayı Başlat sonraki zaman otomatik olarak yüklenir.  
  
7.  Tıklatın **Tamam** kapatmak için **seçenekleri** iletişim kutusu.  
  
### <a name="to-load-framework-symbols-using-the-modules-window"></a>Modüller penceresi kullanarak Framework sembol yüklemek için  
  
1.  İçinde **modülleri** penceresinde, kendisi için simgeler yüklenmedi modülü bir sağ tıklatın. Simgeler yüklerse veya bakarak değil tarafından söyleyebilir **simgeleri durumu** sütun.  
  
2.  İşaret **simgeleri gelen yük** tıklatıp **Microsoft simge sunucuları** simgeleri Microsoft Genel semboller sunucusundan karşıdan yüklemek için veya **simge yolu** bir dizinden yüklemek için daha önce simgeleri depoladığınız.  
  
### <a name="to-load-framework-symbols-using-the-call-stack-window"></a>Çağrı yığını penceresini kullanarak Framework sembol yüklemek için  
  
1.  İçinde **çağrı yığını** penceresinde, kendisi için simgeler yüklenmedi çerçeve bir sağ tıklatın. Çerçeve çıkışı soluk.  
  
2.  İşaret **yük simgeleri gelen** tıklatıp **Microsoft simge sunucuları** veya **simge yolu**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [Simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)