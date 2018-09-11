---
title: Hata ayıklayıcıda DLL'ler ve yürütülebilir dosyaları görüntüleme | Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.modules
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, Modules window
- Modules window
- executable files, displaying while debugging
- debugging [Visual Studio], displaying modules
- DLLs, displaying while debugging
- modules, displaying
ms.assetid: d840fdca-b035-4452-b652-72580c831896
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f582c435239c83503b179d6bb5e142936a41cb4b
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279017"
---
# <a name="view-dlls-and-executables-using-the-modules-window-in-the-visual-studio-debugger"></a>DLL'ler ve yürütülebilir dosyalar Visual Studio hata ayıklayıcısı modüller penceresini kullanarak görüntüleyin
 
**Modülleri** penceresi listeler DLL'ler ve yürütülebilir (EXE), programınız tarafından kullanılan ve her biri için ilgili bilgileri gösterir. 

> [!NOTE]
>  Bu özellik, SQL veya komut dosyası hata ayıklama için kullanılamaz. 
  
### <a name="to-display-the-modules-window"></a>Modüller penceresini görüntülemek için  
  
-   Hata ayıklarken, seçin **hata ayıklama > Windows** ve ardından **modülleri**.  
  
     Varsayılan olarak, **modülleri** penceresi modülleri yükleme sırası tarafından sıralar. Ancak, herhangi bir sütuna göre sıralamak seçebilirsiniz.  
  
### <a name="to-sort-by-any-column"></a>Herhangi bir sütuna göre sıralamak için  
  
-   Sütun üst kısmındaki düğmeye tıklayın.  
  
     Sembolleri yüklemek veya bir sembol yolu belirtin **modülleri** kısayol menüsünü kullanarak pencere.  
  
## <a name="loading-symbols"></a>Semboller yükleniyor  
 İçinde **modülleri** penceresi, hata ayıklama simgeleri yüklü modüllerine sahip görebilirsiniz. Bu bilgiler görünür **sembol durumu** sütun. Durum diyorsa **atlandı loadingCannot bulun veya PDB dosyası açın**, veya **yükleme Ekle/Çıkar ayarı tarafından devre dışı bırakıldı**, hata ayıklayıcının sembolleri Microsoft ortak Sembol ' indirin yönlendirebilirsiniz sunucuları veya bilgisayarınızdaki bir sembol dizinden simgeleri yüklemek için. Daha fazla bilgi için [belirtin sembol (.pdb) ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
#### <a name="to-load-symbols-manually"></a>Simgeleri el ile yüklemek için  
  
1.  İçinde **modülleri** penceresinde, kendisi için olmayan semboller modülü sağ tıklatın.  
  
2.  İşaret **sembolleri şuradan Yükle** ve ardından **Microsoft sembol sunucuları** veya **sembol yolu**.  
  
#### <a name="to-change-symbol-load-settings"></a>Sembol yükleme ayarlarını değiştirmek için  
  
1.  İçinde **modülleri** penceresinde herhangi bir modülden sağ tıklayın.  
  
2.  Tıklayın **sembol ayarları**.  
  
     Artık açıklandığı gibi sembol yükleme ayarlarını değiştirebilirsiniz [sembol konumlarını belirtin ve yükleme davranışını](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Specify_symbol_locations_and_loading_behavior). Değişiklikler, hata ayıklama oturumunu yeniden başlatılana kadar etkili olmaz.  
  
#### <a name="to-change-symbol-load-behavior-for-a-specific-module"></a>Belirli bir modül için Sembol yükleme davranışını değiştirmek için  
  
1.  İçinde **modülleri** penceresinde modülü sağ tıklatın.  
  
2.  İşaret **otomatik sembol yükleme ayarlarını** ve ardından **elle her zaman yük** veya **varsayılan**. Değişiklikler, hata ayıklama oturumunu yeniden başlatılana kadar etkili olmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütmeyi kesme](/previous-versions/visualstudio/visual-studio-2010/7z9se2d8(v=vs.100))   
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)   
 [Simge (.pdb) ve Kaynak Dosyaları Belirtme](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)