---
title: "Nasıl yapılır: hangi DLL'de kilitlendiğini programınızın bulma | Microsoft Docs"
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.dll
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8dc06d433739b4c0706374a691474207a45c5766
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683653"
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>Nasıl Yapılır: Programınızın Hangi DLL'de Kilitlendiğini Bulma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: Bul, DLL bilgisayarınızı Program kilitlendi,](https://docs.microsoft.com/visualstudio/debugger/how-to-find-which-dll-your-program-crashed-in).  
  
[NOT]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için Araçlar menüsünden içeri ve dışarı aktarma ayarları seçin. Daha fazla bilgi için [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Uygulamanızı bir sistem DLL'i veya başka birisinin kodu çağrısı sırasında kilitleniyor bulmak kilitlenme oluştuğunda hangi DLL etkindi gerekirse. Kendi programımı dışında bir DLL içindeki bir kilitlenme karşılaşırsanız, konumu şunu kullanarak belirleyebilirsiniz **modülleri** penceresi.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>Modüller penceresini kullanarak bir kilitlenme burada bulmak için oluştu  
  
1.  Kilitlenme durumu oluştuğu adresini not edin.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Windows**, tıklatıp **modülleri**.  
  
3.  İçinde **modülleri** penceresinde Bul **adresi** sütun. Bunu görmek için kaydırma çubuğunu kullanmanız gerekebilir.  
  
4.  Tıklayın **adresi** DLL'leri adresine göre sıralamak için sütunun üstünde düğme.  
  
5.  Sıralanmış listenin kilitlenme konumu adresi aralığı içeren DLL bulmak için tarayın.  
  
6.  Bakmak **adı** ve **yolu** DLL adı ve yolu görmek için sütun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yerel DLL'lerde hata ayıklama](../debugger/how-to-debug-native-dlls.md)   
 [Nasıl yapılır: modüller penceresini kullanma](../debugger/how-to-use-the-modules-window.md)





