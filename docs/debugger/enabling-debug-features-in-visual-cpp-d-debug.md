---
title: Hata ayıklama Visual C++'ta özelliklerini etkinleştirme (-D_DEBUG) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /D_DEBUG compiler option [C++]
- debugging [C++], enabling debug features
- debugging [MFC], enabling debug features
- assertions, enabling debug features
- D_DEBUG compiler option
- MFC libraries, debug version
- debug builds, MFC
- _DEBUG macro
ms.assetid: 276e2254-7274-435e-ba4d-67fcef4f33bc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 5298879d93bf4e86df7610d5891e73bdbb67c4a1
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="enabling-debug-features-in-visual-c-ddebug"></a>Visual C++'de Hata Ayıklama Özelliklerini Etkinleştirme (/D_DEBUG)
İçinde [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], simgenin programınızla derlediğinizde onaylar etkinleştirilen gibi hata ayıklama özellikleri **_DEBUG** tanımlanmış. Tanımlayabileceğiniz **_DEBUG** iki yoldan biriyle:  
  
-   Belirtin **# _DEBUG define** kaynak kodunuzdaki veya  
  
-   Belirtin **/D_DEBUG** derleyici seçeneği. (Sihirbazları, Visual Studio, projenizin oluşturursanız **/D_DEBUG** hata ayıklama yapılandırmasını da otomatik olarak tanımlanır.)  
  
 Zaman **_DEBUG** olan tanımlanan derleyici tarafından çevrelenen kodun bölümlerini derler **#ifdef _DEBUG** ve `#endif`.  
  
 Bir MFC programı hata ayıklama yapılandırmasını MFC kitaplığını hata ayıklama sürümü ile bağlamanız gerekir. MFC başlık dosyaları doğru olan bağlamak için MFC kitaplık tanımladığınız, gibi simgeleri temel sürümünü **_DEBUG** ve **_UNICODE**. Ayrıntılar için bkz [MFC kitaplık sürümleri](/cpp/mfc/mfc-library-versions).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)   
 [C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)