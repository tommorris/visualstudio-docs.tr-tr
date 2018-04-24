---
title: 'Nasıl yapılır: yerel çerçeveler çağrı yığını penceresinde olmadığında yönetilen kodların dışına Adımlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Call Stack window, missing native frames
- code, managed code
- native frames
- stepping, out of managed code
- managed code, stepping out of
ms.assetid: 97cdd2a8-02a9-4a06-a5b1-c92b1e431979
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e21d45cd65fc6bc6a66f2f7c698952f0cdd788b9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window"></a>Nasıl Yapılır: Yerel Çerçeveler Çağrı Yığını Penceresinde Olmadığında Yönetilen Kodların Dışına Adımlama
Kodunuzu görünmez yerel çerçeveler olup olmadığını **çağrı yığını** penceresinde, yönetilen kodun dışına Adımlama beklenmeyen sonuçlar verebilir. Geçici bir çözüm olarak, bir kesme noktası yerine kullanabileceğiniz **Step Out**.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-display"></a>Yerel çerçeveler çağrı yığını görüntüden eksik olmadığında yönetilen kodların dışına adım  
  
1.  Yerel kodda, yönetilen kod çağrısından sonra bir konum kesme noktası ayarlayın.  
  
2.  Üzerinde **hata ayıklama** menüsünde seçin **devam**.  
  
     Yönetilen çağrı tamamlandığında, yürütme yerel kodda kesme noktasındaki durdurur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: çağrı yığını penceresini kullanma](../debugger/how-to-use-the-call-stack-window.md)