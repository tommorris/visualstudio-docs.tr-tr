---
title: "Nasıl yapılır: pencereler görünümünde pencere arama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- windows, searching in Windows view
ms.assetid: 30306970-b861-4315-acf8-f86a43d4e73b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: dfec3f78e9f95a55d453c45c5a264125152cbf1b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-search-for-a-window-in-windows-view"></a>Nasıl Yapılır: Pencereler Görünümünde Pencere Arama
Arama ölçütü olarak tutamacını, resim yazısı, sınıf veya kendi başlık ve sınıf birleşimi kullanarak Windows görünümünde belirli bir pencere için arama yapabilirsiniz. Ayrıca, arama ilk yönünü belirtebilirsiniz. İletişim kutusunda alanları penceresi ağacında seçilen pencere özniteliklerini gösterir.  
  
 (Masaüstü alt öğeleri olan tüm windows), ikinci düzey genişletilmiş ağaç ile başlangıç sınıfı adı ve başlık Masaüstü düzeyi windows belirleyebilir. Bir masaüstü düzeyi penceresi seçtikten sonra belirli alt pencere bulmak için bu düzey genişletebilirsiniz.  
  
### <a name="to-search-for-a-window-in-windows-view"></a>Pencereler görünümünde pencere aramak için  
  
1.  Bu nedenle pencereleri o Spy ++, [Windows görünümü](../debugger/windows-view.md) penceresi ve hedef penceresi görünür.  
  
2.  Gelen **arama** menüsünde seçin **Bul penceresi**.  
  
     [Pencere arama iletişim kutusu](../debugger/window-search-dialog-box.md) açar.  
  
    > [!TIP]
    >  Ekran görünmesine için seçin **Gizle Spy** seçeneği. Bu seçenek ana Spy ++ penceresi gizlendiğinden ve yalnızca bırakır **pencere arama** iletişim kutusu diğer uygulamalarınızı en üstünde görünür. Spy ++ ana penceresi tıkladığınızda geri **Tamam** veya **iptal**, veya kaldırdığınızda **Gizle Spy ++** seçeneği.  
  
3.  Sürükleme **Bulucu Aracı** hedef penceresi üzerinde. Aracı sürüklediğinizde **pencere arama** iletişim kutusu, seçili penceresinde ayrıntıları görüntüler.  
  
     - veya -  
  
     İstediğiniz pencere tanıtıcısı (örneğin, hata ayıklayıcı'dan) biliyorsanız, bunu yazabilirsiniz **işlemek** kutusu.  
  
     - veya -  
  
     Başlık ve/veya istediğiniz pencere sınıfı biliyorsanız, bunları yazabilirsiniz **resim yazısı** ve **sınıfı** metin kutuları ve clear **işlemek** metin kutusu.  
  
4.  Seçin **yukarı** veya **aşağı** arama ilk yönlerinin.  
  
5.  **Tamam**'ı tıklatın.  
  
     Eşleşen bir pencere bulunursa, onu vurgulanan [Windows görünümü](../debugger/windows-view.md) penceresi.