---
title: "Hata ayıklayıcıda DLL'ler ve yürütülebilir dosyalar görüntülemek | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.modules
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
caps.latest.revision: "36"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 772c252265e15c3c928fbcc47c756ceafd9e1362
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="view-dlls-and-executables-using-the-modules-window-in-the-visual-studio-debugger"></a>DLL'ler ve yürütülebilir dosyalar Visual Studio hata ayıklayıcısı modülleri penceresinde kullanarak görüntüleme
 
**Modülleri** penceresi listeler DLL'ler ve yürütülebilir (EXE), program tarafından kullanılır ve her biri için ilgili bilgileri gösterir. 

> [!NOTE]
>  Bu özellik SQL ya da komut dosyasında hata ayıklama için kullanılabilir değil. 
  
### <a name="to-display-the-modules-window"></a>Modüller penceresini görüntülemek için  
  
-   Hata ayıklarken, seçin **hata ayıklama > Windows** ve ardından **modülleri**.  
  
     Varsayılan olarak, **modülleri** penceresi modülleri yük sıraya göre sıralar. Ancak, herhangi bir sütuna göre sıralamak seçebilirsiniz.  
  
### <a name="to-sort-by-any-column"></a>Herhangi bir sütuna göre sıralamak için  
  
-   Sütunun üstünde düğmesini tıklatın.  
  
     Yük simgeleri ya da bir simge yolu belirtin **modülleri** kısayol menüsünü kullanarak penceresi.  
  
## <a name="loading-symbols"></a>Simgeler yükleniyor  
 İçinde **modülleri** penceresi, hata ayıklama simgeleri yüklenen modüllerine olmadığını görebilirsiniz. Bu bilgiler **simgesi durum** sütun. Durum diyorsa **Atlanan loadingCannot bulmak veya PDB dosyası açın**, veya **dahil etme/hariç tutma ayarı tarafından devre dışı yükleme**, Microsoft ortak simgesini simgeleri indirmek için hata ayıklayıcı yönlendirebilirsiniz sunucuları veya bilgisayarınızdaki bir simge dizinden simgeleri yüklenemedi. Daha fazla bilgi için bkz: [belirtin simge (.pdb) ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
#### <a name="to-load-symbols-manually"></a>Simgeler el ile yüklemek için  
  
1.  İçinde **modülleri** penceresinde, kendisi için simgeler Modül yüklenmedi bir sağ tıklatın.  
  
2.  İşaret **yük simgeleri gelen** ve ardından **Microsoft simge sunucuları** veya **simge yolu**.  
  
#### <a name="to-change-symbol-load-settings"></a>Simge yükleme ayarlarını değiştirmek için  
  
1.  İçinde **modülleri** penceresinde herhangi bir modül sağ tıklayın.  
  
2.  Tıklatın **simge ayarları**.  
  
     Artık açıklandığı gibi simge yükleme ayarlarını değiştirebilirsiniz [simge konumları belirtin ve yükleme davranışını](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md#BKMK_Specify_symbol_locations_and_loading_behavior). Değişiklikleri hata ayıklama oturumu yeniden başlatılana kadar etkili olmaz.  
  
#### <a name="to-change-symbol-load-behavior-for-a-specific-module"></a>Belirli bir modülü için simge yükleme davranışını değiştirmek için  
  
1.  İçinde **modülleri** penceresinde modülü sağ tıklatın.  
  
2.  İşaret **otomatik simge yükleme ayarlarını** ve ardından **her zaman yük elle** veya **varsayılan**. Değişiklikleri hata ayıklama oturumu yeniden başlatılana kadar etkili olmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütmeyi kesme](http://msdn.microsoft.com/en-us/30fc4643-f337-4651-b1ff-f2de2c098d40)   
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)   
 [Simge (.pdb) belirtin ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)