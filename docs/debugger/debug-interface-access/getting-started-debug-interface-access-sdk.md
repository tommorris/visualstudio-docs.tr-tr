---
title: "(Hata ayıklama arabirimi Erişim SDK'sı) Başlarken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .dbg files
- DBG files
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 938aaf760a2a6305580331945875391e6ad819af
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="getting-started-debug-interface-access-sdk"></a>Başlarken (Arabirim Erişimi SDK'sında Hata Ayıklama)
Hata ayıklama arabirimi erişim (DIA) SDK yönerge belgeleri ve nasıl DIA API kullanılacağını anlatan bir örnek sağlar. Arabirimleri ve yöntemleri DIA SDK'ın .pdb ve .dbg dosyaları açmak ve içeriklerini sembolleri, değerleri, öznitelikler, adresleri ve diğer hata ayıklama bilgileri için arama özel uygulamalar geliştirmek için kullanın. Bu SDK başvuru tabloları için C++ uygulamalarında bulunan simgeleri ile ilişkili özellikleri de sağlar.  
  
 En iyi DIA SDK'yı kullanmak için aşağıdaki bilgi sahibi olmanız:  
  
-   C++ programlama dili  
  
-   COM programlama  
  
-   Örnek derleme için visual Studio tümleşik geliştirme ortamı (IDE)  
  
 DIA SDK ile Visual Studio normal şekilde yüklendiğinden ve varsayılan konumuna *[sürücü]*\Program Visual Studio 9.0\DIA SDK. Eklenecek kullanmak için yapmanız gereken tek şey şekilde yüklemesinin bir parçası olarak DIA SDK uygulayan msdia90.dll otomatik olarak kaydedilir `dia2.h` program ve bağlantı `diaguids.lib`.  
  
 Başlık: include\dia2.h  
  
 Kitaplığı: lib\diaguids.lib  
  
 DLL: bin\msdia80.dll  
  
 IDL: idl\dia2.idl  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Genel bakış](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)  
 DIA. temel mimarisini incelemeleri  
  
 [Sorgulama. Pdb dosyası](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 .Pdb dosyasını sorgulama DIA API kullanmak adım adım yönergeler verilmektedir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama arabirimi Erişim SDK'sı](../../debugger/debug-interface-access/debug-interface-access-sdk.md)