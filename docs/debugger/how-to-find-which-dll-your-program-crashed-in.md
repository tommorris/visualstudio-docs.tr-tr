---
title: "Nasıl yapılır: hangi DLL'de kilitlendiğini programınızı Bul | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.dll
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6232f86e9e9f5d59e9e109d08b75120cc90902c2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>Nasıl Yapılır: Programınızın Hangi DLL'de Kilitlendiğini Bulma
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için Araçlar menüsünden içeri ve dışarı aktarma ayarları seçin. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
 Bir sistem DLL'inin veya başkasının kod yapılan bir çağrı sırasında uygulama çökerse, bulma kilitlenme meydana geldiğinde hangi DLL etkin gerekir. Kendi programı dışında bir kilitlenme DLL'de karşılaşırsanız, konumu kullanarak tanımlayabilirsiniz **modülleri** penceresi.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>Modüller penceresini kullanarak bir kilitlenme burada bulmak için oluştu  
  
1.  Kilitlenme oluştuğu adresi unutmayın.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Windows**, tıklatıp **modülleri**.  
  
3.  İçinde **modülleri** penceresinde Bul **adresi** sütun. Scrollbar görmek için kullanmanız gerekebilir.  
  
4.  Tıklatın **adresi** DLL'leri adresine göre sıralamak için sütunun üstündeki düğmesi.  
  
5.  Bağlantı adres aralığı kilitlenme konumunu içeren DLL bulmak için sıralanmış tarayın.  
  
6.  Bakmak **adı** ve **yolu** DLL adını ve yolunu görmek için sütun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL projelerinde hata ayıklama](../debugger/debugging-dll-projects.md)   
 [Nasıl yapılır: modüller penceresini kullanma](../debugger/how-to-use-the-modules-window.md)