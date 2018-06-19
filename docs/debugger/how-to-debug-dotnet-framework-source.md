---
title: 'Nasıl yapılır: .NET Framework kaynağında hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 02/23/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- debugging, .NET Framework source
ms.assetid: fc12e472-ac6a-4e77-8e22-a769e13a03b8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 8377ed73479441272b2f1910767fa7e2a4ff0196
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31475645"
---
# <a name="how-to-debug-net-framework-source"></a>Nasıl Yapılır: .NET Framework Kaynağında Hata Ayıklama
.NET Framework kaynak hata ayıklamak için kod simgelerini hata ayıklama için erişimi olmalıdır. Ayrıca, .NET Framework kaynağına atlama etkinleştirmeniz gerekir.  
  
 .NET Framework etkinleştirebilirsiniz atlama ve içinde indirme simgesi **seçenekleri** iletişim kutusu. Sembol indirme etkinleştirdiğinizde, simgeler hemen indirin ya da daha sonra yükleme seçeneği yalnızca etkinleştirebilirsiniz seçebilirsiniz. Simgeler hemen yüklemeyin simgeleri uygulamanızın hatalarını ayıklama başlangıç sonraki saati indirilir. El ile yükleme yoluyla da yapabilirsiniz **modülleri** penceresi veya **çağrı yığını** penceresi.  
  
### <a name="to-enable-net-framework-source-debugging"></a>.NET Framework kaynak hata ayıklamayı etkinleştirmek için  
  
1.  Üzerinde **Araçları** menüsünde tıklatın **seçeneği**s.  
  
2.  İçinde **seçenekleri** iletişim kutusu, tıklatın **hata ayıklama** kategorisi.  
  
3.  İçinde **genel** kutusunda, ayarlamak **etkinleştirmek .NET Framework kaynağı atlama.**  
  
    1.  Etkin sadece kendi kodumu olsaydı, bir uyarı iletişim kutusu, sadece kendi kodumu şimdi devre dışı olduğunu bildirir. **Tamam**'ı tıklatın.  
  
    2.  Ayarlanmış bir simge önbellek konumu yok, başka bir uyarı iletişim kutusunda varsayılan bir simge önbellek konumu şimdi ayarlandığını söyler. **Tamam**'ı tıklatın.  
  
4.  Altında **hata ayıklama** kategorisini tıklatın **simgeleri**.  
  
5.  Simgeler önbellek konumunu değiştirmek isterseniz, konumu Düzenle **önbelleğe simgeleri bu dizinde** veya'ı tıklatın **Gözat** bir konum seçmek için.  
  
6.  Simgeler hemen karşıdan yüklemek istiyorsanız, **yük simgeleri konumları kullanarak**.  
  
     Bu düğme Tasarım modunda kullanılabilir değildir, ancak hata ayıklama sırasında kullanılabilir.  
  
     Simgeleri şimdi indirmek seçmezseniz simgeleri programınızı hata ayıklamayı Başlat sonraki zaman otomatik olarak yüklenir.  
  
7.  Tıklatın **Tamam** kapatmak için **seçenekleri** iletişim kutusu.  
  
### <a name="to-load-framework-symbols-using-the-modules-window"></a>Modüller penceresi kullanarak Framework sembol yüklemek için  
  
1.  İçinde **modülleri** penceresi (hata ayıklama sırasında seçin **hata ayıklama** > **Windows** > **modülleri**), simgeler yüklenmez modülü sağ tıklatın. Simgeler yüklerse veya bakarak değil tarafından söyleyebilir **simgeleri durumu** sütun.  
  
2.  İşaret **simge ayarlarını** tıklatıp **Microsoft simge sunucuları** simgeleri Microsoft Genel semboller sunucusundan karşıdan yüklemek için. Veya modülü sağ tıklatın ve seçin **yük simgeleri** daha önce depoladığınız simgeleri bir dizinden yüklenecek.  
  
### <a name="to-load-framework-symbols-using-the-call-stack-window"></a>Çağrı yığını penceresini kullanarak Framework sembol yüklemek için  
  
1.  İçinde **çağrı yığını** penceresinde, kendisi için simgeler yüklenmedi çerçeve bir sağ tıklatın. Çerçeve çıkışı soluk.  
  
2.  İşaret **simge ayarlarını** tıklatıp **Microsoft simge sunucuları**, veya modülü sağ tıklatın ve seçin **simge yolu**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [Simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)