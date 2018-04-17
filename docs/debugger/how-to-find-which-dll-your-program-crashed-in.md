---
title: "Nasıl yapılır: hangi DLL'de kilitlendiğini programınızı Bul | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.dll
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5aca05ea9ab8010ba91592b766de796636f3eb96
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>Nasıl Yapılır: Programınızın Hangi DLL'de Kilitlendiğini Bulma
  
 Bir sistem DLL'inin veya başkasının kod yapılan bir çağrı sırasında uygulama çökerse, bulma kilitlenme meydana geldiğinde hangi DLL etkin gerekir. Kendi programı dışında bir kilitlenme DLL'de karşılaşırsanız, konumu kullanarak tanımlayabilirsiniz **modülleri** penceresi.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>Modüller penceresini kullanarak bir kilitlenme burada bulmak için oluştu  
  
1.  Kilitlenme oluştuğu adresi unutmayın.

    Adres hata iletisinde görüntülenmiyorsa, DLL tanımlamak için alternatif yöntemler kullanmanız gerekebilir. Bir sistem DLL'i şüpheleniyorsanız, şunları yapabilirsiniz [yük simgeleri](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) Microsoft simgesi hata ayıklama sırasında sunucularından. Aksi takdirde, gerekebilir [bir döküm dosyası oluşturma](../debugger/using-dump-files.md) yığın yerine bilgi olduğu. Çeşitli [Araçları](https://blogs.msdn.microsoft.com/andrehal/2009/12/31/what-is-a-dump-and-how-do-i-create-one/) döküm dosyaları oluşturmak kullanılabilir.
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **Windows**, tıklatıp **modülleri**.  
  
3.  İçinde **modülleri** penceresinde Bul **adresi** sütun. Scrollbar görmek için kullanmanız gerekebilir.  
  
4.  Tıklatın **adresi** DLL'leri adresine göre sıralamak için sütunun üstündeki düğmesi.  
  
5.  Bağlantı adres aralığı kilitlenme konumunu içeren DLL bulmak için sıralanmış tarayın.  
  
6.  Bakmak **adı** ve **yolu** DLL adını ve yolunu görmek için sütun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL projelerinde hata ayıklama](../debugger/debugging-dll-projects.md)   
 [Nasıl yapılır: modüller penceresini kullanma](../debugger/how-to-use-the-modules-window.md)