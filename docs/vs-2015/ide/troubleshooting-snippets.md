---
title: Kod parçacıklarının sorunlarını giderme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IntelliSense Code Snippets, troubleshooting
- troubleshooting IntelliSense Code Snippets
- troubleshooting Visual Basic, IntelliSense Code Snippets
ms.assetid: 7b6dd40e-2f78-4b50-8e68-41fac1bcb81e
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a6cc8cde833d9580e3fae03df2df11e87eed8cf2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687461"
---
# <a name="troubleshooting-snippets"></a>Sorun Giderme Parçacıkları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [sorun giderme parçacıkları](https://docs.microsoft.com/visualstudio/ide/troubleshooting-snippets).  
  
IntelliSense kod parçacıkları ile ilgili sorunlar genellikle iki sorunları neden: hatalı kod parçacığı dosyasının içeriğini ya da bozuk kod parçacığı dosyası.  
  
## <a name="common-problems"></a>Yaygın sorunlar  
  
### <a name="the-snippet-cannot-be-dragged-from-file-explorer-to-a-visual-studio-source-file"></a>Kod parçacığı bir Visual Studio kaynak dosyası için dosya Gezgini'nden sürüklenemez  
  
-   XML kod parçacığı dosyası bozulmuş olabilir. **XML Düzenleyicisi** içinde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] sorunları XML yapısı içinde bulabilirsiniz.  
  
-   Kod parçacığı dosyasını kod parçacığı şemaya uygun olmayabilir. **XML Düzenleyicisi** içinde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] sorunları XML yapısı içinde bulabilirsiniz.  
  
### <a name="the-code-has-compiler-errors-that-are-not-highlighted"></a>Kodu değil vurgulanan derleyici hataları var  
  
-   Bir proje başvurusu eksik olabilir. Kod parçacığı hakkında belgeleri inceleyin. Referans bilgisayarda bulunmazsa yüklemeniz gerekir. Bir kod parçacığı eklemeden, gerekli tüm başvuruları projeye eklemeniz gerekir. Kod parçacığı başvuru bilgileri eksikse, hata olarak için kod parçacığı Oluşturucu bildirilebilir.  
  
-   Bir değişken tanımlanmamış olabilir. Tanımlanmamış bir kod parçacığı değişkenlerinde vurgulanmış olmalıdır. Aksi durumda, kod parçacığı oluşturan hata olarak bildirilebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod Parçacıkları](../ide/code-snippets.md)



