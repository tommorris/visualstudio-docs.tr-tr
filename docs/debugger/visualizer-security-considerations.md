---
title: "Görselleştirici güvenlik konuları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, security
- security [Visual Studio], visualizers
ms.assetid: cdd86bd5-b729-409b-a7c6-374efa091eb1
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d5075e55f1db35f7a588094a7c398c9d4c25483c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="visualizer-security-considerations"></a>Görselleştirici Güvenlik Konuları
Görselleştirici yazma olası güvenlik tehditlerini içerir. Bilinen hiçbir yararlanma şu anda bu olası tehditleri var, ancak geliştiriciler bunları farkında olmalı ve gelecekteki açıklarına karşı koruma sağlamak için burada açıklandığı gibi uygun güvenlik önlemleri alın.  
  
 Hata ayıklayıcı görselleştiriciler kısmi güven uygulama tarafından izin verilenden daha yüksek ayrıcalıklar gerektirir. Kısmi güven ile kodda durduğunda görselleştiriciler yüklemez. Görselleştirici kullanarak hata ayıklamak için tam güven ile kod çalıştırması gerekir.  
  
## <a name="possible-malicious-debuggee-component"></a>Olası zararlı ayıklayıcı bileşeni  
 Görselleştiriciler en az iki sınıfları oluşur: hata ayıklayıcı yan ve diğeri ayıklayıcı tarafında birinde. Görselleştiriciler genellikle özel dizinlerde put ayrı derlemeler dağıtılır, ancak bunlar da ayıklayıcı dışında yüklenebilir. Bu oluştuğunda, hata ayıklayıcı ayıklayıcı dışında kod alır ve hata ayıklayıcısı tam güven içinde çalışır.  
  
 Ayıklayıcı tam olarak güvenilir değil tam güven ile ayıklayıcı tarafı kodu çalışan sorunlu haline gelir. Görselleştirici ayıklayıcıya ayıklayıcı bir kısmi güven derlemeyi yüklemeye çalışırsa, Visual Studio Görselleştirici sona erdirir.  
  
 Ancak, ikincil bir güvenlik açığı hala bulunmaktadır. Başka bir kaynaktan (ayıklayıcı değil) yüklendi bir hata ayıklayıcı kenar ayıklayıcı tarafı ilişkilendirebilirsiniz. Ayıklayıcı yan kendi adına eylemleri gerçekleştirmek için hata ayıklayıcı yan güvenilen anlayabilirsiniz. Örneğin, "Bu dosyayı Sil" mekanizması güvenilir hata ayıklayıcı tarafı sınıfı gösterir, kullanıcının kendi Görselleştirici istediğinde kısmi güven ayıklayıcı Bu mekanizma çağıramadı.  
  
 Bu güvenlik açığından azaltmak için Görselleştirici tarafından kullanıma sunulan arabirimlerinin oluşturduğunu unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görselleştirici mimarisi](../debugger/visualizer-architecture.md)   
 [Nasıl yapılır: Görselleştirici yazma](../debugger/how-to-write-a-visualizer.md)   
 [Özel Görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md)   
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)